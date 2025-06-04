## Authentication Flow (Login)

We have 3 steps in the authentication flow:

1. Make an authentication request to the Login API  
2. Handle the Login API response:  
   - On login **success**  
   - On login **failure**  
3. Store the JWT token

---

### ✅ In this commit (Make Auth req to login API):

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

-----------------------------------------------------------------------------