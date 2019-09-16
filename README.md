# project
report

1. 아두이노를 활용하여 주변 밝기의 명암에 따라 원에서 표시되는 색이 바뀌는 코드를 짜보았습니다. 아두이노와 조도 센서를 활용하여 주변 밝기가 밝으면 초록색으로, 어두우면 빨간색으로 표시되도록 하였습니다. 조도센서에서 받은 값을 프로세싱을 통하여 색깔을 표시하는 코드입니다. 색깔표시는 프로세싱에서 원을 나타내어 원 내부의 색깔을 빨간색과 초록색으로 표시되도록 하였습니다.
코드를 직접 짜보면서, 이러한 원리를 활용한다면 일상생활에서 많이 쓰이고 있는 센서라는 물건을 만들 수 있을 것 같습니다.
이러한 기술은 사물인터넷(IOT)이라는 기술에 포함되어 다가오는 4차 산업혁명 시대에 가장 알맞는 기술이라는 것도 알게 되었습니다.
앞으로 이러한 창의적인 코드들을 직접 짜보면서, 다가오는 시대를 주도하는 인재로 성장할 수 있도록 노력하겠습니다. 창의공학 파이팅!
"회로 사진 링크를 첨부합니다. https://github.com/kdh1004/project/blob/669822b4e30513b013811ac55de01ce68d5da7d4/%EC%BA%A1%EC%B2%98.JPG"

-------------------------------------

2.

void setup() {
  Serial.begin(9600);
}
int a;
void loop(){
  int a=analogRead(A0);
  Serial.println(a);
  if(a>255) a=0;
  delay(500);
}
--------------------------------------
3.

import processing.serial.*;
Serial p;
void setup(){
  size(300,300);
  p=new Serial(this,"COM4",9600);
}
void draw(){
  if(p.available()>0){
    String m=p.readString();
    int a =int(m.trim());
    println(a);
    if(a>310) fill(0,255,0);
    else      fill(255,0,0);
    ellipse(150,150,200,200);
  }
