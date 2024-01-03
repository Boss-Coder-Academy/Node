# NodeJS


### Agenda:

**1. Introduction to Node.js**  
    - What is Node.js?    
    - Node.js vs. traditional server-side languages  
    - Understanding npm (Node Package Manager)

**2. Installation**

**3. Getting Started with Node.js**  
    - Creating your first Node.js application  
    - Understanding the event-driven, non-blocking architecture  
    - Working with modules and the `require` statement  

**4. Core Concepts**  
    - Callbacks and Asynchronous Programming  
    - Promises and `async/await`  
    - Event Loop and Event Emitters  

**5. File System Operations**  
    - Reading and writing files  
    - Working with directories  
    - File streaming  

**6. Web Development with Node.js**  
    - Creating a simple HTTP server  
    - Handling HTTP requests and responses  
    - Routing and middleware  
    - Express.js framework  

**7. Scaling and Performance Optimization**  
    - Load balancing  
    - Caching strategies  
    - Profiling and optimizing code  

**8. Advanced Topics**  
    - Streams and Buffers  
    - Worker Threads  
    - Debugging Node.js applications  
    - Profiling and optimizing performance  

**9. Assignments**  


---

## 1. Introduction to Node.js:

### 1.1 What is Node.js?

Node.js is a server-side JavaScript runtime built on the V8 JavaScript engine. It allows developers to execute JavaScript code on the server, enabling the development of scalable and high-performance network applications. Node.js is event-driven and non-blocking, making it particularly suitable for handling concurrent connections and building real-time applications.

### 1.2 Node.js vs. traditional server-side languages:

Node.js differs from traditional server-side languages, such as PHP or Ruby, in its non-blocking nature. Traditional languages often use synchronous, blocking I/O, which can lead to performance bottlenecks in applications with many simultaneous connections. Node.js, on the other hand, uses an event-driven, non-blocking model, making it efficient for handling numerous concurrent operations.

### 1.3 Understanding npm (Node Package Manager):

npm is the default package manager for Node.js, and it simplifies the process of managing dependencies and third-party libraries in Node.js projects. Developers can easily install, update, and remove packages using npm commands.

**Example: Initializing a Node.js Project with npm**

To start a new Node.js project, you can use the following commands:

```bash
# Create a new directory for your project
mkdir my-node-project

# Navigate into the project directory
cd my-node-project

# Initialize a new Node.js project (creates a package.json file)
npm init
```

Running `npm init` will prompt you to provide information about your project, and it will generate a `package.json` file with the project configuration.



## 2. Installation

You have to follow the following steps to install the Node.js on your Windows :

**Step-1: Downloading the Node.js ‘.msi’ installer.**

The first step to installing Node.js on Windows is to download the installer. Visit the official Node.js website i.e.) https://nodejs.org/en/download/ and download the .msi file according to your system environment (32-bit & 64-bit). An MSI installer will be downloaded to your system.

![Alt Text](https://i.postimg.cc/bvVCp7W8/image.png)



**Step 2: Running the Node.js installer.**

Now you need to install the node.js installer on your PC. You need to follow the following steps for the Node.js to be installed:-

- Double-click on the .msi installer.
The Node.js Setup wizard will open.

- Welcome To Node.js Setup Wizard.
Select “Next”

![Alt](https://i.postimg.cc/t4Wp15yL/image.png)



- After clicking “Next”, the End-User License Agreement (EULA) will open.

   - Check “I accept the terms in the License Agreement”

    - Select “Next”

![Alt](https://i.postimg.cc/t4Wp15yL/image.png)



- Destination Folder

Set the Destination Folder where you want to install Node.js and select “Next”

![Alt](https://i.postimg.cc/8kfpQD9p/image.png)



- Custom Setup  
  - Select “Next”

![Alt](https://i.postimg.cc/tTVLfRT8/image.png)


- Ready to Install Node.js.

- The installer may prompt you to “install tools for native modules”. 

  - Select “Install”

![Alt](https://i.postimg.cc/2jQtBKBd/image.png)


- Installing Node.js.

  - Do not close or cancel the installer until the install is complete

  - Complete the Node.js Setup Wizard.

  - Click “Finish”

![Alt](https://i.postimg.cc/4xd2q42w/image.png)


**Step 3: Verify that Node.js was properly installed or not.**

To check that node.js was completely installed on your system or not, you can run the following command in your command prompt or Windows Powershell and test it:-

C:\Users\Admin> node -v


![Alt](https://i.postimg.cc/8czLcc60/image.png)


If node.js was completely installed on your system, the command prompt will print the version of the node.js installed.







## 3. Getting Started with Node.js:

### 3.1 Creating Your First Node.js Application:

To create a simple Node.js application, follow these steps:

**Step 1: Create a new file (e.g., `app.js`):**

```javascript
// app.js
console.log('Hello, Node.js!');
```

**Step 2: Run the Node.js application:**

Open a terminal, navigate to the directory containing `app.js`, and run the following command:

```bash
node app.js
```

**Explanation:**
  
- In this example, we've created a basic Node.js script (`app.js`) that uses the `console.log` statement to output 'Hello, Node.js!' to the console.
- Node.js scripts can be executed using the `node` command followed by the script's filename.


### 3.2 Understanding the Event-Driven, Non-Blocking Architecture:

Node.js is designed to be event-driven and non-blocking, which allows it to handle many concurrent connections efficiently. This is achieved through asynchronous programming using callbacks, promises, and `async/await`.

**Example: Asynchronous Callbacks:**

```javascript
// asyncCallback.js
const fs = require('fs');

// Asynchronous file read operation
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error('Error reading file:', err);
    return;
  }
  console.log('File content:', data);
});

console.log('Reading file...');
```

**Code Explanation:**

**+ const fs = require('fs');:**

1. The required keyword is used to import the 'fs' (file system) module in Node.js.
2. The 'fs' module provides functionality for working with the file system, including file reading and writing operations.

**+ fs.readFile('example.txt', 'utf8', (err, data) => {:**

1. fs.readFile is an asynchronous function that reads the contents of a file.
2. The first argument is the path to the file ('example.txt' in this case).
3. The second argument specifies the file encoding ('utf8' for text files).
4. The third argument is a callback function that will be invoked once the file reading operation is complete.

**+ (err, data) => {:**

1. This is an ES6 arrow function defining the callback.
2. The callback takes two parameters: err for error information and data for the content of the file.

**+ if (err) { console.error('Error reading file:', err); return; }:**

1. Checks if an error occurred during the file reading operation.
2. If an error occurs, it logs the error message to the console and exits the callback early.

**+ console.log('File content:', data);:**

1. If there is no error, it logs the content of the file to the console.


**+ console.log('Reading file...');:**

This line is outside the readFile callback and will be executed immediately after initiating the file reading operation.
Demonstrates the non-blocking nature of Node.js, as this statement is executed while the file is being read asynchronously.


**Example: Promises and `async/await`:**

```javascript
// asyncPromise.js
const fs = require('fs/promises');

async function readFileAsync() {
  try {
    const data = await fs.readFile('example.txt', 'utf8');
    console.log('File content:', data);
  } catch (err) {
    console.error('Error reading file:', err);
  }
}

readFileAsync();
console.log('Reading file asynchronously...');
```

**Code Explanation:**

**+ const fs = require('fs/promises');:**

This time, we're using the 'fs.promises' API, which provides Promise-based versions of the file system functions.

**async function readFileAsync() {:**

Defines an asynchronous function named readFileAsync.

**try { const data = await fs.readFile('example.txt', 'utf8');:**

1. The await keyword is used inside an asynchronous function to wait for the promise returned by fs.promises.readFile to resolve.
2. If successful, the file content is stored in the variable data.



**+ console.log('File content:', data);:**

Logs the content of the file to the console.

**+ } catch (err) { console.error('Error reading file:', err); }:**

If an error occurs during the asynchronous operation, it is caught and logged.

**+ readFileAsync();:**

Invokes the asynchronous function.

**+ console.log('Reading file asynchronously...');:**

This statement is executed immediately after invoking readFileAsync, showcasing the non-blocking behavior of asynchronous operations.






## 4. Core Concepts:

### 4.1 Callbacks and Asynchronous Programming:

Callbacks are functions that are passed as arguments to other functions and are executed once an asynchronous operation is completed. They are a fundamental concept in Node.js, allowing you to handle asynchronous tasks effectively.

**Example: Asynchronous File Reading with Callbacks**

```javascript
// readFileCallback.js
const fs = require('fs');

// Asynchronous file read operation with a callback
function readFileAsync(filePath, callback) {
  fs.readFile(filePath, 'utf8', (err, data) => {
    if (err) {
      callback(err, null);
      return;
    }
    callback(null, data);
  });
}

// Usage of the readFileAsync function
readFileAsync('example.txt', (err, data) => {
  if (err) {
    console.error('Error reading file:', err);
    return;
  }
  console.log('File content:', data);
});

console.log('Reading file asynchronously...');
```

**Breakdown:**

1. **`function readFileAsync(filePath, callback) {`**:

   - Defines a function `readFileAsync` that takes a file path (`filePath`) and a callback function (`callback`) as parameters.

2. **`fs.readFile(filePath, 'utf8', (err, data) => {`**:

   - Uses `fs.readFile` for asynchronous file reading with a callback.
   - Reads the content of the file specified by `filePath` using 'utf8' encoding.

3. **`if (err) { callback(err, null); return; }`**:

   - Checks for errors during file reading.
   - Calls the callback with the error and a `null` data value if an error occurs.

4. **`callback(null, data);`**:

   - Calls the callback with `null` as the error and the file data if no error occurs.

5. **`readFileAsync('example.txt', (err, data) => {`**:

   - Calls `readFileAsync` with the file path ('example.txt') and a callback function.

7. **`if (err) { console.error('Error reading file:', err); return; }`**:

   - Checks for errors in the callback and logs them if present.

8. **`console.log('File content:', data);`**:

   - Logs the content of the file if no error occurs.

9. **`console.log('Reading file asynchronously...');`**:

   - Demonstrates non-blocking behaviour by logging this statement immediately after initiating the file reading operation.

This example illustrates the use of callbacks for asynchronous file reading in Node.js, showcasing the importance of handling asynchronous operations efficiently.

### 4.2 Promises and async/await:

Promises provide a cleaner and more structured way to handle asynchronous operations. The `async/await` syntax simplifies working with promises, making asynchronous code appear more like synchronous code.

**Example: Asynchronous File Reading with Promises and async/await**

```javascript
// readFilePromise.js
const fs = require('fs').promises;

async function readFileAsync(filePath) {
  try {
    const data = await fs.readFile(filePath, 'utf8');
    console.log('File content:', data);
  } catch (err) {
    console.error('Error reading file:', err);
  }
}

// Usage of the readFileAsync function
readFileAsync('example.txt');

console.log('Reading file asynchronously...');
```

**Breakdown:**

1. **`const fs = require('fs').promises;`**:

- Utilizes the `promises` property of the 'fs' module to access Promise-based versions of file system functions.

2. **`async function readFileAsync(filePath) {`**:
 - Defines an asynchronous function `readFileAsync` that takes a file path (`filePath`) as a parameter.

3. **`const data = await fs.readFile(filePath, 'utf8');`**:

- Uses `await` to wait for the promise returned by `fs.readFile` to resolve.
- If successful, the file content is stored in the variable `data`.

4. **`console.log('File content:', data);`**:

- Logs the content of the file.

5.** `} catch (err) { console.error('Error reading file:', err); }`**:

- Catches and logs any errors that occur during the asynchronous operation.

6. **`readFileAsync('example.txt');`**:

- Calls `readFileAsync` with the file path ('example.txt').

7. **`console.log('Reading file asynchronously...');`**:

- Demonstrates non-blocking behaviour by logging this statement immediately after initiating the file reading operation.

This example demonstrates asynchronous file reading using promises and `async/await`, providing a cleaner and more readable alternative to callback-based code.

### 4.3 Event Loop and Event Emitters:

The event loop is a core concept in Node.js that enables handling multiple asynchronous tasks efficiently. Event emitters are objects that emit events, and listeners can be attached to respond to those events.

**Example: Using Event Emitters**

```javascript
// eventEmitterExample.js
const EventEmitter = require('events');

// Create an event emitter instance
const myEmitter = new EventEmitter();

// Register an event listener
myEmitter.on('myEvent', (arg) => {
  console.log('Event triggered with argument:', arg);
});

// Emit the 'myEvent' event
myEmitter.emit('myEvent', 'Hello, Event Emitters!');
```

**Breakdown:**

1. **`const EventEmitter = require('events');`**:

   - Imports the `EventEmitter` class from the 'events' module.

2. **`const myEmitter = new EventEmitter();`**:

   - Creates a new instance of the `EventEmitter` class, named `myEmitter`.

3. **`myEmitter.on('myEvent', (arg) => {`**:

   - Registers an event listener for the 'myEvent' event.
   - The listener takes an argument (`arg`) and logs it to the console.

4. **`myEmitter.emit('myEvent', 'Hello, Event Emitters!');`**:

   - Emits the 'myEvent' event with the argument 'Hello, Event Emitters!'.
   - This triggers the previously registered listener.

5. **Output**:

   ``` bash
   Event triggered with argument: Hello, Event Emitters!
   ```

This example demonstrates the basic usage of event emitters. Events and listeners provide a powerful mechanism for building scalable and modular applications in Node.js. The event loop ensures that these events are handled asynchronously, contributing to the non-blocking nature of Node.js.










## 5. File System Operations:

### 5.1 Reading and Writing Files:

**- Reading and Writing Files Synchronously:**

Synchronous file operations in Node.js can be performed using `fs.readFileSync` for reading and `fs.writeFileSync` for writing. These operations block the execution of the program until the file operation is completed.

**Example: Reading and Writing Files Synchronously**

```javascript
// fileOperationsSync.js
const fs = require('fs');

// Reading a file synchronously
try {
  const data = fs.readFileSync('input.txt', 'utf8');
  console.log('Read file synchronously:', data);
} catch (err) {
  console.error('Error reading file synchronously:', err);
}

// Writing to a file synchronously
try {
  fs.writeFileSync('output.txt', 'Hello, Node.js!');
  console.log('Write to file synchronously successful');
} catch (err) {
  console.error('Error writing to file synchronously:', err);
}
```

**Example explanation:**

- `fs.readFileSync` reads the content of 'input.txt' synchronously, and the content is logged to the console.
- `fs.writeFileSync` writes 'Hello, Node.js!' to 'output.txt' synchronously, and a success message is logged.

- Reading and Writing Files Asynchronously:

Asynchronous file operations in Node.js use `fs.readFile` for reading and `fs.writeFile` for writing. These operations do not block the program execution and use callback functions to handle the result or errors.


**Example: Reading and Writing Files Asynchronously**

```javascript
// fileOperationsAsync.js
const fs = require('fs');

// Reading a file asynchronously
fs.readFile('input.txt', 'utf8', (err, data) => {
  if (err) {
    console.error('Error reading file asynchronously:', err);
    return;
  }
  console.log('Read file asynchronously:', data);
});

// Writing to a file asynchronously
const contentToWrite = 'Hello, Node.js!';
fs.writeFile('output.txt', contentToWrite, (err) => {
  if (err) {
    console.error('Error writing to file asynchronously:', err);
    return;
  }
  console.log('Write to file asynchronously successful');
});
```

**In this example:**

- `fs.readFile` reads the content of 'input.txt' asynchronously, and the content is logged in the callback.
- `fs.writeFile` writes 'Hello, Node.js!' to 'output.txt' asynchronously, and a success message is logged in the callback.

### 5.2 Working with Directories:

Working with directories involves creating directories using `fs.mkdir` and reading the contents of a directory using `fs.readdir`.

**Example: Creating and Reading Directories**

```javascript
// directoryOperations.js
const fs = require('fs');

// Creating a directory
fs.mkdir('myDirectory', (err) => {
  if (err) {
    console.error('Error creating directory:', err);
    return;
  }
  console.log('Directory created successfully');
});

// Reading the contents of a directory
fs.readdir('myDirectory', (err, files) => {
  if (err) {
    console.error('Error reading directory:', err);
    return;
  }
  console.log('Files in the directory:', files);
});
```

**Example Explanation:**

- `fs.mkdir` creates a directory named 'myDirectory' asynchronously, and a success message is logged in the callback.
- `fs.readdir` reads the contents of 'myDirectory' asynchronously, and the files in the directory are logged in the callback.

### 5.3 File Streaming:

File streaming in Node.js allows you to work with large files or data streams without loading the entire content into memory. This is achieved using the `fs.createReadStream` and `fs.createWriteStream` methods.

**Example: File Streaming**

```javascript
// fileStreaming.js
const fs = require('fs');

// Create a readable stream
const readableStream = fs.createReadStream('largeFile.txt', 'utf8');

// Create a writable stream
const writableStream = fs.createWriteStream('outputStream.txt');

// Pipe the readable stream to the writable stream
readableStream.pipe(writableStream);

// Handle events on the writable stream
writableStream.on('finish', () => {
  console.log('File streaming complete');
});

// Handle errors on the readable stream
readableStream.on('error', (err) => {
  console.error('Error reading file:', err);
});

// Handle errors on the writable stream
writableStream.on('error', (err) => {
  console.error('Error writing to file:', err);
});
```

**Example Explanation:**

- `fs.createReadStream` creates a readable stream from 'largeFile.txt'.
- `fs.createWriteStream` creates a writable stream to 'outputStream.txt'.
- `readableStream.pipe(writableStream)` pipes the content from the


## 6. Web Development with Node.js

### 6.1. Creating a Simple HTTP Server:

Creating an HTTP server in Node.js involves using the built-in `http` module. Below is a simple example of creating an HTTP server that listens on a specified port.

**Example: Creating a Simple HTTP Server**

```javascript
// simpleServer.js
const http = require('http');

// Create an HTTP server
const server = http.createServer((req, res) => {
  // Set the response header
  res.writeHead(200, { 'Content-Type': 'text/plain' });

  // Send a response to the client
  res.end('Hello, World!\n');
});

// Listen on port 3000
const PORT = 3000;
server.listen(PORT, () => {
  console.log(`Server running at http://localhost:${PORT}/`);
});
```

**Explanation:**

- This example uses the `http.createServer` method to create an HTTP server.
- The server listens for incoming requests, and the callback function is executed for each request.
- The `res.writeHead` method sets the HTTP status code to 200 (OK) and the content type to plain text.
- The `res.end` method sends the response to the client and closes the connection.



### 6.2. Handling HTTP Requests and Responses:

Handling HTTP requests and responses involves processing client requests and sending appropriate responses. The following example demonstrates handling different types of HTTP requests (GET and POST) and responding accordingly.

**Example: Handling HTTP Requests and Responses**

```javascript
// requestResponseHandler.js
const http = require('http');

const server = http.createServer((req, res) => {
  // Log the request method and URL
  console.log(`Received ${req.method} request for ${req.url}`);

  // Set the response header
  res.writeHead(200, { 'Content-Type': 'text/plain' });

  // Handle different HTTP methods
  if (req.method === 'GET') {
    res.end('This is a GET request\n');
  } else if (req.method === 'POST') {
    let body = '';
    req.on('data', (chunk) => {
      body += chunk;
    });

    req.on('end', () => {
      res.end(`This is a POST request with data: ${body}\n`);
    });
  } else {
    res.end('Unsupported HTTP method\n');
  }
});

const PORT = 3000;
server.listen(PORT, () => {
  console.log(`Server running at http://localhost:${PORT}/`);
});
```

**Explanation:**

- This example logs the request method and URL to the console.
- The server responds differently based on the HTTP method:
  - For a GET request, it sends a simple message.
  - For a POST request, it collects and echoes back the data sent in the request body.
  - For any other method, it responds with an "Unsupported HTTP method" message.


### 6.3. Routing and Middleware:

Routing involves directing incoming requests to specific handlers based on the requested URL. Middleware functions can be used to perform actions before reaching the final request handler. The following example demonstrates basic routing and middleware concepts.

**Example: Routing and Middleware**

```javascript
// routingMiddleware.js
const http = require('http');

// Middleware function
const logMiddleware = (req, res, next) => {
  console.log(`Received ${req.method} request for ${req.url}`);
  next(); // Call the next middleware or route handler
};

// Route handler
const homeHandler = (req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('Welcome to the home page!\n');
};

const aboutHandler = (req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('This is the about page.\n');
};

// Create an HTTP server
const server = http.createServer((req, res) => {
  // Use the log middleware
  logMiddleware(req, res, () => {
    // Route requests based on URL
    if (req.url === '/') {
      homeHandler(req, res);
    } else if (req.url === '/about') {
      aboutHandler(req, res);
    } else {
      res.writeHead(404, { 'Content-Type': 'text/plain' });
      res.end('Not Found\n');
    }
  });
});

const PORT = 3000;
server.listen(PORT, () => {
  console.log(`Server running at http://localhost:${PORT}/`);
});
```

**Explanation:**

- Middleware functions, like `logMiddleware`, can perform actions before passing control to the next handler.
- Route handlers, such as `homeHandler` and `aboutHandler`, are responsible for generating responses based on the requested URL.
- The server routes requests to the appropriate handler based on the


## 7. Scaling and Performance Optimization:

### 7.1 Load Balancing:

Load balancing involves distributing incoming network traffic across multiple servers to ensure no single server bears too much load, thus enhancing reliability and responsiveness.

**Example 7.1**: Load Balancing with Nginx

In this example, Nginx is used as a reverse proxy and load balancer for distributing traffic to multiple Node.js servers.

**Nginx Configuration:**

```nginx
# nginx.conf

http {
    upstream nodejs_servers {
        server localhost:3001;
        server localhost:3002;
        server localhost:3003;
        # Add more servers as needed
    }

    server {
        listen 80;

        location / {
            proxy_pass http://nodejs_servers;
            proxy_http_version 1.1;
            proxy_set_header Upgrade $http_upgrade;
            proxy_set_header Connection 'upgrade';
            proxy_set_header Host $host;
            proxy_cache_bypass $http_upgrade;
        }
    }
}
```

**Explanation:**

- Nginx is configured to listen on port 80 and act as a reverse proxy for multiple Node.js servers.
- The `upstream` directive defines a group of backend servers (`localhost:3001`, `localhost:3002`, `localhost:3003`).
- Requests are distributed among these servers using the `proxy_pass` directive.

**Usage:**

1. Start multiple Node.js servers on ports `3001`, `3002`, `3003`.
2. Configure Nginx with the provided configuration.
3. Make requests to Nginx (e.g., `http://localhost/`), and Nginx will distribute traffic among the Node.js servers.



### 7.2 Caching Strategies:

Caching involves storing copies of frequently accessed data to reduce response time and alleviate server load. In Node.js, caching can be implemented at various levels, such as in-memory caching or using external caching systems like Redis.

**Example 7.2**: In-Memory Caching with `memory-cache`

```javascript
// server.js
const express = require('express');
const cache = require('memory-cache');

const app = express();

// Middleware for in-memory caching
const cacheMiddleware = (req, res, next) => {
  const key = '__express__' + req.originalUrl || req.url;
  const cachedData = cache.get(key);

  if (cachedData) {
    res.send(cachedData);
  } else {
    res.sendResponse = res.send;
    res.send = (body) => {
      cache.put(key, body, 10000); // Cache data for 10 seconds
      res.sendResponse(body);
    };
    next();
  }
};

// Use caching middleware for specific routes
app.get('/cached-route', cacheMiddleware, (req, res) => {
  // Simulate data fetching
  const data = { message: 'Data from the server' };
  res.json(data);
});

// Start the server
const PORT = 3000;
app.listen(PORT, () => {
  console.log(`Server running at http://localhost:${PORT}`);
});
```

**Explanation:**

- This example uses the `memory-cache` library for in-memory caching.
- The `cacheMiddleware` middleware checks if the requested data is in the cache; if yes, it sends the cached data.
- If the data is not in the cache, it fetches the data, caches it, and sends the response.

**Usage:**

1. Install the `memory-cache` library using `npm install memory-cache`.
2. Run the provided `server.js` script.
3. Make requests to `http://localhost:3000/cached-route`. The first request will fetch data from the server, and subsequent requests within 10 seconds will retrieve the cached data.


### 7.3 Profiling and Optimizing Code:

Profiling involves analyzing the performance of a Node.js application to identify bottlenecks and areas for optimization.

**Example 7.3**: Profiling and Optimizing Code with `clinic`

```bash
# Install the clinic package globally
npm install -g clinic

# Run the clinic doctor to profile your Node.js application
clinic doctor -- node your-app.js
```

**Explanation:**

- The `clinic` package provides tools for profiling and visualizing Node.js applications.
- The `clinic doctor` command analyses your application's performance and generates a report.

**Usage:**

1. Install `clinic` globally using `npm install -g clinic`.
2. Run your Node.js application with the `clinic doctor` command.
3. Open the generated report in a web browser to visualize and analyze the performance of your application.

Note: Profiling tools can vary, and other tools like `profiler` and `New Relic` can also be used for profiling and optimizing Node.js applications.






## 8. Advanced Topics:

### 8.1 Streams and Buffers:

**Streams** and **buffers** are fundamental concepts in Node.js for handling data efficiently, especially when dealing with large datasets or real-time applications.

**Example 8.1**: Streaming Data with `fs` and `createReadStream`

```javascript
// streamExample.js
const fs = require('fs');

// Create a readable stream from a file
const readableStream = fs.createReadStream('largeFile.txt', 'utf8');

// Create a writable stream to a new file
const writableStream = fs.createWriteStream('outputStream.txt');

// Pipe the readable stream to the writable stream
readableStream.pipe(writableStream);

// Handle events on the writable stream
writableStream.on('finish', () => {
  console.log('File streaming complete');
});

// Handle errors on the readable stream
readableStream.on('error', (err) => {
  console.error('Error reading file:', err);
});

// Handle errors on the writable stream
writableStream.on('error', (err) => {
  console.error('Error writing to file:', err);
});
```

**Explanation:**

- `createReadStream` and `createWriteStream` are used to create readable and writable streams, respectively.
- `pipe` is used to pipe the content from the readable stream to the writable stream.
- Events like `'finish'` and `'error'` are handled to determine when the streaming is complete or if there are any errors.

**Usage:**

1. Create a large file named `largeFile.txt` with some content.
2. Run the `streamExample.js` script.
3. The content of `largeFile.txt` will be streamed to a new file named `outputStream.txt`.



### 8.2 Worker Threads:

**Worker threads** in Node.js allow parallel execution of JavaScript code, leveraging multi-core systems for better performance.

**Example 8.2**: Using Worker Threads

```javascript
// main.js
const { Worker, isMainThread, parentPort } = require('worker_threads');

if (isMainThread) {
  // This code runs in the main thread
  const worker = new Worker(__filename);

  // Listen for messages from the worker thread
  worker.on('message', (message) => {
    console.log('Received message from worker:', message);
  });

  // Send a message to the worker thread
  worker.postMessage('Hello from the main thread');
} else {
  // This code runs in the worker thread
  parentPort.on('message', (message) => {
    console.log('Received message from main thread:', message);

    // Send a message back to the main thread
    parentPort.postMessage('Hello from the worker thread');
  });
}
```

**Explanation:**

- The `Worker` class is used to create a new worker thread.
- The `isMainThread` property is used to determine whether the code is running in the main thread or a worker thread.
- Communication between the main thread and the worker thread is achieved using the `postMessage` and `on('message', ...)` methods.

**Usage:**

1. Run the `main.js` script.
2. The main thread creates a worker thread, sends a message to it, and listens for messages from it.
3. The worker thread listens for messages from the main thread, processes the message, and sends a response back to the main thread.


### 8.3 Debugging Node.js Applications:

Debugging in Node.js can be done using the built-in `debugger` statement, or by using more advanced tools like `VSCode` or `Chrome DevTools`.

**Example 8.3: Debugging with VSCode**

1. Add the following line to your Node.js script where you want to set a breakpoint:

```javascript
debugger;
```

2. Run your script with the `--inspect` flag:

```bash
node --inspect your-script.js
```

3. Open VSCode and go to the "Run and Debug" tab.
4. Click on the green play button or press F5 to start debugging.
5. The VSCode debugger will stop at the `debugger` statement, allowing you to inspect variables, set breakpoints, and step through code.




### 8.4 Profiling and Optimizing Performance:

**Profiling** involves analyzing the performance of a Node.js application to identify bottlenecks and areas for optimization.

**Example 8.4**: Profiling with `clinic`

```bash
# Install the clinic package globally
npm install -g clinic

# Run the clinic doctor to profile your Node.js application
clinic doctor -- node your-app.js
```

**Explanation:**

- The `clinic` package provides tools for profiling and visualizing Node.js applications.
- The `clinic doctor` command analyzes your application's performance and generates a report.

**Usage:**
1. Install `clinic` globally using `npm install -g clinic`.
2. Run your Node.js application with the `clinic doctor` command.
3. Open the generated report in a web browser to visualize and analyze the performance of your application.

**Note:** Profiling tools can vary, and other tools like `profiler` and `New Relic` can also be used for profiling and optimizing Node.js applications.

These examples cover advanced topics in Node.js, including streams and buffers, worker threads, debugging, and performance optimization. These concepts are crucial for building scalable and high-performance Node.js applications.




## 9. Assignment

**Task 1: Create a Signup page using node NodeJS**

**Desired Output:**

![Alt](https://i.postimg.cc/Ls7sLswW/image.png)


- Design the following file structure with these relevant files and folders

![ALt](https://i.postimg.cc/yxLt3Drg/image.png)

- Now install the following modules and dependencies
  - Express
  - Ejs
  - Bcrypt
  - Fs

also, install Nodemon: npm i --save-dev nodemon

- And write the following code in the different files as follows:

**index.ejs**

```html
<html>
<head>
  <title>User Login</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f2f2f2;
      margin: 0;
      padding: 0;
    }


    .heading {
      text-align: center;
      margin-top: 200px;
    }


    .heading h1 {
      color: #333;
    }
  </style>
</head>
<body>
  <div class="heading">
    <h1>Welcome</h1>
  </div>
</body>
</html>

```


**LoginPage.js**

```html
const express = require("express");
const app = express();
const bcrypt = require("bcrypt");
const fs = require("fs");


const usersDataFile = "./users.json";


app.use(express.urlencoded({ extended: true }));


app.listen(3000, () => {
  console.log("Server started on port 3000");
});


app.get("/", (req, res) => {
  res.render("index.ejs");
});


app.set("view engine", "ejs");


// Register route
app.get("/register", (req, res) => {
  res.render("register.ejs", { error: null });
});


app.post("/register", async (req, res) => {
  try {
    const { name, email, password } = req.body;


    if (!name || !email || !password) {
      return res.render("register.ejs", {
        error: "Please enter all fields.",
      });
    }


    const hashedPassword = await bcrypt.hash(password, 10);


    const user = {
      id: Date.now().toString(),
      name,
      email,
      password: hashedPassword,
    };


    const usersData = JSON.parse(fs.readFileSync(usersDataFile));
    usersData.push(user);


    fs.writeFileSync(usersDataFile, JSON.stringify(usersData));


    res.redirect("/login");
  } catch (error) {
    console.log(error);
    res.redirect("/register");
  }
});


```

**register.ejs**


```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>User Register</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      margin: 0;
      padding: 0;
      background: url('https://i.redd.it/how-can-someone-make-this-background-with-html-and-css-i-v0-zjgs096khv591.jpg?s=44a32b2f6835cde7290c4610dc01d5fa0c082ad9') center center fixed;
      background-size: cover;
      height: 100vh;
      overflow: hidden;
    }


    .register-box {
      width: 400px;
     
      margin: 0 auto;
      padding: 20px;
      background-color: rgba(0, 0, 0, 0.8);
      border: 1px solid #ccc;
      border-radius: 4px;
      margin-top: 50vh; /* Adjusted margin-top */
      transform: translateY(-50%); /* Center the login box */
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      color: #fff;
    }


    .register-box .heading {
      text-align: center;
      margin-bottom: 20px;
    }


    .register-box .heading h1 {
      color: #e50914;
    }


    .register-box form label {
      display: block;
      margin-bottom: 10px;
      color: #ccc;
    }


    .register-box form input[type="text"],
    .register-box form input[type="email"],
    .register-box form input[type="password"] {
      width: 95%;
      padding: 10px;
      margin-bottom: 20px;
      border: 1px solid #ccc;
      border-radius: 4px;
      background-color: #fff;
      color: #333;
    }


    .register-box form button[type="submit"] {
      width: 100%;
      padding: 10px;
      background-color: #e50914;
      color: #fff;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }


    .register-box form button[type="submit"]:hover {
      background-color: #45a049;
    }


    .register-box a {
      color: #ccc;
      text-decoration: none;
      display: block;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="register-box">
    <div class="heading">
      <h1>Register</h1>
    </div>
    <div>
      <% if (error) { %>
        <p><%= error %></p>
      <% } %>
      <form action="/register" method="POST">
        <label for="name">Name&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</label>
        <input type="text" id="name" name="name" required><br><br>
        <label for="email">Email &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</label>
        <input type="email" id="email" name="email" required><br><br>
        <label for="password">Password</label>
        <input type="password" id="password" name="password" required><br><br>
        <button type="submit">Register</button>
      </form>
    </div><br>
    <a href="/login">Login Page</a><br><br>
  </div>
</body>
</html>

```



**Task 2**: Create a Login page using NodeJS


**Desired Output:**

![Alt](https://i.postimg.cc/zfLzzrvF/image.png)
