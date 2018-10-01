Here are some notes on the payments API.


PROJECT-1986.payment_api_v3_create_payments_scope is the expirement I enabled.

I keep getting an order is invalid. I made the order using the cart/checkout then created an order using the checkout api. 
I have tried serveral orders, but it keeps returning order invalid. What makes the order valid so that I can get a payment access token?

```
{
  "order": {
    "id": 183
  }
}

```

`https://api.bigcommerce.com/stores/jrah6gmn/v3/payments/access_tokens`

## PaymentAccessTokenRequest under Create an access token

Why is there an is_recurring field? Does it do anything?
Why would I want to fill in shopper_session?

## Stored Card
- Right now this looks like its read only. Is this in anticipation of vaulted cards?
- Brand - you mean like visa, mastercard
- iin where would a dev get this
- token where would they get the token

## Payment Method
- test mode: Normally (and this is just from a merchants view), you set test mode on the payment portals site. What does setting
it here do? For example is if I select test mode here, but its not selected on the payment provides end what happens?

# Process a payment for a particular order

## Card
- type is enum and then its card again. Are there more types coming? What are the other options?
- verification_value: Where is this from? Do oyu mean the cvv on the card?

## Stored Card
- type: Just says to classify this payment instrument and it is stored_card? Are there others? 

## Payment Request
- payment_method_id What identifier? It doesn't explain where that can be found


## First attempts

{
    "status": 500,
    "code": 10000,
    "title": "Something went wrong with your request, please try again",
    "type": "https://developer.bigcommerce.com/api#api-status-codes"
}


{
    "status": 422,
    "code": 20001,
    "title": "Order is invalid.",
    "type": "https://developer.bigcommerce.com/api#api-status-codes"
}

{
  "order": {
    "id": 183 //order I created via api.
  }
}
