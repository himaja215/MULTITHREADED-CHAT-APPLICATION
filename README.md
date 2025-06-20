# MULTITHREADED-CHAT-APPLICATION

*COMPANY* : CODETECH IT SOLUTIONS

*NAME* : KONDAKAYALA REDDY HIMAJA 

*INTERN ID* : CT04DF358

*DURATION* : 4-WEEKS

*MENTOR* : NEELA SANTOSH

*DESCRIPTION FOR SERVER* :

The given Java program implements a multithreaded chat server named ChatServer that allows multiple clients to connect and exchange messages in real time. It listens on port 5678 using a ServerSocket, and each time a new client connects, a new thread (ClientHandler) is created to manage that client’s communication. The server prints a message on the console whenever a new client connects. Each ClientHandler maintains input and output streams to receive messages from and send messages to the connected client. The program uses a Set<PrintWriter> called clientWriters to keep track of all active clients’ output streams, which allows the server to broadcast messages to all connected users.

When a client connects, it is prompted to send its name, which is read and used for personalizing messages. The server then sends a welcome message to all clients. After that, any message sent by a client is broadcast to everyone in the format [name]: message. The broadcast() method ensures that all connected clients receive the message by iterating over the clientWriters set. To ensure thread safety while accessing the shared set, synchronization blocks are used. If a client disconnects or an error occurs, the server logs the disconnection, removes the client from the active writer set, and broadcasts a message indicating that the user has left the chat. This program is a basic yet effective demonstration of socket programming and multithreading in Java, providing real-time communication between multiple clients through a centralized server.


*DESCRIPTION FOR CLIENT* :

The given Java program ChatClient is a client-side implementation of a multithreaded chat application that connects to a server running on localhost at port 5678. Once connected, it enables the user to send and receive real-time messages. The program starts by establishing a socket connection to the server and initializing necessary input/output streams: a BufferedReader for user input from the console, a PrintWriter for sending messages to the server, and another BufferedReader for receiving messages from the server. Upon a successful connection, the user is prompted to enter their name, which is immediately sent to the server to identify the user in the chat.

To handle incoming messages without interrupting user input, the program launches a separate thread (readThread) that continuously reads messages from the server and displays them on the console. This allows the client to receive and display messages asynchronously, even while the user is typing. Simultaneously, the main thread is used to read user input and send it to the server. If the user types "exit", the client breaks out of the loop and closes the socket connection, effectively leaving the chat.

The client handles exceptions gracefully, displaying error messages if the server connection fails or is lost. Overall, this program provides a basic but functional client for a chat application, demonstrating key concepts such as multithreading, socket programming, user interaction, and stream handling in Java. It works in tandem with the ChatServer program to enable real-time group communication between multiple clients connected to the same server.



*OUTPUT* :

![Image](https://github.com/user-attachments/assets/defe871c-34fb-4480-af65-ad8c72ed3705)


![Image](https://github.com/user-attachments/assets/cb9dd2df-307a-43fc-a9b9-156870ade05d)






