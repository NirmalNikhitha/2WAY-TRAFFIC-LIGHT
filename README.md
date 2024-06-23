# 2WAY-TRAFFIC-LIGHT
2 WAY TRAFFIC LIGHT USING PIC16F877A
# CONFIGURATION BITS
#pragma config FOSC = HS        
#pragma config WDTE = OFF      
#pragma config PWRTE = OFF      
#pragma config BOREN = OFF      
#pragma config LVP = ON         
#pragma config CPD = OFF        
#pragma config WRT = OFF        
#pragma config CP = OFF         
#include <xc.h>
# Define crystal frequency (20 MHz)
#define _XTAL_FREQ 20000000
#define RED1    RB0
#define YELLOW1 RB1
#define GREEN1  RB2
#define RED2    RB3
#define YELLOW2 RB4
#define GREEN2  RB5
int main() {
// Set PORTB as output
    TRISB = 0x00; 
// Initialize PORTB to 0
    PORTB = 0x00; 
    while(1) {
        RED1 = 1;
        GREEN2 = 1;
// 5 seconds delay    
        __delay_ms(5000); 
        RED1 = 0;
        GREEN2 = 0;
        YELLOW1 = 1;
        YELLOW2 = 1;
// 2 seconds delay
        __delay_ms(2000); 
        YELLOW1 = 0;
        YELLOW2 = 0;
        GREEN1 = 1;
        RED2 = 1;
// 5 seconds delay
        __delay_ms(5000); 
        GREEN1 = 0;
        RED2 = 0;
        YELLOW1 = 1;
        YELLOW2 = 1;
        __delay_ms(2000);
        YELLOW1 = 0;
        YELLOW2 = 0;
    }
}
