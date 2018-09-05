---
title: Multi-language
weight: 3
---

```raw
POST https://api-sandbox.dwolla.com/customers
Content-Type: application/vnd.dwolla.v1.hal+json
Accept: application/vnd.dwolla.v1.hal+json
Authorization: Bearer 0Sn0W6kzNicvoWhDbQcVSKLRUpGjIdlPSEYyrHqrDDoRnQwE7Q

{
"firstName": "Joe",
"lastName": "Buyer",
"email": "jbuyer@mail.net",
"ipAddress": "99.99.99.99"
}

HTTP/1.1 201 Created
Location: https://api-sandbox.dwolla.com/customers/247b1bd8-f5a0-4b71-a898-f62f67b8ae1c
```

```ruby
request_body = {
  :firstName => 'Joe',
  :lastName => 'Buyer',
  :email => 'jbuyer@mail.net',
  :ipAddress => '99.99.99.99'
}

# Using DwollaV2 - https://github.com/Dwolla/dwolla-v2-ruby (Recommended)
new_customer = app_token.post "customers", request_body
new_customer.response_headers[:location] # => "https://api-sandbox.dwolla.com/customers/247b1bd8-f5a0-4b71-a898-f62f67b8ae1c"

```

```javascript
var requestBody = {
  firstName: 'Joe',
  lastName: 'Buyer',
  email: 'jbuyer@mail.net',
  ipAddress: '99.99.99.99'
};

appToken
  .post('customers', requestBody)
  .then(function(res) {
    res.headers.get('location'); // => 'https://api-sandbox.dwolla.com/customers/247b1bd8-f5a0-4b71-a898-f62f67b8ae1c'
  });
```

```python
request_body = {
  'firstName': 'Joe',
  'lastName': 'Buyer',
  'email': 'jbuyer@mail.net',
  'ipAddress': '99.99.99.99'
}

# Using dwollav2 - https://github.com/Dwolla/dwolla-v2-python (Recommended)
new_customer = app_token.post('customers', request_body)
new_customer.headers['location'] # => 'https://api-sandbox.dwolla.com/customers/247b1bd8-f5a0-4b71-a898-f62f67b8ae1c'

```

```php
<?php
$customersApi = new DwollaSwagger\CustomersApi($apiClient);

$new_customer = $customersApi->create([
  'firstName' => 'Joe',
  'lastName' => 'Buyer',
  'email' => 'jbuyer@mail.net',
  'ipAddress' => '99.99.99.99'
]);

print($new_customer); # => https://api-sandbox.dwolla.com/customers/247b1bd8-f5a0-4b71-a898-f62f67b8ae1c
?>
```

```java
CustomersApi cApi = new CustomersApi(a);

CreateCustomer newCustomerData = new CreateCustomer();

myNewCust.setFirstName("Joe");
myNewCust.setLastName("Buyer");
myNewCust.setEmail("jbuyer@mail.com");
myNewCust.setIpAddress("99.99.99.99");

try {
    Unit$ r = cApi.create(myNewCust);
    System.out.println(r.getLocationHeader()); // => https://api-sandbox.dwolla.com/customers/247B1BD8-F5A0-4B71-A898-F62F67B8AE1C
}
catch (Exception e) {
    System.out.println("Something's up!");
}
```