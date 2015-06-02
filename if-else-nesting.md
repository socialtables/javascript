This is really a specific case of code being clear and functions doing a single
thing: Simple if / else statements are just fine, but multiple levels are
sources of confusion. For example,

```javascript
if (foo) {
  bar();
}
else {
  baz();
  }
```
is just fine. However:

```javascript
if (foo) {
  bar();
}
else {
  foobar = a();
  foobaz = b();
  if (foobar && foobaz) {
    quux();
  }
  else {
    baz();
  }
}
```
should raise a reviewer's eyebrow, and

```javascript
if (foo) {
  bar();
}
else {
  foobar = a();
  foobaz = b();
  if (foobar && foobaz) {
    quux();
  }
  else {
    yolo = foobar ? solo() : together();
    if (yolo) {
      danceLikeNobodysWatching();
    }
    else {
      baz();
    }
  }
}
```
is calling out to be refactored.
