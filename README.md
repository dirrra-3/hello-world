# hello-world

#include <gl\glut.h>
#include <iostream>
#include <math.h>
using namespace std;
int c = 0;
float E = 475 / 7;
int xman, yman, xmanfirst, ymanfirst, xman_org, yman_org;
int turn = 0; // represents which player's turn
int clickTime = 2; //he can click 2 times
//
char BoardMem[7][7] = { //Board memory 
	'G', '0', '0', '0', '0', '0', 'B', //the bottom most row of the board
	'0', '0', '0', '0', '0', '0', '0',
	'0', '0', '0', '0', '0', '0', '0',
	'0', '0', '0', '0', '0', '0', '0',
	'0', '0', '0', '0', '0', '0', '0',
	'0', '0', '0', '0', '0', '0', '0',
	'B', '0', '0', '0', '0', '0', 'G', }; //top row of the board

/*void drawStrokeText(char*string,int x,int y,int z)
{
	  char *c;
	  glPushMatrix();
	  glTranslatef(x, y+8,z);
	  glScalef(0.09f,-0.08f,z);
  
	  for (c=string; *c != '\0'; c++)
	  {
    		glutStrokeCharacter(GLUT_STROKE_ROMAN , *c);
	  }
	  glPopMatrix();
}
void print(void)
{ 
	glClear(GL_COLOR_BUFFER_BIT); 
	glLoadIdentity();
 
	glColor3f(0,1,0);
	drawStrokeText("Osama Hosam's OpenGL Tutorials",500,500,-2.0f);
	glutSwapBuffers(); 
}
*/

	void stickman(float xtranslation, float ytranslation, float g, float b)
{
	glMatrixMode(GL_MODELVIEW); // To operate on model-view matrix
	glLoadIdentity();

	glTranslatef(-34.0 + xtranslation*5.7, -34.0 + ytranslation*5.7, -60.0f);

	glColor3f(0.0, g, b);
	glBegin(GL_POLYGON);
	glVertex3f((4.0 + 25)*0.5, (6.5 + 25)*0.5, -1.0);
	glVertex3f((6.0 + 25)*0.5, (6.5 + 25)*0.5, -1.0);
	glVertex3f((6.0 + 25)*0.5, (8.5 + 25)*0.5, -1.0);
	glVertex3f((4.0 + 25)*0.5, (8.5 + 25)*0.5, -1.0);
	glEnd();
	glFlush();

	glColor3f(0.0, g, b);
	glBegin(GL_LINES);
	glVertex3f((5.0 + 25)*0.5, (6.5 + 25)*0.5, -1.0);
	glVertex3f((5.0 + 25)*0.5, (3.0 + 25)*0.5, -1.0);
	glVertex3f((3.5 + 25)*0.5, (5.1 + 25)*0.5, -1.0);
	glVertex3f((6.5 + 25)*0.5, (5.1 + 25)*0.5, -1.0);
