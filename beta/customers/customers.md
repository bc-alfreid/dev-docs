How do I assign attributes to a customer. I was not able to figure out the format?

---

Based on the schema, to  create a customer its an object array(see below). But its actually an array object to create customers. 

Customer Collection Request is what I based this on. I also removed customer_id and id from the request and updated the required fields. A few others were object arrays based on the schema, but that was only for the response. THe create/update needed an array object.

```
{
  "customers": [
    {
      "email": "ut anim dolor",
      "first_name": "consecte",
      "last_name": "non ",
      "id": 26576113,
      "company": "occ",
      "phone": "ea mag",
      "customer_since_date": "1971-02-11T11:27:42.594Z",
      "registration_ip_address": "velit sunt elit",
      "notes": "nulla ",
      "tax_exempt_category": "Duis irur",
      "authentication": {
        "force_password_reset": false,
        "new_password": "velit Ut"
      },
      "customer_group_id": 94333134,
      "address_count": -92936898,
      "addresses": [
        {
          "id": -16378212,
          "customer_id": 93157841,
          "first_name": "nostrud",
          "last_name": "cupidat",
          "company": "tem",
          "address1": "ad ",
          "address2": "in e",
          "city": "",
          "state_or_province": "cu",
          "postal_code": "a",
          "country_code": "ad",
          "country": "dolor",
          "phone": "tem",
          "address_type": "commercial"
        },
        {
          "id": 75251475,
          "customer_id": 1704105,
          "first_name": "m",
          "last_name": "cu",
          "company": "cupi",
          "address1": "proide",
          "address2": "sed id",
          "city": "L",
          "state_or_province": "mollit ad ",
          "postal_code": "esse m",
          "country_code": "do",
          "country": "",
          "phone": "ni",
          "address_type": "residential"
        },
        {
          "id": 52990251,
          "customer_id": -68596327,
          "first_name": "non tem",
          "last_name": "",
          "company": "officia ",
          "address1": "qui Ut",
          "address2": "",
          "city": "adipisi",
          "state_or_province": "a",
          "postal_code": "incididunt",
          "country_code": "ex",
          "country": "sed sin",
          "phone": "do anim ",
          "address_type": "commercial"
        }
      ],
      "attribute_count": -85437732,
      "attributes": [
        {
          "id": -62997935,
          "customer_id": -5237536,
          "attribute_id": -97146807,
          "value": "magna cupidatat irure labore",
          "date_modified": "1989-01-30T08:10:06.550Z",
          "date_created": "1983-03-16T16:50:03.113Z"
        },
        {
          "id": -64814840,
          "customer_id": -18156587,
          "attribute_id": 32586739,
          "value": "aliquip",
          "date_modified": "2000-11-27T03:26:10.996Z",
          "date_created": "1966-10-26T02:42:18.085Z"
        },
        {
          "id": 87074300,
          "customer_id": 48603026,
          "attribute_id": -64191249,
          "value": "fugiat dolor nulla incididunt esse",
          "date_modified": "1952-10-30T18:38:55.875Z",
          "date_created": "1992-09-17T12:14:04.768Z"
        },
        {
          "id": 42481440,
          "customer_id": 46941942,
          "attribute_id": -21765702,
          "value": "dolor Excepteur quis pariatur est",
          "date_modified": "1955-09-29T00:59:37.816Z",
          "date_created": "1946-12-09T05:11:03.535Z"
        }
      ]
    },
    {
      "email": "ei",
      "first_name": "ea",
      "last_name": "elit magn",
      "id": -81992841,
      "company": "e",
      "phone": "velit e",
      "customer_since_date": "2006-12-08T04:56:23.817Z",
      "registration_ip_address": "eiusmod amet",
      "notes": "sunt ",
      "tax_exempt_category": "sit oc",
      "authentication": {
        "force_password_reset": true,
        "new_password": "Lorem id"
      },
      "customer_group_id": 9469334,
      "address_count": -65244799,
      "addresses": [
        {
          "id": 91561850,
          "customer_id": -56588411,
          "first_name": "cupidatat ",
          "last_name": "i",
          "company": "ma",
          "address1": "est si",
          "address2": "dolor ",
          "city": "",
          "state_or_province": "deserunt L",
          "postal_code": "E",
          "country_code": "la",
          "country": "in ei",
          "phone": "es",
          "address_type": "commercial"
        },
        {
          "id": 58777425,
          "customer_id": -34947968,
          "first_name": "in ",
          "last_name": "ad",
          "company": "nulla id ",
          "address1": "enim",
          "address2": "c",
          "city": "culp",
          "state_or_province": "ad",
          "postal_code": "vo",
          "country_code": "no",
          "country": "sunt",
          "phone": "dolor",
          "address_type": "commercial"
        },
        {
          "id": -78191094,
          "customer_id": -82984474,
          "first_name": "et E",
          "last_name": "id ma",
          "company": "adipisic",
          "address1": "qui dolo",
          "address2": "",
          "city": "magna Ut d",
          "state_or_province": "lab",
          "postal_code": "exerci",
          "country_code": "qu",
          "country": "Lo",
          "phone": "aliqua sun",
          "address_type": "commercial"
        },
        {
          "id": -11798032,
          "customer_id": 33550120,
          "first_name": "nostr",
          "last_name": "",
          "company": "L",
          "address1": "eu Lor",
          "address2": "c",
          "city": "non s",
          "state_or_province": "cupi",
          "postal_code": "minim off",
          "country_code": "la",
          "country": "cillum",
          "phone": "fugia",
          "address_type": "commercial"
        }
      ],
      "attribute_count": -23812275,
      "attributes": [
        {
          "id": 17033501,
          "customer_id": -75343118,
          "attribute_id": -29870391,
          "value": "commodo dolor est tempor elit",
          "date_modified": "1970-06-22T23:04:10.334Z",
          "date_created": "1989-10-18T06:17:59.710Z"
        }
      ]
    },
    {
      "email": "in irure nisi enim laboris",
      "first_name": "pr",
      "last_name": "venia",
      "id": -86655242,
      "company": "",
      "phone": "anim Exc",
      "customer_since_date": "1951-11-01T22:03:44.812Z",
      "registration_ip_address": "minim",
      "notes": "fug",
      "tax_exempt_category": "mollit do",
      "authentication": {
        "force_password_reset": false,
        "new_password": "magna"
      },
      "customer_group_id": -88339953,
      "address_count": 74642378,
      "addresses": [
        {
          "id": -63596496,
          "customer_id": 77218550,
          "first_name": "",
          "last_name": "deseru",
          "company": "sed irure",
          "address1": "ad labore ",
          "address2": "elit",
          "city": "Ut est ",
          "state_or_province": "do",
          "postal_code": "dolor",
          "country_code": "mi",
          "country": "",
          "phone": "c",
          "address_type": "commercial"
        },
        {
          "id": 50708055,
          "customer_id": -44140221,
          "first_name": "consec",
          "last_name": "cillum cup",
          "company": "deseru",
          "address1": "",
          "address2": "",
          "city": "Lore",
          "state_or_province": "minim ",
          "postal_code": "ull",
          "country_code": "no",
          "country": "",
          "phone": "",
          "address_type": "commercial"
        }
      ],
      "attribute_count": 2179918,
      "attributes": [
        {
          "id": 72169826,
          "customer_id": -73241824,
          "attribute_id": -81144499,
          "value": "id laborum sed ex ut",
          "date_modified": "2017-07-20T04:21:54.642Z",
          "date_created": "1978-09-06T11:52:18.757Z"
        }
      ]
    },
    {
      "email": "ad",
      "first_name": "u",
      "last_name": "offi",
      "id": 15941177,
      "company": "dolo",
      "phone": "in",
      "customer_since_date": "1957-03-12T01:29:45.967Z",
      "registration_ip_address": "occaecat aliquip in",
      "notes": "anim",
      "tax_exempt_category": "o",
      "authentication": {
        "force_password_reset": true,
        "new_password": "magna"
      },
      "customer_group_id": 47978154,
      "address_count": 6961836,
      "addresses": [
        {
          "id": 76179543,
          "customer_id": -90325605,
          "first_name": "cul",
          "last_name": "commodo ",
          "company": "dol",
          "address1": "aliqui",
          "address2": "Duis s",
          "city": "",
          "state_or_province": "c",
          "postal_code": "su",
          "country_code": "ex",
          "country": "qui ",
          "phone": "nostru",
          "address_type": "commercial"
        },
...
```

---

I got 504 Gateway Timeout errors frequently. I just kept retrying until it worked

---

Are the fields below the only ones that can be updated?

- email
- first name
- last name
- authentication
- company
- customer_group_id
- notes
- tax_exempt_category

---
Will the /DELETE endpoints delete all objects (customer, address etc) if the id is not passed in as part of the query? (Didn't want to test my store :) )

---

Get Address
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
---

DetailedErrors is an empty object. Any reason why?

---
IdsRequest is an empty array. What is this used for?

https://bigcommerce-customer-attributes-beta.docs.stoplight.io/api-reference/models/idsrequest

---
Will the batch size ever increase, for example creating customer attributes.

```
{
    "status": 422,
    "title": "Max batch size allowed is 1",
    "type": "https://developer.bigcommerce.com/api#api-status-codes",
    "errors": {}
}
```
---

When creating customer attributes can the dates also be apart of the request? Such as setting your own date_created?

---

I was trying to update a customer address https://api.bigcommerce.com/stores/jrah6gmn/v3/customers/addresses
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

This did work,
[{
	"id":16,
	"address1": "555 East Street",
	"phone": "1234567890"
}]

---
