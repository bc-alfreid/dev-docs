Questions:
1. Is there anyway during create or update customer I can add the attributes values?
I wasn't able to figure out the correct formatting for the create/update customer request.

2. I made a few schema changes. I noticed the Create and Update used the response, but it was not in the right format. Array Object. `[{}]`. So I broke them out into thier own models and also updated the create to remove the id in some instances from the request example. Please review the docs and let me know if they are not correct. 

3. I got 504 Gateway Timeout errors frequently. I just kept retrying until it worked. Is that normal for now. 

4. Are the fields below the only ones that can be updated on PUT /customer?

- email
- first name
- last name
- authentication
- company
- customer_group_id
- notes
- tax_exempt_category

5. Will the /DELETE endpoints delete all objects (customer, address etc) if the id is not passed in as part of the query? (Didn't want to test my store :) )

6. The query params are not working for the /GET endpoints. I get a 422 each time. I just used address as the example here. 
`name` and `customer_id` are not working as query params
https://api.bigcommerce.com/stores/jrah6gmn/v3/customers/addresses?customer_id=20
```
{
    "status": 422,
    "title": "The filter(s): customer_id are not valid filter parameter(s).",
    "type": "https://developer.bigcommerce.com/api#api-status-codes",
    "errors": {}
}
```

7. DetailedErrors is an empty object. Any reason why?

8. IdsRequest is an empty array. What is this used for?
https://bigcommerce-customer-attributes-beta.docs.stoplight.io/api-reference/models/idsrequest

9. Will the batch size ever increase, for example creating customer attributes.

```
{
    "status": 422,
    "title": "Max batch size allowed is 1",
    "type": "https://developer.bigcommerce.com/api#api-status-codes",
    "errors": {}
}
```

10. When creating customer attributes can the dates also be apart of the request? Such as setting your own date_created?

11. I was trying to update a customer address https://api.bigcommerce.com/stores/jrah6gmn/v3/customers/addresses

```
[{
	"id":16, //address id
	"address1": "555 East Street"
}]
```

and it required a phone number as well. Do they always have to pass in the pn during an update? If true, is there a reason why?

I did check that add and it has a pn. 

```
{
    "data": [
        {
            "id": 16,
            "address1": "123 Main Street",
            "address2": "",
            "address_type": "residential",
            "city": "Austin",
            "company": "",
            "country": "United States",
            "country_code": "US",
            "customer_id": 11,
            "first_name": "Jane",
            "last_name": "Doe",
            "phone": "1234567890",
            "postal_code": "78751",
            "state_or_province": "Texas"
        }....
```

This did work
```
[{
	"id":16,
	"address1": "555 East Street",
	"phone": "1234567890"
}]
```
12. > The ability to get the hat size from the Customer Resource Object in stencil. This is coming later right, no need to go into this? 

13. It would be neat if the attribute name also returned in the /GET Customers response. That way they don't have to do a join to see the name. 

```
      "attributes": [
        {
          "id": 1,
          "customer_id": 11,
          "attribute_id": 1,
          "attribute_value": "55",
          "date_created": "2018-11-14T18:58:08Z",
          "date_modified": "2018-11-14T18:58:08Z"
        }
      ]
```

# Documentation (please ignore the formatting)

<h1> Customers API </h1>
<h3> On this Page </h3>
<ul>
	<li><a href="#payments_postman-collection">Introduction</a></li>
  	<li><a href="#payments_postman-collection">Postman Collection</a></li>
  	<li><a href="#payments_workflow">Workflow</a></li>
  	<li><a href="#payments_technical-details">Technical Details</a></li>
	<li><a href="#payments_postman-collection">Differences between existing Customer API</a></li>
  	<li><a href="#payments_current-limitations">Current Limitations</a></li>
  	<li><a href="#payments_webhooks">Webhooks </a></li>
	<li><a href="#payments_oauth-scopes">OAuth Scopes</a></li>
  	<li><a href="#payments_sample-app-diagram">Sample App Diagram</a></li>
</ul>

---
## Introduction
The Customer Attributes API allows for data to be stored aganist a customer. For example by creating an attribute of hat size, then storing the value of 10 aganist a customer. When that customer is queried it will return an attribute of hat size with a value of 9. 

---
## Postman Collection
[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/86ccd56a3d6a7701f065)
---

## Workflow

### Create a Customer Attribute

Creating a [customer attribute](#link to /POST here) requires the name of the attribute and the data type of the attribute. 

[
  {
    "name": "Hat Size",
    "type": "string"
  }
]

The name accepts a string. As a best practice, the name should be descriptive of the data it is associated with. 
The type accepts a string and it can be set to string, number or date. 

Note: Once the data type is set, it can not be changed. The attribute will need to be deleted then created again with the new data type. This will also delete it from the customer.

### Create a Customer Attribute Value

---
## Technical Details

### Customer Attribute
A customer attribute contains a description of the data(name) and the type(string, number, data). 
Attribute names are not available on the customer object. The attribute name is available 

### Customer Attribute Value
A customer attribute values are stored directly on the customer object and return as part of the response when doing a /GET or /PUT aganist the customer resource. 

### Example Customer Attribute 
(this response has been shortned)

```
      "attributes": [
        {
          "id": 1,
          "customer_id": 11,
          "attribute_id": 1,
          "attribute_value": "55",
          "date_created": "2018-11-14T18:58:08Z",
          "date_modified": "2018-11-14T18:58:08Z"
        }
      ]
 ```

---

## Differences between existing Customer API

### Request URL

The new Customers API has been streamlined. Now instead of needed a different url to get a single customer vs all customers. One url used with a query parameter added to return the only the data needed. This is the same for all CRUD actions on the new customers API.

Single Customer 
`/customers?customer_id=12`

Single Customer
`/customers/{customer_id}`

 
### Querying

### Response

---
## Current Limitation



