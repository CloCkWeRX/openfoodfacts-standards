## Publish your food product data as open data

OpenFoodFacts.org is an open datastore with over half a million products, their ingredients and their imagery.

If you are a producer of food, public health authority or food standards body, you too can publish open data.

### Benefits
By sharing your data, you help consumers, product distributors, health authorities and more.

Product distributors - OpenFoodFacts data is available for e-commerce vendors, making it trivial to provide high quality product imagery.

Consumers - Customers with allergies, dietary or ethical preferences can find your products; and readily assess them with a mobile device

Health authorities - Many national food standards bodies conduct research and evaluation of the food supply chain, by publishing your data openly you contibute to public health research

### Licensing

The recommended license for open database content is [ODBL](https://opendatacommons.org/licenses/odbl/) - conceptually very similar to Creative Commons, expressly designed for databases.

### Schema (v0.1)

#### Required data
An OpenFoodFacts.org listing is a subclass of [schema.org/Product](http://schema.org/Product)
 * gtin13	- required - The EAN-13/GTIN-13 (barcode) code of the product.
 * name - required - Product name, excluding brand
 * off:country_where_sold - required - the primary country where this food product is sold, ie ```Australia```

#### Optional data
 * brand - the primary [schema.org/brand](http://schema.org/brand)
 * off:quantity - a string containing the units (Example: 350 g, 1 L)
 * off:ingredients_description - A textual ingredients description as per food labelling standards. Where possible, allegens can be highlighted with the use of underscores.
 * url - A link to an official product page.
 * image - A link to an official product [image](http://schema.org/image), for use under the ODBL.
 * off:product_image_ingredients_url - A link to an official product image with ingredient text, for use under the ODBL.
 * off:product_image_nutrition_facts_url - A link to an official product image with the nutrition facts, for use under the ODBL.
 * off:labels_and_certifications - A comma delimited list of labels or certifications, such as ```Vegetarian,Halal```
 * off:ingredients_country_of_origin - The primary country where ingredients where sourced from
 * off:country_of_manufacture - The primary country where the product was manufactured

### Imagery guidance


### Formats
CSV and JSON-LD are the recommended publishing formats, depending on your use case.

CSV is good for bulk data extracts and singular values.

JSON-LD is good for publishing your content for individual items, allowing both Google and OpenFoodFacts.org to retrieve them.
When publishing with JSON-LD, a sitemap (list of URLs) is required.

#### CSV
Given openfoodfacts.org is an international project, the recommended filenaming convention is to put the RFC 5646 language code in the filename:
```
0.1-products.en.csv
```

##### Example data
```
gtin13,name,off:country_where_sold
"9310092000422","Apricot Nectar Fruit Drink","Australia"
```
#### Example JSON (JSON-LD)
Use https://search.google.com/structured-data/testing-tool/u/0/ to check your data

See https://developers.google.com/search/docs/guides/create-URLs for sitemap creation

```
{
  "@context": {
     "@language": "en", 
     "@vocab": "http://schema.org",
     "off": "http://openfoodfacts/schema/0.1/#"
   },
  "@type": "Product",
  "additionalType": "off:OpenFoodFactsListing",
  "gtin13": "9310092000422",
  "name": "Apricot Nectar Fruit Drink",
  "image": "front.jpg",
  "off:country_where_sold": "Australia"
}
```

### How can I get my data imported?
Raise an [issue via github](https://github.com/openfoodfacts/openfoodfacts-server/issues) linking to your data in either CSV or JSON-LD+Sitemap format.
