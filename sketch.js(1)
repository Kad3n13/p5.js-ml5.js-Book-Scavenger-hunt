let asign;
let video;
let label = "analysis...";

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

  let overlayColor = null;

  if (label == "x64 ASSEMBLY LANGUAGE BOOK") {
    overlayColor = color(40, 40, 35, 128);  
  } else if (label == "Design Patterns OOP BOOK") {
    overlayColor = color(150, 200, 230, 128);  
  } else if (label == 'THE ANSI "C" PROGRAMMING LANGUAGE BOOK') {
    overlayColor = color(20, 40, 80, 128);  
  } else if (label == "CompTIA +A BOOK") {
    overlayColor = color(100, 30, 60, 128);
    
  } else if (label == "Practical Electronics For Inventors Book") {
    overlayColor = color(255, 210, 0, 128);
  
  } else if (label == "CCSP BOOK") {
    overlayColor = color(255, 200, 50 ,128);
  
  } else if (label == "OS Three Easy Pieces BOOK") {
    overlayColor = color(255, 255, 255, 128);
  
  } else if (label == "Psychology Book") {
    overlayColor = color(255, 50, 50, 128);
  
  } else if (label == "Cheicle Reaction Enginnering Book") {
    overlayColor = color(0, 0, 0, 175);
  
  } else if (label == "21st Century C BOOK") {
    overlayColor = color(180, 150, 220, 128);
  
  } else if (label == "Crimanology book") {
    overlayColor = color(20, 30, 80, 175);
  }


  if (overlayColor) {
    fill(overlayColor);
    rect(0, 0, width, height);
  }


  fill(255, 200);
  rect(0, height - 50, width, 50);

  fill(0);
  textSize(20);
  textAlign(CENTER, CENTER);
  text(label, width / 2, height - 25);
}
