stylus-comment-bug
==================

http://learnboost.github.io/stylus/docs/comments.html

a.styl
------

```css
// A1 - Single line comment
.a1 {
  color: red;
}

/*
 * A2 - Multi line comment (THIS COMMENT WILL NOT BE SHOWED IN THE COMPILED CSS)
 */
.a2 {
  color: green;
}

/*!
 * A3 - Multi-line buffered
 */
.a3 {
  color: blue;
}
```

b.styl
------

```css
// B1 - Single line comment
.b1 {
  color: Salmon;
}

/*
 * B2 - Multi line comment (THIS COMMENT WILL NOT BE SHOWED IN THE COMPILED CSS)
 */
.b2 {
  color: LemonChiffon;
}

/*!
 * B3 - Multi-line buffered
 */
.b3 {
  color: Chocolate;
}
```

styles.styl
-----------
```css
@import "a"
@import "b"
```

Terminal
--------
$ stylus a.styl -p
> IT WORKS!

$ stylus b.styl -p (IT WORKS!)
> IT WORKS!

but...

$ stylus styles.styl -p
> Suppresses inappropriately the multi-line comments from a.styl and b.styl. See the result below:

```css
.a1 {
  color: #f00;
}
.a2 {
  color: #008000;
}
/*
 * A3 - Multi-line buffered
 */
.a3 {
  color: #00f;
}
.b1 {
  color: Salmon;
}
.b2 {
  color: LemonChiffon;
}
/*
 * B3 - Multi-line buffered
 */
.b3 {
  color: Chocolate;
}
```
