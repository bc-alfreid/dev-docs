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

