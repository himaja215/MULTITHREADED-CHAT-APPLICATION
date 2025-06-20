# MULTITHREADED-CHAT-APPLICATION

*COMPANY* : CODETECH IT SOLUTIONS

*NAME* : KONDAKAYALA REDDY HIMAJA 

*INTERN ID* : CT04DF358

*DURATION* : 4-WEEKS

*MENTOR* : NEELA SANTOSH

*DESCRIPTION * :

The given Java program implements a simple multithreaded chat server named ChatServer that allows multiple clients to connect and communicate with each other in real-time. It uses java.net for networking and java.io for input-output operations. The server listens on port 5678 and uses a ServerSocket to accept incoming client connections. Each new connection is handled by a dedicated thread, managed by an inner class called ClientHandler, which extends the Thread class. This design ensures that each client can send and receive messages independently without blocking other clients, enabling real-time chat functionality.

When a client connects, the server prints a message on the console indicating a new client connection and then starts a new ClientHandler thread for that client. Inside the ClientHandler, input and output streams (BufferedReader and PrintWriter) are set up to read messages from and send messages to the connected client. Each client's output stream is stored in a shared Set<PrintWriter> called clientWriters, which keeps track of all active clients. This set is synchronized to prevent concurrency issues when multiple threads modify it simultaneously.

The server first reads the client’s name and welcomes them with a broadcast message to all connected clients. Then, it enters a loop to continuously read messages from the client and broadcast them to all other connected clients in the format [name]: message. The broadcast() method is used to send messages to every client by iterating through the clientWriters set and printing the message to each client’s output stream. Synchronization ensures thread safety when accessing the shared set of writers.

If a client disconnects (e.g., closes the application), an IOException is caught, the client socket is closed, and the client’s writer is removed from the clientWriters set. A message is then broadcast to all remaining users informing them that the user has left the chat. The program provides a solid demonstration of how multithreading and socket programming can be used to create a real-time chat server. It manages multiple clients effectively, handles disconnections gracefully, and keeps the user experience consistent by broadcasting updates to all users. While the current version is basic, features such as private messaging, authentication, and message history could be added to make it more robust and production-ready.


*OUTPUT* :

