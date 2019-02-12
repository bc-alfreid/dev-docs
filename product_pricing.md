
## Pricing on BigCommerce
[Working title]

## Introduction

Product pricing is an important part of a BigCommerce store. This article will go over catalog pricing on simple products and products with variants. It will go over the price types on a product, how price is weighted and pricing precision.

[Note: The images all images used are based on the [Cornerstone]() theme and may differ from your theme. Most of the examples assume prices are entered with tax. Where applicable, different configurations will be mentioned.]


## Default Price
Default Price
Price of the product. In the Control Panel this shows as Default Price. Default price can be entered with or without tax. This will depend on the stores [tax settings](https://support.bigcommerce.com/s/article/Manual-Tax-Setup). The price appears on the product detail page and is what a shopper expects to pay during checkout.

The default price is accessible from:
* Control Panel
* API

## Cost Price
How much it costs you to buy the product. This does not display on the storefront and is for your use. It does not change cart or product detail page pricing. 

The cost price is accessible from:
* Control Panel
* API

## MSRP (Retail Price)
Manufacturer’s Suggested Retail Price or Retail price is used to show how much cheaper the product you are selling is compared to other sites. When entered this will show on the product detail page, usually with a strike-through. This does not change the cart pricing of a product.

The MSRP is accessible from:
* Control Panel
* API


## Sale Price
Used to offer a product for a cheaper price. This overwrites the default price of the product. It does not affect the cost price or the retail price.

The sale price is accessible from:
* Control Panel
* API

## Map Price
Map price or minimum advertised price, is the lowest price a retailer can sell the item for. This is an agreement between the seller and the maker of the product. Map price is not displayed on the storefront and only accessible from the API.

The map price is accessible from:
API

## Calculated Price
The calculated price is the final price of the product after it takes the sale price into account. If a product has variants, the calculated price is shown twice. Once under the default product and again under the variant. This is a read-only field accessible from the API only.

The calculated price is accessible from:
API

## Variant Pricing
Pricing on [variants]() will override the default pricing if a price is set at the SKU level. If the SKU’s do not have a price, then they will use the Default Price. 

Cost Price can be set per variant. It does not display to the customer. 

Sale Price can be set per variant. This will override the any default product pricing, including the default product sale price. 

The variant price is accessible from:
* Control Panel
* API

### Bulk Pricing 

Bulk pricing offers shoppers a discount if the purchase a certain number of items. 

The variant price is accessible from:
* Control Panel
* API


## Customer Groups

Customer groups allows you to organize customers and give them discounts. '

Customer Groups are accessible from:
* Control Panel
* API


## Price Lists
[keeping this section short and any extra move to the main Price List article]

Price Lists are accessible from:
* Control Panel
* API

## Modifiers

## Cart 
### List Price
### Sale Price 
### Extended List Price
### Extended Sale Price

## Pricing Precision
Price can be input using up to 4 decimal places.

Depending on the price, it can round up or down. We allow up to 4 decimal places and use the 5th decimal place to either roundup or down. This holds true for all pricing options available on a product.

Example:
* `“price”: 10.99999` - rounds up to 11
* `“price”: 10.99994` - rounds down to 10.9999

### Display

Currency settings allows for inputting a large number of decimal places for display. Since pricing precision cuts off at 4, the rest are displayed as zero’s.

[add pdp image here]



