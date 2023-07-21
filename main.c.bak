#include <at89c5131.h>
#include "serial.c"

char board_count[4]= {8,6,4,4};
unsigned char ch=0, ch1=0, ch2=0;
char* names[4]={" UART-", " TIVA-", " AT328-", " STM32-"};
int i=0;
void main(){
	uart_init();
	
	while(1){
		transmit_string("Micro-controllers available:");
		for (i=0; i<4; i++){
			transmit_string(names[i]);
			ch=board_count[i]+48;
			transmit_char(ch);
			
		}
		transmit_string("\r\n");
		transmit_string("Press I for Issue and R for Return\r\n");
		ch = receive_char();
		if (ch == 'i' | ch == 'I'){
			transmit_string("Enter micro-controller to be borrowed:\r\n");
			
			ch1 = receive_char();
			transmit_string("Enter Quantity:\r\n");
			ch2 = receive_char()-48;
			if (ch1=='1'){
				if (board_count[0]>ch2){
					board_count[0]-=ch2;
					transmit_string("Requested micro-controller allocated!\r\n");
				}
				else{
					transmit_string("Requested micro-controller not available...\r\n");
				}
			}
			else if (ch1=='2'){
				if (board_count[1]>ch2){
					board_count[1]-=ch2;
					transmit_string("Requested micro-controller allocated!\r\n");
				}
				else{
					transmit_string("Requested micro-controller not available...\r\n");
				}
			}
			else if (ch1=='3'){
				if (board_count[2]>ch2){
					board_count[2]-=ch2;
					transmit_string("Requested micro-controller allocated!\r\n");
				}
				else{
					transmit_string("Requested micro-controller not available...\r\n");
				}
			}
			else if (ch1=='4'){
				if (board_count[3]>ch2){
					board_count[3]-=ch2;
					transmit_string("Requested micro-controller allocated!\r\n");
				}
				else{
					transmit_string("Requested micro-controller not available...\r\n");
				}
			}
			
			
			
		}
		else if(ch == 'r' | ch == 'R'){
				transmit_string("Enter micro-controller to be returned:\r\n");
				ch1 = receive_char();
				if (ch1=='1'){
					if (board_count[0]>=8){
						
						transmit_string("You can’t return what you don’t have...\r\n");
					}
					else{
						
						transmit_string("Enter Quantity:\r\n");
						ch2=receive_char()-48;
						if (ch2+board_count[0] <=8){
							board_count[0]+=ch2;
							transmit_string("Returned micro-controller received!\r\n");
						}
						else{
							transmit_string("Returned micro-controller out of bounds...\r\n");
						}
					}
				}
				else if (ch1=='2'){
					if (board_count[1]>=6){
						
						transmit_string("You can’t return what you don’t have...\r\n");
					}
					else{
						
						transmit_string("Enter Quantity:\r\n");
						ch2=receive_char()-48;
						if (ch2+board_count[1] <=6){
							board_count[1]+=ch2;
							transmit_string("Returned micro-controller received!\r\n");
						}
						else{
							transmit_string("Returned micro-controller out of bounds...\r\n");
						}
					}
				}
				else if (ch1=='3'){
					if (board_count[2]>=4){
						
						transmit_string("You can’t return what you don’t have...\r\n");
					}
					else{
						
						transmit_string("Enter Quantity:\r\n");
						ch2=receive_char()-48;
						if (ch2+board_count[2] <=4){
							board_count[2]+=ch2;
							transmit_string("Returned micro-controller received!\r\n");
						}
						else{
							transmit_string("Returned micro-controller out of bounds...\r\n");
						}
					}
				}
				else if (ch1=='4'){
					if (board_count[3]>=4){
						
						transmit_string("You can’t return what you don’t have...\r\n");
					}
					else{
						
						transmit_string("Enter Quantity:\r\n");
						ch2=receive_char()-48;
						if (ch2+board_count[3] <=4){
							board_count[3]+=ch2;
							transmit_string("Returned micro-controller received!\r\n");
						}
						else{
							transmit_string("Returned micro-controller out of bounds...\r\n");
						}
					}
				}
				
			}
		
		
		
		
		
	}
}