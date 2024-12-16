// Recursive circle drawing along both axes
// Each recursive step reduces the size and shifts positions to create a grid of circles

function setup() {
  createCanvas(400, 400);
  ellipseMode(RADIUS);
  noLoop();
}

function draw() {
  background(200);
  recursiveCircles(width / 2, height / 2, width / 4);
}

// Draw circles recursively along both axes
function recursiveCircles(x, y, r) {
  if (r > 4) {
    stroke(random(100, 255), random(100, 255), random(100, 255));
    strokeWeight(2);
    noFill();
    circle(x, y, r);

    // Recurse for circles along axes
    recursiveCircles(x - r, y, r / 2); // Left
    recursiveCircles(x + r, y, r / 2); // Right
    recursiveCircles(x, y - r, r / 2); // Top
    recursiveCircles(x, y + r, r / 2); // Bottom
  }
}
