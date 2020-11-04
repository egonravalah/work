**Test work**

**Step 1 - Tooling**
Set up a docker-compose file that provides the following:

- a PostgreSQL database
- a container running a web service

**Step 2 - Architecture**
Pick a web framework to implement a simple web service that will contain:

- a few JSON API endpoints
- a single endpoint returning an HTML page (optional)
- a connection to the postgres database

**Step 3 - Data model**
Design all necessary data models to store the following items in the PostgreSQL database for a flower store (the minimum desired attributes are listed):

- Products (flowers):

- - Name
  - Stock
  - Price

- Orders

- - Time when the order was made
  - Product ordered
  - Quantity ordered
  - Order line subtotal at the time of ordering
  - Order total at the time of ordering

**Step 4 - Mock data**
Design a mock data generator that:

- Can be executed from the command line inside the container
- Generates at least 20 products in the database with varying prices and stocks
- Generates at least 50 orders in the database with varying quantities and products

**Step 5 - APIs**
The web service should provide the following APIs that return a JSON response:

- List of all products (in paginated manner)

- - inputs: page number, page size
  - outputs: list of product objects

- List of all orders (in paginated manner)

- - inputs: page number, page size
  - outputs: list of order objects

- Finds related products given a product identifier

- - inputs: unique identifier of a product
  - outputs: other products that have been purchased alongside the given product
  - detail: order the results by popularity, where popularity is defined by the number of times a product has been purchased (not the quantity of the product in any given order)

**Step 6 - User interface or documentation**
Provide a single HTML endpoint that allows testing of the above APIs or documentation for calling the APIs defined in the previous section with a tool such as curl.
