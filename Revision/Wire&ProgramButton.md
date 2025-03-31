# How to Wire and Program a button

![image](./imagelist/Wire&Program.png)

```
const int buttonPin = 2;
const int ledPin = 13;

int buttonState = 0;

void setup(){
    pinMode(ledPin, OUTPUT);
    pinMode(buttonPin, INPUT);
}

void loop(){
    buttonState = digitalRead(buttonPin);
    if (buttonState == HIGH){
        digitalWrite(ledPin, HIGh);
    }
    else
    {
        digitalWrite(ledPin, LOW);
    }
}
```