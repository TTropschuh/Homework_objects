```javascript
// Sketch from Week 4 Conditionals

let ball = {};

ball.x = 0;
ball.y = 0;
ball.XSpeed = 2.5;
ball.YSpeed = 1;
ball.ColorR = 0;
ball.ColorG = 0;
ball.ColorB = 0;

function setup() {
    createCanvas(400, 400);
    ball.x = width / 2;
    ball.y = height / 2;
}

function draw() {
    //background(255);
    drawBall();
    ball.x += ball.XSpeed;
    ball.y += ball.YSpeed;

    if (ball.x < 0 || ball.x > width) {
        ball.XSpeed = ball.XSpeed * -1;
      ball.ColorR = random (0, 255);
      ball.ColorG = random (0, 255);
      ball.ColorB = random (0, 255);

    }
    if (ball.y < 0 || ball.y > height) {
        ball.YSpeed = ball.YSpeed * -1;
      ball.ColorR = random (0, 255);
      ball.ColorG = random (0, 255);
      ball.ColorB = random (0, 255);

    }

}

function drawBall() {
    noStroke();
    fill(ball.ColorR, ball.ColorG, ball.ColorB);
    ellipse(ball.x, ball.y, 25);
}
```

```javascript
// Sketch from Week 5 Loops

let myCircle = {};

function setup() {
  createCanvas(400, 400);

myCircle.x = width/2;
myCircle.y = height/2;
myCircle.size = 100;
myCircle.num = 5;

}

function draw() {

  background(40);


  drawCircle();

}

function drawCircle() {

  let steps = myCircle.size / myCircle.num;
  for (let i = 0; i < myCircle.num; i++) {
    noFill();
    strokeWeight(6);
    stroke(255);
    ellipse(myCircle.x, myCircle.y, myCircle.size  - i * steps, myCircle.size  - i * steps);


  }
}
```
```javascript
//Sketch from Week 7 Arrays

let point1 = [];
let point2 = [];
let numLines = 20;



function setup() {
  createCanvas(400, 400);

  for (let i = 0; i < numLines; i++) {
    point1[i] = {
      x: random(50, 350),
      y: random(50, 350),
      display: function() {
        line(this.x, this.y, this.y, this.x);
        if (this.x > width / 2) {
          ellipse(this.x, this.y, 10);
        }

        if (this.x < width / 2) {
          ellipse(this.x, this.y, 10);
        }
      }
    }
  }
}

function draw() {
  background(220);
  for (let i = 0; i < point1.length; i++) {
    point1[i].display();
  }

  noLoop();
}
```
