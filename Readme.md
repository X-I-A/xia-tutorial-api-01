# X-I-A API Tutorial - 01
## Getting Started

Welcome to XIA API tutorial!

The goal of this tutorial is to quickly show you how to build a complex application by using X-I-A API framework. 
This framework is microservice based in order to get a fast learning curve for developers and AI.

## How to use this tutorial

Each tutorial is ended by a series number like 01-02-03. The longer the series is, the more advanced topic is discussed.
It will be better to finish basic tutorial before going through advanced ones. Each tutorial has example code. 
Installation instruction could be found at tutorial/install.md.

## Let's start !
### Data to API in 2 minutes

Please clone and deploy the example code (see [installation guide](tutorial/install.md) for instruction).

Or just visiting the already deployed [online version](https://xia-tutorial-api-01-srspyyjtqa-ew.a.run.app/order)

After it is done, three services are deployed:

* /doc: Auto-generated OpenAPI document

[online version](https://xia-tutorial-api-01-srspyyjtqa-ew.a.run.app/doc)

* /api: API Endpoint

Here is a 40-second-video to show how to quickly construct a playground with /doc and /api endpoints.

https://user-images.githubusercontent.com/49595269/216164016-5aff811d-4424-4066-82e4-a3e7682f32fe.mp4

* /: The demo also comes with a simple Online Editor. It just covers little functionality of API, and it is only designed for demo purpose.

Here is a 30-second-video to show briefly how editor works:

https://user-images.githubusercontent.com/49595269/212530070-17cf7f9e-c75f-43b8-ab51-4317dccb1812.mp4


### Define your own data model

In order to use your own data model, you just need to focus on application logic.

1. Adapting data models in models directory
2. Importing defined models into config.py
3. Defining resource mapping in config.py, just like:
```
    RESOURCE_MAPPING = { "order": PurchaseOrder }
```
For the above example, if you want to manipulate Python data model PurchaseOrder, you could use:
* /api/order for api call
* /order for web editing

### Other files:

Only 6 other files relates to the application. Other files are related to tutorial

* compile.py: Used to compile static files, including html file from defined data models
* Dockerfile: build container
* main.py: Flask application main program
* requirements.txt: pip package dependencies 
* requirement-xia.txt: pip package dependencies of xia scope
* VERSION: Deploy version, Single source of truth of version number in CI/CD process

Also keeping two empty directories:
* static: Holding static files
* templates: Holding html templates

And also a js library:
* /static/js/redoc: Parsing OpenApi schema to webpage, based on [Redocly](https://github.com/Redocly/redoc)

That is all what you need to make it work

### Next Step: Making your data persistent

Data Model use by default RamEngine which keeps data in Memory. 
In order to make your data persistent, you will need to change data engine. 
X-I-A is capable of working with any database. Please follow the next tutorial:
* Tutorial 02: Database Engine Integration
* Tutorial 03: User Authentication
* Tutorial 04: Authorization Management
* Tutorial 05: Applying rate limits // Payment
* Tutorial 06: Making independent microservice work as a complex application 
* Tutorial 07: Examples of complex application

### Going deeper on data model topic
* [Tutorial 01-01](https://github.com/X-I-A/xia-tutorial-api-01-01): Simple Data Model (Documents / Fields / Actions / EmbeddedDocuments)
* [Tutorial 01-02](https://github.com/X-I-A/xia-tutorial-api-01-02): Advanced Data Models (ExternalDocument)
* [Tutorial 01-03](https://github.com/X-I-A/xia-tutorial-api-01-03): No over fetching and no under fetching (Lazy mode and Catalog Object )
* [Tutorial 01-04](https://github.com/X-I-A/xia-tutorial-api-01-04): Data manipulation (CRUD)
* [Tutorial 01-05](https://github.com/X-I-A/xia-tutorial-api-01-05): Transactional Query
