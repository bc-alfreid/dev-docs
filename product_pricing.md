
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
Available in Fixed ($5), Relative (-$2), or Percentage (-25%). Might apply to one product, a category of products, or the entire store's products.

The variant price is accessible from:
* Control Panel
* API


## Customer Groups

Customer groups allows you to organize customers and give them discounts. 
Available in Fixed ($5), Relative (-$2), or Percentage (-25%). Might apply to one product, a category of products, or the entire store's products.

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

Pricing Table [working title]
This table shows the order in which pricing is applied to the product. The weighting is read from top to bottom. Each price overwrites the pricing that came before. 

| Price Type | Behavior  | Example | Product | Variant | Other |
|--|--|--|--|--| -- |
| Default Product Price | Required on product.| T-Shirt: $25  | Price: $25</br></br>Calculated Price: $ 25 | N/A |
| Sale Price | Overrides the default product price.  Optional on product | With a discount of $5 each item is now only $20 | ~~Price: $25~~</br></br>Sale Price: $20</br></br>Calculated Price: $ 20 | N/A|
| Variant Price |Overrides default product or sale pricing. The base product will still show the default pricing in an API response. On the storefront, the shopper only sees variant pricing. </br>Optional on product | Small T-Shirt: $30</br></br>Medium T-Shirt: $35</br></br>Large T-Shirt: $40| ~~Price: $25~~</br></br>~~Sale Price: $20~~</br></br>~~Calculated Price: $ 20~~ | Price: $30</br></br>Calculated Price: $30|
| Variant Sale Price | Overrides default product, sale pricing or variant pricing. The base product will still show the default pricing in an API response. On the storefront, the shopper only sees variant pricing.Optional on product |Small T-Shirt: ~~$30~~ $15</br></br>Medium T-Shirt: $35</br></br>Large T-Shirt: $40| ~~Price: $25~~</br></br>~~Sale Price: $20~~</br></br>~~Calculated Price: $ 20~~ | ~~Price: $30~~</br></br>Sale Price: $15</br></br>Calculated Price: $15 |
| Customer Groups | It is combined with any previous sale or variant pricing. Optional on product. |It will use the variant sale pricing to take $2 off each item. For example, variant price is $15. With the Customer Group Discount it is now $13 off each item.  |~~Price: $25~~</br></br>~~Sale Price: $20~~</br></br>~~Calculated Price: $ 20~~ | ~~Price: $30~~</br></br>Sale Price: $15</br></br>Calculated Price: $15</br></br>Product Display Page: $13 |
| Product Bulk Pricing |  Applies a storewide discount on products based on a tiered discount. Bulk Pricing does not change the default, variant or customer pricing. Bulk pricing is combined with any previous sale or customer group pricing. It is combined with any previous default pricing, sale pricing, variant pricing and customer group discounts. | If the storewide discount is buy 20 get $1 off each item. Then each item will be $12. This is because this is now including the previous customer group discount. | ~~Price: $25~~</br></br>~~Sale Price: $20~~</br></br>~~Calculated Price: $ 20~~ | ~~Price: $30~~</br></br>Sale Price: $15</br></br>Calculated Price: $15</br></br>Product Display Page: Buy in Bulk and Save | Cart Price: $12 |
| Price List Variant | It is only availble to Customer Groups. Required for Price List. | 2% discount on all product variants. This will be on top of the variant sale pricing. It no longer includes customer group pricing or bulk pricing. Small T-Shirt: $30 Medium T-Shirt: $35 Large T-Shirt: $40| N/A | ~~Price: $30~~</br></br>Sale Price: $15</br></br>Calculated Price: $ 15 | Price List Variant, based on Variant Sale Price</br></br>Price: $14.70</br></br> Sale Price: N/A</br></br>Calculated Price: $14.70 |




