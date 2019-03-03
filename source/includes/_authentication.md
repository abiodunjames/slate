
# Authentication

> Make sure to replace `example-app-id` with your appid and `example-app-key` with your appkey.

Vtion uses `appid` and `appkey`  to allow access to the search API. You can request for your application Id and application Key by sending a mail to [info@vtion.ai](maito:info@vtion.ai).
Vtion expects `appid` and `appkey` to be included in all API requests to the server in a header that looks like the following:

`appid: example-app-id`
`appkey: example-app-key`

# Searching Product feed

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
import axios from 'axios';

axios.post('https://api.vtion.ai/v1/search', {
        image: base64Image
    },
    {
        headers: {
            appid: 'example-app-id',
            appkey: 'example-app-key'
        }
    }).then((response) => {
    console.log(response);
}).catch((error) => {
    console.log(error);
})
```

> The search api returns a JSON structured response like this:

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

Searches for similar products within the product feed based on an image provided that is not  within the product feed. The results are ordered by how similar they are to the image.
