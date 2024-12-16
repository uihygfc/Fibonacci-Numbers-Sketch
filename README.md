function setup() {
  createCanvas(400, 400);
  ellipseMode(RADIUS);
  noLoop(); 
}

function draw() {
  background(220);
  rCircle(width / 2, color(0, 128, 255)); 
}

function rCircle(r, c) {
  if (r > 1) { 
    stroke(c);
    strokeWeight(2);
    noFill();
    circle(width / 2, height / 2, r);
    const nextColor = lerpColor(c, color(255), 0.2); 
   
    rCircle(r / 2, nextColor);
  }
}

function rCircles(x1, x2, c) {
  const d = abs(x1 - x2);
  if (d > 4) { 
    const r = d / 2;
    const hr = r / 2;

    stroke(c);
    strokeWeight(2);
    noFill();

    circle(x1, height / 2, r);
    circle(x2, height / 2, r);

    const nextColor = lerpColor(c, color(255), 0.2); 
    rCircles(x1 - hr, x1 + hr, nextColor);
    rCircles(x2 - hr, x2 + hr, nextColor);
  }
}
