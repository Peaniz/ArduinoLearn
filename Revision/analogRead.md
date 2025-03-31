# Analog Read 

```
int sensorPin = A0;
int ledPin = 13;
int sensorValue = 0;

void setup(){
    pinmode(ledPin, OUTPUT);
}

void loop(){
    sensorValue = analogRead(sensorPin);
    digitalWrite(ledPin, HIGH); // turn the ledPin on
    delay(sensorValue); // stop the program for <sensorValue> milliseconds:
    digitalWrite(ledPin, LOW);
    delay(sensorValue);

}
```

