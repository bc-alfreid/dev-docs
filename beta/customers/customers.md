## Introduction
The Customer Attributes API allows for data to be stored against a customer. For example, by creating an attribute of hat size, then storing the value of 10 against a customer. When that customer is queried it will return an attribute of hat size with a value of 10. 

### Customer Attribute
A customer attribute contains a description of the data (name) and the type (string, number, data). 
Attribute names are not available on the customer object. 

[Get Customer Attribute]

### Customer Attribute Value
A customer attribute values are stored directly on the customer object and return as part of the response when doing a /GET or /PUT against the customer resource. 
[Get Customer Attribute Value]
---

## Workflow

### Create a Customer Attribute

Creating a [customer attribute](#link to /POST here) requires the name of the attribute and the data type of the attribute. 

```
[
  {
    “name”: “Hat Size”,
    “type”: “string”
  }
]
```

Name accepts a string. As a best practice, the name should be descriptive of the data associated with the attribute. Types available are string, number and date.

Note: Once the data type is set, it can not be changed. The attribute will need to be deleted then created again with the new data type. This will also delete it from the customer.

### Create a Customer Attribute Value

Once the Customer Attribute is created, then assign it to a customer with a value.

There are two ways to assign the Customer Attribute Value to the customer:
1. Have attributes array as part of the Create a Customer request.
2. A /PUT request to update the customer.

Create a Customer Request Example
```
[
  {
    "email": "johndoe@email.com",
    "first_name": "John",
    "last_name": "Doe",
    "company": "BigCommerce",
    "phone": "1234567890",
    "registration_ip_address": "123.4.56.789",
    "notes": "Warehouse",
    "customer_group_id": 5,
    "addresses": [
      {
        "first_name": "John",
        "last_name": "Doe",
        "address1": "Bennelong Point ",
        "city": "Sydney",
        "state_or_province": "New South Wales",
        "postal_code": "2000",
        "country_code": "AU",
        "phone": "1234567890",
        "address_type": "commercial"
      },
      {
        "first_name": "John",
        "last_name": "Doe",
        "address1": "111 E West Street",
        "address2": "654",
        "city": "Akron",
        "state_or_province": "Ohio",
        "postal_code": "44325",
        "country_code": "US",
        "phone": "1234567890",
        "address_type": "residential"
      }
    ],
     "attributes": [
      {
        "attribute_id": 1,
        "value": "45"
      },
      {
        "attribute_id": 2,
        "value": 12
      }
    ],
    "authentication": {
      "force_password_reset": true,
      "new_password": "tempPassword1"
    }
  }
]
```

Update a Customer Example. The customer ID is required.
```
[
  {
    "id": 32,
    "email": "etu",
    "first_name": "Excepte",
    "last_name": "incidi",
    "company": "anim",
    "phone": "quis ",
    "registration_ip_address": "l",
    "notes": "adipisicing incididunt quis dolor",
    "tax_exempt_category": "Excepteur ",
    "customer_group_id": -76846758,
    "authentication": {
      "force_password_reset": true,
      "new_password": "cupidatat dolore"
    }
  }
]
```

---

## Differences between existing Customer API

### Request URL

The new Customers API is streamlined. Now instead of needed a different URL to get a single customer vs all customers. One URL used with a query parameter added to return only the data needed. This is the same for all CRUD actions on the new Customers API.

- Single Customer on V3
 --`/customers?customer_id=12`

Single Customer on V2
-- `/customers/{customer_id}`

 
### Querying
Using queries is a bigger part of the new V3 Customers API. Instead of using a different endpoint to get a certain customer, there is one GET endpoint per resource with filters. 

Get Customer Address by name and company. 
`/customers/addresses?compant:in=bigcommerce,commongood&customer_id:in1,2,3`

Get Attribute Values where the attribute id is one and the customer id is one.
`/customers/attribute-values?attribute_id:in=1&customer_id:in=1`

### Requests

Requests on this endpoint require at array object for all Create and Update Actions. 

Update a Customer V3
`/customers`

```
[
  {
    “id”: 65206491,
    “email”: “etu”,
    “first_name”: “Excepte”,
    “last_name”: “incidi”,
    “company”: “anim”,
    “phone”: “quis “,
    “registration_ip_address”: “l”,
    “notes”: “adipisicing incididunt quis dolor”,
    “tax_exempt_category”: “Excepteur “,
    “customer_group_id”: -76846758,
    “authentication”: {
      “force_password_reset”: true,
      “new_password”: “cupidatat dolore”
    }
  }
]
```

Update a Customer on V2
`/customers/{customer_id}`
```

{
  “first_name”: “Jane”,
  “email”: “jane@email.com”,
  “phone”: “1234567890”
}

```

### Authentication Object

On the new Customers endpoint, when creating a customer there are two ways to set customers passwords. 
A new password can be set under the `authentication > new password` object in a /PUT or /POST. To have customers reset the password set `force_password_reset` to `true` under `authentication > new password` object in a /PUT or /POST

[Password Confirmation]() and [validation]() are still available under V2 Customers. 

---
### Endpoints Still on V2
- [Customer Groups]()
- [Password Validation]()
- Password Confirmation

---
## Webhooks
- [Customers]()
---
## OAuth Scopes
- [Customers]()
