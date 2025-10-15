
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```ORG 00H
MOV TMOD, #20H	
MOV TH1, #0FDH 
MOV SCON, 40H
SETB TR1
MOV SBUF, #'B'
WAIT:JNB TI,WAIT 
CLR TI 
END


```
### (ii) Serial Port to Transfer a Message

```
ORG 00H
MOV TMOD,#20H
MOV TH1,#0FCH
MOV SCON,#40H
SETB TR1
MOV B,30H
MOV DPTR,#4500H
AGAIN:MOVX A,@DPTR
MOV SBUF,A
WAIT:JNB TI,WAIT
CLR TI
INC DPTR
DJNZ  B,AGAIN
END


```

### OUTPUT:
<img width="684" height="855" alt="Screenshot 2025-10-15 131624" src="https://github.com/user-attachments/assets/56dd406e-db78-49d8-8d98-699616100fc7" />
<img width="1076" height="1198" alt="Screenshot 2025-10-15 132325" src="https://github.com/user-attachments/assets/893fa6d8-de13-46b8-8c8b-6e24002c618a" />

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
