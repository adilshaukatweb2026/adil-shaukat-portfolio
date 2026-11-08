# CSS Combinators

## Introduction

CSS Combinators are used to select HTML elements based on their relationship with other elements.
They help us apply styles to specific elements without adding extra classes or IDs.

## 1. Descendant Combinator (Space)

The Descendant Combinator selects all elements that are inside a specified parent element, even if they are deeply nested.

### Syntax

```css
parent child {
    property: value;
}
div p {
    color: red;
}
```

### HTML Example
```html
<div>
    <p>Paragraph 1</p>
    <section>
        <p>Paragraph 2</p>
    </section>
</div>
```

### CSS Example
```css
div p {
    color: red;
}
```

### Working

Both paragraphs will become red because both are inside the div element. The first paragraph is a direct child, while the second paragraph is inside the section element.

## 2. Child Combinator (>)

The Child Combinator selects only the direct children of a specified parent element. It does not select nested elements.

### Syntax

```css
parent > child {
    property: value;
}

div > p {
    color: blue;
}
```

### HTML Example

```html
<div>
    <p>Direct Child</p>
    <section>
        <p>Nested Child</p>
    </section>
</div>
```

### CSS Example

```css
div > p {
    color: blue;
}
```

### Working

Only the first paragraph will become blue because it is a direct child of the div element. The second paragraph will not become blue because it is inside the section element.

## 3. Adjacent Sibling Combinator (+)

The Adjacent Sibling Combinator selects an element that comes immediately after another specified element. Both elements must have the same parent.

### Syntax

```css
element + sibling {
    property: value;
}

h2 + p {
    color: green;
}
```
### HTML Example

```html
<div>
    <h2>Heading</h2>
    <p>First Paragraph</p>
    <p>Second Paragraph</p>
</div>
```

### CSS Example

```css
h2 + p {
    color: green;
}
```

### Working

Only the first paragraph will become green because it comes immediately after the h2 element. The second paragraph will not become green because it does not come immediately after the h2 element.

## 4. General Sibling Combinator (~)

The General Sibling Combinator selects all specified sibling elements that come after another element. Both elements must have the same parent.

### Syntax

```css
element ~ sibling {
    property: value;
}

h2 ~ p {
    color: orange;
}
```

### HTML Example

```html
<div>
    <h2>Heading</h2>
    <p>First Paragraph</p>
    <span>Some Text</span>
    <p>Second Paragraph</p>
</div>
```

```css
h2 ~ p {
    color: orange;
}
```

### Working

Both paragraphs will become orange because they are siblings of the h2 element and come after it. The span element between them does not affect the selection.