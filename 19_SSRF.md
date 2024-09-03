# Server Site Request Forgery

## Make crAPI send an HTTP call to “www.google.com" and return the HTTP response

1. Login to the application from http://localhost:8888/login
2. After adding a vehicle, we will have an option to send service request to mechanic by using the Contact Mechanic option (you need to send your VIN inside the body).
3. Observe the POST request sent after the Send Service Request. You will find a property `mechanic_api`
4. Send the request again but change the URL in `mechanic_api` to `https://www.google.com`

## Hints

```
POST http://localhost:8888/workshop/api/merchant/contact_mechanic

{"mechanic_code":"TRAC_JHN","problem_details":"test","vin":"4KQEV62ABHF098155","mechanic_api":"https://www.google.com","repeat_request_if_failed":false,"number_of_repeats":1}
```
