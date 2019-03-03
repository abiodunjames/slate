# Product feed
> Sample product feed format in json

```json
[
{
    "id":"10006373783",
    "title":"White Nike shoe",
    "image_link":"http://www.exampleshop.com/product/image/working-boots.png",
    "link":"http://www.exampleshop.com/product/white-nike-shoe-10006373783.html",
    "price":"$71.80"
}
]
```
A product feed is a file that contains information about all products on your site. We will use this information to train our models.

## Supported Format

Only two formats are supported for product feeds

1. JSON
2. CSV

## Product Information to provide

All field names must be in English. Product information should not contain HTML tags or style tags.

**id**:  The `id` is a unique product identifier that represents only one product. Once an `id` is assigned to a product and imported, it may not be used for a different product, 
nor can the `id` for a particular product change. 
<aside class="notice">
This field is required for all products in the feed, and cannot be empty/blank.
</aside>

**title**: This field is required for all products in the feed, and cannot be empty/blank. The title is the product’s name, typically as it is displayed on the product’s detail page. This will be used as the main text descriptor for a given product.

**image_link**: This field is required for all products in the feed, and cannot be empty/blank: The image_link is a URL that specifies a file path to a given product’s image. Ideally, images should be at least 800x800 pixels and under 5MB. The image must have a Content-Type header specified, either image/png, image/gif or image/jpeg.

**link**: This field is required for all products in the feed, and cannot be empty/blank. The link is the product’s dedicated detail page. The link is usually, although not necessarily, unique to a given product. The product information on this URL should match the corresponding information provided in your feed. Please specify the protocol (http:// or https://) for all URLs.

**price**: This field is optional. It's the price required for the product



