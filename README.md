# toml

A minimal TOML library in zepto. It is a stub right now.

## Usage

**This is not yet implemented**

Usage is pretty simple. There is a file called `test.zp` that shows
the most basic usage examples I can think of.

Decoding from TOML looks like this:
```clojure
(define x (toml:parse
            "unnamed = 10
             lol     = { 10: 'hello', 11: [1, 2] }
             [this]
             that = 10"))
; this will return a hash-map like so:
; #{lol: #{10: hello, 11: (1 2)}, unnamed: 10, this: #{that: 10}, }
```

Encoding to TOML looks like this:
```clojure
(define x (toml:dump #{10 (1 2) 3 "something"}))
; this will return a string like so:
; 10 = [1, 2]
; 3 = "something"
```

Integrity is, of course preserved.
```clojure
(define test #{"key" (1 2 3)})
(hash-eqv? test (toml:parse (toml:dump test))) ; this yields #t
```

Yay, right?

<br/>

*Have fun!*
