C++ Chat Room Application
This is a basic chat room application written in C++ using Boost.Asio for asynchronous network I/O and multi-threading for handling multiple clients simultaneously. It allows multiple clients to connect to a central server and exchange messages in real time within a shared chat room.

🚀 Features
Asynchronous Communication:
Utilizes Boost.Asio to perform non-blocking I/O, allowing the server to handle many client connections concurrently without blocking operations.

Multi-threading:
Each client session runs in a separate thread to ensure smooth concurrent communication with multiple clients.

Room Management:
Implements a simple room abstraction that manages all connected clients and facilitates message broadcasting.

Message Handling:
Encodes, decodes, and dispatches messages between clients efficiently using structured message handling logic.

🧱 Architecture Overview
1. Session
Represents an individual client session. It handles:

Reading incoming messages asynchronously.

Sending outgoing messages asynchronously.

Managing the client's socket connection.

2. Room
Acts as a chat room managing a collection of clients. It:

Adds/removes clients.

Delivers messages to all connected clients.

3. Message
Represents the message exchanged between clients. It:

Encodes and decodes message headers and bodies.

Prepares messages for safe transmission over the network.

🔧 Key Functionalities
✅ Asynchronous I/O
Uses async_read and async_write from Boost.Asio to handle non-blocking message transfers.

Ensures high scalability by not blocking on I/O operations.

✅ Multi-threading
Each session runs on a dedicated thread.

Enables concurrent message handling across multiple clients.

✅ Session Management
The Session class:

Manages individual client communication.

Ensures messages are correctly routed.

Prevents cross-client message interference.

✅ Room Management
The Room class:

Maintains an active list of client sessions.

Supports broadcasting messages to all members.

Handles client join and leave operations.

📦 Dependencies
Boost C++ Libraries (specifically Boost.Asio)

C++11 or higher
