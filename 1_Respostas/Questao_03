1. Dada uma variável `a` do tipo `char` (um byte), escreva os trechos de código em C para:
	(a) Somente setar o bit menos significativo de `a`.
	a = a | 0x01; 
	(b) Somente setar dois bits de `a`: o menos significativo e o segundo menos significativo.
	a = a | 0x03;
	(c) Somente zerar o terceiro bit menos significativo de `a`.
	a = a | 0x04;
	(d) Somente zerar o terceiro e o quarto bits menos significativo de `a`.
	a = a & 0x0C;
	(e) Somente inverter o bit mais significativo de `a`.
	a = a ^ 0x01;
	(f) Inverter o nibble mais significativo de `a`, e setar o nibble menos significativo de `a`. 
	a = a ^ 0xF0;
	a = a | 0x0F;
2. Considerando a placa Launchpad do MSP430, escreva o código em C para piscar os dois LEDs ininterruptamente.

#include <msp430g2553.h>
#define LED1 BIT0
#define LED2 BIT6
#define LEDS (LED1|LED2)

void atraso(volatile unsigned int i)
{
	while((i--)>0);
}

int main(void)
{
	WDTCTL = WDTPW | WDTHOLD;
	P1OUT |= LEDS;
	P1DIR |= LEDS;
	while(1)
	{
		atraso(0xffff);
		P1OUT ^= LEDS;
	}
	return 0;
}

3. Considerando a placa Launchpad do MSP430, escreva o código em C para piscar duas vezes os dois LEDs sempre que o usuário pressionar o botão.

#include <msp430g2553.h>
#define LED1 BIT0
#define LED2 BIT6
#define LEDS (LED1|LED2)
#define BTN  BIT3

void atraso(volatile unsigned int i)
{
	while((i--)>0);
}

int main(void)
{
	j = 2;
	
	WDTCTL = WDTPW | WDTHOLD;
	
	P1DIR |= LEDS;
	P1DIR &= ~BTN;
	
	P1REN |= BTN;
	P1OUT |= BTN;
	
	while(1)
	{
		if(((P1IN&BTN)==0) && (j > 0)){
			atraso(0xffff);
			P1OUT ^= LEDS;
			j--;
		}
		else{
			P1OUT &= ~LEDS;
		}
	}
	return 0;
}

4. Considerando a placa Launchpad do MSP430, faça uma função em C que pisca os dois LEDs uma vez.

#include <msp430g2553.h>
#define LED1 BIT0
#define LED2 BIT6
#define LEDS (LED1|LED2)

void atraso(volatile unsigned int i)
{
	while((i--)>0);
}

int main(void)
{
	WDTCTL = WDTPW | WDTHOLD;

	P1DIR |= LEDS;

	P1OUT |= LEDS;
	atraso(0xffff);
	P1OUT ^= LEDS;

	while(1);
	
	return 0;
}

5. Reescreva o código da questão 2 usando a função da questão 4.

6. Reescreva o código da questão 3 usando a função da questão 4.
