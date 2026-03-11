
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
#include<reg51.h>
void main(void)
{
	TMOD=0X20;
	TH1=0XFA;
	SCON=0X50;
	TR1=1;
	SBUF='A';
	while (T1==0);
		T1=0;
	while(1);
}



```
### (ii) Serial Port to Transfer a Message

```
#include <reg51.h>

void main(void)
{
    unsigned char msg[] = "RITHISH";
    unsigned char i;

    TMOD = 0x20;      // Timer1 Mode2
    TH1  = 0xFD;      // 9600 baud rate
    SCON = 0x50;      // Serial mode1
    TR1  = 1;         // Start Timer1
    for(i = 0; msg[i] != '\0'; i++)
    {
        SBUF = msg[i];
        while(TI == 0);
        TI = 0;
    }
    while(1);
}






```

### OUTPUT:
<img width="1082" height="639" alt="image" src="https://github.com/user-attachments/assets/a9b25394-2277-4226-bd6c-9f7ee2e3fee2" />

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
