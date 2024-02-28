# REST APIs

<show-structure for="chapter,procedure" depth="1"/>

## API to Get Order Details By Reference ID

Use a REST client and make the GET Request, the URL requires the order `reference id` as a path parameter:


<api-doc openapi-path="../api/spec.yml">
<api-endpoint endpoint="/massivetransaction/api/ext/v1/transactions/{referenceId}" method="GET"></api-endpoint>
</api-doc>


Below is an example screenshot from a `REST` client showing a successful 200 OK HTTP response.
Remember to set the `base_url` depending on the environment to use.

For dev, use:

```bash
    https://api.dev.gmint.io
   ```

## Get Notifications for Purchase Orders

Clients can register one or many webhook URLs to receive notifications whenever there is a status change for their
purchase orders.

> **BEFORE YOU START**
>
> The webhook URLs to register must return a 2xx HTTP response to indicate successful receipt of the notification. 
> Failure to do so will result in retries by our system. (Up to 3 attempts)
> 
{style="note"}

<api-doc openapi-path="../api/spec_2.yml"/>

### Handling Webhook Notifications 

<p>Once your webhook URL(s) are registered, you will automatically receive notifications whenever there is a status
change for your purchase orders. These notifications will be sent to the registered webhook URL(s) as <code>HTTP POST</code>
requests</p>

<code-block lang="JSON">
{
 "event": "orders.status",
 "order": {
 "referenceId": "G2123456789",
 "priorStatus": "CREATED",
 "currentStatus": "CHARGED"
 }
}
</code-block>
