## 1. DOM Manipulation

The DOM (Document Object Model) is an object-oriented, tree-structured representation of an HTML page. JavaScript uses the DOM API to select, create, modify, and delete HTML elements, apply styles, and handle events.

**Selecting elements (modern way):**

```javascript
// Select by ID
const btn = document.querySelector("#myBtn");

// Select by class
const card = document.querySelector(".card");

// Select all matching elements
const allItems = document.querySelectorAll("li");
```

**Modifying elements:**

```javascript
const div = document.querySelector("#info");
div.innerHTML = "<strong>Updated!</strong>";   // set HTML content
div.style.display = "none";                    // hide element
div.classList.add("highlight");                // add CSS class
div.classList.toggle("active");                // toggle CSS class
```

**Creating & removing elements:**

```javascript
const newDiv = document.createElement("div");
newDiv.innerText = "Hello from JS!";
document.body.append(newDiv);

document.querySelector("#oldDiv").remove();
```

**DOM Traversal:**

```javascript
const parent   = document.querySelector("#about").parentNode;
const children = document.querySelector("#about").children;
```

---

## 2. Event Handling

UI programming in the browser follows an **event-driven model** — code runs in response to user actions (clicks, keypresses, form input, etc.).

**Attaching event listeners (recommended way via DOM):**

```javascript
document.addEventListener("DOMContentLoaded", () => {
  const btn = document.querySelector("#myBtn");
  btn.addEventListener("click", handleClick);
});

function handleClick(event) {
  console.log("Clicked!", event.type);   // event.type = "click"
  console.log("Target:", event.target);  // the element clicked
}
```

**Stopping default browser behavior:**

```javascript
async function onAddHero(event) {
  event.preventDefault(); // stops <a> from navigating
  const heroesDiv = document.querySelector("#heroes");
  heroesDiv.innerHTML = await getHeroEditor();
}
```

---

## 3. Accessing Web APIs with Fetch

**AJAX** (Asynchronous JavaScript and JSON) allows background communication with a server without reloading the page. The modern `fetch()` API is the standard tool for this.

**GET request:**

```javascript
async function getStudent(studentId) {
  const response = await fetch(`/api/students/${studentId}`);
  return await response.json(); // parse response body as JSON
}
```

**POST request:**

```javascript
const email    = document.querySelector("#email").value;
const password = document.querySelector("#password").value;

fetch("/login", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ email, password })
});
```

---

## 4. HTML Templates (Template Literals)

JavaScript **template literals** (backtick strings with `${...}` placeholders) allow you to generate dynamic HTML from data objects — similar to filling in a form template.

**Basic template:**

```javascript
const payment = {
  date: "1/2/2024", name: "Mr Bean",
  amount: 200, reason: "Donation", receiver: "Juha"
};

const receiptTemplate = (p) => `
  <div>
    <p>Date: ${p.date}</p>
    <p>From: ${p.name}, Amount: QR ${p.amount}</p>
    <p>For: ${p.reason}</p>
    <p>Received by: ${p.receiver}</p>
  </div>`;

document.body.innerHTML = receiptTemplate(payment);
```

**Rendering an array with `.map()`:**

```javascript
const days = ["Mon", "Tue", "Wed", "Thu", "Fri"];

const html = `<ul>
  ${days.map(day => `<li>${day}</li>`).join("\n")}
</ul>`;

document.body.innerHTML = html;
```

**Conditional expression inside a template:**

```javascript
const isHappy = true;
const mood = `Feeling: ${isHappy ? "😀" : "😢"}`;
console.log(mood);
```

---

## 5. localStorage

`localStorage` allows persistent key/value data storage inside the user's browser — data survives page refreshes and browser restarts, with a limit of at least **5MB**, scoped per domain.

**Basic CRUD operations:**

```javascript
// Store
localStorage.setItem("username", "johndoe");

// Retrieve
const name = localStorage.getItem("username");
console.log(name); // "johndoe"

// Delete one key
localStorage.removeItem("username");

// Clear everything
localStorage.clear();
```

**Practical example — click counter:**

```javascript
function clickCounter() {
  const count = parseInt(localStorage.getItem("clickCount") || "0") + 1;
  localStorage.setItem("clickCount", count);
  document.querySelector("#count").innerHTML =
    `Button clicked ${count} times.`;
}
```

> ⚠️ **Note:** `localStorage` always stores values as **strings** — remember to parse numbers with `parseInt()` or `JSON.parse()` when reading them back.

---

## Further Reading (from the slides)

- [MDN – DOM Introduction](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
- [MDN – Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
- [MDN – Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)