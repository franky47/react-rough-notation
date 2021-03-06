# Rough Notation React (Wrapper)

This is a React wrapper for [RoughNotation](https://roughnotation.com/), a small JavaScript library to create and animate annotations on a web page.

- [Visit website to see it in action](https://roughnotation.com/)
- [Library docs](https://github.com/pshihn/rough-notation)

![Rough Notation logo](https://roughnotation.com/images/social.png)

## Table of contents

<!-- TOC -->

- [Rough Notation React (Wrapper)](#rough-notation-react-wrapper)
  - [Table of contents](#table-of-contents)
  - [Installation](#installation)
  - [RoughNotation Component](#roughnotation-component)
    - [Usage](#usage)
    - [Props](#props)
    - [Type values](#type-values)
  - [RoughNotationGroup Component](#roughnotationgroup-component)
    - [Usage](#usage)
    - [Props](#props)
  - [Playground](#playground)
  - [TODO](#todo)

<!-- /TOC -->

## Installation

You can add rough-notation to your project via npm.

```
npm install --save react-rough-notation
```

Then just import the components you need.

```js
import { RoughNotation, RoughNotationGroup } from "react-rough-notation";
```

## RoughNotation Component

This is the main component, is a span element by default but you can change the tag name by anything you want using the `customElement` prop.

### Usage

```jsx
<RoughNotation type="underline" show={state.show}>
  Hello RoughNotation
</RoughNotation>
```

### Props

Any unlisted prop will be pass to the component so you can use any react prop to handle interactions or styling.

| name                | type     | default                                                        | description                                                                                                                                                               |
| ------------------- | -------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| animate             | boolean  | true                                                           | Turn on/off animation when annotating                                                                                                                                     |
| animationDelay      | number   | 0                                                              | Delay in animation in milliseconds                                                                                                                                        |
| animationDuration   | number   | 800                                                            | Duration of the animation in milliseconds                                                                                                                                 |
| color               | string   |                                                                | String value representing the color of the annotation sketch                                                                                                              |
| customElement       | string   | span                                                           | Element wrapper tagName                                                                                                                                                   |
| getAnnotationObject | function | (annotation) => {}                                             | Callback function called after annotation init, it will receive the javascript [annotation object](https://github.com/pshihn/rough-notation#annotation-object) as a param |
| padding             | 5        | number                                                         | Padding between the element and roughly where the annotation is drawn                                                                                                     |
| show                | boolean  | false                                                          | Show/hide the annotation                                                                                                                                                  |
| strokeWidth         | number   | 1                                                              | Width of the annotation strokes                                                                                                                                           |
| type                | enum     | underline, box, circle, highlight, strike-through, crossed-off | This is a mandatory field. It sets the annotation style                                                                                                                   |

### Type values

| value          | description                                             |
| -------------- | ------------------------------------------------------- |
| underline      | Create a sketchy underline below an element             |
| box            | This style draws a box around the element               |
| circle         | Draw a circle around the element                        |
| highlight      | Creates a highlight effect as if maked by a highlighter |
| strike-through | This style draws a box around the element               |
| crossed-off    | This style draws a box around the element               |

## RoughNotationGroup Component

This is a wrapper for multiple annotations, it will trigger the `show()` method on every child annotation after the prev annotation animation is complete. **It does not render any HTML element.**

### Usage

```jsx
<RoughNotationGroup show={state.show}>
  <RoughNotation type="underline">Hello,</RoughNotation>
  <RoughNotation type="underline">This is</RoughNotation>
  <RoughNotation type="underline">a Test</RoughNotation>
</RoughNotationGroup>
```

### Props

| name | type    | default | description                |
| ---- | ------- | ------- | -------------------------- |
| show | boolean |         | show/hides the annotations |

## Playground

You can find a [CodeSandbox demo here](https://codesandbox.io/s/react-rough-notation-playground-gvkq2?file=/src/App.js)

## TODO

- [ ] Add group annotation custom order support
- [ ] Auto compile and publish to npm
- [ ] Testing
