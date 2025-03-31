# Attach Interrupt

### Value: 
1. LOW trigger when pin is low
2. CHANGE trigger when the pin changes
3. RISING trigger when pin goes from low to high
4. FALLING trigger when pin goes from high to low
5. HIGH trigger when pin is high

### Example:

```
const byte ledPin = 13;
const byte IntteruptPin = 2;
volatile byt state = LOW; //using volatile for variables that 
can change unexpectedly

void setup()
{
    pinMode(ledPin, OUTPUT);
    pinMode(interruptPin, INPUT_PULLUP);
    attachInterrupt(digitalPintoInterrupt(interruptpin), blink, CHANGE);
}

void loop(){
    digitalWrite(ledPin, state);
}

void blink()
{
    state = !state;
}
```