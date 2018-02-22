
;Name: Mohammad Mahadi Hossain
;ID : 1421281042
;Section: 06
;Assignment: 01





include 'emu8086.inc'
org 100h
.model large
.stack 100h    


;enter string like>-> hello >-> press ENTER >-> word count will be shown in ASCII

 PRINTN 'This Program will count the Number of Characters in Hexadecimal Number System: '
 PRINTN 'Enter a String:';This line will print a message on the console

    mov bl,0            ;initializing bl == 0 
    
    
    lp:
    mov ah,1            ;this line of code is for Taking Input From the User until ENTER is Pressed
    int 21h
    inc bl
    
    cmp al, 0Dh         ; I'm checking with Hex value of ENTER which is 0Dh
    je  Terminate:      ; If input == ENTER then TERMINATE LOOP
    jmp lp              ; Here I'm using a LOOP for continous stream of input
    
    Terminate:
    
    
                        
                       
    sub bl,1            ;I'm subtracting 1 from bl to Discard the value of Enter ->cret -> 0D  
    PRINTN "Number of Characters: "
    mov ah,2
    mov dl,bl
    int 21h             ; Calling Interrupt for Printing in the console

    
 ret