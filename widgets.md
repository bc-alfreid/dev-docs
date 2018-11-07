# Widgets/Placements APIs

## Introduction
The Storefront Widgets API allows developers to programmatically associate content with regions on a BigCommerce storefront.  The content can consist of HTML, CSS, and JavaScript, and the API supports configuration via [Handlebars variables](). This is flexible enough to render nearly any type of content, including banners, carousels, video, in-browser live chat, and much more.


## Requirements

## Technical Details

## How to use
Get the avail theme regions for the page https://api.bigcommerce.com/stores/jrah6gmn/v3/content/regions?templateFile=pages/home . Must have a filter otherwise retuns 400 status invalid. 

Create a Theme Region
Find a list of pages here: https://stencil.bigcommerce.com/docs/js-pg-cycle
**Question** - Anyway to make the theme region without having to open the theme files and do it manually?
Must have a fil

### Example 1
### Example 2
### Example 3

## OAuth Scopes
## Webhooks
## Related Endpoints


Edit a private theme file or copy of any marketplace theme file to define regions on the page
Specify the placement and order of the widget in a region
Add a widget (handlebars template and configuration) onto a page region
Add the widget to:
All browse pages (ex. product, category pages)
Particular instance of the page type (ex. single product detail page)
Particular non-browse page (home page/about us page)
Activate or deactivate the widget in a given region on the page
Prevent things like html, head, body, etc to be placed in content blocks. We expect only HTML which is valid inside a <body> tag
limit is 500
  
Can add own theme region by adding to theme. 
Widget Templates are resusable
