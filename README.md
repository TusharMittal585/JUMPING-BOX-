# JUMPING-BOX-
var canvas;
var music; 
var floor1,floor2;
var floor3,floor4,box;

function preload(){
    music = loadSound("music.mp3");
}


function setup(){
    canvas = createCanvas(800,600);

    floor1=createSprite(100,450,150,10)
    floor1.shapeColor="yellow"
    floor2=createSprite(305,450,150,10)
    floor1.shapeColor="green"
    floor3=createSprite(510,450,150,10)
    floor3.shapeColor="red"
    floor4=createSprite(715,450,150,10)
    floor4.shapeColor="blue"
    box=createSprite(20,20,20,20) 
    box.shapeColor="black"
    box.velocityX=4;
    box.velocityY=4;

} 

function draw() { 
    background(rgb(169,169,169));
    createEdgeSprites();
    box.bounceOff(edges);

   drawSprites();

   
   
    if(floor1.isTouching(box) && box.bounceOff(floor1)){
        box.shapeColor="yellow"
    }
    if(floor2.isTouching(box) && box.bounceOff(floor2)){
        box.shapeColor="green"
    }
    if(floor3.isTouching(box) && box.bounceOff(floor3)){
        box.shapeColor="red"
    }
    if(floor4.isTouching(box) && box.bounceOff(floor4)){
        box.shapeColor="blue"
    } 
    if(box.isTouching(floor1) || box.isTouching(floor2) || box.isTouching(floor3) || box.isTouching(floor4)){
        music.play();
    }
    if(floor3.isTouching(box)){
        box.shapeColor=rgb(255,128,0);
        box.velocityX=0;
        box.velocityY=0;
        music.stop();
    }
   
  } 
