
### Overall implementation of Project.
###
### Traffic Flow Controller - Sequential Traffic Light Controller.
### 
### 
***Overview Of a Project***
###  
A sequential traffic light controller is a system designed to manage the flow of traffic at an intersection by cycling through a predefined sequence of traffic light states. The controller ensures that vehicles from different directions can move safely and efficiently by controlling the duration and order of green, yellow, and red lights.

### 
###
***Components Required***
* VSD Squadronmini Board
* LEDs
* Jumper Wires
* Breadboard
* Resistors
* Power Supply
  ###
  ###

  ***Pinout Table***
![image](https://github.com/user-attachments/assets/a4bf7c07-cb29-4ca2-8098-f57f84b7e5e3)

  
***Pinout Diagram***


![image](https://github.com/user-attachments/assets/11c25943-6773-400e-aee1-ba3b1c445727)



***Program Code***
```sh
#include <ch32v00x.h>
#include <stdio.h> 

// Define GPIO pins for ONE direction
#define GREEN_LIGHT_PIN GPIO_Pin_2   // Green light 
#define YELLOW_LIGHT_PIN GPIO_Pin_3  // Yellow light
#define RED_LIGHT_PIN GPIO_Pin_4     // Red light 

// Function prototypes
void GPIO_Config(void);
void TrafficLightControl(void);

// GPIO configuration function
void GPIO_Config(void) {
    GPIO_InitTypeDef GPIO_InitStructure = {0};

    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE); // Enable clock for Port D

    // Configure GPIO pins 
	GPIO_InitStructure.GPIO_Pin = GREEN_LIGHT_PIN | YELLOW_LIGHT_PIN | RED_LIGHT_PIN;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // Initial state: All lights off
    GPIO_WriteBit(GPIOD, GREEN_LIGHT_PIN | YELLOW_LIGHT_PIN | RED_LIGHT_PIN, RESET);
}

// Traffic light control function 
void TrafficLightControl(void) {
    // Green light on
    GPIO_WriteBit(GPIOD, GREEN_LIGHT_PIN, SET);
    GPIO_WriteBit(GPIOD, YELLOW_LIGHT_PIN | RED_LIGHT_PIN, RESET);
    Delay_Ms(5000); // Keep green light on for 5 seconds

    // Yellow light on
    GPIO_WriteBit(GPIOD, GREEN_LIGHT_PIN | RED_LIGHT_PIN, RESET);
    GPIO_WriteBit(GPIOD, YELLOW_LIGHT_PIN, SET);
    Delay_Ms(5000); // Keep yellow light on for 5 seconds

    // Red light on
    GPIO_WriteBit(GPIOD, GREEN_LIGHT_PIN | YELLOW_LIGHT_PIN, RESET);
    GPIO_WriteBit(GPIOD, RED_LIGHT_PIN, SET);
    Delay_Ms(5000); // Keep red light on for 5 seconds
}

int main(void) {
    
    Delay_Init(); 
    GPIO_Config();

    while(1) {
        TrafficLightControl(); 
    }
}
```
###
####
***Demonstration of a Project***







https://github.com/user-attachments/assets/eb65cd6c-1277-4d4c-94b0-01a19a09c7b1














