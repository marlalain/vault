# HATEOAS
(or Hypermedia as the Engine of Application State)
Specified as [[Richardson Maturity Model#Level 3 Hypermedia Controls]]

---

In HATEOAS, a client (or front-end) interacts with a network application dynamically through [[Hypermedia|hypermedia]]. It allows you to navigate through numerous endpoints and interact with the REST API without prior knowledge of the API itself.

What happens when a client access a web page? Even in the root of the site (`/` or `/home`, for example), the user gets sent numerous links ([[Hypermedia]]) and with these links it can navigate through the whole system.

The restrictions imposed by HATEOAS decouple client and server. This enables server functionality to evolve independently. 

## Example

For example, this GET request fetches an account resource, requesting details in a [[JSON]] representation.

```http
GET /accounts/12345 HTTP/1.1
Host: bank.example.com
```

The response is:

```http
HTTP/1.1 200 OK
```

```json
{
    "account": {
        "account_number": 12345,
        "balance": {
            "currency": "usd",
            "value": 100.00
        },
        "links": {
            "deposits": "/accounts/12345/deposits",
            "withdrawals": "/accounts/12345/withdrawals",
            "transfers": "/accounts/12345/transfers",
            "close-requests": "/accounts/12345/close-requests"
        }
    }
}

```

The response contains these possible follow-up links: POST a deposit, withdrawal, transfer, or close request (to close the account).

As an example, later, after the account has been overdrawn, there is a different set of available links, because the account is overdrawn.

```http
HTTP/1.1 200 OK
```

```json
{
    "account": {
        "account_number": 12345,
        "balance": {
            "currency": "usd",
            "value": -25.00
        },
        "links": {
            "deposits": "/accounts/12345/deposits"
        }
    }
}
```
j
---

Related: [[HAL]], [[REST]], [[Richardson Maturity Model]]