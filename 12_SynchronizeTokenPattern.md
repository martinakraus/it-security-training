# Synchronize Token Pattern

## Preperation

1. Open the application `stp-against-csrf `
2. Run `npm i` to install dependencies
3. To run the application: `npm start` 

## Task: Use the CSRF Token to prevent Cross Site Request Forgery Attacks

1. Inside the  method `app.get('/', csrfProtection, (req, res) => {..})`:
  - Extract the SessionId out of the cookie;
  - Generate a csrf-token with `req.csrfToken`
  - Store the token inside the global `tokenStore`- Object
  - Extend the `res.render`-Function by adding an Object `{csrfToken: token}` to it.

2. Inside the method `app.post('/login', (req, res)`
- Extract the SessionId out of the cookie;
- compare the `_csrf`-Token with the token stored for this sessionId from the tokenStore
- redirect to the `/error`-Page if it's not the token we have stored for this sessionId
## Hints


```typescript
app.get('/', csrfProtection, (req, res) => {
    const sessionId = req.cookies['connect.sid'];
    const token = req.csrfToken();
    tokenStore[sessionId] = token;
    res.render('index', { csrfToken: token });
});

app.post('/login', (req, res) => {
...
   const sessionId = req.cookies['connect.sid'];
    if (_csrf !== tokenStore[sessionId]) {
       return res.redirect('/error');
    }
...})
```

