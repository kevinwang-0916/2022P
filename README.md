# 2022P
學習互動技術概論
# Week01
## 1. 建置環境

    桌面 > 葉正聖老師上課軟體 > Processing > 7.zip解壓縮

## 2. 畫正方
    (1) 靜態模式(剛開始)
```p
void setup(){
    size(500,500);
}
```
    (2) 動態模式(持續)
```p
void draw()
{
  background(#73E68C);
  fill(#F5FFFA);     //顏色
  rect(100,100,100,150);　　//長方形（X位置 , Y位置 , 長 , 寬）
  rect(mouseX,mouseY,100,150);
}
```

## 3. 變成網頁形式

### 3-1設定 p5.js 
    (1) 點右上角 Java > Manage...
    (2) 下載 p5 .... 

### 3-2 P語言->js
            （https://pde2js.herokuapp.com/）


## 4. 滑鼠畫圖
```p
void setup()　　///只執行一次
{   
    size(500,500);   ///畫面大小
    background(#FFFFF2);   ///背景顏色
    stroke(255,0,0);   ///畫筆顏色
}
void draw()　　///每秒60次
{   
    if(mousePressed)
    {
        line(mouseX , mouseY , pmouseX , pmouseY );   ///畫線
    }
}
void keyPressed()
{
    if (key == '1' ) stroke(#4682B4);
    if (key == '2' ) stroke(#6A5ACD);
    if (key == '3' ) stroke(#E6005C);
}
```
# Week02
## 0.做卡片
## 1.一張卡
```p
size(500,500);

int w=25;

rect(100-w/2,100-w/2,150+w,250+w,20);

fill(0,255,0);

rect(100,100,150,250,20);
```

## 2.多張卡
```p
void setup(){

  size(500,500);

}

int W=25;

void draw(){

  drawCard(100,100);

  drawCard(130,130);

  drawCard(160,160);

}

void drawCard(int x, int y){

  fill(255);

  rect(x-W/2,y-W/2,150+W,250+W,20);

  fill(#FF00F2);

  rect(x,y,150,250,20);

}
```


## 3.有字的Poker
```c++
void setup(){

  size(500,500);

}

int W=25;

void draw(){

  drawCard(100,100,"S4");

  drawCard(130,150,"H3");

  drawCard(160,200,"D5");

  drawCard(190,250,"CJ");

}

void drawCard(int x, int y, String face){

  fill(255);

  rect(x-W/2,y-W/2,150+W,250+W,20);

  fill(#FF00F2);

  rect(x,y,150,250,20);

  fill(0);

  textSize(40);

  text(face,x,y+40);

}
```



### 3-1.中文字
```c++
void setup(){

  size(500,500);

  PFont font = createFont("標楷體",40);     ///字形,大小

  textFont(font);

}

int W=25;

void draw(){

  drawCard(100,100,"黑桃4");

  drawCard(130,150,"紅心3");

  drawCard(160,200,"方塊5");

  drawCard(190,250,"梅花J");

}

void drawCard(int x, int y, String face){

  fill(255);

  rect(x-W/2,y-W/2,150+W,250+W,20);

  fill(#FF00F2);

  rect(x,y,150,250,20);

  fill(0);

  textSize(40);

  text(face,x,y+40);

}
```


### 3-2.中文字顏色
```c++
void setup(){

  size(500,500);

  PFont font = createFont("標楷體",40);

  textFont(font);

}

int W=25;

void draw(){

  drawCard(100,100,"黑桃4");

  drawCard(130,150,"紅心3");

  drawCard(160,200,"方塊5");

  drawCard(190,250,"梅花J");

}

void drawCard(int x, int y, String face){

  fill(255);

  rect(x-W/2,y-W/2,150+W,250+W,20);

  fill(#FF00F2);50,20);

  if(face.indexOf("黑桃") == -1 && face.indexOf("梅花") == -1)

    fill(#FF0000);     ///紅

  else

    fill(0);    ///黑

  textSize(40);

  text(face,x,y+40);

}
```


### 3-3.Suffle隨機抽排
```c++
void setup(){

  size(500,500);

  PFont font = createFont("標楷體",40);

  textFont(font);

  String [] flower = {"黑桃","紅心","方塊","梅花"};

  face1 = flower[int(random(4))] + int(random(13)+1);

  face2 = flower[int(random(4))] + int(random(13)+1);

  face3 = flower[int(random(4))] + int(random(13)+1);

  face4 = flower[int(random(4))] + int(random(13)+1);

}

String face1, face2, face3, face4;

void draw(){

  drawCard(100,100,face1);

  drawCard(130,150,face2);

  drawCard(160,200,face3);

  drawCard(190,250,face4);

}

void drawCard(int x, int y, String face){

  int W=25;

  fill(255);

  rect(x-W/2,y-W/2,150+W,250+W,20);

  fill(#FF00F2);

  rect(x,y,150,250,20);

  if(face.indexOf("黑桃") == -1 && face.indexOf("梅花") == -1)

    fill(255,0,0);

  else

    fill(0);

  textSize(40);

  text(face,x,y+40);

}
```



## 4.點擊洗牌
```c++
void setup(){

  size(500,500);

  PFont font = createFont("標楷體",40);

  textFont(font);

  String [] flower = {"黑桃","紅心","方塊","梅花"};

  face1 = flower[int(random(4))] + int(random(13)+1);

  face2 = flower[int(random(4))] + int(random(13)+1);

  face3 = flower[int(random(4))] + int(random(13)+1);

  face4 = flower[int(random(4))] + int(random(13)+1);

}

void mousePressed(){

  String [] flower = {"黑桃","紅心","方塊","梅花"};

  face1 = flower[int(random(4))] + int(random(13)+1);

  face2 = flower[int(random(4))] + int(random(13)+1);

  face3 = flower[int(random(4))] + int(random(13)+1);

  face4 = flower[int(random(4))] + int(random(13)+1);

}

String face1, face2, face3, face4;

void draw(){

  drawCard(100,100,face1);

  drawCard(130,150,face2);

  drawCard(160,200,face3);

  drawCard(190,250,face4);

}

void drawCard(int x, int y, String face){

  int W=25;

  fill(255);

  rect(x-W/2,y-W/2,150+W,250+W,20);

  fill(#FF00F2);

  rect(x,y,150,250,20);

  if(face.indexOf("黑桃") == -1 && face.indexOf("梅花") == -1)

    fill(255,0,0);

  else

    fill(0);

  textSize(40);

  text(face,x,y+40);

}
```
