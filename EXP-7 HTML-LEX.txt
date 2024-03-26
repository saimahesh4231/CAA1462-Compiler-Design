%{
#include<stdio.h>
%}
%%
\<[^>]*\> fprintf(yyout,"%s\n",yytext);
.|\n;
%%
int yywrap(){
return 1;
}
int main()
{
yyin=fopen("input1.html","r");
yyout=fopen("output1.txt","w");
yylex();
}
