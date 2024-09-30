
# JavaScript Code for Mathematical Expression

![Screenshot 2024-09-27 165308](https://github.com/user-attachments/assets/b0b148d8-8abb-4bb1-b5ad-2a9dfc9917e7)


\[
\frac{\int \sqrt{x^2 - 5} \, dx - 3 \int \frac{x}{\sqrt{x^2 + 5}} \, dx}{\int \frac{x \left( (x^2 + 5) - 3 \right)}{\sqrt{x^2 + 5}} \, dx}
\]



```javascript
// Import mathjs library
const math = require('mathjs');

// Define the functions
const integrand1 = (x) => Math.sqrt(x * x - 5);
const integrand2 = (x) => (x / Math.sqrt(x * x + 5));
const integrand3 = (x) => (x * ((x * x + 5) - 3) / Math.sqrt(x * x + 5));

// Define integration limits (we can use indefinite or definite limits here)
const lowerLimit = 1; // you can change this based on the limits you want
const upperLimit = 10; // you can change this based on the limits you want

// Compute the integrals
const integral1 = math.integral('sqrt(x^2 - 5)', 'x').evaluate({ x: upperLimit }) - math.integral('sqrt(x^2 - 5)', 'x').evaluate({ x: lowerLimit });
const integral2 = math.integral('x / sqrt(x^2 + 5)', 'x').evaluate({ x: upperLimit }) - math.integral('x / sqrt(x^2 + 5)', 'x').evaluate({ x: lowerLimit });
const integral3 = math.integral('x * ((x^2 + 5) - 3) / sqrt(x^2 + 5)', 'x').evaluate({ x: upperLimit }) - math.integral('x * ((x^2 + 5) - 3) / sqrt(x^2 + 5)', 'x').evaluate({ x: lowerLimit });

// Combine the results as per the original formula
const result = (integral1 - 3 * integral2) / integral3;

console.log("Result of the expression: ", result);
```

## How to Use:

1. Install the `mathjs` library using the following command:

```
npm install mathjs
```

2. Run the script in a Node.js environment.

The integrals are evaluated using limits from 1 to 10, but you can adjust these limits or perform indefinite integration by modifying the `lowerLimit` and `upperLimit` variables.
