Para todas as questões, considere que as variáveis `f`, `g`, `h`, `i` e `j` são do tipo inteiro (16 bits na arquitetura do MSP430), e que o vetor `A[]` é do tipo inteiro. Estas variáveis estão armazenadas nos seguintes registradores:

- f: R4
- g: R5
- h: R6
- i: R7
- j: R8
- A: R9

Utilize os registradores R11, R12, R13, R14 e R15 para armazenar valores temporários.

1. Traduza as seguintes linhas em C para a linguagem assembly do MSP430. Utilize somente as seguintes instruções: mov.w, add.w e sub.w.

(a) `f = 0;
mov.w #0,R4

(b) `g++;`
mov.w #1, R11
add.w R11, R5

(c) `h--;
mov.w #1, R11
sub.w R11, R6

(d) `i += 2;`
mov.w #2, R11
add.w R11, R7

(e) `j -= 2;
mov.w #2, R11
sub.w R11, R8`

2. Traduza as seguintes linhas em C para a linguagem assembly do MSP430. Utilize somente as seguintes instruções: mov.w, add.w, sub.w, clr.w, dec.w, decd.w, inc.w e incd.w.

(a) `f = 0;`

(b) `g++;`

(c) `h--;`

(d) `i += 2;`

(e) `j -= 2;`

3. Traduza as seguintes linhas em C para a linguagem assembly do MSP430. Utilize somente as seguintes instruções: mov.w, add.w, sub.w, clr.w, dec.w, decd.w, inc.w e incd.w.

(a) `f *= 2;
mov.w R4, R11
add.w R11, R4`

(b) `g *= 3;
mov.w R5, R11
add.w R11, R5
add.w R11, R5`

(c) `h *= 4;`
mov.w R6, R11
add.w R11, R6
add.w R11, R6`
add.2 R11, R6

(d) `A[2] = A[1] + A[0];`
mov.w R9, R15
add.w 2(R9), R15
mov.w R15, 4(R9)

(e) `A[3] = 2*f - 4*h;`
mov.w R4, R15   ;t = f
add.w R15, R4   ;f = f + t (2f)

mov.w R6, R15   ;t = h
add.w R15, R6   ;h = h + t (2h)
mov.w R6, R15   ;t = h
add.w R15, R6   ;h = h + t (4h)

sub.w R6, R4    ;f = 2f - 4h

mov.w R4, 6(R9) ;A[3] = f

(f) `A[3] = 2*(f - 2*h);`
mov.w R6, R15   ;t = h
add.w R15, R6   ;h = h + t (2h)
sub.w R6, R4    ;f = f - h
mov.w R4, R15   ;t = f
add.w R15, R4   ;f = f+t
