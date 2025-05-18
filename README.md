# Ex-3-RECOGNITION-OF-A-VALID-ARITHMETIC-EXPRESSION-THAT-USES-OPERATOR-AND-USING-YACC
# Date:
# AIM
To write a yacc program to recognize a valid arithmetic expression that uses operator +,- ,* and /.
# ALGORITHM
1.	Start the program.
2.	Write a program in the vi editor and save it with .l extension.
3.	In the lex program, write the translation rules for the operators =,+,-,*,/ and for the identifier.
4.	Write a program in the vi editor and save it with .y extension.
5.	Compile the lex program with lex compiler to produce output file as lex.yy.c. eg $ lex filename.l
6.	Compile the yacc program with yacc compiler to produce output file as y.tab.c. eg $ yacc –d arith_id.y
7.	Compile these with the C compiler as gcc lex.yy.c y.tab.c
8.	Enter an arithmetic expression as input and the tokens are identified as output.
# PROGRAM
  ```
%{ 
#include <stdio.h> 
/* This YACC program is for recognizing the Expression */ 
%} 
%token A ID 
%% 
statement: A'='E 
| E { 
printf("\n Valid arithmetic expression"); 
$$=$1; 
} 
; 
  E: E'+'ID 
| E'-'ID 
| E'*'ID 
| E'/'ID 
| ID 
; 
%% 
extern FILE*yyin; 
int main() { 
do { 
yyparse(); 
}while(!feof(yyin)); } 
yyerror(char*s) 
{ fprintf(stderr, "Error: %s\n",s);
}
```


# OUTPUT

![image](https://github.com/user-attachments/assets/7869bf22-b175-4800-a99a-fd6f83f312d3)

# RESULT
A YACC program to recognize a valid arithmetic expression that uses operator +,-,* and / is executed successfully and the output is verified.
