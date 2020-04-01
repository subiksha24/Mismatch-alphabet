# mismatch-alphabet-
//Giving input string and find mismatched alphabet from string in continuous series
// pgm to find mismatched character in input string 
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
int main()
{
char ch,ip[100],out[100];
int as[100],b[100],i,r,flag;
int no[26]={0},n,c,t,x;
scanf("%s",&ip);
n=strlen(ip);
for(c=0;c<n;c++)
{
ch=ip[c]-'a';
no[ch]++;
}
t=0;
for(ch='a';ch<='z';ch++)
{
x=ch-'a';
for(c=0;c<no[x];c++)
{
out[t]=ch;
t++;
}}
out[t]='\0';
r=strlen(out);
for(i=0;i<r;i++)
{
as[i]=out[i];
}
flag=as[2]-as[1];
for(i=0;i<2;i++)
{
if((as[i]+flag)==as[i+1])
{
out[i]=as[i];
}
else
{
as[r-1]=as[i];
}
}
for(i=3;i<r;i++)
{
out[i]=as[i];
}
printf("%c",out[strlen(out)-1]);return 0;
}
