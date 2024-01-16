# NodeJS

### Firstly understand What is backend development?

Back-end Development refers to the server-side development. Which user is unable to see what's going on at the backend. Or as you can say Backend developers work behind the scenes to control everything which you don’t see on a website.

The role may include creating, maintaining, testing, and debugging a website. This includes the core application logic, databases, data and APIs, and more.

So in the backend we will be going to learn about how we will make a server using node js and database as a mongoDB.

Now we will move ahead with the node js.

### Introduction to Node.js:

Node.js is an open-source, cross-platform, JavaScript runtime environment that executes JavaScript code outside a web browser.

open-source: Means anyone can access it [it is publically accessible]
Cross-platform: Means we can run the node js coding in various platforms or where javascript is installed or can run.

 Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine. It allows you to run JavaScript on the server side, providing a powerful and efficient way to build scalable network applications. Node.js is event-driven and non-blocking, making it well-suited for handling concurrent connections and building real-time applications.

It is known for its asynchronous event-driven model, which allows it to handle a large number of concurrent connections without blocking.
Because it uses non-blocking operations This makes it particularly useful for building real-time applications, such as chat applications or online gaming platforms.
It is in between the client side and Database which take care of the request and response.

### By using node js we can make wide variety of the application such as:

`Web applications:` Node.js is a popular choice for building web applications because it is fast, scalable, and efficient.

`Real-time applications:` Node.js is well-suited for building real-time applications, such as chat apps and multiplayer games.

`Streaming applications:` Node.js can be used to build streaming applications, such as video streaming and audio streaming.

`APIs:` Node.js can be used to build APIs that can be used by other applications.

An API (Application Programming Interface) is a set of rules that define how two applications can communicate with each other


### Need for Node.js:

1. **Single Language:** With Node.js, you can use JavaScript for both server-side and client-side development, providing consistency across your entire application.

2. **Asynchronous and Event-Driven:** Node.js is designed to handle asynchronous operations efficiently, making it suitable for building scalable and performant applications.

3. **Community and Modules:** Node.js has a large and active community, and it provides a vast ecosystem of modules through npm (Node Package Manager), making it easy to add functionality to your applications.

### Here are some of the benefits of using Node.js:

Fast: Node.js is very fast because it uses an event-driven, non-blocking I/O model. This means that it can handle a large number of concurrent connections without slowing down.

Scalable: Node.js is very scalable, making it a good choice for applications that need to handle a lot of traffic. It can easily be scaled horizontally by adding more servers.

Reusable: Node.js has a large and active community, which means that there are many reusable modules available. This can save you a lot of time and effort when developing your applications.

JavaScript: Node.js is written in JavaScript, which is a popular language that is known for its simplicity and expressiveness. This makes it easy to learn and use, even for beginners.

Real-time applications: Node.js is well-suited for building real-time applications, such as chat apps and multiplayer games. This is because it can handle a large number of concurrent connections and keep them all up-to-date with the latest data.

### Blocking and Non-blocking Operations:

- **Blocking Operations:** In traditional synchronous programming, a blocking operation means that the program is paused until the operation completes. This can lead to performance issues, especially in applications that need to handle multiple tasks simultaneously.

- **Non-blocking Operations:** Node.js is designed to be non-blocking. Instead of waiting for operations to complete, it continues to execute other tasks. This is achieved through callbacks and event-driven architecture.



### REPL (Read-Eval-Print Loop):

Node.js comes with a handy tool called REPL, which stands for Read-Eval-Print Loop. It allows you to interactively run JavaScript code. To start REPL, open your terminal and type `node` and press Enter.

You can then type JavaScript commands, and they will be executed immediately. It's a great way to experiment with code snippets and get quick feedback.

For initialising the node js project follow the following steps:
```
npm init
npm install --y
Then, create your first file index.js
And write console.log(“hello world”) in index.js
And run the server.
```

## Modules:
A module is a self-contained piece of code that can be imported into other modules. Modules can be used to organise code, reuse code, and share code.
It has a set of variable functions which we can reuse.
There are different modules such as:
1. Fs module,
2. Core modules,
3. Third party modules,
4. Local modules


### 3. FS Module:

The `fs` (File System) module in Node.js allows you to work with the file system on your computer. Here's a simple example:

The `fs` (File System) module in Node.js provides an API for interacting with the file system. It allows you to perform various operations such as reading, writing, and manipulating files and directories. Below, I'll explain some of the key methods in the `fs` module along with code examples.

### 1. `fs.readFile(path[, options], callback)`

This method is used to asynchronously read the entire contents of a file. It takes a file path, an optional options object (for specifying encoding, flag, etc.), and a callback function that is called with two arguments: `err` (if an error occurs) and `data` (the file content).

```javascript
const fs = require('fs');

fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log(data);
});
```

> 'utf8' (alias: 'utf-8'): Multi-byte encoded Unicode characters. Many web pages and other document formats use UTF-8. This is the default character encoding. When decoding a Buffer into a string that does not exclusively contain valid UTF-8 data, the Unicode replacement character U+FFFD � will be used to represent those errors.


### 2. `fs.readFileSync(path[, options])`

This method is the synchronous version of `fs.readFile`. It blocks the execution until the file is read completely. It returns the file content or throws an error if something goes wrong. 
The synchronous APIs block the Node.js event loop and further JavaScript execution until the operation is complete. Exceptions are thrown immediately and can be handled using try…catch, or can be allowed to bubble up.

```javascript
const fs = require('fs');

try {
  const dataSync = fs.readFileSync('example.txt', 'utf8');
  console.log(dataSync);
} catch (err) {
  console.error(err);
}
```

### 3. `fs.writeFile(file, data[, options], callback)`

This method is used to asynchronously write data to a file. It takes a file path, data to be written, an optional options object, and a callback function that is called after the operation is complete.

```javascript
const fs = require('fs');

fs.writeFile('output.txt', 'Hello, Node.js!', 'utf8', (err) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('File written successfully');
});
```

### 4. `fs.writeFileSync(file, data[, options])`

This is the synchronous version of `fs.writeFile`. It blocks the execution until the file is written completely.

```javascript
const fs = require('fs');

try {
  fs.writeFileSync('output.txt', 'Hello, Node.js!', 'utf8');
  console.log('File written successfully');
} catch (err) {
  console.error(err);
}
```

### 5. `fs.appendFile(file, data[, options], callback)`

This method is used to asynchronously append data to a file. It works similarly to `fs.writeFile` but appends the data to the end of the file.

```javascript
const fs = require('fs');

fs.appendFile('output.txt', '\nAppended Text', 'utf8', (err) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('Data appended successfully');
});
```

### 6. `fs.appendFileSync(file, data[, options])`

This is the synchronous version of `fs.appendFile`.

```javascript
const fs = require('fs');

try {
  fs.appendFileSync('output.txt', '\nAppended Text', 'utf8');
  console.log('Data appended successfully');
} catch (err) {
  console.error(err);
}
```

These are just a few of the many methods available in the `fs` module. Other methods include those for working with directories (`fs.readdir`, `fs.mkdir`, `fs.rmdir`, etc.) and for file information (`fs.stat`, `fs.access`, etc.).

Certainly! Here are a few more examples of using the `fs` module for various file system operations in Node.js:

### 1. Directory Operations:

#### Reading the Contents of a Directory:

```javascript
const fs = require('fs');

fs.readdir('./myDirectory', (err, files) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('Files in the directory:', files);
});
```

#### Creating a Directory:

```javascript
const fs = require('fs');

fs.mkdir('./newDirectory', (err) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('Directory created successfully');
});
```

### 2. File Information:

#### Getting File Stats:

```javascript
const fs = require('fs');

fs.stat('./file.txt', (err, stats) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('File stats:', stats);
  console.log('Is it a directory?', stats.isDirectory());
  console.log('Is it a file?', stats.isFile());
});
```

### 3. File Renaming and Deleting:

#### Renaming a File:

```javascript
const fs = require('fs');

fs.rename('oldFile.txt', 'newFile.txt', (err) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('File renamed successfully');
});
```

#### Deleting a File:

```javascript
const fs = require('fs');

fs.unlink('fileToDelete.txt', (err) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('File deleted successfully');
});
```

### 4. Copying Files:

```javascript
const fs = require('fs');

// Asynchronous file copy
fs.copyFile('source.txt', 'destination.txt', (err) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('File copied successfully');
});

// Synchronous file copy
fs.writeFileSync('destinationSync.txt', fs.readFileSync('sourceSync.txt'));
console.log('File copied synchronously');
```

### 5. Watching for Changes:

```javascript
const fs = require('fs');

// Watch for changes in a directory
fs.watch('./myDirectory', (eventType, filename) => {
  console.log(`Event type: ${eventType}`);
  if (filename) {
    console.log(`Filename: ${filename}`);
  } else {
    console.log('Filename not provided');
  }
});
```

### Use of different files using fs module 

The `fs` module in Node.js is versatile and can be used to read and write various file formats, not limited to just text files. The ability to read or write a specific file format depends more on the purpose of your application and the libraries/modules available for processing that format. Here are some common file formats and the typical ways to work with them in Node.js:

1. **Text Files (.txt, .csv, .json, etc.):** As demonstrated earlier, you can read and write text files using the `fs` module. This includes plain text files, CSV files, and JSON files.

2. **Binary Files (Images, Audio, Video, etc.):** Binary files can be read and written using the `fs` module. However, you'll work with the raw binary data, and for meaningful processing (e.g., image manipulation, audio processing), you may need specialized libraries.

    ```javascript
    const fs = require('fs');

    // Read binary data from an image file
    const imageData = fs.readFileSync('image.jpg');
    ```

3. **JSON Files (.json):** JSON files are a common format for configuration and data exchange. You can use the `fs` module to read JSON files, and `JSON.parse` to convert the content into a JavaScript object.

    ```javascript
    const fs = require('fs');

    // Read JSON data from a file
    const jsonData = fs.readFileSync('data.json', 'utf8');
    const parsedData = JSON.parse(jsonData);
    ```

4. **XML Files (.xml):** While Node.js itself does not have built-in support for XML, there are third-party libraries like `xml2js` that you can use to parse and manipulate XML files.

    ```javascript
    const fs = require('fs');
    const xml2js = require('xml2js');

    // Read XML data from a file
    const xmlData = fs.readFileSync('data.xml', 'utf8');

    // Parse XML data
    xml2js.parseString(xmlData, (err, result) => {
      if (err) {
        console.error(err);
        return;
      }
      console.log(result);
    });
    ```

5. **SQLite Databases (.sqlite):** While the `fs` module is not used directly for reading SQLite databases, you can use modules like `sqlite3` to interact with SQLite databases.

    ```javascript
    const sqlite3 = require('sqlite3').verbose();
    const db = new sqlite3.Database('example.db');

    db.serialize(() => {
      db.each('SELECT * FROM my_table', (err, row) => {
        console.log(row);
      });
    });

    db.close();
    ```

6. **PDF Files (.pdf):** Reading and processing PDF files typically requires third-party libraries such as `pdf-parse` or `pdf2json`.

    ```javascript
    const fs = require('fs');
    const pdf = require('pdf-parse');

    const dataBuffer = fs.readFileSync('document.pdf');

    pdf(dataBuffer).then((data) => {
      console.log(data.text);
    });
    ```

Always check the Node.js documentation and npm registry for specific modules that might help with your file format of interest. Each file format may have its own unique considerations, and using specialized libraries is often recommended for more complex formats.

# Day-2

Absolutely! Let's dive into Day 2 topics.

### 1. Creating a Simple Server:

#### Step-by-Step Procedure:

1. Import the `http` module.
2. Create an HTTP server using the `createServer` method.
3. Define a callback function that handles incoming requests and responses.
4. Start the server by listening on a specific port (e.g., 3000).

#### Code Example:

```javascript
const http = require('http');

// Create an HTTP server
const server = http.createServer((req, res) => {
    
//writeHead sets the response status code and headers, while write is used to send the response body.
res.writeHead(200, { 'Content-Type': 'text/plain' });
// Set the response HTTP header with HTTP status and Content type
res.write('Hello, World!');
res.end();
});


// Listen on port 3000, IP defaults to 127.0.0.1
server.listen(4100, () => {
  console.log('Server running at http://127.0.0.1:3000/');
});
```

#### Explanation:

- **`require('http')`:** Imports the built-in `http` module, which provides functionality to create HTTP servers and clients.

- **`createServer` Method:** Creates an HTTP server that invokes the specified callback function for each incoming request. The callback function takes two arguments, `req` (the request) and `res` (the response).

- **Setting Response Headers:** The `res.writeHead` method is used to set the response HTTP header. In this example, it sets the status code to 200 (OK) and the content type to 'text/plain'.

- **`res.end('Hello, Node.js!\n')`:** Sends the response body to the client. In this case, it sends the string 'Hello, Node.js!\n'.

- **`server.listen(3000, '127.0.0.1', callback)`:** Makes the server listen on port 3000 and the IP address 127.0.0.1 (localhost). The callback function is executed once the server is listening.

### 2. Modules and Types of Modules:

#### Modules:
In Node.js, a module is a file or a folder containing a set of functions, variables, or even other modules. Modules allow you to organize your code into reusable and maintainable units.

#### Types of Modules:

- **Built-in Modules:** These are modules that come with Node.js, such as `fs` for file system operations, `http` for creating HTTP servers, and `path` for handling file paths.

- **Third-Party Modules:** These are modules created by the community and can be easily added to your project using npm (Node Package Manager).

- **Custom Modules:** These are modules created by you to organize your code into smaller, manageable pieces.

#### Example:

Let's create a simple custom module. Create a file named `math.js`:

```javascript
// math.js
const add = (a, b) => a + b;
const subtract = (a, b) => a - b;

module.exports = { add, subtract };
```

Now, in another file (e.g., `app.js`), you can use this module:

```javascript
// app.js
const math = require('./math');

console.log(math.add(5, 3));       // Output: 8
console.log(math.subtract(8, 3));  // Output: 5
```

### 3. HTTP Status Codes:

HTTP status codes indicate the outcome of a request made by the client to the server. They are three-digit numbers where the first digit defines the class of response, and the last two digits do not have any categorization role.

Some common status codes include:

- `200 OK`: The request was successful.
- `201 Created`: The request was successful, and a new resource was created.
- `400 Bad Request`: The server cannot or will not process the request due to an apparent client error.
- `404 Not Found`: The requested resource could not be found on the server.
- `500 Internal Server Error`: A generic error message returned when an unexpected condition was encountered on the server.

### 4. HTTP Requests:

HTTP (Hypertext Transfer Protocol) is the foundation of any data exchange on the Web. It is a protocol used for transmitting hypermedia, and it defines how messages are formatted and transmitted, and what actions web servers and browsers should take in response to various commands.

HTTP requests are messages sent by a client to initiate an action on the server. The most common types of HTTP requests are:

- **GET:** Retrieve data from the server.
- **POST:** Send data to the server to create a new resource.
- **PUT:** Send data to the server to update a resource.
- **DELETE:** Request the removal of a resource.

#### Making HTTP Requests in Node.js:


- **Using the `axios` module (Third-Party):**

    ```bash
    npm install axios
    ```

    ```javascript
    const axios = require('axios');

    axios.get('https://www.example.com')
      .then((response) => {
        console.log(response.data);
      })
      .catch((error) => {
        console.error(error);
      });
    ```

Feel free to explore these examples and let me know if you have any questions or if you'd like more details on any specific topic!


### How to perform routing with get and post 

```javascript 
const http = require('http');
// const url = require('url');

const jsonObj = {
    "name":"SP",
    "age":"24"
}
const server = http.createServer((req, res) => {
    console.log(req.url);
    console.log(req.method)
 
  if (req.url === '/home'&& req.method==="GET") {
    res.write("This is the home page");
    res.end();
  } else if (req.url === '/about' && req.method==="POST") {
    res.write("This is About page");
    res.end();
  } else if(req.url === '/json' && req.method==="POST"){
    const data = JSON.stringify(jsonObj)
    res.write(data)
    res.end()
  }
})

// Start the server on port 3000
server.listen(4100, () => {
  console.log('Server running at http://localhost:4100/');
});

```

### HTTP Headers

HTTP headers are key-value pairs sent by the server in the response or by the client in the request. They provide additional information about the request or the response, allowing the client and server to communicate various details. Here's an explanation of some common response headers:

### 1. `Connection:`

The `Connection` header indicates whether the connection should be kept open for further requests or closed after the current request-response cycle. 

- `Connection: keep-alive`: The connection should be kept open for multiple requests.
- `Connection: close`: The connection should be closed after the current request-response.

### 2. `Content-Type:`

The `Content-Type` header specifies the media type of the resource being sent. It informs the client how to interpret the content of the response.

Example values:
- `Content-Type: text/html`: The content is HTML.
- `Content-Type: application/json`: The content is in JSON format.
- `Content-Type: image/jpeg`: The content is an image in JPEG format.

### 3. `Date:`

The `Date` header indicates the date and time when the response was generated. It helps in understanding the freshness of the response.

Example:
```
Date: Sat, 01 Jan 2023 12:00:00 GMT
```

### 4. `Keep-Alive:`

The `Keep-Alive` header is used to allow the connection to be reused for multiple requests, instead of establishing a new connection for each request. It helps in reducing latency.

- `Keep-Alive: timeout=5, max=1000`: Specifies that the connection can be kept alive for 5 seconds and can handle a maximum of 1000 requests.

### 5. `Transfer-Encoding:`

The `Transfer-Encoding` header indicates the form of encoding that has been applied to the message body. One common value is `chunked`, where the message body is sent in chunks.

Example:
```
Transfer-Encoding: chunked
```

In chunked encoding, the body is divided into a series of chunks, each preceded by its size in hexadecimal followed by a newline and the chunk itself.

These headers play a crucial role in defining the behavior and characteristics of the HTTP communication between the client and the server. They help in conveying metadata about the content, managing connections, and ensuring efficient and reliable communication.






# Express

- Express is a framework built on top of Node.
- Express is a tool that makes it easier to build web applications using Node.js.
- It provides for handling HTTP requests, routing, and middleware.
- Express helps you manage everything, from routes to handling requests .
- It simplifies the process of creating servers, handling routes, and managing middleware.

### What are the advantages of using Express?
1. With a myriad of HTTP utility methods and middleware , creating a 
robust API is quick and easy .
2. Express provides a thin layer of fundamental web application features, 
without obscuring Node.js features that you know .
3. Many popular frameworks are based on Express .
4. Express helps you manage everything, from routes to handling requests 
5. Open Source Community : It has an open-source community,so the 
code is always reviewed and improved .
6. Express Framework is reliable and has a huge community around




| Feature                         | HTTP (Node.js)                     | Express.js                                   |
| ------------------------------- | --------------------------------- | -------------------------------------------- |
| **Routing**                     | Manual routing setup using `http` module. | Simplified routing with dedicated routing methods (`get`, `post`, etc.). |
| **Middleware**                  | Manually configure middleware functions. | Built-in middleware and easy middleware setup. |
| **Request and Response Objects**| Basic request and response objects. | Enhanced request and response objects with additional methods and properties. |
| **Handling Parameters**         | Manually parse parameters from URL. | Supports route parameters and query parameters more easily. |
| **Static File Serving**         | Manually handle static file serving. | Built-in middleware for serving static files (`express.static`). |
| **Error Handling**              | Manually handle errors.            | Built-in error handling middleware (`app.use((err, req, res, next) => {...})`). |
| **Organizing Routes**           | Routes scattered across multiple files. | Routes can be organized using `Router` and modularized into separate files. |
| **Flexibility**                 | Low-level control over HTTP features. | Higher-level abstraction with conventions and easier development. |
| **Learning Curve**               | Steeper learning curve due to manual setup. | Easier for beginners due to a more structured and feature-rich framework. |
| **Community Support**           | Community support for Node.js.     | Active and large community support with a rich ecosystem of middleware. |
| **Built-in Features**            | Minimal built-in features.         | Extensive built-in features like routing, middleware, and template engines. |
                                                                     
## Example using Express of get and post method

```javascript
const express = require('express');
const app = express();
const port = 4040;

// Handling GET requests
app.get('/', (req, res) => {
  res.send('Hello, Express! This is a GET request.');
});

app.post('/', (req, res) => {
  res.send('This is a POST request.');
});

app.put('/users/:id', (req, res) => {
  const userId = req.params.id;
  res.send(`This is a PUT request for user with ID ${userId}`);
});

app.delete('/users/:id', (req, res) => {
  const userId = req.params.id;
  res.send(`This is a DELETE request for user with ID ${userId}`);
});

app.all('/other', (req, res) => {
  res.send(`This is a ${req.method} request.`);
});

// Start the server
app.listen(port, () => {
  console.log(`Express server listening at http://localhost:${port}`);
});

```

### Example-2

```javascript

const express = require('express');
const app = express();
const port = 4040;
const data = require('./data');

// Handling GET requests
app.get('/', (req, res) => {
  res.send('Hello, Express! This is a GET request.');
});

app.get('/bollywood', (req, res) => {
  // res.send(data);
  const result = data.filter((item)=>item.category === "Bollywood") 
    res.send(result);
});

app.get('/hollywood', (req, res) => {
  const userId = req.params.id;
  res.send(`This is a PUT request for user with ID ${userId}`);
});

app.get('/food', (req, res) => {
  const userId = req.params.id;
  res.send(`This is a DELETE request for user with ID ${userId}`);
});

app.all('/other', (req, res) => {
  res.send(`This is a ${req.method} request.`);
});

// Start the server
app.listen(port, () => {
  console.log(`Express server listening at http://localhost:${port}`);
});
```

```javascript
const data = [

    {
        id: 1,
        name: "Pizza",
        category: "Food",
        price:280,
        image: "https://img.freepik.com/premium-photo/aesthetic-dripping-tasty-pizza-slice-generative-ai_863013-1954.jpg",
        text: "Pizza is a dish of Italian origin consisting of a usually round, flat base of leavened wheat-based dough topped with tomatoes, cheese, and often various other ingredients, which is then baked at a high temperature, traditionally in a wood-fired oven",
    },
    {
        id: 2,
        name: "Burger",
        category: "Food",
        price:290,
        image: "https://c4.wallpaperflare.com/wallpaper/672/503/735/fast-food-junk-food-food-hamburger-wallpaper-preview.jpg",
        text: "A burger is a patty of ground beef grilled and placed between two halves of a bun. Slices of raw onion, lettuce, bacon, mayonnaise, and other ingredients add flavor. Burgers are considered an American food but are popular around the world",
    }
]
module.exports=data

```


### Example 3

Certainly! To create a server using Express with three routes that send data from different files, you can follow this example:

1. **Create a file named `data1.js` with some data:**
   ```javascript
   // data1.js
   module.exports = {
       message: 'Data from data1.js',
   };
   ```

2. **Create a file named `data2.js` with some data:**
   ```javascript
   // data2.js
   module.exports = {
       message: 'Data from data2.js',
   };
   ```

3. **Create your Express server in `server.js`:**
   ```javascript
   // server.js
   const express = require('express');
   const app = express();
   const port = 3000;

   // Import data from different files
   const data1 = require('./data1');
   const data2 = require('./data2');

   // Route 1: Send data from data1.js
   app.get('/route1', (req, res) => {
       res.json(data1);
   });

   // Route 2: Send data from data2.js
   app.get('/route2', (req, res) => {
       res.json(data2);
   });

   // Route 3: Send a custom message
   app.get('/route3', (req, res) => {
       res.send('Custom message from route3');
   });

   // Start the server
   app.listen(port, () => {
       console.log(`Server is running at http://localhost:${port}`);
   });
   ```

4. **Run your server:**
   ```
   node server.js
   ```

Now, you have an Express server with three routes:

- `/route1`: Sends data from `data1.js`
- `/route2`: Sends data from `data2.js`
- `/route3`: Sends a custom message




# Day4:

# Express Routing

**Routing** defines the way in which the client requests are handled by the application endpoints.

There are two ways to implement routing in node.js :

1:Using Framework: The most popular is Express.js.

2:Without using Framework

## Using Framework:
```javascript
     const express = require('express')
     const  app = express()

     app.get('/', function(req, res) {
         res.send('Hello Sir')
     })
     app.post('/login', function(req, res) {
         res.send('this is the login page')
     })
     app.post('/signup', function(req, res) {
         res.send('this is the signup page')
     })

     app.listen(4011,()=>{
        console.log("server is running")
     })
```
## without using Framework:
```javascript
    const http = require('http');
      http.createServer(function (req, res) {
    res.writeHead(200, {'Content-Type': 'text/html'});



     if(req.url ==='/about') {
        res.write(' This is about us page');
        res.end();
    }
    else if(req.url ==='/contact') {
        res.write(' This is contact us page');
        res.end();
    }
    else {
        res.write('Hello World!');
        res.end();
    }
    }).listen(4012, () =>{
    console.log("server start at port 4012");
    });

```

#### Perform routing in different files using Router()

Certainly! In Express, you can use the `Router` to modularize your routes and keep them in separate files. Here's an example of how you can create a simple application with three pages (Home, Bollywood, Hollywood) and organize the routing using the `Router`:

### File: `app.js` (Main Application)

```javascript
const express = require('express');
const app = express();
const port = 3000;

// Import the routes module
const routes = require('./routes');

// Use the routes module for the "/pages" path
app.use('/pages', routes);

// Start the server
app.listen(port, () => {
  console.log(`Express server listening at http://localhost:${port}`);
});
```

### File: `routes.js` (Routes Module)

```javascript
const express = require('express');
const router = express.Router();

// Home page
router.get('/', (req, res) => {
  res.send('Home Page');
});

// Bollywood page
router.get('/bollywood', (req, res) => {
  res.send('Bollywood Page');
});

// Hollywood page
router.get('/hollywood', (req, res) => {
  res.send('Hollywood Page');
});

// Export the router to be used in other files
module.exports = router;
```

### Steps to Run the Example:

1. Save the above code in two separate files (`app.js` and `routes.js`).
2. Open a terminal and navigate to the directory containing these files.
3. Run `npm install express` to install the Express module (if you haven't already).
4. Run `node app.js` to start the Express server.
5. Open your browser and visit:
   - http://localhost:3000/pages/ (Home Page)
   - http://localhost:3000/pages/bollywood (Bollywood Page)
   - http://localhost:3000/pages/hollywood (Hollywood Page)

### Explanation:

- **`app.use('/pages', routes)`:** In the `app.js` file, we're telling Express to use the `routes` module for any path starting with `/pages`. This means that the routes defined in `routes.js` will be relative to `/pages`.

- **`express.Router()`:** In the `routes.js` file, we create an instance of `Router` using `express.Router()`. This allows us to define routes and middleware specific to this router.

- **`router.get('/', ...)`, `router.get('/bollywood', ...)`, etc.:** These are route handlers for different paths. They respond to GET requests for the specified paths under the `/pages` prefix.

- **`module.exports = router;`:** We export the router from `routes.js` so that it can be used in other files (in this case, `app.js`).

This modular approach makes it easy to organize and maintain your routes, especially as your application grows. Each page or feature can have its own file, and the main application file (`app.js`) remains clean and focused.



### Routing through 3 files

```javascript
const express = require('express');
const app = express();
const port = 4040;

// Import the routes module
const routes = require('./routes');

// Use the routes module for the "/pages" path
app.use('/pages', routes);

// Start the server
app.listen(port, () => {
  console.log(`Express server listening at http://localhost:${port}`);
});
```

//routes.js
```javascript
const express = require('express');
const routerTwo = require('./routesTwo');
const router = express.Router();


// Home page
router.get('/', (req, res) => {
  res.send('Home Page');
});

router.use('/article', routerTwo);

// Export the router to be used in other files
module.exports = router;

```

//routestwo.js
```javascript
const express = require('express');
const routerTwo = express.Router();

// Bollywood page
routerTwo.get('/bollywood', (req, res) => {
    res.send('Bollywood Page');
  });
  
// Hollywood page
  routerTwo.get('/hollywood', (req, res) => {
    res.send('Hollywood Page');
  });

  module.exports = routerTwo
```


## What is a Query Parameter?

A query parameter is a key-value pair appended to the end of a URL, typically used to pass information from a client to a server. Query parameters are separated from the URL path by a question mark (`?`) and from each other by an ampersand (`&`). They are commonly used to send additional data to the server, such as search terms, filters, or pagination details.

### Use of Query Parameters:

- **Filtering Data:** Query parameters can be used to filter data based on certain criteria.
- **Pagination:** Specify the page number and number of items per page.
- **Search Queries:** Pass search terms to the server.
- **Configuring Requests:** Customize the behavior of requests.

### Example 1: Filtering Data

Let's create an Express server that uses query parameters to filter a list of items. Save the following code in a file (e.g., `example1.js`):

```javascript
const express = require('express');
const app = express();
const port = 3000;

const items = [
  { id: 1, name: 'Item 1' },
  { id: 2, name: 'Item 2' },
  { id: 3, name: 'Item 3' },
];

// Endpoint to get filtered items based on a query parameter
app.get('/api/items', (req, res) => {
  const category = req.query.category;

  if (!category) {
    return res.status(400).send('Category query parameter is required.');
  }

  const filteredItems = items.filter(item => item.name.includes(category));
  res.json(filteredItems);
});

// Start the server
app.listen(port, () => {
  console.log(`Express server listening at http://localhost:${port}`);
});
```

**Explanation:**

- This example defines an endpoint `/api/items` that expects a query parameter named `category`.
- If the `category` parameter is provided, it filters the list of items based on whether their names include the specified category.
- If the `category` parameter is not provided, it responds with a 400 Bad Request status.

**Testing:**

- Open your browser or a tool like Postman.
- Visit http://localhost:3000/api/items?category=Item to get items with names containing "Item."

### Example 2: If the age is grater than 18 then give the access

Save the following code in another file (e.g., `example2.js`):

```javascript
const express = require('express');
const app = express();
const port = 4040;

const items = [
  { id: 1, name: 'Item 1' },
  { id: 2, name: 'Item 2' },
  { id: 3, name: 'Item 3' },
];

// Endpoint to get filtered items based on a query parameter
app.get('/api/items', (req, res) => {
  const {category,age} = req.query;
  // console.log(query);

  if (!category) {
    return res.status(400).send('Category query parameter is required.');
  }

  const filteredItems = items.filter(item => item.name.includes(category)); 
  if(age>=18){
    return res.json(filteredItems);
  }
  return res.send("age is less then 18")
});

// Start the server
app.listen(port, () => {
  console.log(`Express server listening at http://localhost:${port}`);
});
```

# Middleware:

**Middleware in Nodejs is a function that are invokes in the middle of the request-response process.**

**middleware is nothing but a function that runs even before the call goes to the API for which it is meant to be .**

- middleware is in between the server and the client that sits in the middle and intercepts incoming requests, processes them, and then passes them on to the next thing if there is nested middleware.

- in this it accepts 3 parameter like:(req,res,next)

- req object and response object are same as previous but the extra parameter is added that is next function

- **next()** is going to forword to next cycle if the autherization is succesfully completed if there is an error then it will not move forword and it will not hit the api it will cancel the request at that time only.

- Middleware refers to functions or sets of functions that have access to the request object (`req`), the response object (`res`), and the next function in the application's request-response cycle. Middleware can perform various tasks, modify request and response objects, end the request-response cycle, and call the next middleware in the stack.

## why we need the middleware?

- It can end the request and response cycle.

- it can call the next middleware by the next().

- it helps developers build applications more efficiently.

- It controls connections between application components

Middleware is used to:

- **Execute Code:** Perform actions before and after handling a request.
- **Modify Request/Response:** Add or modify properties of the request or response objects.
- **End Request-Response Cycle:** End the cycle prematurely if necessary.
- **Invoke the Next Middleware:** Call the next middleware in the stack.

### 3. Where Can We Use Middleware in Projects?

Middleware can be used at various stages in a project:

- **Logging:** Log information about incoming requests.
- **Authentication:** Check if a user is authenticated.
- **Error Handling:** Handle errors in a centralized location.
- **Parsing:** Parse incoming data (e.g., JSON, forms).
- **CORS Handling:** Set headers for Cross-Origin Resource Sharing.

### 4. How It Helps:

- **Modularity:** Breaks down application logic into modular, reusable components.
- **Orderly Execution:** Middleware functions are executed in a specific order.
- **Centralized Logic:** Allows centralizing common logic (e.g., logging, authentication) for easier maintenance.
- **Error Handling:** Can catch and handle errors in a centralized way.


### Example of Middleware:

Here's a simple example of a middleware function that logs information about incoming requests:

```javascript
// Middleware function
function loggerMiddleware(req, res, next) {
  console.log(`[${new Date().toISOString()}] ${req.method} ${req.url}`);
  next(); // Call the next middleware in the stack
}

// Using the middleware in an Express app
const express = require('express');
const app = express();

// Apply the loggerMiddleware to all routes
app.use(loggerMiddleware);

app.get('/', (req, res) => {
  res.send('Hello, Middleware!');
});

app.listen(3000, () => {
  console.log('Server running on http://localhost:3000');
});
```


### 5. Types of Middleware:

#### a. **Application-Level Middleware:**
   - **Usage:** Applied to the entire application.
   - **Example:** Logging middleware, authentication middleware.
   - **Implementation:** `app.use(loggerMiddleware);`

#### b. **Router-Level Middleware:**
   - **Usage:** Applied to specific routes.
   - **Example:** Middleware for a specific route.
   - **Implementation:** `router.use(middlewareFunction);`

#### c. **Error-Handling Middleware:**
   - **Usage:** Specialized middleware to handle errors.
   - **Example:** Middleware with four parameters (`(err, req, res, next)`).
   - **Implementation:** `app.use((err, req, res, next) => { /* handle error */ });`

#### d. **Third-Party Middleware:**
   - **Usage:** Developed by third parties.
   - **Example:** Body parsing middleware (`express.json()`).
   - **Implementation:** `app.use(express.json());`

#### e. **Built-In Middleware:**
   - **Usage:** Included with Express.
   - **Example:** `express.static` for serving static files.
   - **Implementation:** `app.use(express.static('public'));`

#### f. **Custom Middleware:**
   - **Usage:** Developed by the application.
   - **Example:** Any middleware created specifically for the project.
   - **Implementation:** Custom functions added with `app.use()` or `router.use()`.

Middleware provides flexibility and enhances the modularity of Express applications, allowing developers to structure their code in a more organized and maintainable way. Each type of middleware serves a specific purpose in the request-response cycle.




### Example of application level middleware :
```javascript
const express = require("express")
const app = express();

const middleware1 = (req, res, next) => {
    console.log("middleware one is running")
    next();
}
const middleware2 = (req, res, next) => {
    console.log("middleware two is running")
    next();
}

app.use(middleware1)  // application level middleware

app.use(middleware2)

app.get("/", (req, res) => {
  // res.sendStatus(200)
  res.send("Home page")
})
app.listen(5001, () => {
    console.log("server is running on the port 5001")
})

```

### if the age is above 18 then give the acess
```javascript
const express = require("express")
const app = express();

const middleware1 = (req, res, next) => {
    console.log("middleware one is running")
    if(!req.query.age){
      res.send("please provide the age");
    }
    else if(req.query.age<18){
      res.send("you can't access the page ")
    }
    else{
      next();
    }
}

app.use(middleware1)  // application level middleware

app.get("/", (req, res) => {
  // res.sendStatus(200)
  res.send("Home page")
})
app.listen(5001, () => {
    console.log("server is running on the port 5001")
})
```



### Example of router level middleware :

Certainly! In this example, we'll create a router with two middleware functions. The first middleware will be invoked when accessing the home page (`/`) and the second middleware when accessing the about page (`/about`).

### Example: Router-Level Middleware

```javascript
const express = require('express');
const app = express();
const port = 3000;

// Middleware 1
const middlewareOne = (req, res, next) => {
  console.log('Middleware One - Logging for Home Page');
  next();
};

// Middleware 2
const middlewareTwo = (req, res, next) => {
  console.log('Middleware Two - Logging for About Page');
  next();
};

// Create a router
const router = express.Router();

// Apply middlewareOne to the home page route
router.get('/', middlewareOne, (req, res) => {
  res.send('Home Page');
});

// Apply middlewareTwo to the about page route
router.get('/about', middlewareTwo, (req, res) => {
  res.send('About Page');
});

// Use the router for a specific path
app.use('/pages', router);

// Start the server
app.listen(port, () => {
  console.log(`Express server listening at http://localhost:${port}`);
});
```

**Explanation:**

1. **`middlewareOne` and `middlewareTwo`:**
   - Two middleware functions that log messages specific to their purposes.
   - Both call `next()` to pass control to the next middleware or route handler.

2. **Creating a Router:**
   - We create an instance of `express.Router()`.

3. **Applying Middleware and Routes:**
   - `router.get('/', middlewareOne, ...)`: Applies `middlewareOne` to the home page route.
   - `router.get('/about', middlewareTwo, ...)`: Applies `middlewareTwo` to the about page route.

4. **Using the Router:**
   - `app.use('/pages', router);`: Mounts the router at the `/pages` path.
   - Middleware and routes within the router will be applied for paths starting with `/pages`.

## error level middleware:

Error level middleware is a middleware function  that is used to handle errors that occur during the request-response cycle app. middleware function is typically the last middleware function in the middleware stack, and it is responsible for catching any errors that were not handled by other middleware functions.

The error level middleware takes four arguments: err, req, res, and next.

 The err argument is the error object that was thrown by a previous middleware function, or by the application code itself. The req argument is the request object, the res argument is the response object, and the next argument is a function that is called to pass control to the next middleware function in the stack.

```javascript
    const express = require('express');
     const app = express();


        function errorHandler(err, req, res, next) {
              res.status(500).send('Something broke!');
         }
       app.use(errorHandler);

       app.listen(4000,()=>{
        console.log("server is running in 4000")
       })

```

# What is CORS?

**CORS stands for Cross-Origin Resource Sharing**

CORS is a mechanism to allows a server to indicate any origins (domain, scheme, or port) other than its own from which a browser should permit loading resources.

For example, if you had your web API on one server and your web app on another you could configure CORS in your Web API to allow your web app to make calls to your web API.

It is used to secure a certain web server from access by other domain like you want to connect the backend port into your frontend port then we use the cors which is sharing the data.

like:
```javascript
        const express = require("express");
        const cors=require("cors")
        const app = express();
        app.use(cors({
            origin:"*"   // with this any port can use it in the frontend to fetch the name and email using fetch or axios
        }))
        app.get("/data",(req, res) => {

            res.json([{
                id:1,
                "name":"akarsh gupta"
                "email":"ak@gmail.com"
            },

            {
                id:2,
                "name":"SHubham Kumar"
                "email":"sk@gmail.com"
            }
            ])
        })

        app.listen(4013)

```

# adding 404 error:

In Express, 404 responses are not the result of an error, so the error-handler middleware will not capture them. This behavior is because a 404 response simply indicates the absence of additional work to do.

Express has executed all middleware functions and routes, and found that none of them responded. All you need to do is add a middleware function at the very bottom of the stack (below all other functions) to handle a 404 response:

like:

    app.use((req, res, next) => {
    res.status(404).send("Sorry can't find that!")
     })


### What is Body Parser?

`body-parser` is a middleware for handling HTTP POST requests in Express.js. It extracts the entire body portion of an incoming request stream and exposes it on `req.body` as something easier to interface with.

Body Parser is a middleware of Node JS used to handle HTTP POST request. Body Parser can parse string based client request body into JavaScript Object which we can use in our application.

It is used when the data we are accesing from the user side like a user fills the form then to use that request object we exposes it on req.body so in that time we need the body-parser.

This body-parser parses the JSON, buffer, string and URL encoded data submitted using HTTP POST request.

if we are not using body-parser then it will lose the data, and request. body field will be empty or undifined. but if we are using the latest version of the express is then we can avoid and we can use insted express.json() instead of that.

### Use of Body Parser:

- **Parsing Request Body:** It parses incoming request bodies in a middleware before your handlers, available under `req.body`.
- **Handling Form Data:** Useful for handling form submissions and processing data sent in the body of a POST request.

### Latest Syntax and Usage:

`body-parser` was previously a separate package, but since Express 4.16.0, it has been added as part of the Express.js core. So, if you are using Express 4.16.0 or later, you don't need to install `body-parser` separately.

The latest syntax involves using the `express.json()` and `express.urlencoded()` middleware functions directly within Express. Here's an example:

The `express.urlencoded({ extended: true })` middleware in Express is used to parse incoming requests with URL-encoded payloads. Let's break down what this means:

#### URL-Encoded Bodies:

When you submit a form on a website, the data from the form is sent in the body of the HTTP request. The way this data is encoded in the request body can vary, and one common way is URL encoding. URL encoding is a way to represent special characters and spaces in a URL-friendly format.

For example, if you submit a form with the data:

```plaintext
name=John Doe&age=25
```

It will be URL-encoded as:

```plaintext
name=John%20Doe&age=25
```

Here, spaces are replaced with `%20`, and special characters are encoded as well. The data is formatted as key-value pairs separated by `&`, and each pair consists of a key and its corresponding value separated by `=`.

### `express.urlencoded({ extended: true })`:

This middleware in Express is responsible for parsing URL-encoded data in the request body. The `extended: true` option allows the parsing of rich objects and arrays.

When you set up this middleware in your Express application like this:

```javascript
app.use(express.urlencoded({ extended: true }));
```

It means that for incoming requests with a `Content-Type` of `application/x-www-form-urlencoded` (which is the default for HTML forms), the middleware will parse the URL-encoded data in the request body and make it available in `req.body`.

### Example:

Suppose you have a form with two fields, "username" and "password," and the form is submitted with the data:

```plaintext
username=johndoe&password=secretpass
```

The `express.urlencoded({ extended: true })` middleware will parse this data and make it available in `req.body`:

```javascript
{
  username: 'johndoe',
  password: 'secretpass'
}
```

In summary, `express.urlencoded({ extended: true })` is a middleware in Express that parses incoming URL-encoded data in the request body, and the `extended: true` option allows for more complex data structures.


```javascript
const express = require('express');
const app = express();
const port = 3000;

// Use middleware to parse JSON bodies
app.use(express.json());

// Use middleware to parse URL-encoded bodies
app.use(express.urlencoded({ extended: true }));

// Example route handling POST request
app.post('/submit', (req, res) => {
  console.log(req.body);
  res.send('Data received successfully!');
});

// Start the server
app.listen(port, () => {
  console.log(`Server running at http://localhost:${port}`);
});
```

**Explanation:**

1. **`express.json()`:**
   - Middleware to parse JSON bodies.
   - Makes `req.body` available for JSON payloads.

2. **`express.urlencoded({ extended: true })`:**
   - Middleware to parse URL-encoded bodies.
   - `extended: true` allows parsing of rich objects and arrays.

3. **Example Route:**
   - Handles a POST request to the `/submit` route.
   - Logs the parsed `req.body` and sends a response.

4. **`app.use(...)`:**
   - Applies the middleware globally to all routes.

### Using Body Parser in Projects:

1. **Install Express:**
   ```bash
   npm install express
   ```

2. **Create Your Express App:**
   ```javascript
   const express = require('express');
   const app = express();
   const port = 3000;
   ```

3. **Use `express.json()` and `express.urlencoded()`:**
   ```javascript
   // Use middleware to parse JSON bodies
   app.use(express.json());

   // Use middleware to parse URL-encoded bodies
   app.use(express.urlencoded({ extended: true }));
   ```

4. **Define Your Routes:**
   ```javascript
   // Example route handling POST request
   app.post('/submit', (req, res) => {
     console.log(req.body);
     res.send('Data received successfully!');
   });
   ```

5. **Start the Server:**
   ```javascript
   app.listen(port, () => {
     console.log(`Server running at http://localhost:${port}`);
   });
   ```

This example sets up a basic Express server with middleware to parse both JSON and URL-encoded bodies. You can expand on this foundation to handle various types of requests and build more complex applications.


//backend
```javascript
const express = require('express');
const app = express();
const port = 6500;
const cors = require('cors')

app.use(cors({ origin: '*' })) 

// Use middleware to parse JSON bodies
app.use(express.json());

// Use middleware to parse URL-encoded bodies
app.use(express.urlencoded({ extended: true }));

// Example route handling POST request
app.post('/submit', (req, res) => {
  console.log(req.body);
  res.send('Data received successfully!');
});

// Start the server
app.listen(port, () => {
  console.log(`Server running at http://localhost:${port}`);
});
```

### Explanation:

1. express.json():

Middleware to parse JSON bodies.
Makes req.body available for JSON payloads.
express.urlencoded({ extended: true }):

2. Middleware to parse URL-encoded bodies.
extended: true allows parsing of rich objects and arrays.
Example Route:

3. Handles a POST request to the /submit route.
Logs the parsed req.body and sends a response.
app.use(...):

4. Applies the middleware globally to all routes.


//frontend

```javascript

import React, { useState } from 'react';
import axios from 'axios';

function App() {
  const [data, setData] = useState('');
  const [response, setResponse] = useState('');

  const submitData = async () => {
    try {
      const result = await axios.post('http://localhost:6500/submit', { data });
      setResponse(result.data);
    } catch (error) {
      console.error('Error:', error.message);
    }
  };

  return (
    <div>
      <h1>React Server Interaction Example</h1>

      <label htmlFor="data">Enter Data:</label>
      <input
        type="text"
        id="data"
        value={data}
        onChange={(e) => setData(e.target.value)}
      />

      <button type="button" onClick={submitData}>
        Submit
      </button>

      <div>
        <strong>Server Response:</strong>
        <p>{response}</p>
      </div>
    </div>
  );
}

export default App;
```


### 1. What is Password Hashing?

Password hashing is a security measure used to protect user passwords by converting them into a fixed-length string of characters, which is typically a hash value. Hashing is a one-way function, meaning it is computationally infeasible to reverse the process and obtain the original password. This ensures that even if the stored hashes are compromised, attackers cannot easily retrieve the actual passwords.

### Password Hashing in Node.js with Bcrypt:

### 2. What is Bcrypt?

Bcrypt is a password hashing algorithm designed by Niels Provos and David Mazières based on the Blowfish cipher. The name “bcrypt” is made of two parts: b and crypt, where b stands for Blowfish and crypt is the name of the hashing function used by the Unix password system.

Bcrypt is a popular library for securely hashing passwords. It employs a key derivation function specifically designed for password hashing. Bcrypt is widely used because it incorporates a salt (random data) into the hash, making it resistant to rainbow table attacks and ensuring that the same password will produce different hashes.

### 3. How Does Bcrypt Work?

Bcrypt uses the Blowfish cipher to hash passwords. It involves the following key features:

- **Salting:** Bcrypt automatically generates and includes a unique salt for each password hash. This prevents attackers from using precomputed tables (rainbow tables) to crack multiple hashes at once.

- **Cost Factor** Bcrypt also uses a cost factor (or work factor) to determine how long it takes to generate a hash. This cost factor can be increased to make it slower as hardware power increases. The higher the cost factor, the more secure the hash and the slower the process. Therefore, you need to find the right balance between security and speed.


**Bcrypt provides several methods** for hashing and comparing passwords, both synchronous and asynchronous. Let's dive into the details of each method:

### 1. `bcrypt.genSalt(rounds, callback)`

- **Asynchronous:** This method generates a salt using the specified number of `rounds` (the cost factor). More rounds result in a more secure hash but also increase the computation time.
  
- **Parameters:**
  - `rounds`: Number of rounds to use for generating the salt.
  - `callback(error, salt)`: A callback function that receives the generated salt.

### 2. `bcrypt.genSaltSync(rounds)`

- **Synchronous:** This is the synchronous version of `genSalt`. It returns the generated salt directly instead of using a callback.

- **Parameters:**
  - `rounds`: Number of rounds to use for generating the salt.

### 3. `bcrypt.hash(data, salt, callback)`

- **Asynchronous:** This method generates a hash for the given data using the provided salt.

- **Parameters:**
  - `data`: The data to be hashed.
  - `salt`: The salt generated using `genSalt`.
  - `callback(error, hash)`: A callback function that receives the generated hash.

### 4. `bcrypt.hashSync(data, salt)`

- **Synchronous:** This is the synchronous version of `hash`. It returns the generated hash directly instead of using a callback.

- **Parameters:**
  - `data`: The data to be hashed.
  - `salt`: The salt generated using `genSalt`.


### 5. `bcrypt.compare(data, hash, callback)`

- **Asynchronous:** This method compares the given data with the provided hash to check if they match.

- **Parameters:**
  - `data`: The data to be compared.
  - `hash`: The hash to be compared against.
  - `callback(error, result)`: A callback function that receives a boolean `result` indicating whether the comparison is successful.

- **Example:**


### 6. `bcrypt.compareSync(data, hash)`

- **Synchronous:** This is the synchronous version of `compare`. It returns a boolean value indicating whether the comparison is successful.

- **Parameters:**
  - `data`: The data to be compared.
  - `hash`: The hash to be compared against.

### Summary:

- **Salt Generation:**
  - Use `genSalt` and `genSaltSync` for asynchronous and synchronous salt generation, respectively.

- **Hash Generation:**
  - Use `hash` and `hashSync` for asynchronous and synchronous hash generation, respectively.

- **Password Comparison:**
  - Use `compare` and `compareSync` for asynchronous and synchronous password comparison, respectively.

### Important Notes:

- **Asynchronous vs. Synchronous:**
  - Asynchronous methods are preferred in Node.js applications to avoid blocking the event loop, especially during heavy computations.

- **Security Note:**
  - Always use asynchronous methods for password hashing and comparison, especially in production, to prevent potential performance issues.

These methods provide a convenient and secure way to handle password hashing and comparison in your Node.js applications using bcrypt.

### 4. Examples of Password Hashing with Bcrypt in Node.js:

#### Bcrypt Dependencies:

```bash
npm install bcrypt
```

#### Password Encryption in Node.js using the JavaScript async Promise:

```javascript
const bcrypt = require('bcrypt');

async function hashPassword(password) {
  const saltRounds = 10;
  const salt = await bcrypt.genSalt(saltRounds);
  const hashedPassword = await bcrypt.hash(password, salt);
  return hashedPassword;
}

// Example usage
hashPassword('mySecretPassword')
  .then((hashedPassword) => {
    console.log('Hashed Password:', hashedPassword);
  })
  .catch((error) => {
    console.error('Error:', error);
  });
```

#### Auto-generating a Salt and Hash:

```javascript
const bcrypt = require('bcrypt');

async function hashPassword(password) {
  const hashedPassword = await bcrypt.hash(password, 10);
  return hashedPassword;
}

// Example usage
hashPassword('mySecretPassword')
  .then((hashedPassword) => {
    console.log('Hashed Password:', hashedPassword);
  })
  .catch((error) => {
    console.error('Error:', error);
  });
```

#### Using the `bcrypt.compare` Function to Verify Passwords:

```javascript
const bcrypt = require('bcrypt');

async function comparePasswords(inputPassword, hashedPassword) {
  const isMatch = await bcrypt.compare(inputPassword, hashedPassword);
  return isMatch;
}

// Example usage
const hashedPassword = '$2b$10$...'; // Replace with a real hashed password
comparePasswords('userInputPassword', hashedPassword)
  .then((isMatch) => {
    if (isMatch) {
      console.log('Password is correct');
    } else {
      console.log('Password is incorrect');
    }
  })
  .catch((error) => {
    console.error('Error:', error);
  });
```

### 5. Node.js Bcrypt Password Hashing Information:

In Node.js, Bcrypt provides a secure and efficient way to hash passwords. It automatically handles salting and allows you to control the work factor to adapt to the changing landscape of security threats.

### 6. Password Hashing Data Costs:

- **Salt:** Bcrypt automatically generates and stores a unique salt for each password. This adds a small overhead in terms of storage but significantly enhances security.

- **Hash Length:** The length of the resulting hash is fixed, regardless of the input password length. This consistency simplifies storage and retrieval.

### 7. Benefits of Password Hashing in Node.js with Bcrypt:

- **Resistance to Attacks:** Bcrypt provides strong resistance against common attacks, including rainbow table attacks and brute force attacks.

- **Salting:** Automatic salting ensures that each password hash is unique, even for users with the same password.

- **Adaptability:** The work factor can be adjusted to adapt to changes in hardware capabilities, maintaining a high level of security over time.

- **Ease of Use:** Bcrypt is user-friendly, making it easy to incorporate password hashing into your Node.js applications.

Using Bcrypt for password hashing is considered a best practice in web development for securing user credentials. It addresses many of the common vulnerabilities associated with storing passwords and provides a solid foundation for authentication security in Node.js applications.


## login and signup API with bcrypt

```javascript
//server.js
const express = require('express');
const app = express();
app.use(express.json())

// Import the routes module
const routes = require('./UserRoute');

// Use the routes module for the "/pages" path
app.use('/pages', routes);

app.listen(8800,()=>{
    console.log("server is running fine")
})
```

```javascript
//userRouter()

const express = require('express');
const router = express.Router();
const bcrypt = require('bcrypt')
// const saltRound = 10;

let arr = []
router.post('/register',(req,res)=>{
    const data = req.body
    console.log(data)
    // const randomvalue = bcrypt.genSaltSync(saltRound)
    //     console.log(randomvalue,"generateSalt")

    let account = arr.find(item=>item.email===loginData.email)
    if(account){
        return res.send("This email is already exist")
    }
    data.mobile = bcrypt.hashSync(data.mobile, 10);
    // console.log(hashpass, "hashed password");
    arr.push(data);
    console.log(arr,"database")
        return res.send("user is registered")
    })

router.post('/login',async(req,res)=>{
    const loginData = req.body
    // console.log(data)
    let account = arr.find(item=>item.email===loginData.email)
    console.log(account)
    if(!account){
        return  res.send("user is not registered")
      }
        const validate = await bcrypt.compare(loginData.mobile,account.mobile)
        if(validate){
           return res.send("user logged in ")
        }
        else{
            return res.send("password is wrong")
        }
})

module.exports = router
```

Authentication and authorization are two fundamental concepts in the field of security, particularly in the context of computer systems and applications.

### Authentication:
When we are talking about authentication then we say that if a
person is providing his credential we will be checking if his credentials are correct
or not or if he is already an existing user or not

**Definition:**
Authentication is the process of verifying the identity of a user, system, or entity. It is the mechanism by which a system validates the claimed identity of an entity, typically through the presentation of credentials such as usernames and passwords, biometric data, security tokens, or other authentication factors.

**Purpose:**
The primary goal of authentication is to ensure that the user or entity accessing a system is who they claim to be.

**Key Components:**
1. **Credentials:** Information provided by the user to prove their identity.
2. **Authentication Factors:** Something the user knows (password), something the user has (security token), or something the user is (biometric data).

### Authorization:
When we are talking about authorization then we check that the
user who has logged is having access for this specific data or not. For example,
an Uber driver can not book the cab from the same account with which he has
logged in Uber application as driver.

**Definition:**
Authorization is the process of granting or denying access to specific resources, functionalities, or actions based on the authenticated user's privileges and permissions. It is the mechanism that determines what actions a user or system is allowed to perform within a given system or application.

**Purpose:**
The primary goal of authorization is to control and restrict access to resources, ensuring that users have appropriate permissions to perform specific actions.

**Key Components:**
1. **Roles and Permissions:** Users are assigned roles, and roles are associated with specific permissions or access levels.
2. **Access Control Lists (ACLs):** Lists that define what actions or operations a particular user or system is allowed or denied.

### Differences:

1. **Focus:**
   - **Authentication:** Centers on verifying identity.
   - **Authorization:** Centers on granting or denying access based on identity.

2. **Goal:**
   - **Authentication:** Ensures that a user is who they claim to be.
   - **Authorization:** Controls what a user can or cannot do after authentication.

3. **Process:**
   - **Authentication:** Involves verifying identity through the presentation of credentials or other authentication factors.
   - **Authorization:** Involves determining what actions or resources a user is allowed to access based on their authenticated identity.

4. **Key Components:**
   - **Authentication:** Credentials, authentication factors.
   - **Authorization:** Roles, permissions, access control lists.

5. **Timing:**
   - **Authentication:** Typically occurs first in the user access process.
   - **Authorization:** Occurs after authentication and is dependent on the authenticated user's identity.

6. **Example:**
   - **Authentication:** Verifying a user's username and password during login.
   - **Authorization:** Determining whether a user has the permission to delete a file after successful authentication.

### Relationship:

Authentication and authorization work hand in hand in the context of user access control. After a user is authenticated (proven to be who they claim to be), the system then uses authorization mechanisms to determine what that authenticated user is allowed to do or access.



### What is JSON Web Token (JWT)?

A JSON Web Token (JWT) is a compact, URL-safe means of representing claims between two parties. These claims are typically used for authentication and authorization purposes. JWTs are commonly used in web development to securely transmit information between parties, especially between a client and a server.

JWTs are mainly used for authentication. After a user signs in to an application, the application then assigns JWT to that user. Subsequent requests by the user will include the assigned JWT. This token tells the server what routes, services, and resources the user is allowed to access.

### Advantages of Node.js Authentication with JWT:

1. **Stateless Authentication:**
   - JWTs enable stateless authentication, meaning the server doesn't need to store the user's session information. This makes it easier to scale applications horizontally.

2. **Cross-Domain Authorization:**
   - JWTs can be used across different domains, making them suitable for microservices architectures and distributed systems.

3. **Security:**
   - JWTs can be signed and optionally encrypted, providing a secure way to transmit data between parties. The signature ensures data integrity, and encryption adds an extra layer of confidentiality.

4. **Reduced Database Load:**
   - Since JWTs are self-contained and include necessary information, there's no need to query the database for user information on every request. This reduces the load on the database.

5. **Flexibility:**
   - JWTs are flexible and can include custom claims, allowing developers to encode additional information beyond standard user authentication details.

6. **Efficient Communication:**
   - Being compact and URL-safe, JWTs are efficient for transmitting information over the network. They are commonly used in HTTP headers or query parameters.

### The Need for JSON Web Token:

The need for JWT arises from challenges associated with traditional session-based authentication:

1. **Statelessness:**
   - HTTP is a stateless protocol, and maintaining user sessions traditionally requires server-side storage or database queries. JWTs allow stateless authentication by encoding user information directly into the token.

2. **Cross-Domain Communication:**
   - Cookies, traditionally used for session management, have domain restrictions. JWTs can be used across different domains, making them suitable for modern web applications with separate frontend and backend servers.

3. **Scalability:**
   - Stateless authentication is crucial for horizontal scalability. As applications grow, stateless solutions like JWTs make it easier to distribute authentication responsibilities.

### Structure of a JWT:

A JWT consists of three parts: a header, a payload, and a signature. These parts are base64-encoded and concatenated with periods (`.`) to form the final JWT.

1. **Header:**
   - Contains information about the type of token and the signing algorithm used. Example:
     ```json
     {
       "alg": "HS256",
       "typ": "JWT"
     }
     ```

2. **Payload:**
   - Contains claims. Claims are statements about an entity (typically, the user) and additional metadata. Example:
     ```json
     {
       "sub": "1234567890",
       "name": "John Doe",
       "iat": 1516239022
     }
     ```

3. **Signature:**
   - Created by combining the encoded header, encoded payload, and a secret. The signature ensures the integrity of the token. Example:
     ```
     HMACSHA256(
       base64UrlEncode(header) + "." +
       base64UrlEncode(payload),
       secret
     )
     ```

### JWT Use Cases:

1. **Authentication:**
   - JWTs are widely used for user authentication. After a user logs in, the server generates a JWT containing user information. The client includes this JWT in subsequent requests to access protected resources.

2. **Single Sign-On (SSO):**
   - JWTs facilitate single sign-on across multiple services. Once a user authenticates with one service and receives a JWT, they can use it to access other services without re-authenticating.

3. **Information Exchange:**
   - JWTs are suitable for securely transmitting information between parties. They are often used in authorization and access control scenarios.

4. **Stateless Sessions:**
   - JWTs can represent session information, allowing for stateless sessions without the need for server-side storage.

5. **Secure Data Exchange:**
   - JWTs can be used to securely transmit data between a client and a server. The signature ensures that the data hasn't been tampered with during transmission.

In summary, JSON Web Tokens provide a versatile and secure way to transmit information, especially for authentication and authorization purposes in web development. Their compact and self-contained nature makes them well-suited for modern, distributed architectures.




```javascript


import React, { useEffect, useState } from 'react';
import { createContext } from 'react';
import axios from 'axios';

export const dataStore = createContext();

const CntxtAPI = (props) => {
  const [data, setData] = useState([]);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await axios.get('http://localhost:5000/api/blog'); // Replace with your backend API URL
        setData(response.data);
      } catch (error) {
        console.error('Error fetching data:', error);
      }
    };

    fetchData();
  }, []);

  return (
    <dataStore.Provider value={data}>
      {props.children}
    </dataStore.Provider>
  );
};

export default CntxtAPI;
```


