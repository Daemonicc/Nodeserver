const http = require('http');

const host = 'localhost';
const port = 3000;

//Parse request body parameter
const parseBody = function (request, callback) {
  let body = '';
  request.on('data', (chunk) => {
    body += chunk.toString();
  });
  request.on('end', () => {
    callback(JSON.parse(body));
  });
};

const requestListener = function (req, res) {
  if (req.url === '/' && req.method === 'GET') {
    res.writeHead(200);
    res.end('Hello World, Welcome to WeJapa Internships');
  }
  if (req.url === '/' && req.method === 'POST') {
    res.writeHead(200);
    parseBody(req, (result) => {
      res.end(`Hello ${result.name}, Welcome to WeJapa Internships`);
    });
  }
};

const server = http.createServer(requestListener);

server.listen(port, host, () => {
  console.log(`Server is running on http://${host}:${port}`);
});
