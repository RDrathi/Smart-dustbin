# Smart-dustbin
This code contains feature for a easy use dustbin with anti- theft mechanism(no network dependent)

#define S1 0
#define trigPin 10
#define echoPin 11
#define led 9
#define led2 8
#define led3 7

void setup() {
  Serial.begin (9600);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(led, OUTPUT);
  pinMode(led2, OUTPUT);
}

void loop() {

   int  in1 = digitalRead(S1);

  if (in1 == LOW ) {
    digitalWrite(led,LOW);
   digitalWrite(led2,HIGH); 
    delay(500);
     digitalWrite(led,LOW);
      digitalWrite(led2,LOW)
      delay(5000);
    digitalWrite(led,HIGH); 
   digitalWrite(led2,LOW);
       delay(500);
      digitalWrite(led,LOW);
      digitalWrite(led2,LOW);
  } else {
  digitalWrite(led,LOW);
      digitalWrite(led2,LOW);
   
  }
  long duration, distance;
  digitalWrite(trigPin, LOW);  // Added this line
  delayMicroseconds(2); // Added this line
  digitalWrite(trigPin, HIGH);
//  delayMicroseconds(1000); - Removed this line
  delayMicroseconds(10); // Added this line
  digitalWrite(trigPin, LOW);
  duration = pulseIn(echoPin, HIGH);
  distance = (duration/2) / 29.1;
  if (distance >= 10) {  // This is where the LED On/Off happens
   // digitalWrite(led,HIGH); // When the Red condition is met, the Green LED should turn off
 // digitalWrite(led2,HIGH);
  digitalWrite(led3,LOW);
}
