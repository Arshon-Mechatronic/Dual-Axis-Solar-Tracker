#include <Servo.h>

Servo horizontal; // horizontal servo

int servoh = 90;

int servohLimitHigh = 60;

int servohLimitLow = 5;

// 65 degrees MAX

Servo horizontal2; // horizontal servo 2

int servoh2 = 90;

int servoh2LimitHigh = 5;

int servoh2LimitLow = 60;

// 65 degrees MAX

Servo vertical; // vertical servo

int servov = 45;

int servovLimitHigh = 60;

int servovLimitLow = 30;

// LDR pin connections

// name = analogpin;

int ldrlt = A0; //LDR top left - BOTTOM LEFT <--- BDG

int ldrrt = A3; //LDR top rigt - BOTTOM RIGHT

int ldrld = A1; //LDR down left - TOP LEFT

int ldrrd = A3; //ldr down rigt - TOP RIGHT

void setup(){

horizontal.attach(9);

horizontal2.attach(11);

vertical.attach(12);

horizontal.write(180);

vertical.write(45);

int rd = analogRead(ldrrd); // down right

int dtime = 10; int tol = 90; // dtime=diffirence time, tol=toleransi

int avt = (lt + rt) / 2; // average value top

int avd = (ld + rd) / 2; // average value down

int avl = (lt + ld) / 2; // average value left

int avr = (rt + rd) / 2; // average value right

int dvert = avt - avd; // check the diffirence of up and down

int dhoriz = avl - avr;// check the diffirence og left and rigt

if (-1*tol > dvert || dvert > tol)

{

if (avt > avd)

{

servov = --servov;

if (servov > servovLimitHigh)

{servov = servovLimitHigh;}

}

else if (avt < avd)

{servov= ++servov;

if (servov < servovLimitLow)

{ servov = servovLimitLow;}

}

vertical.write(servov);

}

if (-1*tol > dhoriz || dhoriz > tol) // check if the diffirence is in the tolerance else

change horizontal angle

{

if (avl > avr)

{

servoh = --servoh;

servoh2 = ++servoh2;

if (servoh < servohLimitLow)

{

servoh = servohLimitLow;

}

if (servoh2 < servoh2LimitLow)

{

servoh2 = servoh2LimitLow;

}

}

delay(2500);

}

void loop() {

int lt = analogRead(ldrlt); // top left

int rt = analogRead(ldrrt); // top right

int ld = analogRead(ldrld); // down left

else if (avl < avr)

{

servoh = ++servoh;

servoh2 = --servoh2;

if (servoh > servohLimitHigh)

{

servoh = servohLimitHigh;

}

if (servoh2 > servoh2LimitHigh)

{

servoh2 = servoh2LimitHigh;

}

}

else if (avl = avr)

{

delay(5000);

}

horizontal.write(servoh);

horizontal2.write(servoh2);

}

delay(dtime);

}
