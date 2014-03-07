#My Coding Style
---

Nowadays I feel a great need to be prodcutive. The best way to accomplish this, is to use the same pattern, conventions and guides in all my projects. But there are so many rules and guides out there than it can be a *little* confusing. 

So, in order words I felt it was about time to define **My Coding Style**.

## Let's rock...


> "All code in any code-base should look like a single person typed it, no matter how many people contributed."

## Topics

- Git
	- Commit
	- Files
- HTML
	- Doctype
	- Meta tags
	- CSS files
	- JS files
	- Inline styles
	- Inline JS
	- Validation
	- Tag names
	- Using H1 ... H6 tags
	- Images
	- Sections
	- Forms
	
- CSS
	- Indentation
	- Class names
	- Colors
- Javascript
	- Indentation
	- Line length
	- Linting
	- Semicolons
	- Variables
	- Strings
	- New lines
	- Whitespace
	- Conditionals
	- Equality
	- Loops
- Markdown

## Git

### Commit

Every commit message, pull request title or issue discussion must be in **English**.

> Reason: English is the universal language nowadays, if you use any other language you're excluding potencial contributors.

Don't use Past or Present Continuous tenses for commit messages, those should be in Imperative Present tense.

```javascript
// Good
Add feature X

// Bad
Added feature X
Adding feature X
```

> Reason: This preference comes from [Git itself](http://git.kernel.org/cgit/git/git.git/tree/Documentation/SubmittingPatches?id=HEAD#n111).

When releasing a new version, write a commit message in the following format "Release - v1.0.0" instead of "v1.0.0".

> Reason: Makes it easier to track version releases in git history. For example, you could run `git log --pretty=format:"%H %s" | grep 'Release'` to fetch only version bump commits.

### Files

Don't commit big files unless they're absolutely required. Big files lead to big git history and it will be a pain for others to use the repo.

## HTML

### Doctype

Always use **HTML 5** doctype.

```html
Good
<!DOCTYPE html>

Bad
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
```

### Meta tags
### CSS files
### JS files
### Inline styles
### Inline JS
### Validation
### Tag names
### Using H1 ... H6 tags
### Images
### Sections
### Forms

## CSS

### Indentation

The unit of indentation is **2 spaces**. Never mix spaces and tabs.

```css
// Good
.class {
  properties
}

// Bad
.class {
properties
}
```
>Reason: TODO

### Class names

Use hyphens between class names instead of camelCase or under_score.

```css
// Good
.my-class {
  properties
}

// Bad
.myClass, my_class {
properties
}
```
>Reason: TODO

### Colors

Always use **lowercase** hex colors instead of color names, and whenever possible use the reduced version.

```css
// Good
.class {
  background-color: #fff;
}

// Bad
.class {
  background-color: white;
}
```
>Reason: TODO

## JavaScript

### Indentation

The unit of indentation is **4 spaces**. Never mix spaces and tabs.

```javascript
// Good
while (condition) {
    statements
}

// Bad
while (condition) {
  statements
}
```

> Reason: TODO

### Line length

Avoid lines longer than **100 characters**. When a statement will not fit on a single line, it may be necessary to break it. Place the break after an operator, ideally after a comma. The next line should be indented **4 spaces**.

```javascript
// Good
YUI().use('aui-module-a', 'aui-module-b', 'aui-module-c', 'aui-module-d',
    'aui-module-e', 'aui-module-f');

// Bad
YUI().use('aui-module-a', 'aui-module-b', 'aui-module-c', 'aui-module-d', 'aui-module-e', 'aui-module-f');
```

Every project should contain a [.editorconfig](https://github.com/zenorocha/my-coding-style/blob/master/.editorconfig) file that automatically set some indentation definitions. Make sure to install [Editor Config's](http://editorconfig.org/) plugin on your code editor and you'll be all set.

> Reason: TODO

### Linting

Use [JSHint](http://www.jshint.com/) to detect errors and potential problems.

The options for JSHint are stored in a [.jshintrc](https://github.com/zenorocha/my-coding-style/blob/master/.jshintrc) file.

> Reason: TODO

### Semicolons

Relying on ASI (Automatic Semicolon Insertion) can cause hard to debug problems, so don't do it. **Always** use semicolons.

```javascript
// Good
a = b + c;
test();

// Bad
a = b + c
test()
```

> Reason: TODO

### Variables

All variables should be declared **before** used. Avoid multiple var statements.

```javascript
// Good
var foo = '',
    bar = '';

// Bad
var foo = '';
var bar = '';
```

Constants (variables with permanent values) are written **uppercase**.

```javascript
// Good
var FOO = 'foo';

// Bad
var foo = 'foo';
```

> Reason: TODO

### Strings

Prefer single quotes over double quotes.

```javascript
// Good
var string = '<p class="foo">Lorem Ipsum</p>';

// Bad
var string = "<p class='foo'>Lorem Ipsum</p>";
```

Hexidecimal colors are written **lowercase**.

```javascript
// Good
var color = '#d96ab6';

// Bad
var color = '#D96AB6';
```

> Reason: TODO

### New lines

Parentheses `()` and commas `,` are **not** followed by indented children on new lines.

```javascript
// Good
YUI().use('aui-module', function (Y) {
    statements
});

// Bad
YUI().use(
    'aui-module',
    function (Y) {
        statements
    }
);
```

Curly brackets `{}` are followed by **new lines** and indented children.

```javascript
// Good
if (condition) {
    statements
}
else {
    statements
}

// Bad
if (condition) {
    statements
} else {
    statements
}
```

> Reason: TODO

### Whitespace

Add spaces between **operators** (`=`, `>`, `*`, etc).

```javascript
// Good
for (i = 0; i < 10; i++) {
    statements
}

// Bad
for (i=0;i<10;i++) {
    statements
}
```

Both function expressions and function declarations **doesn't** have a space between the function keyword and the function name.

```javascript
// Good
var foo = function() {
    statements
};

// Bad
var foo = function () {
    statements
};

// Good
function bar() {
    statements
}

// Bad
function bar () {
    statements
}
```

Add spaces **outside** parentheses `()` but avoid it inside.

```javascript
// Good
if (x > 10) {
    statements
}

// Bad
if( x > 10 ){
    statements
}
```

Empty lines have no trailing spaces.

> Reason: TODO

### Conditionals

Avoid inline conditionals. Every conditional (with single or multiple statements) should use **curly brackets** `{}`. The only exception to this rule is `else if`.

```javascript
// Good
if (condition) {
    statements
}
else if (condition) {
    statements
}
else {
    statements
}

// Bad
if (condition) statement;
else if (condition) statement;
else statement;
```

> Reason: TODO

### Equality

Strict equality checks `===` should be used in favor of `==`.

```javascript
// Good
if (foo === 'foo') {
    statement
}

// Bad
if (foo == 'foo') {
    statement
}

// Good
if (bar !== 'bar') {
    statement
}

// Bad
if (bar != 'bar') {
    statement
}
```

> Reason: TODO

### Loops

Avoid inline loops. Every loop (with single or multiple statements) should use **curly brackets** `{}`.

```javascript
// Good
for (initialization; condition; expression) {
    statements
}

// Bad
for (initialization; condition; expression) statement;
```

> Reason: TODO

###### References

Heavily inspired by:

[Pedro Nauck Coding Style](https://github.com/pedronauck/my-coding-style)

[Zeno Rocha Coding Style](https://github.com/zenorocha/my-coding-style)

[Mark Otto Code Guide](https://github.com/mdo/code-guide)

[30 HTML Best Practices](http://code.tutsplus.com/tutorials/30-html-best-practices-for-beginners--net-4957)

[20 HTML Best practices you should follow](http://sixrevisions.com/web-standards/20-html-best-practices-you-should-follow/)