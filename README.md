## Publish your food product data as open data

OpenFoodFacts.org is an open datastore with over half a million products, their ingredients and their imagery.

If you are a producer of food, public health authority or food standards body, you too can publish open data.

### Licensing

The recommended license for open database content is (ODBL)[https://opendatacommons.org/licenses/odbl/] - conceptually very similar to Creative Commons, expressly designed for databases.

### Schema
 * barcode - required
 * product name - required
 * quantity
 * ingredients_description
 * product_image_front_url
 * product_image_ingredients_url
 * product_image_nutrition_facts_url

### Formats
JSON and CSV are the recommended publishing formats. Given openfoodfacts.org is an international project, the recommended filenaming convention is to put the ISO 639‑1 (TODO: Check this) language code in the filename:
```
products.en.csv
products.en-AU.json
```

#### Example JSON

#### Example CSV
