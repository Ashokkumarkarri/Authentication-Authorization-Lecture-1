# Authentication & Authorization

- Client Server Communication
  - Authentication & Authorization
- E-Commerce Application
  - Authentication Flow
- Route Parameters
  - history

---

# Authentication & Authorization | Cheat Sheet

## Concepts in Focus
- Client-Server Communication
- Authentication
- Authorization
- Authentication Flow
- Route Parameters
- History
- E-Commerce Application

---

## 1. Client-Server Communication

![Client-Server Communication](https://assets.ccbp.in/frontend/content/react-js/session-13-client-server-communication.png)

---

## 1.1 Authentication
Authentication is the process of verifying a user's identity.

## 1.2 Authorization
Authorization is the process of verifying whether the user is authenticated and permitted to perform some actions like accessing resources, etc.

Example:

- After successful authentication, employees are only allowed to access certain resources based on their roles.
  - Admin can Read, Create, Delete, and Update the Resources
  - User can only Read and Create the Resources

![Authentication vs Authorization](https://assets.ccbp.in/frontend/content/react-js/session-13-authentication-authorization-difference.png)

---

## 2. Authentication Flow

![Authentication Flow](https://assets.ccbp.in/frontend/content/react-js/session-13-authentication-flow.png)

---

## 3. Route Parameters

When a component is rendered by the Route, some additional props are passed.

They are:
- match
- history
- location

### 3.1 History

The history object has some methods to control the navigation in the browser, and it also maintains the history of the routes we navigated.

It has the following methods to control the navigation in the browser:

- push()
- replace()
- go()
- goBack()
- goForward(), etc.

The `history.push()` and `history.replace()` methods are used to navigate to other routes programmatically.

#### 3.1.1 history.push()

With the `history.push()` method, the user can go forward and backwards in the browser, and the URL will change.

**Syntax:**

```js
history.push("PATH");
```

#### 3.1.2 history.replace()

The `history.replace()` method replaces the current URL with new one. The user can't go backwards to the previous URL.

**Syntax:**

```js
history.replace("PATH");
```

---

## 4. E-Commerce Application

- Make an Authentication Request to Login API
- Handle Login API Response
  - On Login Success
  - On Login Failure
- Store the JWT Token

**Authenticated Credentials:**  
- Username: rahul  
- Password: rahul@2021


When the `history.push()` is triggered, the path will change. The switch inside `App.js` will trigger again, and the corresponding component will render.

If the Response status code is 2XX, then `response.ok` will be true else it is false.  
Whenever the route changes, the switch in the `App.js` will trigger again, and the corresponding component will render.

---
---
