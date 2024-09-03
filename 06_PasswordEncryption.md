# Simple Password Encryption with Bcrypt

## Preperation

1. Open the application `password-encryption`
2. Run `npm i`
3. To start the Server run `npm start`

## Task 1: Implement Register Route

The register-Handler stores the password as plain text.
We need to fix that:

- Import the bcrypt Library in your server.js file
- use the `hash`-Function to hash the given password
- Define a number for saltRounds the algorithm takes generating the salt
- You can see the hashed passwords inside the file `database/db.json`

## Task 2: Implement Login Route

The Login-Handler compares the passwords as plain text.
We need to fix that:

- Import the bcrypt Library in your server.js file
- use the `compare`-Function to compare the hash passwords


## Hints

You can use the Postman Collection `Password-Encryption/Password-Encryption.postman_collection.json` for testing your endpoints


```javascript
import bcrypt from 'bcrypt';

...
// Task 1
const saltRounds = 10;
const hashedPassword = await bcrypt.hash(password, saltRounds);

// Task 2
const passwordMatch = await bcrypt.compare(password, user.password);
```
