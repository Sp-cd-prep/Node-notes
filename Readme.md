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

#### Making HTTP Requests in Node.js:

- **Using the `http` module (Built-in):**

    ```javascript
    const http = require('http');

    const options = {
      hostname: 'www.example.com',
      port: 80,
      path: '/',
      method: 'GET',
    };

    const req = http.request(options, (res) => {
      let data = '';

      res.on('data', (chunk) => {
        data += chunk;
      });

      res.on('end', () => {
        console.log(data);
      });
    });

    req.on('error', (error) => {
      console.error(error);
    });

    req.end();
    ```

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



### 4. HTTP Requests:

HTTP requests are messages sent by a client to initiate an action on the server. The most common types of HTTP requests are:

- **GET:** Retrieve data from the server.
- **POST:** Send data to the server to create a new resource.
- **PUT:** Send data to the server to update a resource.
- **DELETE:** Request the removal of a resource.

#### Code Example (Simple HTTP GET Request using `http` module):

```javascript
const http = require('http');

const options = {
  hostname: 'www.example.com',
  port: 80,
  path: '/',
  method: 'GET',
};

const req = http.request(options, (res) => {
  let data = '';

  // A chunk of data has been received.
  res.on('data', (chunk) => {
    data += chunk;
  });

  // The whole response has been received.
  res.on('end', () => {
    console.log(data);
  });
});

req.end();
```

#### Explanation:

- **`http.request(options, callback)`:** Initiates an HTTP request. `options` specify details like the hostname, port, path, and method. The `callback` function handles the response.

- **Event: `'data'`:** The `'data'` event is emitted when a chunk of data is received. Concatenate these chunks to build the complete response.

- **Event: `'end'`:** The `'end'` event is emitted when the entire response has been received.

- **`req.end()`:** Sends the request.

These topics provide a foundational understanding of creating a basic server, working with modules, understanding HTTP status codes, and making HTTP requests. If you have any questions or need more clarification on any part, feel free to ask!

### How to perform routing with get 

```javascript 
const http = require('http');
// const url = require('url');

const server = http.createServer((req, res) => {
 
  if (req.url === '/') {
    res.writeHead(200, { 'Content-Type': 'text/plain' });
    res.end('This is the home page');
  } else if (req.url === '/about') {
    res.writeHead(200, { 'Content-Type': 'text/plain' });
    res.end('About us');
  } else {
    notFound(res);
  }
})

// Start the server on port 3000
server.listen(4100, () => {
  console.log('Server running at http://localhost:3000/');
});
```