# Qenta Proxy Server

<!--Writerside adds this topic when you create a new documentation project.
You can use it as a sandbox to play with Writerside features, and remove it from the TOC when you don't need it anymore.-->


## Access the server

To verify the server is up and running, In the address bar, enter the URL where the Spring server is configured to run.
If not specified in your configuration, a common default URL is:

<a href="http://localhost:8080/swagger-ui.html">http://localhost:8080/swagger-ui.html</a>

Make sure to set the correct port number in case you used the --server.port=custom_port_number or docker run in
a different port.


## Confirming Server Availability

If the server is running and accessible, Swagger UI will load, displaying a user-friendly interface for exploring and
testing your API endpoints.
Navigate through the available API documentation to understand the available endpoints, request/response
formats, and any additional information provided.

![Swagger](swagger.png){ style="block" thumbnail="true"}

## Test the server

You can use curl to test the `REST API` endpoints of your %product_2%. Here's an example using the provided curl
command:


```bash
curl --location --request POST "http://localhost:8080/qenta-sdk/orders" ^
--header "Content-Type: application/json" ^
--header "Accept: */*" ^
--header "Host: localhost:8080" ^
--header "Connection: keep-alive" ^
--data-raw "{ \"currency\" : \"EUR\", \"fiatAmount\" : 120.0, \"accountId\" : \"3213\"}"
```

<p>This curl command performs a POST request to the specified URL <code>(http://localhost:8080/qenta-sdk/orders)</code> with a
<code>JSON</code> payload</p>

<tabs>
    <tab title="Response Confirmation">
        After executing the curl command, you should receive an HTTP response. A successful request returns a 200 OK
status.
    </tab>
    <tab title="Example HTTP Response ">
        <p>Below is an example screenshot from a REST client showing a successful 200 OK HTTP response after executing the
        curl command.</p>
    </tab>
</tabs>

