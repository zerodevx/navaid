# navaid

> Fork of Navaid with shadow dom support

[Navaid](https://github.com/lukeed/navaid) is a tiny client-side router. 
[It doesn't support shadow dom anchor links.](https://github.com/lukeed/navaid/issues/30) 
Now it does.

#### What changed?

Just one line.

[Before:](https://github.com/lukeed/navaid/blob/9989c05ece026f2786f3582bb35ea4dc86afc574/src/index.js#L53)

```js
var x = e.target.closest('a'), y = x && x.getAttribute('href');
```

[After:](https://github.com/zerodevx/navaid/blob/b447317126c259bba012deba4929b4fa3a4586df/src/index.js#L53-L54)

```js
var x = e.composedPath, x = e.path || x && x() || [e.target], x = x[0].closest('a'), y = x && x.getAttribute('href');
```

| Package   | Version       | Size      |
|-----------|---------------|-----------|
| Original  | v1.2.0        | 909 bytes |
| Forked    | v1.2.0-fork.3 | 934 bytes |

Demo: https://zerodevx.github.io/navaid/

#### Install with NPM

```
$ npm i -D @zerodevx/navaid
```

#### Or from CDN

```html
<head>
  <script src="https://cdn.jsdelivr.net/npm/@zerodevx/navaid@latest"></script>
  ...
</head>
```

For usage docs, please refer to the original project.
