# test
chall link: https://static.cor.team/uploads/646804dc1464496e49422efa4ca83cf62f82f080e3d62a40f2188c97740d042d/m%3C3l.exe
gef➤  x/60i 0x100054
   0x100054:    mov    al,0x3
   0x100056:    xor    ebx,ebx
=> 0x100058:    mov    ecx,0x100111
   0x10005d:    mov    dl,0xff
   0x10005f:    int    0x80 # read(stdin, buffer=0x100111, count = 255)
   0x100061:    xor    esi,esi
   0x100063:    cmp    esi,0x12
   0x100066:    je     0x10007f # for loop that runs 0x12(18) times i think
   0x100068:    mov    al,BYTE PTR [esi+0x100111]
   0x10006e:    rol    al,0xd
   0x100071:    mov    bl,BYTE PTR [esi+0x100210]
   0x100077:    cmp    al,bl
   0x100079:    jne    0x100088
   0x10007b:    inc    si
   0x10007d:    jmp    0x100063
   0x10007f:    mov    WORD PTR ds:0x100234,0x1 # beginning of 18-time for loop
   0x100088:    mov    ebx,0x1
   0x10008d:    mov    eax,0x4
   0x100092:    cmp    WORD PTR ds:0x100234,0x1
   0x10009a:    je     0x1000aa
   0x10009c:    mov    ecx,0x100310
   0x1000a1:    mov    edx,0xd
   0x1000a6:    int    0x80
   0x1000a8:    jmp    0x1000b6
   0x1000aa:    mov    ecx,0x1002ae
   0x1000af:    mov    edx,0x62
   0x1000b4:    int    0x80
   0x1000b6:    mov    eax,0x1
   0x1000bb:    mov    ebx,0x0
   0x1000c0:    int    0x80
   0x1000c2:    mov    ah,0xa
   0x1000c4:    lea    edx,[esi]
   0x1000c6:    adc    DWORD PTR [edx],eax
   0x1000c8:    mov    BYTE PTR [esi],0x11
   0x1000cb:    add    bh,bh
   0x1000cd:    mov    BYTE PTR [esi],0x12
   0x1000d0:    add    bh,bh
   0x1000d2:    int    0x21 # exit/return i think - https://stackoverflow.com/questions/12591673/whats-the-difference-between-using-int-0x20-and-int-0x21-ah-0x4c-to-exit-a-16
   0x1000d4:    xor    esi,esi
   0x1000d6:    cmp    esi,0x12
   0x1000d9:    je     0x1000ec
   0x1000db:    mov    al,BYTE PTR [ebx+edx*1-0x75f2cbfe]
   0x1000e2:    pushf  
   0x1000e3:    and    al,BYTE PTR [ebx]
   0x1000e5:    cmp    al,bl
   0x1000e7:    jne    0x1000f2
   0x1000e9:    inc    esi
   0x1000ea:    jmp    0x1000d6
   0x1000ec:    mov    DWORD PTR [esi],0x10334
   0x1000f2:    xor    ebx,ebx
   0x1000f4:    mov    ah,0x9
   0x1000f6:    cmp    DWORD PTR [esi],0x34
   0x1000f9:    add    eax,DWORD PTR [ecx]
   0x1000fb:    je     0x100107
   0x1000fd:    lea    edx,[esi]
   0x1000ff:    lahf   
   0x100100:    add    ecx,ebp
   0x100102:    and    DWORD PTR [esp+ecx*2+0x168d21cd],esi
   0x100109:    ss add ecx,ebp
   0x10010c:    and    DWORD PTR [esp+ecx*2+0xff21cd],esi
