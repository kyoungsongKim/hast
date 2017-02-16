# hast

Server and client libraries for topology in linux, using TCP/IP and Unix Domain socket. Main features are multi-threading and tiny enough to be embeded in program. 

## Main Feature of Server Class

* The way server deal with request is like the concept of `goroutine` in GO. You can set the maximum amount of threads (or by default, server will process each request independently, so there is no limit for amount of threads) to deal with requests. It's not thread-pool with fixed amount of threads, the amount of threads is dynamic, so it can be 1 to maximum amount in any time. 
* You can set server to be Anti-Data-Racing, so server won't process requests with same incoming message.
* Server can be freezed with all threads or certain threads by the call from client. More details are in the `example` folder. 

## Main Feature of Client Class

* `client_core` is a client library for single-thread used. It send request and wait for the reply.
* `client_thread` is a client library for multi-thread used. It can send request and open a new thread to receive the reply.

## Getting Started

* Only for Linux (kernel > 2.5.44 because using `epoll.h`). 
* You will need an C++ compiler which can support C++11.
* Header-only library, so copy `hast` folder to your include folder.
* Usage of the libraries and other details please refer to `example` folder and this project's wiki page (WIP).
* This project use `std::thread`, so compile file with `std::thread` library.

## Framework

* There is another my project called 'dalahast' is the framework for this projet. It provide more features, rules, and UI interface for the diagram of topology. 

## Bugs and Issues

This project is still in developed and maintained. Open an issue if you discover some problems.
