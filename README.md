## Publish your food product data as open data

OpenFoodFacts.org is an open datastore with over half a million products, their ingredients and their imagery.

If you are a producer of food, public health authority or food standards body, you too can publish open data.

### Licensing

The recommended license for open database content is [ODBL](https://opendatacommons.org/licenses/odbl/) - conceptually very similar to Creative Commons, expressly designed for databases.

### Schema (v0.1)

#### Required data
An OpenFoodFacts.org listing is a subclass of [schema.org/Product](http://schema.org/Product)
 * gtin14	- required - The GTIN-14 (barcode) code of the product.
 * name - required - Product name, excluding brand
 
#### Optional data
 * brand - the primary [schema.org/brand](http://schema.org/brand)
 * quantity - a string containing the units (Example: 350 g, 1 L)
 * ingredients_description - A textual ingredients description as per food labelling standards. Where possible, allegens can be highlighted with the use of underscores.
 * product_official_url - A link to an official product page.
 * product_image_front_url - A link to an official product image, for use under the ODBL.
 * product_image_ingredients_url - A link to an official product image with ingredient text, for use under the ODBL.
 * product_image_nutrition_facts_url - A link to an official product image with the nutrition facts, for use under the ODBL.

### Formats
JSON and CSV are the recommended publishing formats. Given openfoodfacts.org is an international project, the recommended filenaming convention is to put the RFC 5646 language code in the filename:
```
products.en.csv
products.en-AU.json
```

#### Example JSON

#### Example CSV
