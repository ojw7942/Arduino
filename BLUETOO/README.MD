![](./IMAGES/z01.png)

```C
#include<SoftwareSerial.h>
SoftwareSerial BT(2, 3);

void setup() {
  BT.begin(9600);
  pinMode(8, OUTPUT);
}
void loop(){
  if(BT.available()) {
    int value = BT.read();
    if(value == '1') {
      digitalWrite(8, HIGH);
    }
    if(value == '2') {
      digitalWrite(8, LOW);
    }
  }
}
```
![](./IMAGES/z03.png)

![](./IMAGES/s01.png)
```c
const int buttonPin = 8;    // 버튼 핀
const int buzzerPin = 2;    // 부저 핀

bool buzzerState = false;        // 부저의 현재 ON/OFF 상태 저장
bool lastButtonState = HIGH;     // 이전 버튼 상태 (초기에는 HIGH)

void setup() {
  pinMode(buttonPin, INPUT_PULLUP);  // 버튼 입력, 내부 풀업 사용
  pinMode(buzzerPin, OUTPUT);        // 부저 출력 모드 설정
  digitalWrite(buzzerPin, LOW);      // 초기에는 부저 OFF
}

void loop() {
  bool currentButtonState = digitalRead(buttonPin);  // 현재 버튼 상태 읽기

  // 눌림 순간 감지 (HIGH → LOW 변화 시 토글 실행)
  if (lastButtonState == HIGH && currentButtonState == LOW) {
    buzzerState = !buzzerState;  // 상태 반전
    digitalWrite(buzzerPin, buzzerState ? HIGH : LOW);  // 부저 ON/OFF
    delay(200);  // 디바운스 처리
  }

  lastButtonState = currentButtonState;  // 현재 상태를 이전 상태로 저장
}
```
![](./IMAGES/s02.png)
```c
const int redPin = 9;
const int greenPin = 8;
const int bluePin = 7;


void setup(){
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  pinMode(bluePin, OUTPUT);
}

void loop() {
  digitalWrite(redPin, HIGH);
  digitalWrite(greenPin, LOW);
  digitalWrite(bluePin, LOW);
  delay(1000);
  digitalWrite(greenPin, HIGH);
  digitalWrite(redPin, LOW);
  digitalWrite(bluePin, LOW);
  delay(1000);
  digitalWrite(bluePin, HIGH);
  digitalWrite(redPin, LOW);
  digitalWrite(greenPin, LOW);
  delay(1000);
}
```    
![](./IMAGES/s02.png)
```c
const int potPin = A0;     // 가변저항 중앙 핀 (아날로그 입력)
const int ledPin = 2;      // PWM 출력 핀에 연결된 LED

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  int potValue = analogRead(potPin);              // 0~1023 입력
  int brightness = map(potValue, 0, 1023, 0, 255); // 0~255로 변환
  analogWrite(ledPin, brightness);                // LED 밝기 조절
  delay(10);
}
```




















