# IN11. Networking and the server side of the web

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 6. Advanced computer science and GPU | IN06 | IN15, SY04 |

## Why this module

The project's API server, its web chat and its artifact server are written on raw sockets, and the data pipeline downloads files with a hand-written HTTP client. Streaming tokens as they are generated uses chunked transfer and Server-Sent Events, file uploads use multipart forms, and plug-ins talk JSON-RPC. This module teaches networking and HTTP from the socket up.

## Objectives

After this module, you can explain how data travels across a network, write TCP clients and servers, implement HTTP/1.1 by hand on both sides, stream responses, and reason about latency and bandwidth.

## Competences evaluated

1. Explain the layers of the TCP/IP model (link, internet, transport, application) and what IP addresses, ports, DNS and routing do.
2. Explain TCP (connections, reliability, ordering, flow control) versus UDP, and the cost of latency and round trips.
3. Write TCP clients and servers with sockets, handling partial reads and writes, timeouts and closed connections.
4. Serve many clients at once with threads, `selectors` or `asyncio`, and compare the approaches.
5. Implement HTTP/1.1 requests and responses by hand: request line, headers, status codes, bodies, `Content-Length`, keep-alive.
6. Implement chunked transfer encoding and range requests (for resumable downloads), on the client and the server.
7. Parse multipart/form-data uploads.
8. Stream events to a browser with Server-Sent Events.
9. Implement JSON-RPC requests, responses, errors and notifications over a socket or standard input and output.
10. Measure latency and throughput, and explain the effect of payload size, round trips and buffering.

## Notions, in learning order

1. **Networks**: packets, layers, IP addresses, ports, DNS, routing (overview).
2. **Transport**: TCP and UDP, connection setup, reliability, congestion and flow control (overview), latency versus bandwidth.
3. **Sockets**: the BSD socket API from C and Python, blocking and non-blocking modes, partial I/O, timeouts.
4. **Concurrency for servers**: thread per connection, event loops with `selectors`, `asyncio` servers.
5. **HTTP/1.1**: message format, methods, headers, status codes, persistent connections.
6. **Bodies**: content length, chunked encoding, ranges, compression headers (decoding comes in the LLM plan).
7. **Forms and uploads**: URL encoding, multipart/form-data.
8. **Streaming to browsers**: Server-Sent Events, event formats, reconnection.
9. **RPC**: JSON-RPC 2.0 over sockets and standard streams.
10. **Performance**: measuring latency and throughput, buffering, Nagle's algorithm (first look).

## Practice

- An HTTP/1.1 static file server written on raw sockets, tested with a browser and with `curl`.
- An HTTP client that downloads a large file with range requests and resumes after interruption (on plain HTTP for now; TLS comes in IN14 and L39).
- A Server-Sent Events endpoint that streams generated text to the IN08 page.
- A JSON-RPC calculator server with a client, over standard input and output.

## Evaluation format

One practical session, about 3 hours: implement server and client features never built during learning (a different HTTP feature set each time), plus questions on TCP and HTTP. Pass mark 100 %.

## References

- James F. Kurose and Keith W. Ross, *Computer Networking: A Top-Down Approach* (book, not free).
- Brian "Beej" Hall, *Beej's Guide to Network Programming* (free).
- RFC 9110 and RFC 9112 (HTTP semantics and HTTP/1.1), the HTML Living Standard section on Server-Sent Events, and the JSON-RPC 2.0 specification (all free).
