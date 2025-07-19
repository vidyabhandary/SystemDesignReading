**gRPC does not natively support REST calls**—it is fundamentally different from REST in both architecture and data format. gRPC is based on **Remote Procedure Call (RPC)** concepts and typically uses **HTTP/2** and **Protocol Buffers (binary serialization)**, while REST uses **HTTP/1.1** with **JSON or XML** over endpoints as resources.

#### gRPC uses:

- HTTP/2 as the transport protocol
- Protocol Buffers (protobuf) for serialization
- Binary format for message encoding
- Specific gRPC client libraries to make calls

#### REST uses:

- HTTP/1.1 or HTTP/2
- JSON, XML, or other text-based formats
- Human-readable message format
- Standard HTTP methods (GET, POST, PUT, DELETE)

However, **it is possible to expose RESTful endpoints alongside gRPC services** by introducing a proxy or gateway. A common approach is using tools like the **gRPC REST Gateway**, which maps RESTful HTTP/JSON requests to gRPC calls. This gateway sits between the client and the gRPC server and translates REST/HTTP requests into gRPC, allowing REST clients to interact with the same backend. For example, in Go, you can annotate your gRPC service definitions to specify how HTTP REST calls should be mapped to gRPC methods. The gateway then handles the conversion:

- **REST client** sends an HTTP request (e.g., POST, GET, with JSON payload).
- **Gateway** translates the request into a gRPC call as defined by your protobuf mappings.
- **gRPC service** processes the request and returns a response, which the gateway then translates back to HTTP/JSON for the client.

**Key points:**
- gRPC servers do not by default accept or process REST/HTTP/JSON calls.
- A proxy, such as gRPC REST Gateway, is required to map and translate REST calls to gRPC.
- Both interfaces can be offered from the same server by routing standard HTTP requests to REST handlers and gRPC (HTTP/2, application/grpc) to the gRPC server.

| Feature                    | Supported in gRPC                   |
| -------------------------- | ----------------------------------- |
| Native REST calls          | ❌ No                                |
| Bridging with gRPC-Gateway | ✅ Yes (via proxy)                   |
| HTTP/2 support             | ✅ Yes                               |
| JSON payloads              | ❌ No (protobuf only) unless bridged |

In summary, **gRPC itself does not allow REST calls directly, but with proper tooling and configuration, you can offer a RESTful API on top of your gRPC services** to support both clients.

[1] https://aws.amazon.com/compare/the-difference-between-grpc-and-rest/

[2] https://blog.postman.com/grpc-vs-rest/

[3] https://www.ibm.com/think/topics/grpc-vs-rest

