# 43-how-to-design-robust-and-predictable-apis-with-idempotency.md

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article1.be68295a7e40.png)

## Metadata
- Author: [[github.com]]
- Full Title: 43-how-to-design-robust-and-predictable-apis-with-idempotency.md
- Category: #articles
- URL: https://github.com/amoslue/system-design-and-architecture/blob/master/en/43-how-to-design-robust-and-predictable-apis-with-idempotency.md

## Highlights
- Retry with idempotency and idempotency keys to allow clients to pass a unique value.
  1. In RESTful APIs, the PUT and DELETE verbs are idempotent.
  2. However, POST may cause ==“double-charge” problem in payment==. So we use a ==idempotency key== to identify the request.
  1. If the failure happens before the server, then there is a retry, and the server will see it for the first time, and process it normally.
  2. If the failure happens in the server, then ACID database will guarantee the transaction by the idempotency key.
  3. If the failure happens after the server’s reply, then client retries, and the server simply replies with a cached result of the successful operation. ([View Highlight](https://read.readwise.io/read/01hbmd87thade1t9rv7jbdbabv))
