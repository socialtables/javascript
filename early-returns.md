Handling validation and error conditions is often done in one of the following
ways:

1:
```javascript
    if (!can(this.user).see.event(this.params.event)) {
        this.status = 401;
        return;
    }
    // Continue with request handling code
```
2:
```javascript
    if (!can(this.user).see.event(this.params.event)) {
        this.status = 401;
    }
    else {
        // Continue with request handling code
    }
```

Both can be useful -- one provides an easy way to scan for the return value,
the other simplifies the function body in some cases. In general, if you find
the first style >5 lines into a function, think about why it needs to be there,
and if there might be a clearer way of writing the code (e.g. splitting out a
validation function).

Related: [If-Else Nesting Considered Harmful](./if-else-nesting.md)

Further reading:
- http://programmers.stackexchange.com/questions/18454/should-i-return-from-a-function-early-or-use-an-if-statement
- http://blog.timoxley.com/post/47041269194/avoid-else-return-early
- http://rmurphey.com/blog/2012/12/10/js-conditionals/ (second part)
