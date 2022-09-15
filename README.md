# E-commerce Back End

## User Story

AS A manager at an internet retail company  
I WANT a back end for my e-commerce website that uses the latest technologies  
SO THAT my company can compete with other e-commerce companies

## Acceptance Criteria

GIVEN a functional Express.js API  
WHEN I add my database name, MySQL username, and MySQL password to an environment variable file  
THEN I am able to connect to a database using Sequelize  
WHEN I enter schema and seed commands  
THEN a development database is created and is seeded with test data  
WHEN I enter the command to invoke the application  
THEN my server is started and the Sequelize models are synced to the MySQL database  
WHEN I open API GET routes in Insomnia for categories, products, or tags  
THEN the data for each of these routes is displayed in a formatted JSON  
WHEN I test API POST, PUT, and DELETE routes in Insomnia  
THEN I am able to successfully create, update, and delete data in my database

## Mock-ups

The following animations shows examples of the apps API routes being tested in insomnia

- This animation shows GET routes to return all categories, all products and all tags being tested  
  <img src="./assets/img/13-orm-homework-demo-01.gif" width="500"/>  

- This animation shows GET routes to return a single category, a single product and a single tag being tested  
  <img src="./assets/img/13-orm-homework-demo-02.gif" width="500"/>  

- This animation shows the POST, PUT, and DELETE routes for categories being tested  
  <img src="./assets/img/13-orm-homework-demo-03.gif" width="500"/>

## Database Models

### Category

    id
        * Int
        * Null = false
        * pk
        * autoInc
    category_name
        * String
        * Null = false

### Product

    id
        * Int
        * Null = false
        * pk
        * autoInc
    product_name
        * string
        * null = false
    price
        * Decimal
        * null = false
        * validate that it's a decimal
    stock
        * integer
        * null = false
        * default = 10
        * validates is number
    category_id
        * Integer
        * fk = category.id

### Tag

    id
        * Int
        * Null = false
        * pk
        * autoInc
    tag_name
        * String

### ProductTag

    id
        * Int
        * Null = false
        * pk
        * autoInc
    product_id
        * Integer
        * fk = product.id
    tag_id
        * Integer
        * fk = tag.id

## Associations

Product belongs to Category, as a category can have multiple products but a product can only belong to one category.

Category has many Product models.

Product belongs to many Tag models. Using the ProductTag through model, allow products to have multiple tags and tags to have many products.

Tag belongs to many Product models.

## Link to Video demo

[Google Drive Link](https://drive.google.com/file/d/1Qo3b5VFsOWYn94VP_p7A22FUJiOCWt19/view?usp=sharing "Module 13 Demo Video")
