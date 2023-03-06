# Java Training
*This is the project I completed as part of my training to become a Java QA Automation Engineer within the company.*

## Topics & Tasks List:
## 1. Maven
### Task #1
While going through this training you will develop console online store application. Each next task will append some functionality or flexibility to it.

Before starting our implementation of `OnlineStore`, we need to prepare project structure and set up dependency manager. To handle our project dependencies and source code build we will use Maven.

Please create multi-module `Maven` project, with such modules:
- parent (this is general store module)
- domain
- store
- consoleApp

## 2. OOP
### Task #2
Store functionality should be based on Object Oriented Programming principles. Classes to create:

- `Product` with attributes such as [name, rate, price]
- `Category` classes with the name attribute, for each store category [bike, phone, milk] and `products list`
- `Store` - class that should handle `category list`
- `RandomStorePopulator` - utility class that will populate our store/category with fake data using `Faker` lib
- `StoreApp` - class with main method to execute our store scenario. When invoking main method, application should init store with categories and products and pretty print this data. Also, categories should be read dynamically (at runtime), from base category package using `Reflections` lib.

## 3. Collections
### Task #3
Starting to extend our store. Append ability of user to interact with our store, while sending commands through read stream. Add support of such commands:

- `sort` - products from store according to config. In resources folder create `xml config file` like:
```
<sort>
    <name>asc</name>
    <price>asc</price>
    <rate>desc</rate>
</sort>
```
`Config` file can contain from 1 to n fields. Sorting should be done using `Comparator`. Sort and print should not modify default store product lists and their order.
- `top` - print top 5 products of whole store sorted via price desc
- `quit` - exit app

## 4. Design Patterns
### Task #4
Read all materials, try to find a proper place for your newly learned patterns in our app. There are a lot of design patterns, but we advise you to pay attention to the following ones:
- Singleton
- Chain of Responsibility
- Factory

The application of patterns consists not only in their implementation, but also in knowing their weaknesses and strengths. Therefore, in addition to realising the selected design patterns in the code, you must write the following justification for each pattern:
- What is the Design Pattern?
- Where did you apply it?
- Justify why you chose this one and not another. What do you gain by using the chosen Design Pattern?

## 5. Multithreading
### Task #5
- Implement `order creation` functionality. 
- Each order should be processed in separate thread. When user selects product, generate a random int from 1 to 30, and create thread that will process selected order for selected time, and after it places the product in another collection (for example, purchased goods). 
- Create one more thread, that will be executed periodically, e.g. once in 2 mins, that will clean up purchased collection.

You can implement this in `native java methods` but better and simpler to use `java.util.concurrent` package.

## 6. Database
### Task #6
Replace `Reflection` and `in-memory` products storage with `database`. You should store categories and products for each category in database tables.

Requirements:
- use `JDBC`
- you can select `any DB` (for simplicity, you can select `H2 database` in files mode)

## 7. HTTP Connection
### Task #7
The same task as previous, but to store and get store data you should

- implement an `HTTP server` (use included in java or external lib), that will handle your categories in-memory or DB, but you will receive them via `HTTP protocol`.
- Also, you should implement `add product to cart` logic in this server, and process this request via HTTP.
- Finally, your `HTTP service` should be secured with `basic authentication` (credentials can be hardcoded).
For HTTP client-side you also can use the default (included in java) or use RestAssured.