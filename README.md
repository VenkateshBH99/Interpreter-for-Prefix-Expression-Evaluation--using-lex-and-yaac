# Interpreter-using-lex-and-yaac
This is an implementation of a simple interpreter using lex and yaac for evaluating a given cfg
## Building the interpreter
yacc -y -d yacc_compile.y

lex yacc_compile.l

gcc -c y.tab.c lex.yy.c

gcc lex.yy.o y.tab.o yacc_compile.c -o compile

./compile

1. example:[ ; [ = x 5 ] [ ; if [ < x 3 ] [ = x [ + x 2 ] ] [ = x [ * x 2 ] ] ] [ return x ] ]

        ans: 10
        
2. example: [ * [ + 1 3 ] [ + 2 3 ] ]

       ans: 20
       
