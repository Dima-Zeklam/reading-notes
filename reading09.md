# WRRC and Java

## The HTTP Request Lifecycle

### Hypertext Transfer Protocol (HTTP)

![Hypertext Transfer Protocol](https://miro.medium.com/max/1200/1*7ZeoFbLKxz7Rp60cArwVQw.png) 

**Is a request-response protocol, for transmitting hypermedia documents, such as HTML. It was designed for communication between web browsers and web servers, but it can also be used for other purposes.**

* Clients and servers communicate by exchanging individual messages (as opposed to a stream of data). The messages sent by the client, usually a Web browser, are called requests and the messages sent by the server as an answer are called responses.
 
* Proxies Between the Web browser and the server may perform numerous functions:

    * caching (the cache can be public or private, like the browser cache)
    * filtering (like an antivirus scan or parental controls)
    * load balancing (to allow multiple servers to serve different requests)
    * authentication (to control access to different resources)
    * logging (allowing the storage of historical information)



#### 1.Local Processing
The browser needs to translate www.example.com to an IP address if it does not already know it. If it knows it, nothing happens at this point. If it does not know it, it contacts a DNS server to resolve the name.
The browser will then look through its own cache of recently requested URLs, the operating system’s cache of recent queries, your router’s cache, and your DNS cache.

#### 2. Resolve an IP
when request arrives at your configured DNS server, the server looks for the address associated with the requested hostname. If it finds one, it sends a response, but If an address for the given domain cannot be resolved, the server responds with a failure and your browser returns an error.

#### 3. Establish a TCP Connection
##### TCP (transmission control protocol)
Is an communication protocols that enables application programs and computing devices to exchange messages over a network.

* The client establishes a TCP connection 
* The client sends its request, and waits for the answer.
* The server processes the request, sending back its answer, providing a status code and appropriate data.
* Much of this is done very simply, using what’s known as a sequence number for every byte sent. This allows the receiver to re-order received packets back into their original order, and allows the sender to retransmit any packet that does not get acknowledged by the receiver.


#### 4.Send an HTTP Request
In general, an HTTP request is divided into 3 parts:

* A request line
   In the request line we place the HTTP method to be used, the URI of the request and the HTTP protocol to be used. 
   
* A set of header fields
Headers are metadata that are sent in the request to provide information about the request. Each header is specified with a name, then two points, and then followed by the value of that header.

* A body, which is optional
In the body of the request we are free to place virtually whatever we want. From the username and password of a person trying to login to our system and the body is quite important, because it represents the content that one wants to transmit.

#### 5. Tearing Down and Cleaning Up

* Once the response has been fully delivered, the client sends a FIN packet at the TCP level 
* **TCP FIN packet** is required to close a connection, which indicates no more data will be transmitted from the sender.
* **FIN-ACK** — Indicates acknowledgment of FIN packet.
*  If the data received is HTML, the browser will start parsing the HTML, and rendering the page you requested.

#### way of performing HTTP requests in Java:
The *HttpUrlConnection* class allows us to perform basic HTTP requests without the use of any additional libraries.

**Example :** 
We can create request by using openConnection() method from *HttpUrlConnection* class:

```
URL url = new URL("http://example.com");
HttpURLConnection con = (HttpURLConnection) url.openConnection();
con.setRequestMethod("GET");
```
Visit [Do a Simple HTTP Request in Java](https://www.baeldung.com/java-http-request) site For more methods and exampls .




