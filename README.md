
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'A' 
WAIT:JNB TI, WAIT
CLR TI 
END
```
### (ii) Serial Port to Transfer a Message

```
#include<reg51.h>
void main(void)
{
unsigned char msg[]="SUBHASH GAUTHAM";
unsigned char i;
TMOD=0X20;//TIMER 1,MODE 2
TH1=0XFC;
SCON=0X40;
TR1=1;
for (i=0; i<17;i++)
{
SBUF= msg[i];
while(TI==0);
TI=0;
}
while(1);
}
```

### OUTPUT:
<img width="500" height="600" alt="Screenshot 2025-10-15 140700" src="https://github.com/user-attachments/assets/6ac07684-d1f4-471d-87e9-131551183334" />
<img width="500" height="600" alt="Screenshot 2025-10-15 141421" src="https://github.com/user-attachments/assets/019459a6-a156-4d1f-a9f3-0e8a95a30952" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
