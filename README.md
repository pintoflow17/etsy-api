
# ETSY API Documentation

The Etsy API provides developers with real-time access to a wealth of data from the Etsy marketplace, including product information, categories, shop details, and shop products. This API is ideal for anyone looking to integrate Etsy's vibrant marketplace data into their applications or websites.

With various endpoints available, the Etsy API allows users to retrieve detailed information on products, shop statistics, and category listings. Its structured JSON responses make it easy to incorporate Etsy data into a wide range of platforms, enabling enhanced user experiences and streamlined access to the unique offerings available on Etsy.

# Authentication
The URL you need to use is the following: `https://etsy-api2.p.rapidapi.com/`
The API requires the headers listed below:

 - **`x-rapidapi-host`**: `etsy-api2.p.rapidapi.com`
 - **`x-rapidapi-key`**: `YOUR_API_KEY`

Make sure to replace `YOUR_API_KEY` with your API key. You can register one [here](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/etsy-api2/pricing).
Some frameworks automatically add extra headers, you have to make sure to remove them in order to get a response from the API.

# Endpoints
The API is configured to accept only **GET** requests. Below are the available endpoints with their descriptions and required parameters.

#### 1. **`GET /product/search`**
-   **Description**: This endpoint allows you to search for products on Etsy's platform.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `query` | string | `-` | The search query for products. | Yes |
| `page` | number | `1` | The page number of the search results.. | No |
| `currency` | string | `USD` | The currency for pricing. Acceptable currency codes include: `USD`, `CAD`, `EUR`, `GBP`, `AUD`, `JPY`, `CNY`, `CZK`, `DKK`, `HKD`, `HUF`, `INR`, `IDR`, `ILS`, `MYR`, `MXN`, `MAD`, `NZD`, `NOK`, `PHP`, `SGD`, `VND`, `ZAR`, `SEK`, `CHF`, `THB`, `TWD`, `TRY`, `PLN`, `BRL`, etc. | No |
| `language` | string | `en-US` | The language code for the description. Acceptable codes include: `de`, `en-GB`, `en-IN`, `en-US`, `es`, `fr`, `it`, `ja`, `nl`, `pl`, `pt`, `ru`, etc. | No |
| `country` | string | `'US'` | The country code for localization. Acceptable country codes include: `US`, `CA`, `GB`, etc. | No |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/product/search?query=gift', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "response": [
    {
      "title": "Hygge Pumpkin Fall Gift Box, Boo Basket, Spooky Season Gift, Cozy Fall Gift Set, Harvest Gift, Pumpkin Spice, Halloween Gifts",
      "listingId": "1759950030",
      "price": {
        "salePrice": "40.99",
        "originalPrice": "45.55",
        "discount": "10%",
        "deliveryInfo": "Returns accepted",
        "currency": "$"
      },
      "rating": "",
      "shopId": 34523747,
      "bestseller": false,
      "...": "..."
    },
    {
      "title": "Hug In A Box, Fall Gift Box, Mom Gift Set, Hygge Gift Box, Thinking Of You Box, Cozy Care Package, Self Care Basket, Blanket Gift Box",
      "listingId": "1773935102",
      "price": {
        "salePrice": "44.01",
        "originalPrice": "62.86",
        "discount": "30%",
        "deliveryInfo": "Returns accepted",
        "currency": "$"
      },
      "rating": "",
      "shopId": 36070715,
      "bestseller": false,
      "...": "..."
    },
    {
      "title": "Personalized Wooden Recipe Book Binder Custom Journal Cookbook Notebook Valentine's Day Bridal Shower Gift Daughter  Birthday Gift Gift Moms",
      "listingId": "811792213",
      "price": {
        "salePrice": "27.50",
        "originalPrice": "50.00",
        "discount": "45%",
        "deliveryInfo": "Returns accepted",
        "currency": "$"
      },
      "rating": "",
      "shopId": 18776409,
      "bestseller": false,
      "...": "..."
    },
    {
      "title": "Groomsmen Gifts, Personalized Bluetooth Speaker, Portable Bluetooth Speaker, Mini Wood Speaker, Bridesmaid Gifts, Portable and Rechargeable",
      "listingId": "722285868",
      "price": {
        "salePrice": "23.99",
        "originalPrice": "29.99",
        "discount": "20%",
        "deliveryInfo": "Free shipping",
        "currency": "$"
      },
      "rating": "",
      "shopId": 10329130,
      "bestseller": true,
      "...": "..."
    },
    {
      "title": "Custom Pet Portrait Glass Suncatcher, Dog Cat Glass Art, Pet Window Hangings, Pet Portrait From Photo, Pet Memorial Gift, Pet Lover Gift",
      "listingId": "1772129768",
      "price": {
        "salePrice": "39.90",
        "originalPrice": "99.73",
        "discount": "60%",
        "deliveryInfo": "Returns accepted",
        "currency": "$"
      },
      "rating": "",
      "shopId": 35207881,
      "bestseller": false,
      "...": "..."
    },
    {
      "title": "Custom Baby Gift: Personalized Baby Sweaters Hand-Embroidered with Love and Care!",
      "listingId": "1572112084",
      "price": {
        "salePrice": "22.02",
        "originalPrice": "81.53",
        "discount": "73%",
        "deliveryInfo": "",
        "currency": "$"
      },
      "rating": "",
      "shopId": 45035280,
      "bestseller": false,
      "...": "..."
    },
    ...
  ]
}
```



#### 2. **`GET /search/suggestion`**
-   **Description**: This endpoint retrieves search suggestions based on a given query on Etsy.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `query` | string | `-` | The search query for suggestions. | Yes |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/search/suggestion?query=gift', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "data": [
    {
      "query": "gift",
      "search_types": [],
      "search_type_names": []
    },
    {
      "query": "gifts for him",
      "search_types": [],
      "search_type_names": []
    },
    {
      "query": "gift for her",
      "search_types": [],
      "search_type_names": []
    },
    {
      "query": "gifts for kids",
      "search_types": [],
      "search_type_names": []
    },
    {
      "query": "gifts for boyfriend",
      "search_types": [],
      "search_type_names": []
    },
    {
      "query": "gift box",
      "search_types": [],
      "search_type_names": []
    },
    "..."
  ]
}
```



#### 3. **`GET /shop/id2`**
-   **Description**: This endpoint retrieves the shop ID for a given listing ID on Etsy's platform.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `listingId` | number | `-` | The unique identifier of the product listing. | Yes |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/shop/id2?listingId=1193254419', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "message": "Unexpected token u in JSON at position 0"
}
```



#### 4. **`GET /shop/id`**
-   **Description**: This endpoint retrieves the shop ID for a given shop name on Etsy's platform.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `shopName` | string | `-` | The name of the shop. | Yes |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/shop/id?shopName=AceElegance', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "data": {
    "shopName": "AceElegance",
    "shopId": 27808603
  }
}
```



#### 5. **`GET /category`**
-   **Description**: This endpoint retrieves all product categories on Etsy's platform.

-   **Parameters**: This endpoint has no parameters.

Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/category', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "data": [
    {
      "view_name": "Search2_View_Filter_CategorySelectorNode",
      "template": "pages/search2_neu/filters/category-selector-node.mustache",
      "data": {
        "id": 1,
        "name": "Accessories",
        "padding_level": 4,
        "margin_level": null,
        "path": "accessories",
        "show_children": true,
        "...": "..."
      },
      "regions": {
        "nodes": [
          {
            "view_name": "Search2_View_Filter_CategorySelectorNode",
            "template": "pages/search2_neu/filters/category-selector-node.mustache",
            "data": {
              "id": 1728,
              "name": "Baby Accessories",
              "padding_level": 6,
              "margin_level": null,
              "path": "accessories/baby-accessories",
              "show_children": false,
              "...": "..."
            },
            "regions": {
              "nodes": [
                {
                  "view_name": "Search2_View_Filter_CategorySelectorNode",
                  "template": "pages/search2_neu/filters/category-selector-node.mustache",
                  "data": {
                    "id": 135,
                    "name": "Baby Carriers & Wraps",
                    "padding_level": 8,
                    "margin_level": null,
                    "path": "accessories/baby-accessories/baby-carriers-and-wraps",
                    "show_children": false,
                    "...": "..."
                  },
                  "regions": {
                    "nodes": []
                  },
                  "view_global_data": [],
                  "css_files": [],
                  "...": "..."
                },
                {
                  "view_name": "Search2_View_Filter_CategorySelectorNode",
                  "template": "pages/search2_neu/filters/category-selector-node.mustache",
                  "data": {
                    "id": 2934,
                    "name": "Baby Headbands",
                    "padding_level": 8,
                    "margin_level": null,
                    "path": "accessories/baby-accessories/baby-headbands",
                    "show_children": false,
                    "...": "..."
                  },
                  "regions": {
                    "nodes": []
                  },
                  "view_global_data": [],
                  "css_files": [],
                  "...": "..."
                },
              ]
            },
            "view_global_data": [],
            "css_files": [],
            "...": "..."
          },
          {
            "view_name": "Search2_View_Filter_CategorySelectorNode",
            "template": "pages/search2_neu/filters/category-selector-node.mustache",
            "data": {
              "id": 2,
              "name": "Belts & Braces",
              "padding_level": 6,
              "margin_level": null,
              "path": "accessories/belts-and-suspenders",
              "show_children": false,
              "...": "..."
            },
            "regions": {
              "nodes": [
                {
                  "view_name": "Search2_View_Filter_CategorySelectorNode",
                  "template": "pages/search2_neu/filters/category-selector-node.mustache",
                  "data": {
                    "id": 3,
                    "name": "Belt Buckles",
                    "padding_level": 8,
                    "margin_level": null,
                    "path": "accessories/belts-and-suspenders/belt-buckles",
                    "show_children": false,
                    "...": "..."
                  },
                  "regions": {
                    "nodes": []
                  },
                  "view_global_data": [],
                  "css_files": [],
                  "...": "..."
                },
                {
                  "view_name": "Search2_View_Filter_CategorySelectorNode",
                  "template": "pages/search2_neu/filters/category-selector-node.mustache",
                  "data": {
                    "id": 4,
                    "name": "Belts",
                    "padding_level": 8,
                    "margin_level": null,
                    "path": "accessories/belts-and-suspenders/belts",
                    "show_children": false,
                    "...": "..."
                  },
                  "regions": {
                    "nodes": []
                  },
                  "view_global_data": [],
                  "css_files": [],
                  "...": "..."
                },
                {
                  "view_name": "Search2_View_Filter_CategorySelectorNode",
                  "template": "pages/search2_neu/filters/category-selector-node.mustache",
                  "data": {
                    "id": 5,
                    "name": "Braces",
                    "padding_level": 8,
                    "margin_level": null,
                    "path": "accessories/belts-and-suspenders/suspenders",
                    "show_children": false,
                    "...": "..."
                  },
                  "regions": {
                    "nodes": []
                  },
                  "view_global_data": [],
                  "css_files": [],
                  "...": "..."
                }
              ]
            },
            "view_global_data": [],
            "css_files": [],
            "...": "..."
          },
          "..."
        ]
      },
      "view_global_data": [],
      "css_files": [],
      "...": "..."
    },
    {
      "view_name": "Search2_View_Filter_CategorySelectorNode",
      "template": "pages/search2_neu/filters/category-selector-node.mustache",
      "data": {
        "id": 66,
        "name": "Art & Collectibles",
        "padding_level": 4,
        "margin_level": null,
        "path": "art-and-collectibles",
        "show_children": false,
        "...": "..."
      },
      "regions": {
        "nodes": [
          {
            "view_name": "Search2_View_Filter_CategorySelectorNode",
            "template": "pages/search2_neu/filters/category-selector-node.mustache",
            "data": {
              "id": 1865,
              "name": "Artist Trading Cards",
              "padding_level": 6,
              "margin_level": null,
              "path": "art-and-collectibles/artist-trading-cards",
              "show_children": false,
              "...": "..."
            },
            "regions": {
              "nodes": []
            },
            "view_global_data": [],
            "css_files": [],
            "...": "..."
          },
          "..."
        ]
      },
      "view_global_data": [],
      "css_files": [],
      "...": "..."
    },
    "..."
  ]
}
```


### Products


#### 1. **`GET product/descriptionV3`**
-   **Description**: This endpoint retrieves product descriptions based on provided parameters.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `listingId` | number | `undefined` | The ID of the product listing. | Yes |
| `currency` | string | `USD` | The currency code for pricing. Acceptable currency codes are: `USD`, `CAD`, `EUR`, `GBP`, `AUD`, `JPY`, `CNY`, `CZK`, `DKK`, `HKD`, `HUF`, `INR`, `IDR`, `ILS`, `MYR`, `MXN`, `MAD`, `NZD`, `NOK`, `PHP`, `SGD`, `VND`, `ZAR`, `SEK`, `CHF`, `THB`, `TWD`, `TRY`, `PLN`, `BRL`. | No |
| `language` | string | `en-US` | The language code for the description. Acceptable language codes are: `de`, `en-GB`, `en-IN`, `en-US`, `es`, `fr`, `it`, `ja`, `nl`, `pl`, `pt`, `ru`. | No |
| `country` | string | `US` | The country code for localization. Acceptable country codes include: `AF`, `AX`, `AL`, `DZ`, `AS`, `AD`, `AO`, `AI`, `AG`, `AR`, `AM`, `AW`, `AU`, `AT`, `AZ`, `BS`, `BH`, `BD`, `BB`, `BE`, `BZ`, `BJ`, `BM`, `BT`, `BO`, `BA`, `BW`, `BV`, `BR`, `IO`, `VG`, `BN`, `BG`, `BF`, `BI`, `KH`, `CM`, `CA`, `CV`, `KY`, `CF`, `TD`, `CL`, `CN`, `CX`, `CC`, `CO`, `KM`, `CG`, `CK`, `CR`, `HR`, `CW`, `CY`, `CZ`, `DK`, `DJ`, `DM`, `DO`, `EC`, `EG`, `SV`, `GQ`, `ER`, `EE`, `ET`, `FK`, `FO`, `FJ`, `FI`, `FR`, `GF`, `PF`, `TF`, `GA`, `GM`, `GE`, `DE`, `GH`, `GI`, `GR`, `GL`, `GD`, `GP`, `GU`, `GT`, `GG`, `GN`, `GW`, `GY`, `HT`, `HM`, `VA`, `HN`, `HK`, `HU`, `IS`, `IN`, `ID`, `IQ`, `IE`, `IM`, `IL`, `IT`, `CI`, `JM`, `JP`, `JE`, `JO`, `KZ`, `KE`, `KI`, `XK`, `KW`, `KG`, `LA`, `LV`, `LB`, `LS`, `LR`, `LY`, `LI`, `LT`, `LU`, `MO`, `MK`, `MG`, `MW`, `MY`, `MV`, `ML`, `MT`, `MH`, `MQ`, `MR`, `MU`, `YT`, `MX`, `FM`, `MD`, `MC`, `MN`, `ME`, `MS`, `MA`, `MZ`, `MM`, `NA`, `NR`, `NP`, `AN`, `NC`, `NZ`, `NI`, `NE`, `NG`, `NU`, `NF`, `MP`, `NO`, `OM`, `PK`, `PW`, `PS`, `PA`, `PG`, `PY`, `PE`, `PH`, `PL`, `PT`, `PR`, `QA`, `RE`, `RO`, `RW`, `SH`, `KN`, `LC`, `MF`, `PM`, `VC`, `WS`, `SM`, `ST`, `SA`, `SN`, `RS`, `SC`, `SL`, `SG`, `SX`, `SK`, `SI`, `SB`, `SO`, `ZA`, `GS`, `KR`, `SS`, `ES`, `LK`, `SD`, `SR`, `SJ`, `SZ`, `SE`, `CH`, `TW`, `TJ`, `TZ`, `TH`, `NL`, `TL`, `TG`, `TK`, `TO`, `TT`, `TN`, `TR`, `TM`, `TC`, `TV`, `UG`, `UA`, `AE`, `GB`, `US`, `UM`, `UY`, `VI`, `UZ`, `VU`, `VE`, `VN`, `WF`, `EH`, `YE`, `CD`, `ZM`, `ZW`. | No |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/product/descriptionV3?listingId=1574427777', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "data": []
}
```



#### 2. **`GET /product/similar`**
-   **Description**: This endpoint allows you to retrieve similar products for a specific listing on Etsy.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `listingId` | number | `-` | The unique identifier of the product listing. | Yes |
| `currency` | string | `USD` | The currency for pricing. Acceptable currency codes are: `USD`, `CAD`, `EUR`, `GBP`, `AUD`, `JPY`, `CNY`, `CZK`, `DKK`, `HKD`, `HUF`, `INR`, `IDR`, `ILS`, `MYR`, `MXN`, `MAD`, `NZD`, `NOK`, `PHP`, `SGD`, `VND`, `ZAR`, `SEK`, `CHF`, `THB`, `TWD`, `TRY`, `PLN`, `BRL`. | No |
| `language` | string | `en-US` | The language code for the description. Acceptable language codes are: `de`, `en-GB`, `en-IN`, `en-US`, `es`, `fr`, `it`, `ja`, `nl`, `pl`, `pt`, `ru`. | No |
| `country` | string | `US` | The country code for localization. | No |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/product/similar?listingId=1502144869', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "data": [
    {
      "title": "Personalized Wooden Birth Flower Garden, Flower Decoration, Grandma Garden, Birthday Flower Bouquet Gift, Mother's Day Gift, Christmas Gift",
      "listingId": "1807079985",
      "price": {
        "salePrice": "4.99",
        "originalPrice": "9.99",
        "currencySymbol": "$",
        "currency": "USD"
      },
      "url": "https://www.etsy.com/listing/1807079985/personalized-wooden-birth-flower-garden",
      "image": "https://i.etsystatic.com/54214646/c/2250/2250/507/0/il/c7e8cf/6383044479/il_340x270.6383044479_jusd.jpg",
      "shopName": "Eddieenyshop",
      "...": "..."
    },
    {
      "title": "Wood Birth Flower Garden - Flower Decoration - Gifts for Mom - Custom Wood Gifts - Walnut Wood Art - Mother's Day Gift - Gifts for Her",
      "listingId": "1723837253",
      "price": {
        "salePrice": "8.10",
        "originalPrice": "9.00",
        "currencySymbol": "$",
        "currency": "USD"
      },
      "url": "https://www.etsy.com/listing/1723837253/wood-birth-flower-garden-flower",
      "image": "https://i.etsystatic.com/39476947/r/il/43089e/6180924868/il_340x270.6180924868_527y.jpg",
      "shopName": "TheCornerWay",
      "...": "..."
    },
    {
      "title": "Personalized Wood Birth Flower Garden, Custom Flower Decoration, Custom Wood Gift, Custom Mother's Day Gift, Valentine's Day Gifts",
      "listingId": "1784787032",
      "price": {
        "salePrice": "4.41",
        "originalPrice": "11.02",
        "currencySymbol": "$",
        "currency": "USD"
      },
      "url": "https://www.etsy.com/listing/1784787032/personalized-wood-birth-flower-garden",
      "image": "https://i.etsystatic.com/53526475/c/2252/2252/495/0/il/0658da/6342457097/il_340x270.6342457097_8scg.jpg",
      "shopName": "Perfecten10",
      "...": "..."
    },
    {
      "title": "Grandma Gift, Mom Birthday Gift, Personalized Gifts for Mom, Flower Pot Custom, Grandmas Garden, Birth Flower Mom Gifts from Daughter",
      "listingId": "1661356121",
      "price": {
        "salePrice": "8.95",
        "originalPrice": "17.90",
        "currencySymbol": "$",
        "currency": "USD"
      },
      "url": "https://www.etsy.com/listing/1661356121/grandma-gift-mom-birthday-gift",
      "image": "https://i.etsystatic.com/13777471/r/il/2fe138/6166878245/il_340x270.6166878245_rpfv.jpg",
      "shopName": "MiraGiftsWorld",
      "...": "..."
    },
    {
      "title": "Light Up Birth Flowers Print with Names | Mom's Garden | Grandma's Garden | Family Birth Month Flowers | Christmas gifts",
      "listingId": "1385407150",
      "price": {
        "salePrice": "30.40",
        "originalPrice": "38.00",
        "currencySymbol": "$",
        "currency": "USD"
      },
      "url": "https://www.etsy.com/listing/1385407150/light-up-birth-flowers-print-with-names",
      "image": "https://i.etsystatic.com/30455340/c/850/675/109/105/il/f01bbd/4929746593/il_340x270.4929746593_bi1o.jpg",
      "shopName": "CocoBananaDesigns",
      "...": "..."
    },
    {
      "title": "Personalized Garden Stone, Mothers Day Gifts for Grandma with Grandkid's Birth Flower Gift, Heart Shape - 6 inch SD-201",
      "listingId": "1702988504",
      "price": {
        "salePrice": "17.90",
        "originalPrice": "23.87",
        "currencySymbol": "$",
        "currency": "USD"
      },
      "url": "https://www.etsy.com/listing/1702988504/personalized-garden-stone-mothers-day",
      "image": "https://i.etsystatic.com/35958918/c/1886/1498/72/499/il/c79c47/5962141878/il_340x270.5962141878_958n.jpg",
      "shopName": "MonaLeahs",
      "...": "..."
    }
  ]
}
```



#### 3. **`GET /product/review`**
-   **Description**: This endpoint allows you to retrieve reviews for a specific product.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `listingId` | number | `-` | The unique identifier of the product listing. | Yes |
| `page` | number | `1` | The page number of the review results. | No |
| `currency` | string | `USD` | The currency code for pricing. | No |
| `language` | string | `en-US` | The language code for the description. | No |
| `country` | string | `US` | The country code for localization. | No |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/product/review?listingId=1215970085', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "data": {
    "reviewsCount": "11,648",
    "averageRating": "4.9693",
    "reviews": [
      {
        "rating": "5",
        "reviewText": "Fast delivery. Exactly as described. Beautiful for gifts",
        "reviewerName": "Aimee Brennan",
        "date": "Aimee Brennan Oct 30, 2024",
        "itemQuality": "5",
        "delivery": "",
        "...": "..."
      },
      {
        "rating": "5",
        "reviewText": "Great gift for Christmas!!!!  Can’t wait to put in the stocking!",
        "reviewerName": "kereen33",
        "date": "kereen33 Oct 30, 2024",
        "itemQuality": "5",
        "delivery": "",
        "...": "..."
      },
      {
        "rating": "5",
        "reviewText": "Such an amazing gift and my boyfriend loved it!",
        "reviewerName": "Angela Janelle Domingo",
        "date": "Angela Janelle Domingo Oct 30, 2024",
        "itemQuality": "5",
        "delivery": "",
        "...": "..."
      },
      {
        "rating": "5",
        "reviewText": "So excited to give these as gifts!",
        "reviewerName": "Meg  Chase",
        "date": "Meg  Chase Oct 30, 2024",
        "itemQuality": "5",
        "delivery": "",
        "...": "..."
      }
    ]
  }
}
```



#### 4. **`GET /product/review-photos`**
-   **Description**: This endpoint allows you to retrieve customer reviews along with photos for a specific product.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `listingId` | number | `-` | The unique identifier of the product listing. | Yes |
| `currency` | string | `USD` | The currency for pricing. | No |
| `language` | string | `en-US` | The language code for the description. | No |
| `country` | string | `US` | The country code for localization. | No |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/product/review-photos?listingId=1215970085', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "data": [
    {
      "imgUrl": "https://i.etsystatic.com/iap/318b88/6390424238/iap_640x640.6390424238_g94ecidy.jpg?version=0",
      "reviewText": "So excited to give these as gifts!",
      "rating": "5",
      "date": "Oct 30, 2024",
      "buyerName": "Meg  Chase",
      "listingUrl": "https://www.etsy.com/listing/1215970085/custom-air-freshener-picture-air?ref=ap-listing",
      "...": "..."
    },
    {
      "imgUrl": "https://i.etsystatic.com/iap/fe5d07/6428859327/iap_640x640.6428859327_d692wjv8.jpg?version=0",
      "reviewText": "So much fun and such a cute gift! Plus, they smell incredible! Highly recommend!!!!",
      "rating": "5",
      "date": "Oct 26, 2024",
      "buyerName": "sheila rapa",
      "listingUrl": "https://www.etsy.com/listing/1215970085/custom-air-freshener-picture-air?ref=ap-listing",
      "...": "..."
    },
    {
      "imgUrl": "https://i.etsystatic.com/iap/81061e/6428397967/iap_640x640.6428397967_nq58gpao.jpg?version=0",
      "reviewText": "Fantastic! Would definitely buy again!",
      "rating": "5",
      "date": "Oct 26, 2024",
      "buyerName": "Sign in with Apple user",
      "listingUrl": "https://www.etsy.com/listing/1215970085/custom-air-freshener-picture-air?ref=ap-listing",
      "...": "..."
    },
    {
      "imgUrl": "https://i.etsystatic.com/iap/8a7556/6376572670/iap_640x640.6376572670_2trgcfg9.jpg?version=0",
      "reviewText": "So fun!! Smells great!! Would make a great white elephant gift. If you want your car to smell good and some extra joy in your life, add this item to your cart.",
      "rating": "5",
      "date": "Oct 24, 2024",
      "buyerName": "ashlynf36",
      "listingUrl": "https://www.etsy.com/listing/1215970085/custom-air-freshener-picture-air?ref=ap-listing",
      "...": "..."
    },
    {
      "imgUrl": "https://i.etsystatic.com/iap/162a80/6424651771/iap_640x640.6424651771_s5qfwkdh.jpg?version=0",
      "reviewText": "I have been ranting and raving about my car freshener. I originally was only going to get my boyfriend on of me but then I decided I needed one too. It is so funny to see your loved one’s face hanging in the window. Especially if you’ve had a bad day. That little something is just another thing to bring joy to your life. \n\nThe quality is great! It was made and delivered really fast, and it smells great! I got the cashmere one and my boyfriend got the mahogany teakwood. Both smell great. \n\nIf you’re thinking about getting one made, do it. You will not regret it.",
      "rating": "5",
      "date": "Oct 24, 2024",
      "buyerName": "ashlynf36",
      "listingUrl": "https://www.etsy.com/listing/1215970085/custom-air-freshener-picture-air?ref=ap-listing",
      "...": "..."
    },
    {
      "imgUrl": "https://i.etsystatic.com/iap/94ad0b/6370841476/iap_640x640.6370841476_f5tcn5lt.jpg?version=0",
      "reviewText": "Amazing product! Came earlier than expected. Would order again!",
      "rating": "5",
      "date": "Oct 22, 2024",
      "buyerName": "Brittany Hill",
      "listingUrl": "https://www.etsy.com/listing/1215970085/custom-air-freshener-picture-air?ref=ap-listing",
      "...": "..."
    },
    "..."
  ]
}
```



#### 5. **`GET /product/bycollection`**
-   **Description**: This endpoint retrieves a collection containing the requested listing.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `listingId` | number | `undefined` | The unique identifier of the product listing. | Yes |
| `currency` | string | `USD` | The currency for pricing. | No |
| `language` | string | `en-US` | The language code for the description. | No |
| `country` | string | `US` | The country code for localization. | No |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/product/bycollection?listingId=1215970085', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "data": [
    {
      "id": 141923929,
      "creatorId": 984365245,
      "slug": "loved",
      "rank": 1,
      "score": 0.9169846773147583,
      "listings": [
        {
          "listingId": 1215970085,
          "title": "Custom Air Freshener, Picture Air Freshener, Cute Car Accessories, Photo Freshener, Car Freshies, Car Decor, Custom Gift, Personalized Gift",
          "imgSrc": "https://i.etsystatic.com/35332887/c/1923/1923/0/77/il/e41fa0/5469863166/il_300x300.5469863166_6sgn.jpg",
          "price": 12.95,
          "currency": "USD",
          "shopId": 35332887,
          "...": "..."
        },
        {
          "listingId": 1574739607,
          "title": "Personalized Plant Car Hanging Accessories, Cute Crochet Flower Car Ornament, Custom Gift Idea for Succulent Plant Lovers",
          "imgSrc": "https://i.etsystatic.com/46146142/c/2000/2000/0/0/il/aa4b9d/5389842977/il_300x300.5389842977_5ztk.jpg",
          "price": 11.96,
          "currency": "USD",
          "shopId": 46146142,
          "...": "..."
        },
        {
          "listingId": 1667724839,
          "title": "Car Coasters, Set of 2 Car Floral Coasters, Cute Car Accessories, Cup Holder Coasters, Preppy Retro Smiley Daisy Checker Car Coasters",
          "imgSrc": "https://i.etsystatic.com/49756982/r/il/adf3b4/6361628250/il_300x300.6361628250_sdo2.jpg",
          "price": 9,
          "currency": "USD",
          "shopId": 49756982,
          "...": "..."
        },
        {
          "listingId": 1741790697,
          "title": "Car Charms | Hanging | Rearview Mirror | Silicone Beaded | Wood Charms | Custom Engraved | Car Accessories | Cute Gift Ideas | Funny | Love",
          "imgSrc": "https://i.etsystatic.com/33368294/c/3000/3000/0/0/il/4d1cd3/6083404653/il_300x300.6083404653_6qbw.jpg",
          "price": 13.5,
          "currency": "USD",
          "shopId": 33368294,
          "...": "..."
        }
      ]
    },
    {
      "id": 140996212,
      "creatorId": 980453910,
      "slug": "car",
      "rank": 2,
      "score": 0.904538631439209,
      "listings": [
        {
          "listingId": 1215970085,
          "title": "Custom Air Freshener, Picture Air Freshener, Cute Car Accessories, Photo Freshener, Car Freshies, Car Decor, Custom Gift, Personalized Gift",
          "imgSrc": "https://i.etsystatic.com/35332887/c/1923/1923/0/77/il/e41fa0/5469863166/il_300x300.5469863166_6sgn.jpg",
          "price": 12.95,
          "currency": "USD",
          "shopId": 35332887,
          "...": "..."
        },
        {
          "listingId": 1682798443,
          "title": "Pearl Pink Bow Disco Car Accessories l Y2K Rear View Mirror Car Decor l Coquette Disco Car Decor l Cute Pink Bow Disco Car Charm l Groovy",
          "imgSrc": "https://i.etsystatic.com/29725047/c/967/967/57/136/il/3e1f5d/5786090984/il_300x300.5786090984_qrba.jpg",
          "price": 9.49,
          "currency": "USD",
          "shopId": 29725047,
          "...": "..."
        },
        {
          "listingId": 1740796438,
          "title": "Coquette Cherry Car Accessories for Women/ Cherry Car Suncatcher/Car Mirror Hanging Suncatcher/Hippie Car Accessory/Cute Car Decor/Car Charm",
          "imgSrc": "https://i.etsystatic.com/28089129/r/il/f6bb5d/6141925493/il_300x300.6141925493_1ts3.jpg",
          "price": 17.1,
          "currency": "USD",
          "shopId": 28089129,
          "...": "..."
        },
        {
          "listingId": 1599659187,
          "title": "Mystic Pearl Car Charm - car accessory - rearview mirror decor - cute boho accessory - yin yang 8 ball pearl - gifts for her",
          "imgSrc": "https://i.etsystatic.com/43067577/c/2250/2250/0/581/il/42eeea/5516798355/il_300x300.5516798355_e75v.jpg",
          "price": 12,
          "currency": "USD",
          "shopId": 43067577,
          "...": "..."
        }
      ]
    },
    {
      "id": 131975252,
      "creatorId": 108561463,
      "slug": "car",
      "rank": 3,
      "score": 0.9007945656776428,
      "listings": [
        {
          "listingId": 1215970085,
          "title": "Custom Air Freshener, Picture Air Freshener, Cute Car Accessories, Photo Freshener, Car Freshies, Car Decor, Custom Gift, Personalized Gift",
          "imgSrc": "https://i.etsystatic.com/35332887/c/1923/1923/0/77/il/e41fa0/5469863166/il_300x300.5469863166_6sgn.jpg",
          "price": 12.95,
          "currency": "USD",
          "shopId": 35332887,
          "...": "..."
        },
        {
          "listingId": 1225313741,
          "title": "Air Freshener: Smiley Flower Green   | Car Air Freshener | Hanging Car Diffuser | Car Charm",
          "imgSrc": "https://i.etsystatic.com/22947528/c/2000/2000/0/0/il/b0dbff/3895251835/il_300x300.3895251835_tehr.jpg",
          "price": 8.25,
          "currency": "USD",
          "shopId": 22947528,
          "...": "..."
        },
        {
          "listingId": 1666977144,
          "title": "Trendy Cutie Air Freshener | Preppy Felt Freshie | Girly Car Accessories | Stocking Stuffer | Girly Car Accessories | Gifts for Girls",
          "imgSrc": "https://i.etsystatic.com/21569381/r/il/db1d18/5821569861/il_300x300.5821569861_ig2x.jpg",
          "price": 10.49,
          "currency": "USD",
          "shopId": 21569381,
          "...": "..."
        },
        {
          "listingId": 1702059525,
          "title": "Mama Car Freshie | Mama gift | Mama car",
          "imgSrc": "https://i.etsystatic.com/41574725/r/il/74874a/5915070665/il_300x300.5915070665_trdw.jpg",
          "price": 12.75,
          "currency": "USD",
          "shopId": 41574725,
          "...": "..."
        }
      ]
    },
    {
      "id": 131554962,
      "creatorId": 238771889,
      "slug": "car-accessories",
      "rank": 4,
      "score": 0.900619626045227,
      "listings": [
        {
          "listingId": 1215970085,
          "title": "Custom Air Freshener, Picture Air Freshener, Cute Car Accessories, Photo Freshener, Car Freshies, Car Decor, Custom Gift, Personalized Gift",
          "imgSrc": "https://i.etsystatic.com/35332887/c/1923/1923/0/77/il/e41fa0/5469863166/il_300x300.5469863166_6sgn.jpg",
          "price": 12.95,
          "currency": "USD",
          "shopId": 35332887,
          "...": "..."
        },
        {
          "listingId": 1666337410,
          "title": "Mini Personalized  Resin Photo Car Vent Clip, Anniversary/couples Gift, Picture Car Accessory, mini Car Air Vent Clip, Vent, Car Decor",
          "imgSrc": "https://i.etsystatic.com/24445070/r/il/48d9c3/5818644175/il_300x300.5818644175_pra9.jpg",
          "price": 9.99,
          "currency": "USD",
          "shopId": 24445070,
          "...": "..."
        },
        {
          "listingId": 1064699469,
          "title": "CarChap upright Lip Balm Holder (the Original, PatentPending) Chapstick remains mess free in heat, featured in Car&Driver, FREE US SHIPPING",
          "imgSrc": "https://i.etsystatic.com/31327660/r/il/ab99ce/5160696174/il_300x300.5160696174_ltaf.jpg",
          "price": 8.99,
          "currency": "USD",
          "shopId": 31327660,
          "...": "..."
        },
        {
          "listingId": 1547568531,
          "title": "Clay Stone Diffuser Car Vent Clip | Passive essential oil diffuser makes for a great car charm and cute car accessories for women",
          "imgSrc": "https://i.etsystatic.com/12117109/c/1123/1123/0/0/il/ab5b5e/5249934137/il_300x300.5249934137_1dm5.jpg",
          "price": 3.49,
          "currency": "USD",
          "shopId": 12117109,
          "...": "..."
        }
      ]
    }
  ]
}
```



#### 6. **`GET /product/description`**
-   **Description**: This endpoint allows you to retrieve the description of a specific product.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `listingId` | number | `undefined` | The unique identifier of the product listing. | Yes |
| `currency` | string | `USD` | The currency for pricing. | No |
| `language` | string | `en-US` | The language code for the description. | No |
| `country` | string | `US` | The country code for localization. | No |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/product/description?listingId=1301638116', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "data": {
    "title": "14K Solid Gold Family Birthstone Necklace, Birthstone Gift, Christmas Gift, Bridesmaid Gift, Gift for Mom, Birthday Gift, Birthstone Jewelry",
    "productId": "1301638116",
    "gtin": "n/a",
    "description": "Silver Birthstone Necklace, Personalized Gifts, 14k Solid Gold Birthstone Jewelry, Family Necklace For Grandmothers, Christmas Gift, Best Gifts for Mothers, Personalized Birthstone Necklace, Family Birthstone Necklace, Birthstone Gift, Dainty Necklace, Gift For Her, Birthday Gift\n\n☆ Back to my store for more options: https://www.etsy.com/shop/aceelegance    \n\n☆ All the pieces you purchased from AceElegance come with a Certificate of Authenticity(925 Sterling \n\nSilver, 8k Solid Gold, 14k Solid Gold, 18k Solid Gold)\n\n☆ www.aceelegance.com ☆\n\n\n► 14k Solid Gold Birthstone Necklace\n\n• Material: High Quality 925 Sterling Silver, 8k Solid Gold, 14k Solid Gold, 18k Solid Gold\n\n• Colors: Gold-plated(it is micron gold plated, and it never tarnishes) ∙ Silver(original silver color) ∙ Rose(rose gold-plated)\n\n• All our jewelry is custom-made by hand with care in our workshop \n\n\n► H O W  T O  O R D E R\n\n• 1-Select the material and the color from the dropdown.\n\n• 2-Select the necklace length.\n\n• 3- Please select the correct number of birthstones in the dropdown. Otherwise, your order may be canceled.\n\nPlease specify the birthstone you want from left to right in order. Example: July-June-August.\n\n• 4- Please let us know if you need help with your order.\n\n\n► O T H E R • I N F O R M A T I O N\n\n• All items are nicely packaged and ready to gift in elegant jewelry boxes. \n\n• If you can&#39;t find the information or need some advice for your design? Feel free to contact us. We are fast to reply :) \n\n• Nickel Free\n\n• Tarnish Resistant  \n\n\n► R E T U R N S • A N D • E X C H A N G E S\n \n• We gladly accept cancellations \n\n• Please request your cancellation before the item is shipped.\n\n• We don&#39;t accept returns or exchanges on jewelry unless the fault was ours. We know that these products can be essential for you, so if you have an issue with your piece, please do not hesitate to contact us, and we can solve the problem.\n\n\n► A D J U S T M E N T S\n\n• If you didn&#39;t order the correct size or your jewelry doesn&#39;t fit, we offer a resizing or adjustment service; an additional fee might be applied.\n\n\n► L O S T • I N • T H E • M A I L\n\n• All packages are insured for up to $700, so if you have any problem receiving your product, please email or leave a message through the ETSY and we will start the remaking process again.\n\n\n► P A Y M E N T\n\n• We accept all credit cards and ETSY gift cards.\n\n\n► S H I P P I N G • P R O C E S S\n\n• Our estimated delivery time is around three days processing time and 4-8 days delivery (usually less) worldwide upon ordering. Every item we create is custom-made and personalized and well worth the wait.",
    "images": [
      "https://i.etsystatic.com/27808603/r/il/17eff8/4476872409/il_fullxfull.4476872409_hru6.jpg",
      "https://i.etsystatic.com/27808603/r/il/dd8d66/4292154829/il_fullxfull.4292154829_7ikv.jpg",
      "https://i.etsystatic.com/27808603/r/il/0ba591/4244514176/il_fullxfull.4244514176_fm31.jpg",
      "https://i.etsystatic.com/27808603/r/il/abc9bc/4292145011/il_fullxfull.4292145011_thdf.jpg",
      "https://i.etsystatic.com/27808603/r/il/437a18/4244514104/il_fullxfull.4244514104_p33j.jpg",
      "https://i.etsystatic.com/27808603/r/il/92629e/4244514166/il_fullxfull.4244514166_6kke.jpg",
      "..."
    ],
    "price": {
      "salePrice": "14.67",
      "originalPrice": "26.67",
      "currency": "$",
      "discount": "45% off"
    },
    "...": "..."
  }
}
```



#### 7. **`GET /product/available`**
-   **Description**: This endpoint checks the availability of a specific product.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `listingId` | number | `undefined` | The unique identifier of the product listing. | Yes |
| `currency` | string | `USD` | The currency for pricing. | No |
| `language` | string | `en-US` | The language code for the description. | No |
| `country` | string | `US` | The country code for localization. | No |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/product/available?listingId=1301638116', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "message": "Endpoint '/product/available' does not exist"
}
```



#### 8. **`GET /product/faq`**
-   **Description**: This endpoint retrieves FAQs for a specific product.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `listingId` | number | `undefined` | The unique identifier of the product listing. | Yes |
| `currency` | string | `USD` | The currency for pricing. | No |
| `language` | string | `en-US` | The language code for the description. | No |
| `country` | string | `US` | The country code for localization. | No |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/product/faq?listingId=1301638116', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "message": "Endpoint '/product/faq' does not exist"
}
```


### shop/(stores)


#### 1. **`GET /shop/info`**
-   **Description**: This endpoint retrieves information about a shop based on provided parameters.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `shopId` | string | `undefined` | The ID of the shop. | Yes |
| `currency` | string | `undefined` | The currency code for pricing. Acceptable currency codes are: `USD`, `CAD`, `EUR`, `GBP`, `AUD`, `JPY`, `CNY`, `CZK`, `DKK`, `HKD`, `HUF`, `INR`, `IDR`, `ILS`, `MYR`, `MXN`, `MAD`, `NZD`, `NOK`, `PHP`, `SGD`, `VND`, `ZAR`, `SEK`, `CHF`, `THB`, `TWD`, `TRY`, `PLN`, `BRL`. | No |
| `language` | string | `undefined` | The language code for localization. Acceptable language codes are: `de`, `en-GB`, `en-IN`, `en-US`, `es`, `fr`, `it`, `ja`, `nl`, `pl`, `pt`, `ru`. | No |
| `country` | string | `undefined` | The country code for localization. Acceptable country codes include `AF`, `AX`, `AL`, `DZ`, `AS`, `AD`, `AO`, `AI`, `AG`, `AR`, `AM`, `AW`, `AU`, `AT`, `AZ`, and many more | No |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/shop/info?shopId=MijMojDesign', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "data": {
    "coverPhotos": [
      {
        "coverPhoto": "https://i.etsystatic.com/ishbcc/d2dfb2/4603139464/ishbcc_420x420.4603139464_4ihzqs5o.jpg?version=0"
      },
      {
        "coverPhoto": "https://i.etsystatic.com/ishbcc/e72177/5384942959/ishbcc_420x420.5384942959_nf3p6bpv.jpg?version=0"
      },
      {
        "coverPhoto": "https://i.etsystatic.com/ishbcc/ef4272/5384936651/ishbcc_420x420.5384936651_e23kvjmb.jpg?version=0"
      },
      {
        "coverPhoto": "https://i.etsystatic.com/ishbcc/cf19ce/5336772182/ishbcc_420x420.5336772182_nrmw5r5n.jpg?version=0"
      }
    ],
    "shopName": "MijMojDesign",
    "shortDescription": "Hand Crafted Personalised Gifts made in the UK",
    "shopLocation": "Flint, United Kingdom",
    "isStarSeller": true,
    "salesCount": "49,151",
    "...": "..."
  }
}
```



#### 2. **`GET /shop/products`**
-   **Description**: This endpoint retrieves products from a specific shop on Etsy's platform.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `shopName` | string | `undefined` | The name of the shop. | Yes |
| `page` | number | `undefined` | The page number of the product results. | No |
| `perPage` | number | `undefined` | The number of products per page. | No |
| `currency` | string | `undefined` | The currency for pricing. | No |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/shop/products?shopName=AceElegance', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "message": "Request failed with status code 400"
}
```



#### 3. **`GET /shop/review`**
-   **Description**: This endpoint retrieves reviews for a shop on Etsy's platform.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `shopName` | string | `undefined` | The name of the shop. | Yes |
| `page` | number | `undefined` | The page number of the review results. | No |
| `perPage` | number | `undefined` | The number of reviews per page. | No |
| `currency` | string | `undefined` | The currency for pricing. Acceptable currency codes are: `USD`, `CAD`, `EUR`, `GBP`, `AUD`, `JPY`, `CNY`, `CZK`, `DKK`, `HKD`, `HUF`, `INR`, `IDR`, `ILS`, `MYR`, `MXN`, `MAD`, `NZD`, `NOK`, `PHP`, `SGD`, `VND`, `ZAR`, `SEK`, `CHF`, `THB`, `TWD`, `TRY`, `PLN`, `BRL`. | No |
| `language` | string | `undefined` | The language code for the description. Acceptable language codes `de`, `en-GB`, `en-IN`, `en-US`, `es`, `fr`, `it`, `ja`, `nl`, `pl`, `pt`, `ru`. | No |
| `country` | string | `undefined` | The country code for localization. Acceptable country codes are: `AF`, `AX`, `AL`, `DZ`, `AS`, `AD`, `AO`, `AI`, `AG`, `AR`, `AM`, `AW`, `AU`, `AT`, `AZ`, `BS`, `BH`, `BD`, `BB`, `BE`, `BZ`, `BJ`, `BM`, `BT`, `BO`, `BA`, `BW`, `BV`, `BR`, `IO`, `VG`, `BN`, `BG`, `BF`, `BI`, `KH`, `CM`, `CA`, `CV`, `KY`, `CF`, `TD`, `CL`, `CN`, `CX`, `CC`, `CO`, `KM`, `CG`, `CK`, `CR`, `HR`, `CW`, `CY`, `CZ`, `DK`, `DJ`, `DM`, `DO`, `EC`, `EG`, `SV`, `GQ`, `ER`, `EE`, `ET`, `FK`, `FO`, `FJ`, `FI`, `FR`, `GF`, `PF`, `TF`, `GA`, `GM`, `GE`, `DE`, `GH`, `GI`, `GR`, `GL`, `GD`, `GP`, `GU`, `GT`, `GG`, `GN`, `GW`, `GY`, `HT`, `HM`, `VA`, `HN`, `HK`, `HU`, `IS`, `IN`, `ID`, `IQ`, `IE`, `IM`, `IL`, `IT`, `CI`, `JM`, `JP`, `JE`, `JO`, `KZ`, `KE`, `KI`, `XK`, `KW`, `KG`, `LA`, `LV`, `LB`, `LS`, `LR`, `LY`, `LI`, `LT`, `LU`, `MO`, `MK`, `MG`, `MW`, `MY`, `MV`, `ML`, `MT`, `MH`, `MQ`, `MR`, `MU`, `YT`, `MX`, `FM`, `MD`, `MC`, `MN`, `ME`, `MS`, `MA`, `MZ`, `MM`, `NA`, `NR`, `NP`, `AN`, `NC`, `NZ`, `NI`, `NE`, `NG`, `NU`, `NF`, `MP`, `NO`, `OM`, `PK`, `PW`, `PS`, `PA`, `PG`, `PY`, `PE`, `PH`, `PL`, `PT`, `PR`, `QA`, `RE`, `RO`, `RW`, `SH`, `KN`, `LC`, `MF`, `PM`, `VC`, `WS`, `SM`, `ST`, `SA`, `SN`, `RS`, `SC`, `SL`, `SG`, `SX`, `SK`, `SI`, `SB`, `SO`, `ZA`, `GS`, `KR`, `SS`, `ES`, `LK`, `SD`, `SR`, `SJ`, `SZ`, `SE`, `CH`, `TW`, `TJ`, `TZ`, `TH`, `NL`, `TL`, `TG`, `TK`, `TO`, `TT`, `TN`, `TR`, `TM`, `TC`, `TV`, `UG`, `UA`, `AE`, `GB`, `US`, `UM`, `UY`, `VI`, `UZ`, `VU`, `VE`, `VN`, `WF`, `EH`, `YE`, `CD`, `ZM`, `ZW`. | No |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/shop/review?shopName=AceElegance', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "data": [
    {
      "userImage": "https://i.etsystatic.com/iusa/2f218a/111470419/iusa_75x75.111470419_ej23.jpg?version=0",
      "userName": "Shelby",
      "date": "Oct 31, 2024",
      "rate": "5",
      "description": "It took a few days later to ship than expected but arrived quickly when it did. Turned out wonderful and came in a beautiful hand crafted wood box",
      "productImage": "https://i.etsystatic.com/4049421915/r/il/59fdf4/4049421915/il_170x135.4049421915_efxz.jpg",
      "...": "..."
    },
    {
      "userImage": "https://i.etsystatic.com/iusa/1bbba1/87366790/iusa_75x75.87366790_g7o9.jpg?version=0",
      "userName": "Katie",
      "date": "Oct 31, 2024",
      "rate": "5",
      "description": "The packaging is absolutely beautiful!",
      "productImage": "https://i.etsystatic.com/4476872409/r/il/17eff8/4476872409/il_170x135.4476872409_hru6.jpg",
      "...": "..."
    },
    {
      "userImage": "https://i.etsystatic.com/iusa/4e14e2/109525221/iusa_75x75.109525221_il63.jpg?version=0",
      "userName": "Mckenzie",
      "date": "Oct 31, 2024",
      "rate": "5",
      "description": "Worth the purchase. Thank you",
      "productImage": "https://i.etsystatic.com/4244514176/r/il/0ba591/4244514176/il_170x135.4244514176_fm31.jpg",
      "...": "..."
    },
    {
      "userImage": "https://i.etsystatic.com/site-assets/images/avatars/default_avatar.png?width=75",
      "userName": "Sign in with Apple user",
      "date": "Oct 30, 2024",
      "rate": "5",
      "description": "Great gift very good quality",
      "productImage": "https://i.etsystatic.com/4049421915/r/il/59fdf4/4049421915/il_170x135.4049421915_efxz.jpg",
      "...": "..."
    },
    {
      "userImage": "https://i.etsystatic.com/site-assets/images/avatars/default_avatar.png?width=75",
      "userName": "samalexandra",
      "date": "Oct 30, 2024",
      "rate": "5",
      "description": "This is such a lovely necklace, exactly what I wanted and really good quality. I also really like the little wooden box it came in and the flowers are a great touch. Very fast shipping to the UK.",
      "productImage": "https://i.etsystatic.com/3500835501/r/il/f69c28/3500835501/il_170x135.3500835501_o15f.jpg",
      "...": "..."
    },
    {
      "userImage": "https://i.etsystatic.com/iusa/71c2f5/100636705/iusa_75x75.100636705_ni45.jpg?version=0",
      "userName": "Aimee",
      "date": "Oct 29, 2024",
      "rate": "4",
      "description": "Really pretty ring! I have short fingers and this ring is so dainty it doesn’t look strange on my hand.",
      "productImage": "https://i.etsystatic.com/4460879683/r/il/2beb81/4460879683/il_170x135.4460879683_tuea.jpg",
      "...": "..."
    },
    "..."
  ]
}
```



#### 4. **`GET /seller/info`**
-   **Description**: This endpoint retrieves information about a seller on Etsy's platform.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `sellerId` | number | `undefined` | The unique identifier of the seller. | Yes |


Example request:
```javascript
fetch('https://etsy-api2.p.rapidapi.com/seller/info?sellerId=28297834', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'etsy-api2.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "data": {
    "isTrader": true,
    "address": "",
    "shortAddress": "",
    "formattedAddressString": "",
    "isBusiness": true,
    "businessRegistrationNumber": "2447959",
    "...": "..."
  }
}
```



## Error Handling
The API returns standard HTTP status codes to indicate the success or failure of API requests. Below are common errors and suggestions for handling them.

|Status Code|Message|Description|Suggested Handling|
|--|--|--|--|
| **400** | Bad Request | The request was malformed or missing required parameters (e.g., `domain` parameter not provided). | Verify that all required parameters are included and correctly formatted. |
| **401** | Unauthorized | Invalid or missing API key in the request headers. | Check that a valid API key is included in `x-rapidapi-key`. |
| **403** | Forbidden | Access to the requested resource is denied, possibly due to rate limits or restricted access. | Review rate limits and ensure API permissions. Retry after a delay if the rate limit is exceeded. |
| **404** | Not Found | The requested domain information could not be found (e.g., domain does not exist). | Check the spelling or availability of the domain. |
| **429** | Too Many Requests | The API rate limit has been exceeded. | Implement rate-limiting logic and retry after the specified rate limit reset time. |
| **500** | Internal Server Error | A server error occurred while processing the request. | Retry the request after a few seconds. If the error persists, contact API support. |
| **503** | Service Unavailable | The API service is temporarily unavailable (e.g., due to maintenance). | Retry the request later or check the API status page for maintenance alerts. |
