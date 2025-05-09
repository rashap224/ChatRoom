chatRoomCpp
Project Description
chatRoomCpp is a basic chat room application written in C++ with Boost.Asio for asynchronous network I/O and threading for multi-client handling. It features multiple clients being able to communicate with a server and share messages within a chat room.

Main Features
Asynchronous Communication: Utilizes Boost.Asio to perform non-blocking I/O, where the server can work with many clients at the same time.
Multi-threading: Uses threading to have multiple client sessions in progress at the same time.
Room Management: A minimal room abstraction used to handle connected clients.
Message Handling: Packages message handling code for message encoding, decoding, and dispatching.
Architecture
The following are the core parts of the project:

Session: A representation of a client session, where it deals with communication with an individual client. It reads the incoming messages, dispatches the outgoing messages, and takes care of the client socket.
Room: It is used to represent a chat room and is in charge of handling a collection of related clients. It adds and removes clients, as well as delivers messages to everyone in the room.
Message: It is used to represent an exchanged message among clients. It encodes and decodes the message header and body.
Critical Functionalities
Async I/O
The program employs Boost.Asio for asynchronous I/O, enabling the server to process multiple client connections without blocking. The async_read and async_write functions in the Session class are employed to read data asynchronously from and write data asynchronously to the client socket.

Threading
The program employs threading to process multiple client connections concurrently. Each client session is executed in a distinct thread, enabling the server to process multiple clients concurrently.

Session Management
The Session class is responsible for a client's connection to the chat room. It coordinates the asynchronous reading and writing of messages, and prevents messages from reaching the wrong recipient.

Room Management
The Room class is responsible for managing the chat room. It maintains a list of all connected clients, and supports methods for adding and removing clients, and for sending messages to all members of the room.
