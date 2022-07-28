# third-week-tasks
this repository include the third week tasks 
this circuit was desighned using tinkerCad simulator using the following code

int ledPin = 13;
int butPin = 2;

bool pressed = false;
bool wasPressed = false;

bool lightToggle = false;


void setup()
{
  pinMode(ledPin, OUTPUT);
  pinMode(butPin, INPUT);
  
  Serial.begin(9600);
}

void loop()
{
  wasPressed = pressed;
  pressed = digitalRead(butPin);
  Serial.println(pressed, wasPressed);
  
  if (pressed && !wasPressed){ //Button just pressed
    lightToggle = !lightToggle;
  } 
  
  digitalWrite(ledPin, lightToggle);
}
