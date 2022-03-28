#include <stdlib.h>
#include <stdio.h>
#define row 4
#define colume 4
#define _CRT_SECURE_NO_WARNINGS

int main()
{
	int mtrx[row][colume] = { {1,2,1,1},{1,1,1,1},{1,1,1,1},{1,1,1,1} };
	int down = 0, up = 0, x, y;
	int temp = row / 2;


	for (x = 0; x < colume; x++)
	{
		for (y = 0; y < row; y++)
		{
			if (x + y <= temp) // חוקיות שאם הם קטנים או שווים ל2
			{
				up = mtrx[x][y] + up;
			}
		}
	}

	for (x = 0; x < colume; x++)
	{
		for (y = 0; y < row; y++)
		{
			if (x + y > row - 1) //חוקיות שאם הם גדולים יותר מהאלכסון המשני
			{
				down = mtrx[x][y] + down;
			}
		}
	}

	if (down == up)
		printf("the numbers above are equal to the ones under...\n");
	else
		printf("the numbers arent equal..\n");

	system("pause");
}
