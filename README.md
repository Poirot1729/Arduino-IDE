# Arduino-IDE
int led=13;
char ch;
void setup() {
Serial.begin(9600); //initialize serial communication
pinMode(led,OUTPUT);
}
void blink()
{ for(int i=0;i<10;i++)
  {digitalWrite(13, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);              // wait for a second
  digitalWrite(13, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);              // wait for a second
  }
}


void loop() {
if(Serial.available()>0)// see if there is any incoming data
{ch=Serial.read();//read the oldest byte in the buffer
if(ch=='H')
digitalWrite(led,HIGH);
if(ch=='L')
digitalWrite(led,LOW);
if(ch=='B')
blink();
  }
}
