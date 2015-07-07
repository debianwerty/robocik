#include <stdio.h>
#include <stdlib.h>
#include <wiringPi.h>
#include <softPwm.h>

#define RANGE	100
#define INITIAL_VALUE 0

//motor 1 LEFT
int enable1_pin = 27;
int in1_pin = 28;
int in2_pin =29;

//motor 2 RIGHT
int enable2_pin = 25;
int   in3_pin = 23;
int   in4_pin =24;


void init_motors()
{
   wiringPiSetup();

  // // initialize left motor (pin0, 2 & 3)
  // softPwmCreate(0, INITIAL_VALUE, RANGE);
  // softPwmCreate(2, INITIAL_VALUE, RANGE);
  // pinMode(3, OUTPUT);
  // digitalWrite(3, HIGH);

  // // initialize right motor (pin4, 5 & 6)
  // softPwmCreate(5, INITIAL_VALUE, RANGE);
  // softPwmCreate(4, INITIAL_VALUE, RANGE);
  // pinMode(6, OUTPUT);
  // digitalWrite(6, HIGH);
  
    // initialize left motor
  softPwmCreate(enable1_pin, INITIAL_VALUE, RANGE);
  pinMode(in1_pin, OUTPUT);
  pinMode(in2_pin, OUTPUT);
  digitalWrite(in1_pin, HIGH);
  digitalWrite(in2_pin, HIGH);

  // initialize right motor (25:pwm, 23:dir & 24:F)
  softPwmCreate(enable2_pin, INITIAL_VALUE, RANGE);
  pinMode(in3_pin, OUTPUT);
  pinMode(in4_pin, OUTPUT);
  digitalWrite(in3_pin, HIGH);
  digitalWrite(in4_pin, HIGH);

}

void stop_motors()
{
  // pinMode(0, OUTPUT);
  // pinMode(2, OUTPUT);
  // pinMode(3, OUTPUT);
  // digitalWrite(0, LOW);
  // digitalWrite(2, LOW);

  // pinMode(5, OUTPUT);
  // pinMode(4, OUTPUT);
  // pinMode(6, OUTPUT);
  // digitalWrite(5, LOW);
  // digitalWrite(4, LOW);

  // stop
  softPwmWrite(enable1_pin, 0);
  softPwmWrite(enable2_pin, 0);
  digitalWrite(in1_pin, HIGH);
  digitalWrite(in2_pin, HIGH);
  digitalWrite(in3_pin, HIGH);
  digitalWrite(in4_pin, HIGH);
  
  printf("motor stopped!!\n");

  // exit(1);

}

double left_speed;
double right_speed;

void motors(double speed, double left_offset, double right_offset)
{
//printf("Speed: %d\n", enable1_pin);
//delay(2000);
//speed = 100;
// to come to me, drive pin 0&5 to some power
// to away from me, drive pin 2&4 to some power

// pin 0:LM+, 2:LM-, 3:LCE
// pin 5:RM+, 4:RM-, 6:RCE
// put M+ high & M- low will come to me
// put M+ low & M- High will away from me

  left_speed = speed + left_offset;
  right_speed = speed + right_offset;

  // forward

  // digitalWrite(in1_pin, HIGH);
  // digitalWrite(in2_pin, LOW);
// softPwmWrite(enable1_pin, 100);

    // digitalWrite(in3_pin, HIGH);
  // digitalWrite(in4_pin, LOW);
// softPwmWrite(enable2_pin, 100);

// left motor
   if (left_speed < 0)  {
    softPwmWrite(enable1_pin, (int) -left_speed);
	digitalWrite(in1_pin, HIGH);
    digitalWrite(in2_pin, LOW);
    //softPwmWrite(2, 0);
  }
  else
  if (left_speed > 0)  {
    softPwmWrite(enable1_pin, (int) left_speed);
	digitalWrite(in1_pin, LOW);
    digitalWrite(in2_pin, HIGH);
    //softPwmWrite(0, 0);
  }

  // right motor
  if (right_speed < 0)  {
    softPwmWrite(enable2_pin, (int) -right_speed);
	digitalWrite(in3_pin, HIGH);
    digitalWrite(in4_pin, LOW);
    //softPwmWrite(4, 0);
  }
  else
  if (right_speed > 0)  {
    softPwmWrite(enable2_pin, (int) right_speed);
	digitalWrite(in3_pin, LOW);
    digitalWrite(in4_pin, HIGH);
 //   softPwmWrite(5, 0);
  } 
  
  
  // left motor
  // if (left_speed < 0)  {
    // softPwmWrite(0, (int) -left_speed);
    // softPwmWrite(2, 0);
  // }
  // else
  // if (left_speed > 0)  {
    // softPwmWrite(2, (int) left_speed);
    // softPwmWrite(0, 0);
  // }

 // right motor
  // if (right_speed < 0)  {
    // softPwmWrite(5, (int) -right_speed);
    // softPwmWrite(4, 0);
  // }
  // else
  // if (right_speed > 0)  {
    // softPwmWrite(4, (int) right_speed);
    // softPwmWrite(5, 0);
  // }
}



