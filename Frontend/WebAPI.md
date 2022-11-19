# Web Storage API

## The localStorage Object

The localStorage object provides access to a local storage for a particular Web Site. It allows you to store, read, add, modify, and delete data items for that domain.

The data is stored with no expiration date, and will not be deleted when the browser is closed.

The data will be available for days, weeks, and years.

```js
localStorage.setItem("name", "John Doe");
localStorage.getItem("name");
```

## The sessionStorage Object

The sessionStorage object is identical to the localStorage object.

The difference is that the sessionStorage object stores data for one session.

The data is deleted when the browser is closed.

```js
sessionStorage.getItem("name");
```

# Web Workers API

```js
//demo_workers.js
let i = 0;

function timedCount() {
  i ++;
  postMessage(i);
  setTimeout("timedCount()",500);
}

timedCount();
```

```js
if (typeof(w) == "undefined") {
  w = new Worker("demo_workers.js");
}
w.onmessage = function(event){
  document.getElementById("result").innerHTML = event.data;
};
```

# JavaScript Fetch API

The Fetch API interface allows web browser to make HTTP requests to web servers.

😀 No need for XMLHttpRequest anymore.

```js
fetch(file)
.then(x => x.text())
.then(y => myDisplay(y));

async function getText(file) {
  let x = await fetch(file);
  let y = await x.text();
  myDisplay(y);
}
```
