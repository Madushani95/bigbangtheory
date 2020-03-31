# bigbangtheory

# Sheldon1
    
    Disassemble the program
    Check for the functions
     
    # Phase_1
        
        disassemble pahse_1
        0x08048b2c <+12>:    push   0x80497c0 can be contain the password.
        print 0x80497c0
        
    # phase_2
    
        disassemble pahse_2
        
   0x08048b5b <+19>:    call   0x8048fd8 <read_six_numbers> #check whether input has 6 numbers
   
   0x08048b63 <+27>:    cmp    DWORD PTR [ebp-0x18],0x1 #check whether first input number is 1. So that first input should be 1

   
   0x08048b6e <+38>:    mov    ebx,0x1 #assign 1 to ebx
   0x08048b73 <+43>:    lea    esi,[ebp-0x18] #assign ebp-0x18 address to esi
   0x08048b76 <+46>:    lea    eax,[ebx+0x1] #eax = ebx + 1 = 2
   0x08048b79 <+49>:    imul   eax,DWORD PTR [esi+ebx*4-0x4] #eax = eax * (esi + ebx * 4 - 4) = 2 * (esi + 1 * 4 - 4) = 2 >>because, esi[0] = 1
   0x08048b7e <+54>:    cmp    DWORD PTR [esi+ebx*4],eax #compare eax with value in the address [esi+ebx*4] 
   0x08048b81 <+57>:    je     0x8048b88 <phase_2+64> #jump to <+64> if above comparison is true/equal >>For this [esi+ebx*4] == 2, esi[1] = 2
   0x08048b83 <+59>:    call   0x80494fc <explode_bomb>
   0x08048b88 <+64>:    inc    ebx #ebx = ebx + 1 = 2
   0x08048b89 <+65>:    cmp    ebx,0x5 #compare ebx with 5
   0x08048b8c <+68>:    jle    0x8048b76 <phase_2+46> #jump to <+46> if ebx <= 5
   
   This loop will repeat while comparing the input digits. 
   eax*[esi+ebx*4-0x4] equation can use to find the 6 digits. 
   
   eax - 2 | 2 | 3 | 6 | 4 | 24 | 5 | 120 | 6 | 720
   ebx - 1     | 2     | 3      | 4       | 5
   esi - 1 | 2 |     6 |     24 |     120 |     720  << password
   

        
        
# Sheldon2

# learnord_win
        
     
     


