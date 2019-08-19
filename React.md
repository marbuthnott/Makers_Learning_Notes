# REACT

## Intro

Computational model

## Composition

Build components that are composed together.

**Share Mutable State** similar to inheritance.

**Elements**: An element is a plain object describing a component instance or DOM node and its desired properties.
```js
const handleElement = React.createElement(
  'h3',
  null,
  handle
)
```

**Components**: Function or a class, that optionally accepts input and returns a react element.
```js
function NameComponent(props) {
  return React.createElement(
    'h1',
    null,
    props.name
  )
}
```

## Steps

* Create `index.html` and include a script tag within the `head` which references the react url from the [React links page](https://reactjs.org/docs/cdn-links.html).

```js
<!DOCTYPE html>
<html>
  <head>
    <title>First React App</title>
    <script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script>
  </head>
  <body>
    <div id='app'></div>

    <script>
      console.log('Test')
      console.log('React', window.React)
    
    </script>
  </body>
</html>
```
This will print `Test` and a React object to the console.

```js
const headerElement = React.createElement(
  'h1'
)
```
will create an element with an `h1` tag.

When you use html within a JavaScript script, it it drawing on JSX syntax.