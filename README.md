# alphabet-conversion
#include<stdio.h>
#include<stdlib.h>
int main()
{
	FILE * fptr;
	FILE * dptr;
	char ch;
	fptr=fopen("c:\\temp\\file1.txt","r");
	if(fptr==NULL)
	{
		printf("unable to open file");
		printf("please check whether the file exists and read priviledge");
		exit(EXIT_FAILURE);
	}
	printf("file opened succesfully,read file contents by character.\n");
	dptr=fopen("c:\\temp\\1.txt","w");
	do
	{
		ch=fgetc(fptr);
		int i=ch;
		if((i>=65)&&(i<=77))
		{
			i=i+45;
			fprintf(dptr,"%c",(char)i);
		}
		else if((i>=78)&&(i<=90))
		{
			i=i-19;
			fprintf(dptr,"%c",(char)i);
	    }
	    else if((i>=97)&&(i<=109))
		{
			i=i-19;
			fprintf(dptr,"%c",(char)i);
	    }
	    else if ((i>=110)&&(i<=122))
		{
			i=i-45;
			fprintf(dptr,"%c",(char)i);
	    }
	    else
	    printf("invalid character");
   }  
   while(ch!=EOF);
   fclose(fptr);
   fclose(dptr);
   return 0;
}
