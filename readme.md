# Elysia Request ID

Elysia plugin to create or forward Request IDs.

## Installation

```bash
bun add --exact elysia-requestid
```

## Usage

```ts
import { requestID } from "elysia-requestid"; // 1. Import
import Elysia from "elysia";

new Elysia()
  .use(requestID()) // 2. Use
  .get("/", ({ requestID }) => {
    return `Hello ${requestID}`; // 3. Available in Context
  })
  .listen(3000);
```

## Options (with defaults)

```ts
requestID({
  // The function to use to generate a request ID
  uuid: crypto.randomUUID,

  // The header to use for the request ID
  header: "X-Request-ID",
});
```
