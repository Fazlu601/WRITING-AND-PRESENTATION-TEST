# **Writting & Presentation Test Week-7**

## **Props - Types**

### **Apa itu Props Types ?**

Prop Types adalah merupakan sebuah library pihak ketiga yang dapat membantu kita untuk memeriksa data props yang kita kirim agar sesuai dengan ekspektasi yang kita inginkan, jika data tidak sesuai maka akan memeunculkan pesan error, sehingga hal tersebut akan memudahkan kita.

### **Cara Instal Props Types**

`npm install prop-types`

### **Contoh Penggunaan Props Types**

```
//Import modul props types
import PropTypes from 'prop-types';

//Pastikan component menerima props melalui parameter
const Header = (props) => {
    return (
        <>
            <h2>Name: {props.char}</h2>
            <h2>Age: {props.age}</h2>
        </>
    );
}

//Lakukan pengecekan data props dengan menggunakan object propTypes
Header.propTypes = {
    char: PropTypes.string,
    age: PropTypes.number,
}
```

## **React - Router**

### **Apa itu React Router ?**

React Router merupakan library paling populer di react yang dapat membantu kita untuk membuat navigasi di antara berbagai URL yang akan mengarahkan kita ke halaman tertentu dengan component yang berbeda.



### **Cara menggunakan react Router**

- Menginstall dependency melalui terminal pada project kita dengan menggunakan comand `npm install react-router-dom`.

- Melakukan import BrowserRouter sebagai provider untuk membungkus component-component apa saja yang akan menggunakan router.

- Mengimport Routes dan route sebagai grouping dan router terhadap component yang ingin kita render berdasarkan path URL tertentu.

- Mengimport Link sebagai pengganti tag anchor yang biasa kita gunakan pada HTML, untuk dapat melakukan navigasi terhadap path URL.


#### **Contoh penerapan react router**
```
import React from 'react';
import { BrowserRouter, Link, Route, Routes } from 'react-router-dom';
import './App.css';

import Manatee from '../Manatee/Manatee';
import Narwhal from '../Narwhal/Narwhal';
import Whale from '../Whale/Whale';

function App() {
  return (
    <div className="wrapper">
      <h1>Marine Mammals</h1>
      <BrowserRouter>
        <nav>
          <ul>
            <li><Link to="/manatee">Manatee</Link></li>
            <li><Link to="/narwhal">Narwhal</Link></li>
            <li><Link to="/whale">Whale</Link></li>
          </ul>
        </nav>
        <Routes>
          <Route path="/manatee">
            <Manatee />
          </Route>
          <Route path="/narwhal">
            <Narwhal />
          </Route>
          <Route path="/whale">
            <Whale />
          </Route>
        </Routes>
      </BrowserRouter>
    </div>
  );
}

export default App;
```

## **State Management React - Redux**

### **Apa itu Redux?**

Jika aplikasi react kita sudah terlalu besar dan mempunyai banyak component dan memiliki suatu state atau data yang harus kita kirimkan ke banyak component, maka hal tersebut akan menjadi masalah dan menyebabkan terjadinya proses props drilling atau bisa disebut sebagai proses inheritance props ke banyak component sekaligus, dan itu akan sangat merepotkan kita sebagai developer.

 Redux merupakan library pihak ketiga yang dapat kita gunakan untuk mengelola global state management, sehingga dengan bantuan redux kita dapat mengelola global state dan menyimpannya ke dalam store, sehingga dengan begitu kita dapat dengan mudah mengakses atau mengelola state yang sama di component manapun. Dengan begitu kita dapat menghindari terjadinya props drilling.

 ### **Cara menggunakan Redux di aplikasi React kita**

- Menginstall Dependency Redux dengan comand `npm install redux react-redux` melalui terminal.

 - Membuat directory redux di dalam src yang berisi sub directory yaitu store, reducer dan action.

 - Membuat function reducer dengan initialState default dan action di parameternya, lalu dalam file reducer berisi conditional switch yang akan mengeksekusi perintah berdasarkan action.type lalu lakukan export.

 - Mengimport CreateStore di dalam file store lalu menginisialisasikan createStore yang sudah berisi reducer ke dalam variabel lalu lakukan export.

 - Mengimport Provider dari react-redux melalui main component untuk dapat memberikan akses store ke child component yang ada di dalamnya.

- Setelah kita berhasil melakukan step by step yang ada diatas, artinya kita sudah berhasil menyiapkan global state, untuk dapat memanggil state yang ada di di dalam store kita bisa menggunakan `useSelector()`, dan jika kita ingin memanipulasi isi dari store kita bisa menggunakan `useDispatch()` dengan argument yang berisi object dan property type.

#### **Create Global State**

 ```
import { createStore } from "redux";
import rootReducer from "./rootReducer";

const store = createStore(rootReducer);

export default store;
 ```

#### **Add Store Provider**

```

import React from 'react'
import ReactDOM from 'react-dom/client'
import { BrowserRouter } from 'react-router-dom';
import { Provider } from 'react-redux';
import store from './redux/store';
import 'bootstrap/dist/css/bootstrap.min.css';
import App from './App'
import './index.css'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
  <BrowserRouter>
    <Provider store={store}>
      <App />
    </Provider>
  </BrowserRouter>
  </React.StrictMode>
)

 ```


### **State Management-Async Action With Redux Thunk and Middleware**

> Redux-Thunk adalah sebuah middleware yang memungkinkan kita memanggil pembuat aksi yang mengembalikan fungsi sebagai ganti objek aksi

> Redux-Thunk solusi ketika kita menggunakan fetch data dari sebuah External API atau yang memiliki side effect (proses ashynchronous).