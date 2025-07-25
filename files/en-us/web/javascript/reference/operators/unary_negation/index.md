---
title: Unary negation (-)
slug: Web/JavaScript/Reference/Operators/Unary_negation
page-type: javascript-operator
browser-compat: javascript.operators.unary_negation
sidebar: jssidebar
---

The **unary negation (`-`)** operator precedes its operand and negates it.

{{InteractiveExample("JavaScript Demo: Unary negation (-) operator")}}

```js interactive-example
const x = 4;
const y = -x;

console.log(y);
// Expected output: -4

const a = "4";
const b = -a;

console.log(b);
// Expected output: -4
```

## Syntax

```js-nolint
-x
```

## Description

The `-` operator is overloaded for two types of operands: number and [BigInt](/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt). It first [coerces the operand to a numeric value](/en-US/docs/Web/JavaScript/Guide/Data_structures#numeric_coercion) and tests the type of it. It performs BigInt negation if the operand becomes a BigInt; otherwise, it performs number negation.

## Examples

### Negating numbers

```js
const x = 3;
const y = -x;
// y is -3; x is 3
```

### Negating non-numbers

The unary negation operator can convert a non-number into a number.

```js
const x = "4";
const y = -x;

// y is -4
```

BigInts can be negated using the unary negation operator.

```js
const x = 4n;
const y = -x;

// y is -4n
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Addition (`+`)](/en-US/docs/Web/JavaScript/Reference/Operators/Addition)
- [Subtraction (`-`)](/en-US/docs/Web/JavaScript/Reference/Operators/Subtraction)
- [Division (`/`)](/en-US/docs/Web/JavaScript/Reference/Operators/Division)
- [Multiplication (`*`)](/en-US/docs/Web/JavaScript/Reference/Operators/Multiplication)
- [Remainder (`%`)](/en-US/docs/Web/JavaScript/Reference/Operators/Remainder)
- [Exponentiation (`**`)](/en-US/docs/Web/JavaScript/Reference/Operators/Exponentiation)
- [Increment (`++`)](/en-US/docs/Web/JavaScript/Reference/Operators/Increment)
- [Decrement (`--`)](/en-US/docs/Web/JavaScript/Reference/Operators/Decrement)
- [Unary plus (`+`)](/en-US/docs/Web/JavaScript/Reference/Operators/Unary_plus)
