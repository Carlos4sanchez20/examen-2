MAIN_PROG CODE                      
 
i equ 0x20
j equ 0x21
k equ 0x22
m equ 0x23
var1 equ 0x24
var2 equ 0x25
var3 equ 0x26
var4 equ 0x27
var5 equ 0x28
var6 equ 0x29
var7 equ 0x30
var8 equ 0x31
con1 equ 0x32
con2 equ 0x33
con3 equ 0x34
con4 equ 0x35
con5 equ 0x36
con6 equ 0x37
con7 equ 0x38
con8 equ 0x39 
ax equ 0x40
bd equ d'0'


START

    BANKSEL PORTA ;
    CLRF PORTA ;Init PORTA
    BANKSEL ANSEL ;
    CLRF ANSEL ;digital I/O
    CLRF ANSELH
    BANKSEL TRISA ;
    CLRF TRISA
    CLRF TRISB
    CLRF TRISC
    CLRF TRISD
    CLRF TRISE
    BCF STATUS,RP1
    BCF STATUS,RP0
    CLRF PORTA
    CLRF PORTB
    CLRF PORTC
    CLRF PORTD
    CLRF PORTE
    
    BCF STATUS, RP1 
    BSF STATUS, RP0 
    MOVLW b'00000000' 
    MOVWF TRISC 
    MOVLW b'00001111' 
    MOVWF TRISD
    BCF STATUS, RP0 
    
    
INITLCD
    BCF PORTA,0		
    MOVLW 0x01
    MOVWF PORTB
    
    BSF PORTA,1		
    CALL time
    BCF PORTA,1
    CALL time
    
    MOVLW 0x0C		
    MOVWF PORTB
    
    BSF PORTA,1		
    CALL time
    BCF PORTA,1
    CALL time
         
    MOVLW 0x3C		
    MOVWF PORTB
    
    BSF PORTA,1		
    CALL time
    BCF PORTA,1
    CALL time
    
    
INICIO
    BCF PORTA,0		
    CALL time
    
    MOVLW 0x01		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time
    
    
    BCF PORTA,0		
    CALL time
    
    MOVLW 0x82		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time
    
    
    MOVLW 'C'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'o'
    MOVWF PORTB
    CALL exec
   
    MOVLW 'n'
    MOVWF PORTB
    CALL exec

    MOVLW 't'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'r'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'a'
    MOVWF PORTB
    CALL exec
    
    MOVLW 's'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'e'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'n'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'a'
    MOVWF PORTB
    CALL exec
    
    MOVLW ':'
    MOVWF PORTB
    CALL exec
    
      BCF PORTA,0		
    CALL time
    
    MOVLW 0xC0		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time
    
    CALL nums
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF var1
    BCF bd,0
    
    
   CALL nums
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF var2
    BCF bd,0
    
    
    CALL nums
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF var3
    BCF bd,0
    
    
    CALL nums
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF var4
    BCF bd,0
    
    
    CALL nums
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF var5
    BCF bd,0
    
    CALL nums
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF var6
    BCF bd,0
    
    CALL nums
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF var7
    BCF bd,0
    
    CALL nums
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF var8
    BCF bd,0
    
 cont2: 
    BCF bd,0
    BCF PORTA,0		
    CALL time
    
    MOVLW 0x90		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time
    MOVLW ' '
    MOVWF PORTB
    CALL exec
    
    MOVLW ' '
    MOVWF PORTB
    CALL exec
    
    MOVLW ' '
    MOVWF PORTB
    CALL exec
    
    MOVLW ' '
    MOVWF PORTB
    CALL exec
    
    MOVLW ' '
    MOVWF PORTB
    CALL exec
    
    MOVLW ' '
    MOVWF PORTB
    CALL exec
    
     MOVLW ' '
    MOVWF PORTB
    CALL exec
    
     MOVLW ' '
    MOVWF PORTB
    CALL exec
     MOVLW ' '
    MOVWF PORTB
    CALL exec
     MOVLW ' '
    MOVWF PORTB
    CALL exec
     MOVLW ' '
    MOVWF PORTB
    CALL exec
    MOVLW ' '
    MOVWF PORTB
    CALL exec
    MOVLW ' '
    MOVWF PORTB
    CALL exec
    MOVLW ' '
    MOVWF PORTB
    CALL exec
    
   BCF PORTA,0		
    CALL time
    
    MOVLW 0x90		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time
    
    MOVLW 'R'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'e'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'p'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'i'
    MOVWF PORTB
    CALL exec
    
    MOVLW 't'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'e'
    MOVWF PORTB
    CALL exec
    
    MOVLW ' '
    MOVWF PORTB
    CALL exec
    
    MOVLW 'c'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'o'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'n'
    MOVWF PORTB
    CALL exec
    
    MOVLW 't'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'r'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'a'
    MOVWF PORTB
    CALL exec
    
    MOVLW ':'
    MOVWF PORTB
    CALL exec
    
     BCF PORTA,0		
    CALL time
    
    MOVLW 0xD0		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time
    
    CALL nums
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF con1
    BCF bd,0
   
    CALL nums 
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF con2
    BCF bd,0
    
    CALL nums 
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF con3
    BCF bd,0
     
    CALL nums 
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF con4
    BCF bd,0
    
    CALL nums
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF con5
    BCF bd,0
    
    
    CALL nums 
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF con6
    BCF bd,0
    
    
    CALL nums 
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF con7
    BCF bd,0
    
    
    CALL nums 
    BTFSS bd,0
    GOTO $-2
    MOVFW ax
    MOVWF con8
    BCF bd,0 
   
    
    
    MOVFW var1
    XORWF con1,W
    BTFSS STATUS,Z
    CALL eq
    
    MOVFW var2
    XORWF con2,W
    BTFSS STATUS,Z
    CALL eq
    
    MOVFW var3
    XORWF con3,W
    BTFSS STATUS,Z
    CALL eq
    
    MOVFW var4
    XORWF con4,W
    BTFSS STATUS,Z
    CALL eq
    
    MOVFW var5
    XORWF con5,W
    BTFSS STATUS,Z
    CALL eq
    
    MOVFW var6
    XORWF con6,W
    BTFSS STATUS,Z
    CALL eq
    
    MOVFW var7
    XORWF con7,W
    BTFSS STATUS,Z
    CALL eq
    
    MOVFW var8
    XORWF con8,W
    BTFSS STATUS,Z
    CALL eq
    
    CALL ok
    
   
    
       
    GOTO INICIO
    
    
eq:
    BCF PORTA,0		
    CALL time
    
    MOVLW 0x01		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time 
    
    BCF PORTA,0		
    CALL time
    
    MOVLW 0x0C		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time
    
    
    BCF PORTA,0		
    CALL time
    
    MOVLW 0xC5		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time
    
    MOVLW 'N'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'o'
    MOVWF PORTB
    CALL exec
    
    MOVLW ' '
    MOVWF PORTB
    CALL exec
    
    MOVLW 'l'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'o'
    MOVWF PORTB
    CALL exec
    
    BCF PORTA,0		
    CALL time
    
    MOVLW 0x96		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time
    
    MOVLW 'c'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'r'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'e'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'o'
    MOVWF PORTB
    CALL exec
   
    
    BSF PORTC,0
    CALL time
    BTFSS PORTD,3
    GOTO $-3
   
    GOTO INICIO
    
ok:
    BCF PORTA,0		
    CALL time
    
    MOVLW 0x01		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time 
    
    BCF PORTA,0		
    CALL time
    
    MOVLW 0xC6		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time
    
    MOVLW '!'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'H'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'a'
    MOVWF PORTB
    CALL exec
    
    MOVLW 's'
    MOVWF PORTB
    CALL exec
   
    
    BCF PORTA,0		
    CALL time
    
    MOVLW 0x95		
    MOVWF PORTB
    CALL exec
    
    BSF PORTA,0		
    CALL time
    
    MOVLW 'p'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'a'
    MOVWF PORTB
    CALL exec
    
    MOVLW 's'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'a'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'd'
    MOVWF PORTB
    CALL exec
    
    MOVLW 'o'
    MOVWF PORTB
    CALL exec
    
    MOVLW '¡'
    MOVWF PORTB
    CALL exec
   
    
    BSF PORTC,0
    CALL time
    BTFSS PORTD,3
    GOTO $-3
    
    GOTO INICIO
     
nums:
    BSF PORTC,0
    CALL time
    BTFSC PORTD,0
    CALL n1
    BTFSC PORTD,1
    CALL n4
    BTFSC PORTD,2
    CALL n7
    BCF PORTC,0
    BSF PORTC,1
    CALL time
    BTFSC PORTD,0
    CALL n2
    BTFSC PORTD,1
    CALL n5
    BTFSC PORTD,2
    CALL n8
    BTFSC PORTD,3
    CALL n0
    BCF PORTC,1
    BSF PORTC,2
    CALL time
    BTFSC PORTD,0
    CALL n3
    BTFSC PORTD,1
    CALL n6
    BTFSC PORTD,2
    CALL n9
    BTFSC PORTD,3
    CALL borrar
    BCF PORTC,2
   
    
 
    RETURN
    

  
    
n0:
  
    MOVLW d'0'
    MOVWF ax
    MOVLW '0'
    MOVWF PORTB
    CALL exec 
    BSF bd,0
    BTFSC PORTD,3
    GOTO $-1
    RETURN
    
n1:
    MOVLW d'1'
    MOVWF ax
    MOVLW '1'
    MOVWF PORTB
    CALL exec
    BSF bd,0
    BTFSC PORTD,0
    GOTO $-1
    RETURN

n2:
    MOVLW d'2'
    MOVWF ax
    MOVLW '2'
    MOVWF PORTB
    CALL exec
    BSF bd,0
    BTFSC PORTD,0
    GOTO $-1
    RETURN

n3: 
    MOVLW d'3'
    MOVWF ax
    MOVLW '3'
    MOVWF PORTB
    CALL exec
    BSF bd,0
    BTFSC PORTD,0
    GOTO $-1
    RETURN
    
n4:
    
    MOVLW d'4'
    MOVWF ax
    MOVLW '4'
    MOVWF PORTB
    CALL exec
    BSF bd,0
    BTFSC PORTD,1
    GOTO $-1
    RETURN
  
n5:
    MOVLW d'5'
    MOVWF ax 
    MOVLW '5'
    MOVWF PORTB
    CALL exec
    BSF bd,0
    
    BTFSC PORTD,1
    GOTO $-1
    RETURN

n6:
    MOVLW d'6'
    MOVWF ax
    MOVLW '6'
    MOVWF PORTB
    CALL exec
    BSF bd,0
    BTFSC PORTD,1
    GOTO $-1
    RETURN
 
n7: 
    MOVLW d'7'
    MOVWF ax 
    MOVLW '7'
    MOVWF PORTB
    CALL exec
    BSF bd,0
    BTFSC PORTD,2
    GOTO $-1
    
    RETURN

n8:  
    MOVLW d'8'
    MOVWF ax
    MOVLW '8'
    MOVWF PORTB
    CALL exec
    BSF bd,0
    BTFSC PORTD,2
    GOTO $-1
    RETURN
    
n9:
    MOVLW d'9'
    MOVWF ax
    MOVLW '9'
    MOVWF PORTB
    CALL exec
    BSF bd,0
    BTFSC PORTD,2
    GOTO $-1
    RETURN
    

exec

    BSF PORTA,1		;exec
    CALL time
    BCF PORTA,1
    CALL time
    RETURN

    
    

    
time
    CLRF i
    MOVLW d'10'
    MOVWF j
ciclo    
    MOVLW d'80'
    MOVWF i
    DECFSZ i
    GOTO $-1
    DECFSZ j
    GOTO ciclo
    RETURN
    

tiemp
    
    movlw d'127' 
    movwf m
mloop1
    decfsz m,f
    goto mloop1
    movlw d'25' 
    movwf i
iloop1
    nop 
    movlw d'62' 
    movwf j
jloop1
    nop 
    movlw d'74' 
    movwf k
kloop1
    decfsz k,f
    goto kloop1
    decfsz j,f
    goto jloop1
    decfsz i,f
    goto iloop1
    return 
			

borrar:
    
    CALL tiemp
    GOTO cont2
   
    END
