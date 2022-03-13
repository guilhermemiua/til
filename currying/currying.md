# Currying

Haskell Curry defines currying technique as:

> "Currying is the technique of translating the evaluation of a function that takes multiple arguments into evaluating a sequence of functions, each with a single argument".

We can describe Currying as a process of linking functions to reduce the number of arguments needed. This technique transforms a function f(a, b, c) into f(a)(b)(c).

Example:

```
// Function
const showNotification = (message, type) => {
  const notificationColor = {
    success: 'green',
    error: 'red',
    warning: 'yellow'
  }

  return lib.notify(message, notificationColor[type])
}

// Curried function
const showNotification = (type) => (message) => {
  const notificationColor = {
    success: 'green',
    error: 'red',
    warning: 'yellow'
  }

  return lib.notify(message, notificationColor[type])
}

const showSuccessNotification = showNotification('success')
showSuccessNotification('Success notification!')
```
