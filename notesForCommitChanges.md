## Authentication Flow (Login)

We have 3 steps in the authentication flow:

1. Make an authentication request to the Login API  
2. Handle the Login API response:  
   - On login **success**  
   - On login **failure**  
3. Store the JWT token

---

### ✅ In this commit: 1 (Make Auth req to login API):

We wrote a function called `submitForm()` and added it to the `<form>` element using `onSubmit`.

In that function, we make a **POST** request to the Login API with the user's credentials.

```js
onSubmit={this.submitForm}
```

```js
submitForm = async event => {
  event.preventDefault() // prevents default form submission behavior (like page reload)
  const {username, password} = this.state
  const userDetails = {username, password} // we need to send these values to the API

  const url = 'https://apis.ccbp.in/login'
  const options = {
    method: 'POST',
    body: JSON.stringify(userDetails), // convert object to JSON string
  }

  const response = await fetch(url, options) // send request to API
  const data = await response.json() // parse the JSON response
  console.log(data)
}

```

###💡 What's next:
Once we make the request to the server, we’ll either get a success or failure response.
1. If we get success, we have to:
    - Navigate to the Home page (home route)
    - Store the JWT token

2. If we get failure, we’ll:
    - Show an error message to the user

We'll handle those cases in the next commit.

---

# ✅ In this commit: 2 (Handling API Success and Navigation in Authentication)

When we use `fetch()` to make an HTTP request, we get a response object.
This response object contains a key called `ok`.

* If `response.ok === true`, that means our API call was **successful**
* If it's `false`, then there was some **error**

We can log the response object using:

```js
console.log(response)
```

---

## 🕽 Checking for Success and Navigating to Home Route

We write logic like this:

* If the response is successful (`ok === true`), we call a function that will handle navigation to the Home route.

```js
if (response.ok === true) {
  // if the response is success, navigate to Home route
  this.onSubmitSuccess()
}
```

---

## 🕽 Navigating Using `history` Object

React Router provides a `history` object.
This object has methods to control browser navigation (like back, forward, and URL changes).

Some commonly used methods are:

* `history.push(path)`
* `history.replace(path)`
* `history.go(n)`
* `history.goBack()`
* `history.goForward()`

But here, we will only focus on `push` and `replace`:

### 🔹 `history.push('/')`

* Navigates to the new route
* User **can** go back and forward using browser buttons
* URL will update

### 🔹 `history.replace('/')`

* Replaces the current URL with the new one
* User **cannot** go back to the previous route using the browser back button

---

### ✅ Example: Navigating to Home on Success

```js
onSubmitSuccess = () => {
  const {history} = this.props
  history.push('/')
}
```

---
Note: we will continue this in the next lecture.
