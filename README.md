#define _CRT_SECURE_NO_DEPRECATE
#include <stdio.h>
#include "ProblemHeader_3.h"

int main()
{
	FILE *myfile = fopen("outputEvenOdd.txt", "r");
	
	
	for (int i = 1; i < 34; i++)
	{
		fprintf(myfile, "%d\n", i);
	}
FILE *myfileEven = fopen("outputEven.txt", "w");
	int readBuff;
	while (feof(myfile))
	{
		fscanf(myfile, "%d", &readBuff);
		fprintf(myfileEven, "%d\n");
		int isEven = MyisEven(readBuff);
		if (isEven == 2)
		{
			fprintf(myfileEven, "%d\n", readBuff);
		}
	}
	fclose(myfile);
	fclose(myfileEven);
	return 0;
}
