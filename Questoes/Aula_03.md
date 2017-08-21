1. Dada uma variável a do tipo char (um byte), escreva os trechos de código em C para: (a) Somente setar o bit menos significativo de a. (b) Somente setar dois bits de a: o menos significativo e o segundo menos significativo. (c) Somente zerar o terceiro bit menos significativo de a. (d) Somente zerar o terceiro e o quarto bits menos significativo de a. (e) Somente inverter o bit mais significativo de a. (f) Inverter o nibble mais significativo de a, e setar o nibble menos significativo de a.

	`(a)` A |= BIT0; 

	`(b)`A|= BIT0+BIT1;

	`(c)` A &= (~BIT2); 

	`(d)` A &= ~(BIT2+BIT3); 

	`(e)` A ^= (BIT3+BIT5+BIT8); 

	`(f)` A |= (BIT4+BIT2+BIT0); A ^= (BIT9+BIT6);

2. Considerando a placa Launchpad do MSP430, escreva o código em C para piscar os dois LEDs ininterruptamente.
	
		#include <msp430g2553.h>
	
		void main (void) {
	
		WDTCTL = WDTPW + WDTHOLD;
	
		for (;;){
		P1DIR = 0x11;
	
		P1OUT = 0x11;
			}

		}

3. Considerando a placa Launchpad do MSP430, escreva o código em C para piscar duas vezes os dois LEDs sempre que o usuário pressionar o botão.
	
		#include <msp430g2553.h>
	
		#define BUT BIT2
	
		#define LED1 BIT0
	
		#define LED2 BIT1
	
		void main (void) {
	
		WDTCTL = WDTPW + WDTHOLD;
	
		P1OUT = 0;
	
		P1DIR = (LED1+LED2);
	
		for (;;){
	
		if (P1IN & BUT ==0){
		
			P1OUT |= (LED1+LED2);
			
			P1OUT = 0;
			
			P1OUT |= (LED1+LED2);
			
			P1OUT = 0;
			
			while (P1IN & BTN == 0 ) {}
		
			}
			
		else {
		
			P1OUT &= ~(LED1+LED2);}
			
			}
		
		}


4. Considerando a placa Launchpad do MSP430, faça uma função em C que pisca os dois LEDs uma vez.

		anular blink()
		{
		
		P1OUT |= (LED1+LED2);
			
		P1OUT = 0;
			
		P1OUT |= (LED1+LED2);
			
		P1OUT = 0;
		
		}	

5. Reescreva o código da questão 2 usando a função da questão 4.
	
		#include <msp430g2553.h>
	
		void main (void) {
	
		WDTCTL = WDTPW + WDTHOLD;
	
		for (;;){
		blink();
			}

		}

6. Reescreva o código da questão 3 usando a função da questão 4.

	
		#include <msp430g2553.h>
	
		#define BUT BIT2
	
		#define LED1 BIT0
	
		#define LED2 BIT1
	
		void main (void) {
	
		WDTCTL = WDTPW + WDTHOLD;
	
		P1OUT = 0;
	
		P1DIR = (LED1+LED2);
	
		for (;;){
	
		if (P1IN & BUT ==0){
			blink();
			
			while (P1IN & BTN == 0 ) {}
		
			}
			
		else {
		
			P1OUT &= ~(LED1+LED2);}
			
			}
		
		}
