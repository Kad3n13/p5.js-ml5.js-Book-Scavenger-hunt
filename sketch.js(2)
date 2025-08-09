let asign;
let video;
let label = "analysis...";

const bookColors = {
  "x64 ASSEMBLY LANGUAGE BOOK": [40, 40, 35, 128],         
  "Design Patterns OOP BOOK": [150, 200, 230, 128],         
  'THE ANSI "C" PROGRAMMING LANGUAGE BOOK': [20, 40, 80, 128],  
  "CompTIA +A BOOK": [100, 30, 60, 128],
  "Practical Electronics For Inventors Book": [255, 210, 0, 128],
  "CCSP BOOK": [255, 200, 50, 128],
  "OS Three Easy Pieces BOOK": [255, 255, 255, 128],
  "Psychology Book": [255, 50, 50, 128],
  "Cheicle Reaction Enginnering Book": [0, 0, 0, 175],
  "21st Century C BOOK": [180, 150, 220, 128],
  "Crimanology book": [20, 30, 80, 175],
};

function setup() {
  createCanvas(1920, 1080);
  pixelDensity(1);

  video = createCapture(VIDEO);
  video.size(1920, 1080);
  video.hide();

  asign = ml5.imageClassifier("https://teachablemachine.withgoogle.com/models/W-_HGQvhU/", video, modelReady);
}

function modelReady() {
  console.log("Model ready!");
  classifyVideo();
}

function classifyVideo() {
  asign.classify(gotResults);
}

function gotResults(error, results) {
  if (error) {
    console.error(error);
    return;
  }

  label = results[0].label;
  classifyVideo();
}

function draw() {
  background(220);
  image(video, 0, 0, width, height);

  let c = bookColors[label];
  if (c) {
    fill(...c);
    rect(0, 0, width, height);
  }

  fill(255, 200);
  rect(0, height - 50, width, 50);

  fill(0);
  textSize(20);
  textAlign(CENTER, CENTER);
  text(label, width / 2, height - 25);
}
