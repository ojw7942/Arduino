![](./IMAGES1/buzzer.png)
```c
void setup() {
  pinMode(3, OUTPUT);
}

void loop(){
  tone(7, 262, 1000);
  delay(500);
  tone(7, 294, 1000);
  delay(500);
  tone(7, 330, 1000);
  delay(500);
  tone(7, 349, 1000);
  delay(500);
  tone(7, 392, 1000);
  delay(500);
  tone(7, 440, 1000);
  delay(500);
  tone(7, 494, 1000);
  delay(500);
```
```c
const int piezo = 7;
char code[] = {'C', 'D', 'E', 'F', 'G', 'A', 'B'};
unsigned int freq[] = {262, 294, 330, 349, 392, 440, 494};
char mData[] = "CCGGAAGpFFEEDCCpGGFFEEDpGGFFEEDpCCGGAAGpFFEEDDCp";
const byte mSize = sizeof(mData);
void setup() {
   pinMode(piezo, OUTPUT);
}

void loop() {
  int playT = 200;
  for(int m=0; m<mSize; m++) {
    for(int k=0; k<7; k++) {
      if(mData[m] == code[k]) tone(piezo, freq[k], playT);
    }
    delay(playT);
  }
  noTone(piezo);
  delay(2000);
}
```

![](./IMAGES1/lcd01.png)

```c
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

// 여기 주소를 스캔 결과에 맞게 수정하세요.
LiquidCrystal_I2C lcd(0x27, 16, 2);

void setup(){
  lcd.init();      // LCD 초기화
  lcd.backlight();  // 백라이트 켜기
  lcd.print("Hello, I2C!");
  }

  void loop() {
    // 할 일 없음
  }
```

![](./IMAGES1/lcd05.png)
#Tinkercad
```c
#include <Adafruit_LiquidCrystal.h>

int seconds = 0;

Adafruit_LiquidCrystal lcd_1(0);

void setup()
{
  lcd_1.begin(16, 2);

  lcd_1.print("hello world");
}

void loop()
{
  lcd_1.setCursor(0, 1);
  lcd_1.print(seconds);
  lcd_1.setBacklight(1);
  delay(500); // Wait for 500 millisecond(s)
  lcd_1.setBacklight(0);
  delay(500); // Wait for 500 millisecond(s)
  seconds += 1;
}
```
#arduino
```c
#include <LiquidCrystal_I2C.h>

int seconds = 0;

LiquidCrystal_I2C lcd_1(0x27, 16, 2);

void setup()
{
  lcd_1.init();

  lcd_1.print("hello world");
}

void loop()
{
  lcd_1.setCursor(0, 1);
  lcd_1.print(seconds);
  lcd_1.setBacklight(1);
  delay(500); // Wait for 500 millisecond(s)
  lcd_1.setBacklight(0);
  delay(500); // Wait for 500 millisecond(s)
  seconds += 1;
}
```

![](./IMAGES1/lcd04.png)

```c


![](./IMAGES1/lcd06.png)


![](./IMAGES1/photo01.png)


![](./IMAGES1/photo02.png)
