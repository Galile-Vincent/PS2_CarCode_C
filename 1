#include "PS2X_lib.h"
#include <Servo.h>
void advance(int a , int se); //左右輪子 前轉
void spin_R(int a , int se); //左輪前轉， 右輪 後傳
void spin_L(int a , int se); //右輪前轉， 左輪 後傳
void back(int a , int se); //左右輪子 後轉
void stopp(int a); //左右輪子 不動
PS2X ps2x;
Servo servoMotor;
int servoPin=5;
int error;// 連接狀態回覆參數 ，數值 0 = 連接成功
int pinI1=9; // L298N的 IN1 腳 電機驅動板定義腳位 左1+
int pinI2=8; // IN2腳位 左2
int pinI3=7; //L298N的 IN3 腳位 電機驅動板定義腳位 右1+
int pinI4=6; // IN4腳位 右2
int a=40; //函數運轉後， delay 的時間
int se=250; // L298N 功率輸出 值0～255， ENA 沒有接上，這個變數就沒有用處
//int error1=9;
//int i;
void setup() {
Serial.begin(9600);
servoMotor.attach(servoPin);
pinMode(pinI1,OUTPUT);
pinMode(pinI2,OUTPUT);
pinMode(pinI3,OUTPUT);
pinMode(pinI4,OUTPUT);
while(1){ //搖桿與接收器 配對連線
error = ps2x.config_gamepad(10 , 12 , 11 ,13 , false , false );
/* 設定 UNO的 腳位 對應的參數 (clock,command,attention,data, Pressures?,
Rumble?) */
if (error == 0)
{ Serial.print("Gamepad found!");
break;}
else { delay(200); }
}
}

void loop(){
ps2x.read_gamepad(false, 0); //每一迴圈 啟動 讀取PS2無線手把的數值
//ps2x.read_gamepad();
//判斷那個按鈕和搖桿 的數值輸出
if(ps2x.Button(PSB_START)) //Start鍵
Serial.println("Start is being held");
if(ps2x.Button(PSB_SELECT)) //Select鍵
Serial.println("Select is being held");
//advance(int a , int se); //左右輪子 前轉
//spin_R(int a , int se); //左輪前轉， 右輪 後傳
//spin_L(int a , int se); //右輪前轉， 左輪 後傳
//back(int a , int se); //左右輪子 後轉
//stopp(int a); //左右輪子 不動
if(ps2x.Button(PSB_PAD_UP)) { //十字方向，上
Serial.print("Up held this hard:");
Serial.println(ps2x.Analog(PSAB_PAD_UP), DEC);
advance(a+150 , se); //左右輪子 前轉
}
if(ps2x.Button(PSB_PAD_RIGHT)){ //十字方向，右
Serial.print("Right held this hard: ");
Serial.println(ps2x.Analog(PSAB_PAD_RIGHT), DEC);
spin_R( a , se); //左輪前轉， 右輪 後傳
}
if(ps2x.Button(PSB_PAD_LEFT)){ //十字方向，左
Serial.print("LEFT held this hard: ");
Serial.println(ps2x.Analog(PSAB_PAD_LEFT), DEC);
spin_L( a , se); //右輪前轉， 左輪 後傳
}
if(ps2x.Button(PSB_PAD_DOWN)){ //十字方向，下
Serial.print("DOWN held this hard: ");
Serial.println(ps2x.Analog(PSAB_PAD_DOWN), DEC);
back(a+150 , se); //左右輪子 後轉
}
if(ps2x.NewButtonState(PSB_L3)) //L3鍵，NewButtonState按下不管多久只會觸發兩次(按下和放開)
Serial.println("L3 pressed");
if(ps2x.NewButtonState(PSB_R3)) //R3鍵
Serial.println("R3 pressed stop");
stopp( a); //左右輪子 不動
if(ps2x.NewButtonState(PSB_L2)) //L2鍵
Serial.println("L2 pressed");
if(ps2x.NewButtonState(PSB_R2)) //R2鍵
Serial.println("R2 pressed");
if(ps2x.NewButtonState(PSB_TRIANGLE)){ //三角按鍵
servoMotor.write(90);
}

if(ps2x.NewButtonState(PSB_CIRCLE)){ //圓型按鍵
Serial.println("Circle pressed");
}
if(ps2x.NewButtonState(PSB_CROSS)){ //X按鍵
servoMotor.write(180);
}
if(ps2x.NewButtonState(PSB_SQUARE)){ //方型按鍵
Serial.println("Square pressed");
}
//讀取顯示兩個搖桿（香菇頭）的數值
//請注意 操作要求： 必須同時 按下“L1”或“R1” 其中的一個鍵，搖動香菇頭搖桿 才能讀到搖桿的數值
if(ps2x.Button(PSB_L1) || ps2x.Button(PSB_R1)) { //按下L1或L2鍵，顯示兩個香菇頭的數值
Serial.print("Stick Values:");
Serial.print(ps2x.Analog(PSS_LY), DEC); //左，上下
if(ps2x.Analog(PSS_LY)<100) advance( a , se);
if(ps2x.Analog(PSS_LY)>150) back( a , se);
Serial.print(",");
Serial.print(ps2x.Analog(PSS_LX), DEC); //左，左右
if(ps2x.Analog(PSS_LX)<30) turn_L( a , se);
if(ps2x.Analog(PSS_LX)>220) turn_R( a , se);
Serial.print(",");
Serial.print(ps2x.Analog(PSS_RY), DEC); //右，上下
Serial.print(",");
Serial.println(ps2x.Analog(PSS_RX), DEC); //右，左右
}
delay(10);
}
// 左右輪子都前進 函數(int a時間，int se 速度）
void advance(int b , int se)
{
// analogWrite(ENA,se); // 左輪方 速度 設定
// analogWrite(ENB,se); //右輪方 速度 設定
digitalWrite(pinI1,1); //左輪前進
digitalWrite(pinI2,0);
digitalWrite(pinI3,1); // 右輪前進
digitalWrite(pinI4,0);
delay(b);
}
//右轉(雙輪) 函數(int a時間，int se 速度）
void spin_R(int b , int se)
{
// analogWrite(ENA,se);//左輪方 速度 設定
// analogWrite(ENB,se);//右輪方 速度 設定

digitalWrite(pinI1,1);
digitalWrite(pinI2,0); //使左輪子 前進 動作
digitalWrite(pinI3,0); //使右輪子 後退 動作
digitalWrite(pinI4,1);
delay(b);
}
//左轉(雙輪) 函數(int a時間，int se 速度）
void spin_L(int b , int se)
{
// analogWrite(ENA,se);//左輪方 速度 設定
// analogWrite(ENB,se);//右輪方 速度 設定
digitalWrite(pinI1,0); //使左輪子 後退 動作
digitalWrite(pinI2,1);
digitalWrite(pinI3,1); //使右輪子 前進 動作
digitalWrite(pinI4,0);
delay(b);
}
// 後退 函數(int a時間，int se 速度）
void back(int b , int se)
{
// analogWrite(ENA,se);//左輪方 速度 設定
// analogWrite(ENB,se);//右輪方 速度 設定
digitalWrite(pinI1,0); //使右輪子 後退 動作
digitalWrite(pinI2,1);
digitalWrite(pinI3,0); //使右輪子 後退 動作
digitalWrite(pinI4,1);
delay(b);
}
//停止 (只要設定時間) 時間數值越大 剎車越強
void stopp(int b)
{
digitalWrite(pinI3,HIGH);
digitalWrite(pinI4,HIGH);
digitalWrite(pinI1,HIGH);
digitalWrite(pinI2,HIGH);
//delay(a);
}
//右轉(雙輪) 函數(int a時間，int se 速度）
void turn_R(int b , int se)
{
// analogWrite(ENA,se);//左輪方 速度 設定
// analogWrite(ENB,se);//右輪方 速度 設定
digitalWrite(pinI3,0); //使右輪子 不轉動 動作
digitalWrite(pinI4,1);
digitalWrite(pinI1,1);

digitalWrite(pinI2,0); //使左輪子 前進 動作
delay(b/2);
}
//左轉(雙輪) 函數(int a時間，int se 速度）
void turn_L(int b , int se)
{
// analogWrite(ENA,se);//左輪方 速度 設定
// analogWrite(ENB,se);//右輪方 速度 設定
digitalWrite(pinI1,0); //使左輪子 不轉動 動作
digitalWrite(pinI2,1);
digitalWrite(pinI3,1); //使右輪子 前進 動作
digitalWrite(pinI4,0);
delay(b/2);
}
