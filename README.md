# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
ADD AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table


| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
| 1200:12                 |              1204:24
| 1201:34                 |              1205:68
| 1202:12                 |
| 1203:34                 |

#### Manual Calculations
![add](https://github.com/user-attachments/assets/758072f7-9ce9-46a8-bda4-68902797d981)
---

## OUTPUT IMAGE FROM MASM SOFTWARE
<img width="621" height="403" alt="add" src="https://github.com/user-attachments/assets/92b7b1a4-cf1d-453e-ac13-45751b3051ec" />


<img width="790" height="256" alt="Screenshot 2025-09-01 212154" src="https://github.com/user-attachments/assets/06f49145-85f3-4126-86b9-23d15620965c"><img width="795" height="232" alt="Screenshot 2025-09-01 211945" src="https://github.com/user-attachments/assets/6599514f-5cb6-429a-bb91-fb4c0d1b346e" />



## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program
```
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
| 1200:12                 |      1204:00
  1201:34                  |     1205:00
| 1202:12
| 1203:34              |                          |
#### Manual Calculations

![subt](https://github.com/user-attachments/assets/47b66f0c-d867-4b75-8c2e-5bd261430c42)

## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="638" height="428" alt="sub" src="https://github.com/user-attachments/assets/6241db34-e1c2-4ac4-8979-bc32415e1dd6" />

<img width="646" height="432" alt="sub1" src="https://github.com/user-attachments/assets/956c1915-9c10-47ea-8c01-0f513cff1781" />

## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
| 1200:12                  |     1204:44
  1201:34                 |      1205:51
| 1202:12                |       1206:97
| 1203:34              |        1207:0A              |

#### Manual Calculations

![mult](https://github.com/user-attachments/assets/9e2116fc-9571-44d0-8d74-fe2c76692335)



## OUTPUT SCREEN FROM MASM SOFTWARE

<img width="646" height="431" alt="mul" src="https://github.com/user-attachments/assets/d2f6ed7d-ccf8-408c-87a8-81bdff43541d" />

<img width="640" height="403" alt="mul1" src="https://github.com/user-attachments/assets/3ba65a57-700f-4dbc-8cbc-95056b4cec70" />

## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
| 1200:12                       
  1201:34                   |   1204:01
| 1202:12                  |    1205:00
| 1203:34                  |   1206:00                   |

#### Manual Calculations

![IMG-20250901-WA0003](https://github.com/user-attachments/assets/73c112cf-1d25-4a72-97b7-5e0c115910bc)

---
## OUTPUT FROM MASM SOFTWARE

<img width="643" height="400" alt="div" src="https://github.com/user-attachments/assets/d3075cee-5a3c-4b85-819b-dd5f11fc9471" />

<img width="640" height="400" alt="div1" src="https://github.com/user-attachments/assets/0a5f8990-c941-44f7-8b63-7ed0e6687682" />


## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.
