---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - php
  - javascript

toc_footers:
  - <a href='mailto:info@vtion.ai'>Request for a Developer keys</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Vtion API! Vtion powers visual search for eCommerce and retail. Using Vtion proprietary AI technology,
 we enable retailers with image recognition solutions from a camera button to image to text technology, in order to create a more engaged, 
 interactive and data-driven omnichannel experience.
                             
We have language bindings in Shell, PHP, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

```shell

```

```php

```

```javascript

```

Vtion uses `appid` and `appkey`  to allow access to the search API. You can request for your application Id and application Key by sending a mail to [info@vtion.ai](maito:info@vtion.ai).
Vtion expects `appid` and `appkey` to be included in all API requests to the server in a header that looks like the following:

`appid: example-app-id`
`appkey: example-app-key`

## Search product feed

> Make sure to replace `example-app-id` with your appid and `example-app-key` with your appkey.

```shell
curl --location --request POST "https://api.vtion.ai/v1/search" \
  --header "appid: example-app-id" \
  --header "appkey: example-app-key" \
  --data "{
	\"image\":\"base-64-image\"}"
```

```php
<?php
$client = new Guzzle\Http\Client();
$request = $client->get('https://api.vtion.ai/v1/search', array('image'=>'base-64-image'), array(
    'headers' => array(
    'appid' => 'example-app-id',
    'appkey' =>'example-app-key'
    )
));
?>
```

```javascript
import vtion from '@abiodunjames/vtionai';
const search = new vtion('example-app-id', 'example-app-key');
search.getClient().search('your-base-64-image')
    .then((response) => {
        console.log(response)
    })
    .catch((err) => {
        console.log(err);
    });
```

Searches for similar products within the product feed based on an image provided that is not  within the product feed. The results are ordered by how similar they are to the image.
> The above command returns JSON structured like this:

```json
{
  "results": [
    {
      "hits": [
        {
          "title": "Kids' Unisex Nightwear - Blue Multicolour", 
          "price": "3000", 
          "IndexId": "46953", 
          "image_link": "https://example.com/catalog/product/Z/C/137237_1542145837.jpg", 
          "link": "https://example.com/product/kids-unisex-nightwear-blue-multicolour-4117533", 
          "id": "4117533"
        }
      ], 
      "nbPredictions": 1
    }
  ]
}
```
