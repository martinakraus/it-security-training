# CSP Trusted Types

## Preperation

1. Open the application `csp-against-xss`
2. Run `npm i` (if you haven't already)
3. Page/ Template to this task: `trusted-names.ejs`
4. Start the Server with `npm start`

## Task A: Create you own Custom Policy

`This will just work inside the Google Chrome Browser or Edge since Firefox isn't supporting Trusted Types yet.`

[Source](https://caniuse.com/?search=trusted%20types)

- The CSP is configured for Trusted Types, by visiting the path `/trusted-types` you should see some errors in the Browser Consoles
- We need to create a Trusted Type:

## Task: Use Purifier for creating a Trusted Type

- Use the already included DomPurify for creation

### Hint

```typescript
    if (window.trustedTypes && trustedTypes.createPolicy) { // Feature testing
    const escaped = DOMPurify.sanitize('<img src=x onerror=alert(1)>' , {RETURN_TRUSTED_TYPE: true})

    document.getElementById('martina').innerHTML = escaped;
}
```

### Optional Task: Use your custom Policy for escaping the dangerous string
- Use your custom Policy for escaping the dangerous string `<img src=x onerror=alert(1)>` before assining to innerHTML:

```typescript
trustedTypes.createPolicy('myEscapePolicy', {
    createHTML: text => {
        // write own policy
    }
});
```

### Hint

```javascript
if (window.trustedTypes && trustedTypes.createPolicy) { // Feature testing
    const escapeHTMLPolicy = trustedTypes.createPolicy('myEscapePolicy', {
        createHTML: text => text.replace(/\</g, '&lt;')
    });

    const escaped = escapeHTMLPolicy.createHTML('<img src=x onerror=alert(1)>')

    document.getElementById('martina').innerHTML = escaped;
}
```


[Official Documentation](https://content-security-policy.com/nonce/)
