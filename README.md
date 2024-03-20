# Encoder
```C++
#define hall_1 2
#define hall_2 3

#define SPEED_1      5 
#define DIR_1        4

int count1 = 0;
int count2 = 0;

void setup() {

  pinMode(2, INPUT);
  pinMode(3, INPUT);
  pinMode(5, OUTPUT);
  pinMode(4, OUTPUT);
  attachInterrupt(digitalPinToInterrupt(hall_1), counter1, RISING);
  attachInterrupt(digitalPinToInterrupt(hall_2), counter2, RISING);
  Serial.begin(9600);


}

void counter1(){
  count1 ++;

}
void counter2(){
  count2 ++;

}
void loop() {

  Serial.println(String(count1) + " " + String(count2));
  digitalWrite(DIR_1, HIGH);
  analogWrite(SPEED_1, 100);

}
```
