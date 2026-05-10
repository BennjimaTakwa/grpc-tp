# Lab 7 – Introduction to gRPC

**Matter:** SoA and Microservices  
**Teacher:** Dr. Salah Gontara  
**Class:** 4Info — AY: 2025/2026

---

## Overview

This lab implements a **gRPC service** using Node.js, Protocol Buffers (protobuf), and a client that communicates with the server via the gRPC protocol.

### Goals
- Implement a gRPC server that receives requests and returns structured responses.
- Create a client that connects to the gRPC service and sends requests.

---

## Project Structure

```
grpc-tp/
├── hello.proto     # Protobuf service definition
├── server.js       # gRPC server (runs on port 50051)
├── client.js       # gRPC client
├── package.json
└── .gitignore
```

---

## Installation

Make sure [Node.js](https://nodejs.org/en/download) is installed, then:

```bash
npm install
```

---

## Usage

### Start the gRPC server (Terminal 1)

```bash
node server.js
```

Expected output:
```
gRPC Server started on 0.0.0.0:50051
```

### Run the client (Terminal 2)

```bash
node client.js
```

Expected output:
```
Server response : Bonjour, TestUser !
```

---

## Testing with Postman

1. Open Postman → **New → gRPC Request**
2. Set host to `localhost:50051`
3. Import `hello.proto`
4. Select service `Greeter` and method `SayHello`
5. Send the following JSON body:

```json
{ "name": "TestUser" }
```

---

## Tools Used

- [Node.js](https://nodejs.org/)
- [@grpc/grpc-js](https://www.npmjs.com/package/@grpc/grpc-js)
- [@grpc/proto-loader](https://www.npmjs.com/package/@grpc/proto-loader)
- Protocol Buffers (proto3)
