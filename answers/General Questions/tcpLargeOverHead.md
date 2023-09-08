# Why does opening a TCP socket have a large overhead?

Simple Answer: opening a TCP socket has overhead because it involves some extra work to set up a secure and reliable connection before you can start sending messages or data over the internet.

## Understand What is TCP socket?

TCP (Transmission Control Protocol) is a network protocol that ensures reliable and ordered data transmission between devices on the internet. It establishes connections, manages data flow, and includes error checking for data integrity. TCP is essential for applications like web browsing, email, and file transfers.

## How TCP works in general

TCP is a special way that computers use to talk to each other over the internet. It's like having a conversation. When you send a message (data) to someone far away, TCP makes sure the message gets there correctly and in the right order. It's like sending a letter with a tracking number to make sure it arrives safely.It ensures reliable and ordered data transmission between computers.
</br>
TCP does this by setting up a "connection" between your computer and the other computer. It's kind of like making a phone call. First, you have to dial the number and wait for the other person to pick up. Then, you can talk.

</br>
TCP establishes a connection between two computers, like a virtual handshake, before data transfer begins. This connection involves a series of steps:

    - sending and receiving control messages to establish parameters,
    - acknowledge received data, and
    - manage flow control.

Once the connection is established, data is divided into small packets and sent over the network. TCP ensures that these packets arrive at the destination in the correct order and without errors. If any data is lost or corrupted during transmission, TCP requests retransmission.

## Understand what is OverHead

Think of "overhead" like the extra work or effort needed to get something done. Imagine you're playing a video game, and you have to pause the game to go to the menu, change some settings, and then come back to playing. Going to the menu and making changes is like overhead because it takes time and effort away from actually playing the game.

"overhead" refers to the additional resources, time, or work required to perform a task beyond the primary function or goal. It can include extra processing, memory, or time that is needed to set up or manage a particular operation.

## Why does opening a TCP socket have a large overhead?

Now, imagine you want to start a conversation with someone using TCP. When you open a "socket" there's some extra work to do before you can start talking, Like :

    - Setting Up Stuff
    - Checking Addresses
    - Getting Permission
    - Making Sure It's Safe

All these extra things take a little bit of time and effort. That's why opening a TCP socket can have what we call "overhead".

Steps in details:

- State Setup: TCP is connection-oriented, meaning it maintains a lot of information about the connection. When you open a socket, the operating system allocates and initializes resources to manage this connection. This includes setting up buffers, managing sequence numbers, and other connection-related parameters.
- System Calls: In most programming languages, opening a TCP socket requires making system calls to the operating system's network stack. These system calls involve transitioning between user mode and kernel mode, which can be relatively slow.
- Address Resolution: When connecting to a remote host, there may be DNS resolution involved, which can introduce latency as it translates domain names into IP addresses.
- Port Allocation: The operating system must allocate a local port for the connection, which can involve checking for available ports and managing port numbers to avoid conflicts.
- Security Handshakes: For secure connections (e.g., TLS/SSL), there's additional overhead due to cryptographic handshakes and authentication.
- Resource Allocation: The OS needs to allocate memory and other resources for managing the socket.
- Concurrency Management: In situations where multiple threads or processes concurrently open sockets, there might be contention for resources, leading to additional overhead due to synchronization.

---

## Resources

1. [On Quora By George J Nazarey](https://www.quora.com/Why-does-opening-a-TCP-socket-have-a-large-overhead)
2. [Wikipedia page of TCP](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)
3. [Stack OverFlow](https://stackoverflow.com/questions/4840116/general-overhead-of-creating-a-tcp-connection)
