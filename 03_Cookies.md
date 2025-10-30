# Cookie Attributes

Assign one or more suitable cookie attributes from the following list to the descriptions below:

- Secure
- HttpOnly
- SameSite= Strict | Lax | None
- Expire/Max-Age

1. E-commerce Website: User Authentication
A user logs in to an e-commerce website. The session is maintained using a cookie that stores the user's authentication token. The goal is to ensure that this session cookie cannot be easily stolen or hijacked by attackers through client-side scripts or over insecure connections. The website supports both HTTP and HTTPS, but all sensitive interactions are served over HTTPS.
2. Remember Me Feature
A news website offers a "Remember Me" option during login, which keeps users logged in even after they close the browser. This feature stores a persistent cookie that identifies the user for future sessions. The site is accessible over both HTTP and HTTPS, but it doesn't involve particularly sensitive user interactions beyond login.
3. Third-Party Analytics Tracking
A website uses a third-party analytics service to track user behavior for marketing purposes. The analytics script sets a tracking cookie to identify users across sessions. The cookie isn't essential for site functionality but is useful for analyzing user behavior. The website operates exclusively over HTTPS, and user privacy is a top priority.
