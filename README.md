#include <GL/gl.h>
#include <GL/glu.h>
#include <GL/glut.h>
#include<math.h>


#include <stdlib.h>
#include <windows.h>

void display();

void reshape(int w,int h);
void timer (int);

void init(){
    glClearColor(0.3,0.6,1.0,0.0);
}

int main(int argc,char**argv)
{
    glutInit(&argc,argv);
    glutInitDisplayMode(GLUT_RGB);

    glutInitWindowPosition(200,0);
    glutInitWindowSize(1200,800);

    glutCreateWindow("20109806/Omar Elnaggar");

    glutDisplayFunc(display);
    glutReshapeFunc(reshape);
    glutTimerFunc(0,timer,0);

    init();

    glutMainLoop();
}

float step=0;

void display()
{
    glClear(GL_COLOR_BUFFER_BIT);
    glLoadIdentity();
    double radius;
///////////////////////GROUND
    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_POLYGON);
    glColor3ub(138,69,19);

    glVertex2f(-15,-6);
    glVertex2f(-15,-10);
     glVertex2f(15,-10);
    glVertex2f(15,-6);
    glEnd();
    glPopMatrix();
    
    ///////////////////////road
    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_LINES);
    glColor3ub(255 ,255 ,255);

    glVertex2f(-14+step,-8);
    glVertex2f(-11+step,-8);

    glVertex2f(-9+step,-8);
    glVertex2f(-6+step,-8);

    glVertex2f(-4+step,-8);
    glVertex2f(-1+step,-8);

    glVertex2f(1+step,-8);
    glVertex2f(4+step,-8);

    glVertex2f(6+step,-8);
    glVertex2f(9+step,-8);

    glVertex2f(11+step,-8);
    glVertex2f(14+step,-8);



    glEnd();
    glPopMatrix();
    
    //LAMP-------------------------------------------
    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_POLYGON);
    glColor3ub(0,0,0);

    glVertex2f(-13,4);
    glVertex2f(-13,-6);
    glVertex2f(-12.5,-6);
    glVertex2f(-12.5,4);
    glEnd();
    glPopMatrix();
    
    //top lamp -------------------------------------------
    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_POLYGON);
    glColor3ub(0,0,0);

    glVertex2f(-14,4);
    glVertex2f(-11.5,4);
    glVertex2f(-11.5,5);
    glVertex2f(-14,5);
    glEnd();
    glPopMatrix();
    
// ----------- lamp lights
  glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_POLYGON);
    glColor3ub(240 ,230 ,140);

    glVertex2f(-11.4,4);
    glVertex2f(-11,4);
    glVertex2f(-11,5);
    glVertex2f(-11.4,5);
    glEnd();
    glPopMatrix();
    
    ////////////////////eyeees///////////////////////
    glPushMatrix();
glTranslated(-13.5,4.6,0);
    glBegin(GL_POLYGON);
    glColor3ub(255 ,255 ,255);

    radius=0.2;
    for(int i =0;i<360;i++)
        {
        double angle=i*3.14/180;
        glVertex2d(cos(angle)*radius,radius*sin(angle));

    }
glEnd();
    glPopMatrix();

    /////////////////////eyyees//////////////////////
    glPushMatrix();
glTranslated(-12,4.6,0);
    glBegin(GL_POLYGON);
    glColor3ub(255 ,255 ,255);

    radius=0.2;
    for(int i =0;i<360;i++)
        {
        double angle=i*3.14/180;
        glVertex2d(cos(angle)*radius,radius*sin(angle));

    }
glEnd();
    glPopMatrix();


    ///////////////////////house
     glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(205 ,133, 0);

    glVertex2f(-10.5,-6);
    glVertex2f(-2.5,-6);
    glVertex2f(-2.5,4);
    glVertex2f(-10.5,4);
    glEnd();
    glPopMatrix();

    ///////////////////////window left
     glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(238 ,216, 174);

    glVertex2f(-9.5,0.5);
    glVertex2f(-7,0.5);
    glVertex2f(-7,3);
    glVertex2f(-9.5,3);
    glEnd();
    glPopMatrix();


    ///////////////////////window right
     glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(238 ,216, 174);

    glVertex2f(-3.5,0.5);
    glVertex2f(-6,0.5);
    glVertex2f(-6,3);
    glVertex2f(-3.5,3);
    glEnd();
    glPopMatrix();


    ///////////////////////door
     glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(255, 236, 139);

    glVertex2f(-8,-6);
    glVertex2f(-5,-6);
    glVertex2f(-5,-2);
    glVertex2f(-8,-2);
    glEnd();
    glPopMatrix();

/////////shape Betwwen houses/////////////////////
     glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(84, 139, 84);

    glVertex2f(0,-6);
    glVertex2f(2,-6);
    glVertex2f(2,-2);
    glVertex2f(0,-2);


    glEnd();
    glPopMatrix();
///////////////
glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_TRIANGLES);
    glColor3ub(193 ,255 ,193);

    glVertex2f(0,-2);
    glVertex2f(2,-2);
    glVertex2f(1,0);

    glEnd();
    glPopMatrix();

/////////////////////// house 2
glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(205 ,133, 0);

    glVertex2f(4.5,-6);
    glVertex2f(12.5,-6);
    glVertex2f(12.5,4);
    glVertex2f(4.5,4);

    glEnd();
    glPopMatrix();

///////////////////////// window left 2
    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(238 ,216, 174);

    glVertex2f(5.5,0.5);
    glVertex2f(7.5,0.5);
    glVertex2f(7.5,3.5);
    glVertex2f(5.5,3.5);


    glEnd();
    glPopMatrix();
///////////////////////// window right 2
    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(238 ,216, 174);

    glVertex2f(9.5,0.5);
    glVertex2f(11.5,0.5);
    glVertex2f(11.5,3.5);
    glVertex2f(9.5,3.5);


    glEnd();
    glPopMatrix();
    
    ///////////////////////// window right2 lines
    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_LINES);
    glColor3ub(0,0,0);

    glVertex2f(9.5,2.5);
    glVertex2f(11.5,2.5);

     glVertex2f(9.5,2);
    glVertex2f(11.5,2);

    glVertex2f(9.5,1.5);
    glVertex2f(11.5,1.5);
    
    //// window left2 lines/////////////////////

    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_LINES);
    glColor3ub(0,0,0);

    glVertex2f(5.5,2.5);
    glVertex2f(7.5,2.5);
     glVertex2f(5.5,2);
    glVertex2f(7.5,2);
    glVertex2f(5.5,1.5);
    glVertex2f(7.5,1.5);
glEnd();
    glPopMatrix();
    
///////////////////////// door  2
    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(255, 236, 139);

    glVertex2f(8,-6);
    glVertex2f(10,-6);
    glVertex2f(10,-2);
    glVertex2f(8,-2);


    glEnd();
    glPopMatrix();
    
/////////////////////////rope
    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_LINES);
    glColor3ub(0,0,0);

    glVertex2f(-2.5,3);
    glVertex2f(4.5,3);

    glEnd();
    glPopMatrix();
    
   //////////////ELZENAAAAAA///////////// 
///////1
    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(255 ,255, 0);


    glVertex2f(-2,2.2);
    glVertex2f(-1.2,2.2);
    glVertex2f(-1.2,2.9);
    glVertex2f(-2,2.9);

     glEnd();
    glPopMatrix();


//////2
glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(238 ,99 ,99);
    glVertex2f(-1,1.9);
    glVertex2f(-0.2,1.9);
    glVertex2f(-0.2,2.9);
    glVertex2f(-1,2.9);

     glEnd();
    glPopMatrix();


/////////3
glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(0 ,255, 0);
    glVertex2f (0,2.2);
    glVertex2f(0.4,2.2);
    glVertex2f(0.4,2.9);
    glVertex2f(0,2.9);

   glEnd();
    glPopMatrix();

/////////4
glPushMatrix();
glTranslated(1.2,2.5,0);
glRotated(39,-3.3,6.5,-80.5);
    glBegin(GL_POLYGON);
    glColor3ub(55 ,255 ,139);

    radius=0.3;
    for(int i =0;i<360;i++)
        {
        double angle=i*3.14/180;
        glVertex2d(cos(angle)+radius,radius*sin(angle));

    }
glEnd();
    glPopMatrix();

 ///////////5
    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(244,77,2);

    glVertex2f(2.5,2);
    glVertex2f(2.9,2);
    glVertex2f(2.9,2.9);
    glVertex2f(2.5,2.9);

   glEnd();
    glPopMatrix();
/////////6
    glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_QUADS);
    glColor3ub(205 ,0 ,0);

    glVertex2f(3.1,1.5);
    glVertex2f(3.9,1.5);
    glVertex2f(3.9,2.9);
    glVertex2f(3.1,2.9);


   glEnd();
    glPopMatrix();


////////////////////Sun
glPushMatrix();
glTranslated(-12.5,7.5,0);
glBegin(GL_POLYGON);
glColor3ub(255,255,0);
radius=2;
for(int i=0;i<360;i++){
    double angle=i*3.14/180;
    glVertex2d(cos(angle)*radius,radius*sin(angle));


}
glEnd();
glPopMatrix();

///////////////skkkky1//////////////////////////
glPushMatrix();
glTranslated(0+step,8,0);
    glBegin(GL_POLYGON);
    glColor3ub(54 ,100 ,139);

    radius=1;
    for(int i =0;i<360;i++)
        {
        double angle=i*3.14/180;
        glVertex2d(cos(angle)+radius,radius*sin(angle));

    }
glEnd();
    glPopMatrix();
//////////////////////skkkky1///////////////////
glPushMatrix();
glTranslated(1.5+step,8,0);
    glBegin(GL_POLYGON);
    glColor3ub(54 ,100 ,139);

    radius=1;
    for(int i =0;i<360;i++)
        {
        double angle=i*3.14/180;
        glVertex2d(cos(angle)+radius,radius*sin(angle));

    }
glEnd();
    glPopMatrix();

///////////////////////skkkky1//////////////////
glPushMatrix();
glTranslated(3+step,8,0);
    glBegin(GL_POLYGON);
    glColor3ub(54 ,100 ,139);

    radius=1;
    for(int i =0;i<360;i++)
        {
        double angle=i*3.14/180;
        glVertex2d(cos(angle)+radius,radius*sin(angle));

    }
glEnd();
    glPopMatrix();

/////////////////////////skkkky1////////////////
glPushMatrix();
glTranslated(1.5+step,9,0);
    glBegin(GL_POLYGON);
    glColor3ub(54 ,100 ,139);

    radius=1;
    for(int i =0;i<360;i++)
        {
        double angle=i*3.14/180;
        glVertex2d(cos(angle)+radius,radius*sin(angle));

    }
glEnd();
    glPopMatrix();

/////////////////////////skkkky2
glPushMatrix();
glTranslated(5.5+step,8,0);
    glBegin(GL_POLYGON);
    glColor3ub(54 ,100 ,139);

    radius=1;
    for(int i =0;i<360;i++)
        {
        double angle=i*3.14/180;
        glVertex2d(cos(angle)+radius,radius*sin(angle));

    }
glEnd();
    glPopMatrix();

/////////////////////////skkkky2
glPushMatrix();
glTranslated(7+step,8,0);
    glBegin(GL_POLYGON);
    glColor3ub(54 ,100 ,139);

    radius=1;
    for(int i =0;i<360;i++)
        {
        double angle=i*3.14/180;
        glVertex2d(cos(angle)+radius,radius*sin(angle));

    }
glEnd();
    glPopMatrix();

    /////////////////////////skkkky2
glPushMatrix();
glTranslated(8.5+step,8,0);
    glBegin(GL_POLYGON);
    glColor3ub(54 ,100 ,139);

    radius=1;
    for(int i =0;i<360;i++)
        {
        double angle=i*3.14/180;
        glVertex2d(cos(angle)+radius,radius*sin(angle));

    }
glEnd();
    glPopMatrix();

    /////////////////////////skkkky2
glPushMatrix();
glTranslated(7+step,9,0);
    glBegin(GL_POLYGON);
    glColor3ub(54 ,100 ,139);

    radius=1;
    for(int i =0;i<360;i++)
        {
        double angle=i*3.14/180;
        glVertex2d(cos(angle)+radius,radius*sin(angle));

    }
glEnd();
    glPopMatrix();
    /////////////winteeeeer
 glPushMatrix();
    glLineWidth(5.0);
    glBegin(GL_LINES);
    glColor3ub(255,255 ,255);


    glVertex2f(1+step,7);
    glVertex2f(1+step,6.5);

     glVertex2f(1+step,5);
    glVertex2f(1+step,4.5);

    glVertex2f(1+step,4);
    glVertex2f(1+step,3.5);

   //

     glVertex2f(2+step,6);
    glVertex2f(2+step,5.5);

     glVertex2f(2+step,5);
    glVertex2f(2+step,4.5);

    //
    glVertex2f(3+step,7);
    glVertex2f(3+step,6.5);

     glVertex2f(3+step,5);
    glVertex2f(3+step,4.5);

    //
    glVertex2f(4+step,7);
    glVertex2f(4+step,6.5);

     glVertex2f(4+step,6);
    glVertex2f(4+step,5.5);

    glVertex2f(4+step,4);
    glVertex2f(4+step,3.5);
  //
    glVertex2f(6+step,7);
    glVertex2f(6+step,6.5);

     glVertex2f(6+step,6);
    glVertex2f(6+step,5.5);

    glVertex2f(6+step,4);
    glVertex2f(6+step,3.5);
    //
    glVertex2f(7+step,7);
    glVertex2f(7+step,6.5);

     glVertex2f(7+step,6);
    glVertex2f(7+step,5.5);

    //

    glVertex2f(8+step,6);
    glVertex2f(8+step,5.5);

    glVertex2f(8+step,4);
    glVertex2f(8+step,3.5);
   //
    glVertex2f(10+step,7);
    glVertex2f(10+step,6.5);

     glVertex2f(10+step,6);
    glVertex2f(10+step,5.5);

    glVertex2f(10+step,4);
    glVertex2f(10+step,3.5);

     glEnd();
    glPopMatrix();
    glFlush();
}






void reshape(int w,int h)
{
    glViewport(0,0,(GLsizei)w,(GLsizei)h);
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluOrtho2D(-15,15,-10,10);
    glMatrixMode(GL_MODELVIEW);
}
void timer (int){
glutPostRedisplay();
glutTimerFunc(1000/10,timer,0);
             step+=0.3;




}
