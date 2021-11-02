# Spring and Sockets

### WebSocket
WebSocket is a computer communications protocol, is a bi-directional, full-duplex, persistent connection between a web browser and a server. 

### STOMP
Text Oriented Message Protocol (STOMP),STOMP provides an interoperable wire format so that STOMP clients can communicate with any supported message broker to provide easy and widespread messaging interoperability among many languages, platforms and brokers.


### What We Will build ?
You will build a server that accepts a message that carries a user’s name. In response, the server will push a greeting into a queue to which the client is subscribed.

1. First we need to :
    * Download and unzip the source repository for this guide, or clone it using Git: git clone [https://github.com/spring-guides/gs-messaging-stomp-websocket.git](https://github.com/spring-guides/gs-messaging-stomp-websocket)
    * cd into gs-messaging-stomp-websocket/initial

2. Create a Resource Representation Class:
* Create The Model that carries the name:

```
package com.example.messagingstompwebsocket;

public class HelloMessage {

  private String name;

  public HelloMessage() {
  }

  public HelloMessage(String name) {
    this.name = name;
  }

  public String getName() {
    return name;
  }

  public void setName(String name) {
    this.name = name;
  }
}
```

* Model the greeting representatio

```
package com.example.messagingstompwebsocket;

public class Greeting {

  private String content;

  public Greeting() {
  }

  public Greeting(String content) {
    this.content = content;
  }

  public String getContent() {
    return content;
  }

}
```

3. Create a Message-handling Controller
* have to  create a controller to receive the hello message and send a greeting message.

```
@Controller
public class GreetingController {


  @MessageMapping("/hello")
  @SendTo("/topic/greetings")
  public Greeting greeting(HelloMessage message) throws Exception {
    Thread.sleep(1000); // simulated delay
    return new Greeting("Hello, " + HtmlUtils.htmlEscape(message.getName()) + "!");
  }
```

4. Configure Spring for STOMP messaging
* Create a Java class named WebSocketConfig
```
@Configuration 
@EnableWebSocketMessageBroker
public class WebSocketConfig implements WebSocketMessageBrokerConfigurer {

  @Override
  public void configureMessageBroker(MessageBrokerRegistry config) {
    config.enableSimpleBroker("/topic");
    config.setApplicationDestinationPrefixes("/app");
  }

  @Override
  public void registerStompEndpoints(StompEndpointRegistry registry) {
    registry.addEndpoint("/gs-guide-websocket").withSockJS();
  }

```
`@Configuration`: to indicate that it is a Spring configuration class.
`@EnableWebSocketMessageBroker` : enables WebSocket message handling, backed by a message broker.
`WebSocketMessageBrokerConfigurer`: to configure the message broker.
`enableSimpleBroker()`: to enable a simple memory-based message broker to carry the greeting messages back to the client on destinations prefixed with /topic.


5. Create a Browser Client
* Create HTML file that imports the SockJS and STOMP javascript libraries that will be used to communicate with our server through STOMP over websocketm and import app.js, which contains the logic of our client application. app.js file contain the following:
    * The **connect()** function :  uses SockJS and stomp.js to open a connection to /gs-guide-websocket, which is where our SockJS server waits for connections.
    * The **sendName()** function :  retrieves the name entered by the user and uses the STOMP client to send it to the /app/hello destination (where GreetingController.greeting() will receive it).

```
var stompClient = null;

function setConnected(connected) {
    $("#connect").prop("disabled", connected);
    $("#disconnect").prop("disabled", !connected);
    if (connected) {
        $("#conversation").show();
    }
    else {
        $("#conversation").hide();
    }
    $("#greetings").html("");
}

function connect() {
    var socket = new SockJS('/gs-guide-websocket');
    stompClient = Stomp.over(socket);
    stompClient.connect({}, function (frame) {
        setConnected(true);
        console.log('Connected: ' + frame);
        stompClient.subscribe('/topic/greetings', function (greeting) {
            showGreeting(JSON.parse(greeting.body).content);
        });
    });
}

function disconnect() {
    if (stompClient !== null) {
        stompClient.disconnect();
    }
    setConnected(false);
    console.log("Disconnected");
}

function sendName() {
    stompClient.send("/app/hello", {}, JSON.stringify({'name': $("#name").val()}));
}

function showGreeting(message) {
    $("#greetings").append("<tr><td>" + message + "</td></tr>");
}

$(function () {
    $("form").on('submit', function (e) {
        e.preventDefault();
    });
    $( "#connect" ).click(function() { connect(); });
    $( "#disconnect" ).click(function() { disconnect(); });
    $( "#send" ).click(function() { sendName(); });
});
```
5. run your application .

6. Test the service 


#### Other guides [Serving Web Content with Spring MVC](https://spring.io/guides/gs/serving-web-content/) , [Building an Application with Spring Boot](https://spring.io/guides/gs/spring-boot/)
