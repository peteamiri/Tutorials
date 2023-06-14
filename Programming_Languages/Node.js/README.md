## Sample Code

```Javascript
const http = require('http');

// Create a server object
const server = http.createServer((req, res) => {
  // Set the response header
  res.writeHead(200, { 'Content-Type': 'text/plain' });

  // Write a response to the client
  res.end('Hello, world!');
});

// Start the server
const port = 3000;
server.listen(port, () => {
  console.log(`Server running on port ${port}`);
});

```
In this example, we're using the built-in http module in Node.js to create a server. The server listens for incoming HTTP requests and responds with "Hello, world!".

We create the server using the createServer method and provide a callback function that takes in a request object (req) and a response object (res). Inside the callback function, we set the response header using writeHead to indicate a successful response with a content type of plain text.

We then send the response content using end with the string `Hello, world!`.

Finally, we start the server by calling the listen method and specifying the port number to listen on (in this case, port 3000). Once the server is running, a message is printed to the console.

You can run this code using Node.js by saving it to a file (e.g., server.js) and executing node server.js in the command line.
