/*w_o_simple_game
The goal of this game is whoever presses the button quickly, he wins*/

#include <stdio.h>
#include <windows.h>
#include <conio.h>

char map[20][20];
char player = 'w';
char player2 = 'o';

int x2 = 18;
int y2 = 5;

int x = 18;
int y = 2;

char walk;

void generateMap()
{
    for(int i=0;i<20;i++)
	{
		for(int j=0;j<20;j++)
		{
			map[i][j] = ' ';
		}
	}
	map[x][y] = player;
	map[x2][y2] = player2;
}

void printMap()
{
for(int i=0;i<20;i++)
	{
		for(int j=0;j<20;j++)
		{
			printf("%c",map[i][j]);
		}
		printf("\n");
	}
	map[18][2] = player;	
}


int main ()
{
	do
	{
		system("cls");
		generateMap();
    	printMap();
    	walk = getch();
    	
    	switch(walk)
		{
			case 'w' :
				if(map[x-1][y]==' ')
				{
					x--;
					map[x+1][y] = ' ';
					map[x][y] = player;
				}
			case 'o' :
					if(map[x2-1][y2]==' ')
				{
					x2--;
					map[x2+1][y2] = ' ';
					map[x2][y2] = player2;
				}
		} 
    	
    	
    	
    	
	} while(y<20000);
 
	
	getchar();
	return 0;
}
