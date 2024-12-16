// Fibonacci sequence generator with memoization
// Memoization stores previously calculated Fibonacci numbers to avoid redundant calculations

let n = 1; // Starting index

// Precomputed Fibonacci values for memoization
let fibs = [0, 1]; // fib(1) = 0, fib(2) = 1

function setup() {
  createCanvas(400, 400);
  noLoop();
  textAlign(CENTER, CENTER);
  textSize(20);
}

function draw() {
  background(220);
  text(`${n}th Fibonacci number: ${fib(n)}`, width / 2, height / 2);
}

// Key press event to increase n and redraw the canvas
function keyPressed() {
  if (key === " ") {
    n += 1;
    redraw();
  }
}

// Recursive Fibonacci function with memoization
function fib(n) {
  if (n <= 0) return 0; // Base case: n <= 0
  if (fibs[n] !== undefined) return fibs[n]; // Return cached value if it exists

  // Calculate and memoize the result
  fibs[n] = fib(n - 1) + fib(n - 2);
  return fibs[n];
}
