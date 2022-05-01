# mini-project

# SIMPLE PROJECT OF ‘’TURNING ON a LAMP USING KEYPAD’’


# ABSTRACT

 Technology is a never-ending process. To be able to design a product using the current technology that will be beneficial to the lives of others is a huge contribution to the community. This paper presents the design and implementation of a low cost based on using keypad to turning on a lamp. The design is based on a standalone Arduino board and input of keypad connected to the digital input of Arduino board and digital output pin (13) connected to the common of relay, because relay working on low voltage it’s that reason triggering AC power with help low voltage (DC5v). The communication between keypad and the Arduino it based on the 4*4 matrix keypad that we will be using. This system is designed to be low cost and scalable allowing variety of devices to be controlled with minimum changes to its core. Arduino based calculate, password-based lock system, home security, home automation system is being used to allow authorized users from accessing the appliances at home or anywhere she/he want to use keypad system.
 
# PROBLEM STATEMENT


There's a universal development in this generation's environment of lighting systems and energy efficient technology.as the new technologies evolve one area in need of new technological advancement is the lighting department for schools, hospitals, commercial stores account for approximately 20% of our countries total energy consumption and our former lighting or light controlling systems have been used for years without the innovation of new useful
The prospect of this keypad-controlled lamp project is to improve the lighting technology such improvements include: energy efficiency, light depreciation, material lifetime, light output and distribution, color quality, color shift and dimmability to provide security system or another system was no longer in smart technology to be unsecure. 
Smart technology it is better to access, keypad based on Arduino board can use as Arduino based calculator, password-based door lock system, home security system or home automation system. to use electronic relay in power system it is how to maintain or to minimize power losses in the power system.
based on home automation, this project to turning on a lamp using keypad, it helps someone want to control ON/OFF a lamp from different position. this project based on smart technology whereas using Arduino to control AC lamp. 
lamentation of a low cost based on using keypad to turning on a lamp. The design is based on a standalone Arduino board and input of keypad connected to the digital input of Arduino board and digital output pin (11) connected to the common of relay, because relay working on low voltage it’s that reason triggering AC power with help low voltage (DC5v). The communication between keypad and the Arduino it based on the 4*4 matrix keypad that we will be using. This system is designed to be low cost and scalable allowing variety of devices to be controlled with minimum changes to its core. Arduino based calculate, password-based lock system, home security, home automation system is being used to allow authorized users from accessing the appliances at home or anywhere she/he want to use keypad system.

# Block Diagram
  
    
 

![tonto](https://user-images.githubusercontent.com/104690864/166156618-e680b902-ce78-4e56-be8e-85ce2fd3c7b8.PNG)






# Description:
Project so called "using 4*4matrix keypad to turning on a lamp" we are able to design and implementation that project. Digital input Arduino read keypad as input, keypad has 8 inputs there are 4colum and 4rows connected to digital input of Arduino (2_9), input keypad to Arduino board Row pin connected from (5_2) and column pin connected from (9_6). whereas column and row crossing each other there are creation of button, when someone pressing a button on the keypad working like switch, continuity creation between row and column then, some button she/he pressed it comes high and LCD read one, Arduino receiving a signal therefore, the common terminal of electronic relay connected to the output pin of Arduino, that common terminal of relay triggering an AC source this, a lamp turned ON

             # SOURCE CODE

#include <Keypad.h>

char* password = "456";  // change the password here, just pick any 3 numbers

int position = 0;

const byte ROWS = 4;

const byte COLS = 3;


char keys[ROWS][COLS] = {

{'#','0','*'},

{'9','8','7'},

{'6','5','5'},

{'3','2','1'},

};


byte rowPins[ROWS] = {5, 6,7,8 };//Pin may change according to sutability

byte colPins[COLS] = { 2,3,4};

Keypad keypad = Keypad( makeKeymap(keys), rowPins, colPins, ROWS, COLS );

int relay=11;



void setup()

{


pinMode(relay, OUTPUT);

setLocked(true);

}


void loop()

{

char key = keypad.getKey();

if (key == '*' || key == '#')

{

position = 0;

setLocked(true);

}

if (key == password[position])

{


if (position == 3)

{

setLocked(false);

}

delay(100);

}

void setLocked(int locked)

{

if (locked) 

{


digitalWrite(11,  LOW);

}

else

{



digitalWrite(11,HIGH);

}

}

# SIMULATION IN PROTEUS

 ![image](https://user-images.githubusercontent.com/104690864/166156545-ca97500d-de88-4bc1-9e9f-43de4cdf9143.png)




# CIRCUIT DIAGRAM IN FRITSING
![image](https://user-images.githubusercontent.com/104690864/166156556-ede6ab86-ac0f-4f6e-89a6-416712d324ae.png)


 
