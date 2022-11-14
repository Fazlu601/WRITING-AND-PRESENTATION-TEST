# **Writting & Presentation Test Week-8**

## **React Context**

### **Apa itu React Context ?**
Context adalah salah satu State Management yg di khususkan buat React Js serta mengelola state secara global, dapat di gunakan bersama useState Hook untuk berbagai state.

### **Cara Membuat Context**

Kita dapat membuat content dengan menggunakan perintah React.createContext(). Context akan sangat berguna jika kita ingin menyimpan data yang nantinya akan diakses oleh berbagai komponen tanpa harus menggunakan props secara turun menurun.

 ```
import React from "react";

const UserContext = React.createContext();

export default UserContext;
 ```

### **Cara Menggunakan Context**
Kita dapat menggunakan Context dengan melakukan pemanggilan Context.Provider dan Context.Consumer. 

- **Context.Provider :** Untuk memprovide data yang dapat diakses oleh komponen-komponen yang berada di dalamnya.

 - **Context.Consumer :** Sebagai accessibility data yang disediakan oleh Context.Provider.

#### **Contoh Penggunaan Context.Provider :**
```
import React from "react";
import UserContext from "./UserContext";

const User = () => {
  return (
    <UserContext.Provider value={{ name: "John Doe" }}>
      <div>
        <h1>User</h1>
        <Profile />
      </div>
    </UserContext.Provider>
  );
};

const Profile = () => {
  return (
    <div>
      <h2>Profile</h2>
      <Name />
    </div>
  );
};

const Name = () => {
  return (
    <UserContext.Consumer>{({ name }) => <p>{name}</p>}</UserContext.Consumer>
  );
};

export default User;
```
#### **Contoh Penggunaan Context.Consumer dengan Hooks :**

```
    import React, { useContext } from "react";
import UserContext from "./UserContext";

const User = () => {
  return (
    <UserContext.Provider value={{ name: "John Doe" }}>
      <div>
        <h1>User</h1>
        <Profile />
      </div>
    </UserContext.Provider>
  );
};

const Profile = () => {
  return (
    <div>
      <h2>Profile</h2>
      <Name />
    </div>
  );
};

const Name = () => {
  const { name } = useContext(UserContext);

  return <p>{name}</p>;
};

export default User;
```

## **React Testing**

React Testing Library adalah seperangkat helpers yang memungkinkan Anda mengetes komponen pada React tanpa bergantung pada detail implementasinya.
Testing dapat dilakukan dengan menggunakan JEST

Pendekatan ini membuat refactoring menjadi mudah dan juga mendorong Anda untuk menerapkan best practices untuk aksesbilitas. Mungkin tidak memberikan cara untuk me-render secara “dangkal” pada sebuah komponen tanpa anak, test runner seperti Jest yang memungkinkan Anda melakukan mocking.

#### **Command Install React Testing Library**

```
npm install --save-dev @testing-library/react
```

#### **Command Install Jest**

```
npm install --save-dev jest
```

#### **Command Install Jest DOM**

```
npm install --save-dev @testing-library/jest-dom
```
 
 #### **Setup Testing pada file jest.config.js**
 ```
module.exports = {
  setupFilesAfterEnv: ["@testing-library/jest-dom/extend-expect"],
};
 ```

#### **Step dari sebuah Testing**

- Assert
- Arrange
- Act

#### **Testing dibagi menjadi 2:**

- Manual Testing
- Automated Testing

#### **Alasan mengapa Menggunakan Testing:**

1. Aplikasi bebas dari error dan bug

2. Aplikasi berjalan sesuai dengan ekspektasi

3. Meningkatkan kualitas dari sebuah software dan kepuasan pengguna

#### **Alasan menggunakan Automated Testing**

1. Lebih reliable karena Manual Testing tetap berpotensi adanya kesalahan dan kekeliruan

2. Lebih cepat dan efisien

3. Mudah untuk dimaintain (Review, Edit, dan Add Collection of Tests)

#### **Automated Testing terdiri dari :**

1. Unit Test

2. End to End Test

3. Integration Test