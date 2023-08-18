# INTEFACING-A-DIGITAL-INPUT-TO-ARM-DEVELOPMENT-BOARD  
### Aim:  
To Interface a Digital Input  (userpush button ) to ARM   development board and write a  program to obtain  the data and flash the led.
### Components required:   
STM32 CUBE IDE, ARM IOT development board,  STM programmer tool.
### Theory: 
The full form of an ARM is an advanced reduced instruction set computer (RISC) machine, and it is a 32-bit processor architecture expanded by ARM holdings. The applications of an ARM processor include several microcontrollers as well as processors. The architecture of an ARM processor was licensed by many corporations for designing ARM processor-based SoC products and CPUs. This allows the corporations to manufacture their products using ARM architecture. Likewise, all main semiconductor companies will make ARM-based SOCs such as Samsung, Atmel, TI etc.
### Procedure:
1. click on STM 32 CUBE IDE, the following screen will appear <img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189166-ac10578c-c059-40e7-8b80-9f84f64bf088.png">2. click on FILE, click on new stm 32 project <img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189215-2d13ebfb-507f-44fc-b772-02232e97c0e3.png"><img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189230-bf2d90dd-9695-4aaf-b2a6-6d66454e81fc.png">3. select the target to be programmed  as shown below and click on next <img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189280-ed5dcf1d-dd8d-43ae-815d-491085f4863b.png">4.select the program name <img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189316-09832a30-4d1a-4d4f-b8ad-2dc28f137711.png">5. corresponding ioc file will be generated automatically <img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189378-3abbdee2-0df6-470f-a3cd-79c74e3d3ad8.png">6.select the appropriate pins as gipo, in or out, USART or required options and configure <img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189403-f7179f1a-3eae-4637-826b-ab4ec35ba1e1.png"><img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189425-2b2414ce-49b3-4b61-a260-c658cb2e4152.png">7.click on cntrl+S , automaticall C program will be generated <img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189443-8b43451d-0b14-47e4-a20b-cc09c6ad8458.png"><img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189450-85ffa969-2ffb-4788-81e5-72d60fdda0f1.png">8. edit the program and as per required <img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189461-a573e62f-a109-4631-a250-a20925758fe0.png">9. use project and build all <img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189554-3f7101ac-3f41-48fc-abc7-480bd6218dec.png">10. once the project is bulild <img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189577-c61cc1eb-3990-4968-8aa6-aefffc766b70.png">11. click on debug option <img height=30% width=100% src="https://user-images.githubusercontent.com/36288975/226189625-37daa9a3-62e9-42b5-a5ce-2ac63345905b.png">
12. connect the  ARM board to power supply and usb 
13. check for execution of the output using run option 
### STM 32 CUBE PROGRAM :
```
ROHIT JAIN D
212222230120
```
```C
#include "main.h"
#include "stdbool.h"
bool button_status;
void push_button();
int main(void)
{
  HAL_Init();
  SystemClock_Config();
  MX_GPIO_Init();
  while (1)
  {
   push_button();
  }
}
void push_button()
{
	 button_status=HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_13);
	 if(button_status==0)
	 {
    HAL_GPIO_WritePin(GPIOA,GPIO_PIN_5,SET);
		  HAL_Delay(50);
		  HAL_GPIO_WritePin(GPIOA,GPIO_PIN_5,RESET);
		  HAL_Delay(50);
	}
	else
	{
		HAL_GPIO_WritePin(GPIOA,GPIO_PIN_5,RESET);
	}
}
```
### Output  :
<img height=40% width=45% src="https://github.com/ROHITJAIND/INTEFACING-A-DIGITAL-INPUT-TO-ARM-DEVELOPMENT-BOARD/assets/118707073/4c074d82-c115-44a8-8997-42a85c064d66"><img height=40% width=45% src="https://github.com/ROHITJAIND/INTEFACING-A-DIGITAL-INPUT-TO-ARM-DEVELOPMENT-BOARD/assets/118707073/d78d0092-1365-409c-8825-ee2cee7539fc">
## Result :
Interfacing a digital Input (Pushbutton ) with ARM microcontroller based IOT development is executed and the results are verified.
