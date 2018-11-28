# SWAGGER
## What is Swagger?

The swagger module provides tools for **designing and building APIs entirely in Node.js.** It integrates with popular Node.js servers, including Express, hapi, restify, and Sails, as well as any Connect-based middleware. With swagger, you can specify, build, and test your API from the very beginning, and it allows you to make changes to your design without rewriting the logic of your implementation. It explicitly isolates the design of your interfaces from writing your controller code, leading to a much better software development lifecycle. 

## Why we need to use?
As a developer we may write the best web API service but **without proper documentation how can other developers discover** and use it?

## What does swagger offers to us?

- Interactive documentation. 
- Discoverability. 
- Client SDK generation

### Tools
- #### Swagger Editor
   --  You can edit swagger documentation file using Swagger Editor
   --you can use online version as well or download it

- #### Swagger UI
  -- It allows you to easily interact with your API
  -- It is auto-magically generated from your Swagger spec
  -- It enables you to see  the operations available  and to test it.

- #### Swagger Codegen
  -- which allows developers to design routes without writing a single line of code in javascript.

## How to use it ?
### 1. Install the swagger module

Install using npm. For complete instructions, see the [install](https://raw.githubusercontent.com/swagger-api/swagger-node/master/docs/install.md) page.

```bash
$ npm install -g swagger
```

### 2. Create a new swagger project

Use the [CLI](./docs/cli.md) to create and manage projects. Learn more on the [quick start](https://raw.githubusercontent.com/swagger-api/swagger-node/master/docs/quick-start.md) page.

```bash
$ swagger project create hello-world
```

### 3. Design your API in the Swagger Editor

The interactive, browser-based [Swagger Editor](http://editor.swagger.io/) is built in. It provides Swagger 2.0 validation and endpoint routing, generates docs on the fly, and consumes easy-to-read YAML.

```bash
$ swagger project edit
```

![screenshot of project editor](https://raw.githubusercontent.com/swagger-api/swagger-node/master/docs/images/swagger-editor.png)

### 4. Write controller code in Node.js

Code your API's business logic in Node.js.

```js
function hello(req, res) {
    var name = req.swagger.params.name.value || 'stranger';
    var hello = util.format('Hello, %s!', name);
    res.json({ "message": hello });
}
```

If you look at the Swagger file in the editor (shown in step 3 above), the `x-swagger-router-controller` element (line 17 in the editor screenshot) specifies the name of the controller file associated with the `/hello` path. For example:

```yaml
    paths:
        /hello:
            x-swagger-router-controller: hello_world
```

## For more reference
- https://swagger.io/
