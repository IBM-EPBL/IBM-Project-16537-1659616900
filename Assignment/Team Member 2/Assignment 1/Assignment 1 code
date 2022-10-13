int trigger=2;
int echo=3;

void setup()
{
  Serial.begin(9600);
  pinMode(trigger,OUTPUT);
  pinMode(echo,INPUT);
  pinMode(12,OUTPUT);
}

void loop()
{
  //Measuring the distance for alerting
  digitalWrite(trigger,LOW);
  digitalWrite(trigger,HIGH);
  delayMicroseconds(10);
  digitalWrite(trigger,LOW);
  float dur=pulseIn(echo,HIGH);
  float dis=(dur*0.0343)/2;
  Serial.print("Distance is: ");
  Serial.println(dis);

  //Turining on LED for Alert
  if(dis>=100)
  {
    digitalWrite(8,HIGH);
    digitalWrite(7,HIGH);
  }

  //Buzering for Ultrasonic Sensor Alert
  if(dis>=100){
     for(int i=0; i<=30000; i=i+10){
       tone(12,i);
       delay(1000);
       noTone(12);
       delay(1000);
     }
  }
    //Measuring Temperate Sensor
  double a= analogRead(A0);
  double t=(((a/1024)*5)-0.5)*100;
  Serial.print("Temp Value: ");
  Serial.println(t);
  delay(1000);
  //TURN LED ON for Temperature alert
  if(t>=100)
  {
    digitalWrite(8,HIGH);
    digitalWrite(7,HIGH);
  }

  //BUZZER FOR TURNING TEMPERATURE
  if(t>=100)
  {
  for(int i=0; i<=30000; i=i+10)
  {
  tone(12,i);
  delay(1000);
  noTone(12);
  delay(1000);
  }
  }

   //TO OFF THE LED
  if(t<100)
  {
    digitalWrite(8,LOW);
    digitalWrite(7,LOW);
  }
}
