## Introduction

https://sourceacademy.org/sicpjs/

## Ch 01

This alternative “fully expand and then reduce” evaluation method is known as `normal-order evaluation`, in contrast to the “evaluate the arguments and then apply” method that the interpreter actually uses, which is called `applicative-order evaluation`.

JavaScript uses `applicative-order evaluation`, partly because of the additional efficiency obtained from avoiding multiple evaluations of expressions such as those illustrated with 5 + 1 and 5 * 2 above and, more significantly, because normal-order evaluation becomes much more complicated to deal with when we leave the realm of functions that can be modeled by substitution.

- Square Roots by Newton's Method

```js
function sqrt(x) {
    return sqrt_iter(1, x);
}

function is_good_enough(guess, x) {
    return abs(square(guess) - x) < 0.001
}

function average(x, y) {
    return (x + y) / 2
}

function improve(guess, x) {
    return average(guess, x / guess)
}

function sqrt_iter(guess, x) {
    return is_good_enough(guess, x)
        ? guess
        : sqrt_iter(improve(guess, x), x)
}

sqrt(9); 3.00009155413138
```
