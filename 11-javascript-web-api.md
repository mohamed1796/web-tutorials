## 1. Web and HTTP

The Web is a global distributed system of interlinked resources accessed via HTTP. It follows a **Client/Server architecture** where browsers send requests and servers send responses.

**URL Structure:**

```
http://localhost:8080/api/users?sort=asc
  ^        ^          ^    ^       ^
protocol  host       port  path  query
```

**HTTP Request Message:**

```http
GET /index.html HTTP/1.1
Host: localhost:3000
User-Agent: Mozilla/5.0

(empty line = end of headers)
```

**HTTP Response Message:**

```http
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 131

<html><body>Hello World</body></html>
```

**Common Status Codes:**

```
200 OK           → Success
301/302          → Redirect
400 Bad Request  → Bad syntax
401 Unauthorized → Authentication needed
404 Not Found    → Resource missing
500 Server Error → Server-side failure
```

---

## 2. Web API (REST Services)

A **Web API** (also called REST Services) is a web-accessible interface that accepts HTTP requests and returns structured data — usually JSON.

**REST's Three Core Concepts:**

|Concept|Example|
|---|---|
|Nouns (Resources)|`/api/employees/123`|
|Verbs (HTTP Methods)|`GET`, `POST`, `PUT`, `DELETE`|
|Representations|JSON, XML|

**CRUD API example for a `books` resource:**

```
GET    /api/books         → Retrieve all books
GET    /api/books/:id     → Retrieve a specific book
POST   /api/books         → Create a new book
PUT    /api/books/:id     → Replace a book
PATCH  /api/books/:id     → Partially update a book
DELETE /api/books/:id     → Delete a book
```

**JSON vs XML Representation:**

```json
{ "code": "cmp123", "name": "Web Development" }
```

```xml
<course>
  <code>cmp123</code>
  <name>Web Development</name>
</course>
```

---

## 3. Web API using Next.js

Next.js uses a **file-system based App Router**. Placing a `route.js` file inside a folder under `app/` creates an API endpoint.

### Getting Started

```bash
npx create-next-app@latest .
npm run dev
```

---

### Basic API Route

```javascript
// app/api/hello/route.js
export async function GET(request) {
  return new Response('Hello, Next.js!');
}
// Access at: http://localhost:3000/api/hello
```

---

### Dynamic Routes

Wrap a folder name in `[brackets]` to create a path parameter:

```javascript
// app/api/books/[id]/route.js
export async function GET(request, { params }) {
  const id = (await params).id;
  return Response.json({ bookId: id });
}
// GET /api/books/42 → { "bookId": "42" }
```

---

### Catch-All Dynamic Routes

Use `[...slug]` to match any number of path segments:

```javascript
// app/api/blogs/[...filterBy]/route.js
export async function GET(request, { params }) {
  const segments = (await params).filterBy;
  // /blogs/2025/3/10 → segments = ["2025", "3", "10"]
  return Response.json({ filters: segments });
}
```

---

### Query Parameters

```javascript
// app/api/products/route.js
export async function GET(request) {
  const { searchParams } = request.nextUrl;
  const sortBy = searchParams.get('sortBy') || 'default';
  // GET /api/products?sortBy=price → sortBy = "price"
  return Response.json({ sortedBy: sortBy });
}
```

---

### POST with Request Body

```javascript
// app/api/books/route.js
export async function POST(request) {
  const body = await request.json();
  // body = { title: "Clean Code", author: "Martin" }
  const newBook = await createBook(body);
  return Response.json(newBook, { status: 201 });
}
```

---

### Reading & Setting Headers

```javascript
// app/api/secure/route.js
import { headers } from 'next/headers';

export async function GET(request) {
  const headersList = await headers();
  const apiKey = headersList.get('apiKey');

  return new Response('Authorized!', {
    status: 200,
    headers: { 'apiKey': apiKey || 'No API Key' }
  });
}
```

---

### Redirect

```javascript
// app/api/old-route/route.js
import { redirect } from 'next/navigation';

export async function GET(request) {
  redirect('https://nextjs.org/');
}
```

---

### Calling the API from the Client

```javascript
// Fetching from a React component or page
const response = await fetch('/api/books');
const books = await response.json();
console.log(books);
```

---

## Resources from the PDF

- Next.js Docs: [https://nextjs.org/docs](https://nextjs.org/docs)
- Next.js Blog: [https://nextjs.org/blog](https://nextjs.org/blog)
- Building APIs with Next.js: [https://nextjs.org/blog/building-apis-with-nextjs](https://nextjs.org/blog/building-apis-with-nextjs)