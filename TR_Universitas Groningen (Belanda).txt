#include <windows.h>
#include <GL/glut.h>

//Jonathan Mario Dwi Priyadi - 672020162
//Sinatria Banyu Adil - 672020166
//CAHAYANI DINDA PERMATASARI - 672020307
//MICHAEL YOHANSON MESAK FOEH - 672020003
//RIZKY BAGUS PRATAMA - 672020311


float xx1 = 0.0, yy1 = 0.0, zz1 = 0.0, xxx1 = 0.0, yyy1 = 0.0, zzz1 = 0.0, sudut = 0.0;
float xrot = 0.0;
float yrot = 0.0;
float xdiff = 0.0;
float ydiff = 0.0;
bool mouseDown = false;
const float BOX_SIZE = 7.0f;

void listputih1()
{
    glBegin(GL_POLYGON);
    glColor3f(1, 1, 1);
    glVertex3f(-59.7, -130, 16.5);
    glVertex3f(-86.2, -130, 16.5);
    glVertex3f(-86.2, -132, 16.5);
    glVertex3f(-59.7, -132, 16.5);
    glEnd();
}
void listputih2()
{
    glBegin(GL_POLYGON);
    glColor3f(1, 1, 1);
    glVertex3f(-59.7, -130, -109.5);
    glVertex3f(-59.7, -130, 16.5);
    glVertex3f(-59.7, -132, 16.5);
    glVertex3f(-59.7, -132, -109.5);
    glEnd();
}
void listkaca()
{
    //kanan
    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-65.7, -142, 36.7);
    glVertex3f(-64.7, -142, 19.7);
    glVertex3f(-64.7, -143.5, 19.7);
    glVertex3f(-65.7, -143.5, 36.7);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-65.7, -158.5, 36.7);
    glVertex3f(-64.7, -158.5, 19.7);
    glVertex3f(-64.7, -160, 19.7);
    glVertex3f(-65.7, -160, 36.7);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-64.7, -129.5, 21.7);
    glVertex3f(-64.7, -129.5, 20.2);
    glVertex3f(-64.7, -171.5, 20.2);
    glVertex3f(-64.7, -171.5, 21.7);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-65.5, -129.5, 33.8);
    glVertex3f(-65.4, -129.5, 31.7);
    glVertex3f(-65.4, -171.5, 31.7);
    glVertex3f(-65.5, -171.5, 33.8);
    glEnd();

    //kiri
    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-79.7, -142, 36.7);
    glVertex3f(-81.2, -142, 19.7);
    glVertex3f(-81.2, -143.5, 19.7);
    glVertex3f(-79.7, -143.5, 36.7);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-79.7, -157.5, 36.7);
    glVertex3f(-81.2, -157.5, 19.7);
    glVertex3f(-81.2, -159, 19.7);
    glVertex3f(-79.7, -159, 36.7);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-80.7, -129.5, 23.7);
    glVertex3f(-81, -129.5, 22.2);
    glVertex3f(-81, -171.5, 22.2);
    glVertex3f(-80.7, -171.5, 23.7);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-80.2, -129.5, 32.7);
    glVertex3f(-80, -129.5, 34.2);
    glVertex3f(-80, -171.5, 34.2);
    glVertex3f(-80.2, -171.5, 32.7);
    glEnd();

    //serong kanan
    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-66.7, -129.5, 43.5);
    glVertex3f(-66.5, -129.5, 42);
    glVertex3f(-66.5, -171.5, 42);
    glVertex3f(-66.7, -171.5, 43.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-68.9, -129.5, 56.5);
    glVertex3f(-68.7, -129.5, 55);
    glVertex3f(-68.7, -171.5, 55);
    glVertex3f(-68.9, -171.5, 56.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-69.3, -141.5, 59.5);
    glVertex3f(-65.8, -141.5, 39);
    glVertex3f(-65.8, -143.5, 39);
    glVertex3f(-69.3, -143.5, 59.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-69.3, -158, 59.5);
    glVertex3f(-65.8, -158, 39);
    glVertex3f(-65.8, -160, 39);
    glVertex3f(-69.3, -160, 59.5);
    glEnd();

    //serong kiri
    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-78.5, -129.5, 43.5);
    glVertex3f(-78.7, -129.5, 42);
    glVertex3f(-78.7, -171.5, 42);
    glVertex3f(-78.5, -171.5, 43.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-76.8, -129.5, 57.5);
    glVertex3f(-77.0, -129.5, 56);
    glVertex3f(-77.0, -171.5, 56);
    glVertex3f(-76.8, -171.5, 57.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-76.6, -141.5, 59.5);
    glVertex3f(-79, -141.5, 39);
    glVertex3f(-79, -143.5, 39);
    glVertex3f(-76.6, -143.5, 59.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-76.6, -157.5, 59.5);
    glVertex3f(-79, -157.5, 39);
    glVertex3f(-79, -160.5, 39);
    glVertex3f(-76.6, -160.5, 59.5);
    glEnd();

    //depan
    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-70.5, -157.5, 61.8);
    glVertex3f(-75.5, -157.5, 61.8);
    glVertex3f(-75.5, -160.5, 61.8);
    glVertex3f(-70.5, -160.5, 61.8);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-70.5, -140.5, 61.8);
    glVertex3f(-75.5, -140.5, 61.8);
    glVertex3f(-75.5, -143.5, 61.8);
    glVertex3f(-70.5, -143.5, 61.8);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-71.4, -129.5, 61.8);
    glVertex3f(-72, -129.5, 61.8);
    glVertex3f(-72, -171.5, 61.8);
    glVertex3f(-71.4, -171.5, 61.8);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-73.8, -129.5, 61.8);
    glVertex3f(-74.4, -129.5, 61.8);
    glVertex3f(-74.4, -171.5, 61.8);
    glVertex3f(-73.8, -171.5, 61.8);
    glEnd();
}
void kakikursi()
{
    glPushMatrix();
    glTranslatef(-58, -6, -115);
    glColor3f(0.8, 0.45, 0);
    glScalef(0.5, 4, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-58, -6, -135);
    glColor3f(0.8, 0.45, 0);
    glScalef(0.5, 4, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-32, -6, -115);
    glColor3f(0.8, 0.45, 0);
    glScalef(0.5, 4, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-32, -6, -135);
    glColor3f(0.8, 0.45, 0);
    glScalef(0.5, 4, 0.5);
    glutSolidCube(4);
    glPopMatrix();
}
void meja()
{
    glTranslatef(0, 0, -10.0);
    glPushMatrix();
    glTranslatef(-45, 0.5, -125);
    glColor3f(0.9, 0.5, 0);
    glScalef(9, 1, 7);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-58, -6, -115);
    glColor3f(0.8, 0.45, 0);
    glScalef(0.5, 4, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-58, -6, -135);
    glColor3f(0.8, 0.45, 0);
    glScalef(0.5, 4, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-32, -6, -115);
    glColor3f(0.8, 0.45, 0);
    glScalef(0.5, 4, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-32, -6, -135);
    glColor3f(0.8, 0.45, 0);
    glScalef(0.5, 4, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    //kursi
    glPushMatrix();
    glTranslatef(-45, -5, -93.5);
    glColor3f(0.9, 0.5, 0);
    glScalef(5.4, 1, 7);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();        //kaki kursi
    glScalef(0.4, 0.9, 1);
    glTranslatef(-67.5, -5.8, 31);
    kakikursi();
    glPopMatrix();
}
void papantulis()
{
    glPushMatrix();
    glTranslatef(20, 15, -139.5);
    glColor3f(0.0, 0.0, 0.0);
    glScalef(13, 8, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(20, 15, -139);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(12.5, 7.5, 0.5);
    glutSolidCube(4);
    glPopMatrix();
}
void mejakursi()
{
    glTranslatef(0, 0, -10.0);
    //meja kursi
    glPushMatrix();        //meja 1
    glScalef(0.3, 1, 1);
    glTranslatef(-218.6, -177, 85);
    meja();
    glPopMatrix();

    glPushMatrix();        //meja 2
    glScalef(0.3, 1, 1);
    glTranslatef(-173.3, -177, 85);
    meja();
    glPopMatrix();
}
void atasbangunan()
{
    glBegin(GL_POLYGON);        //depan
    glColor3f(1, 0.7, 0);
    glVertex3f(-60, -41.5, 16);
    glVertex3f(-86, -41.5, 16);
    glVertex3f(-86, -53.5, 16);
    glVertex3f(-60, -53.5, 16);
    glEnd();

    glBegin(GL_POLYGON);        //belakang
    glColor3f(1, 0.7, 0);
    glVertex3f(-60, -41.5, -109);
    glVertex3f(-86, -41.5, -109);
    glVertex3f(-86, -53.5, -109);
    glVertex3f(-60, -53.5, -109);
    glEnd();

    glBegin(GL_POLYGON);        //kanan
    glColor3f(0.92, 0.64, 0);
    glVertex3f(-60.2, -41.5, 16);
    glVertex3f(-60.2, -41.5, -109);
    glVertex3f(-60.2, -53.5, -109);
    glVertex3f(-60.2, -53.5, 16);
    glEnd();

    glBegin(GL_POLYGON);        //kiri
    glColor3f(1, 0.74, 0.14);
    glVertex3f(-85.8, -41.5, 16);
    glVertex3f(-85.8, -41.5, -109);
    glVertex3f(-85.8, -53.5, -109);
    glVertex3f(-85.8, -53.5, 16);
    glEnd();
}
void listatasbangunan()
{
    glBegin(GL_POLYGON);
    glColor3f(0.3, 0.3, 0.3);
    glVertex3f(-60.1, -41.5, 13);
    glVertex3f(-60.1, -41.5, 11);
    glVertex3f(-60.1, -53.5, 11);
    glVertex3f(-60.1, -53.5, 14);
    glEnd();
}
void listataspanjang()
{
    glBegin(GL_POLYGON);        //list atas bangunan kanan
    glColor3f(0.3, 0.3, 0.3);
    glVertex3f(-60.1, -41.5, 16);
    glVertex3f(-60.1, -41.5, -109);
    glVertex3f(-60.1, -43, -109);
    glVertex3f(-60.1, -43, 16);
    glEnd();
}
void listataspanjangdepan()
{
    glBegin(GL_POLYGON);        //depan
    glColor3f(0.3, 0.3, 0.3);
    glVertex3f(-60, -41.5, 16.1);
    glVertex3f(-86, -41.5, 16.1);
    glVertex3f(-86, -43, 16.1);
    glVertex3f(-60, -43, 16.1);
    glEnd();
}
void jendelaatas()
{
    glBegin(GL_POLYGON);            //kaca atas segitiga depan
    glColor3f(0.6, 0.6, 1);
    glVertex3f(-70.5, -129.5, 61.7);
    glVertex3f(-75.5, -129.5, 61.7);
    glVertex3f(-75.5, -171.5, 61.7);
    glVertex3f(-70.5, -171.5, 61.7);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-70.5, -157.5, 61.8);
    glVertex3f(-75.5, -157.5, 61.8);
    glVertex3f(-75.5, -160.5, 61.8);
    glVertex3f(-70.5, -160.5, 61.8);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-70.5, -140.5, 61.8);
    glVertex3f(-75.5, -140.5, 61.8);
    glVertex3f(-75.5, -143.5, 61.8);
    glVertex3f(-70.5, -143.5, 61.8);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-71.4, -129.5, 61.8);
    glVertex3f(-72, -129.5, 61.8);
    glVertex3f(-72, -171.5, 61.8);
    glVertex3f(-71.4, -171.5, 61.8);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-73.8, -129.5, 61.8);
    glVertex3f(-74.4, -129.5, 61.8);
    glVertex3f(-74.4, -171.5, 61.8);
    glVertex3f(-73.8, -171.5, 61.8);
    glEnd();
}
void tombakatassegitiga()
{
     glPushMatrix();
    glTranslatef(-6.5, 160, -15);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(3, 60, 5);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-6.5, 190, -15);
    glRotatef(-90.0, 1, 0, 0);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(3, 3, 10);
    glutSolidCone(1, 1, 16, 16);
    glPopMatrix();
}
void coversegitiga()
{
    glBegin(GL_POLYGON);        //segitiga atas depan
    glColor3f(1, 0.7, 0);
    glVertex3f(-73.2, 8, 16);
    glVertex3f(-86, -41.5, 16);
    glVertex3f(-60, -41.5, 16);
    glEnd();

    glBegin(GL_POLYGON);        //depan 1
    glColor3f(1, 0.7, 0);
    glVertex3f(-66.6, 8, 16);
    glVertex3f(-79.4, 8, 16);
    glVertex3f(-79.4, -41.5, 16);
    glVertex3f(-66.6, -41.5, 16);
    glEnd();

    glBegin(GL_POLYGON);        //depan 2
    glColor3f(1, 0.7, 0);
    glVertex3f(-69.9, 27.5, 16);
    glVertex3f(-76.1, 27.5, 16);
    glVertex3f(-76.1, -41.5, 16);
    glVertex3f(-69.9, -41.5, 16);
    glEnd();

    glBegin(GL_POLYGON);        //list atas segitiga depan
    glColor3f(0.3, 0.3, 0.3);
    glVertex3f(-66.6, 8, 16.1);
    glVertex3f(-79.4, 8, 16.1);
    glVertex3f(-79.4, 6, 16.1);
    glVertex3f(-66.6, 6, 16.1);
    glEnd();

    glPushMatrix();             //tombak atas segitiga 1
    glTranslatef(-67.1, -169.5, 9);
    glScalef(-0.1, 1, -0.5);
    tombakatassegitiga();
    glPopMatrix();

    glPushMatrix();             //tombak atas segitiga 1
    glTranslatef(-80.1, -169.5, 9);
    glScalef(-0.1, 1, -0.5);
    tombakatassegitiga();
    glPopMatrix();

    glPushMatrix();             //tombak atas segitiga 2
    glTranslatef(-76.8, -44, 9);
    glScalef(-0.1, 0.4, -0.5);
    tombakatassegitiga();
    glPopMatrix();

    glPushMatrix();             //tombak atas segitiga 2
    glTranslatef(-70.5, -44, 9);
    glScalef(-0.1, 0.4, -0.5);
    tombakatassegitiga();
    glPopMatrix();

    glBegin(GL_POLYGON);        //segitiga atas depan
    glColor3f(1, 0.7, 0);
    glVertex3f(-73.2, 40, 16);
    glVertex3f(-76.1, 27.5, 16);
    glVertex3f(-69.9, 27.5, 16);
    glEnd();
}
void ataptotal()
{
    glBegin(GL_POLYGON);        //atap kanan
    glColor3f(0.4, 0.4, 0.4);
    glVertex3f(-60, -41.5, 16);
    glVertex3f(-60, -41.5, -109);
    glVertex3f(-73.2, 7.5, -109);
    glVertex3f(-73.2, 7.5, 16);
    glEnd();

    glBegin(GL_POLYGON);        //atap kiri
    glColor3f(0.4, 0.4, 0.4);
    glVertex3f(-73.2, 7.5, -109);
    glVertex3f(-73.2, 7.5, 16);
    glVertex3f(-85.8, -41.5, 16);
    glVertex3f(-85.8, -41.5, -109);
    glEnd();

    glPushMatrix();             //atap depan 1
    glColor3f(0.53, 0.64, 0.56);
    glTranslatef(-72.7, -49, 32.6);
    glScalef(-0.15, 0.6, 0.6);
    glRotatef(90.0f, -1.0f, 0.0f, 0.0f);
    glutSolidTorus(10, 50, 6, 20);
    glPopMatrix();

    glPushMatrix();             //atap depan 2
    glColor3f(0.67, 0.75, 0.69);
    glTranslatef(-72.7, -39.6, 32.6);
    glScalef(-0.13, 0.6, 0.6);
    glRotatef(90.0f, -1.0f, 0.0f, 0.0f);
    glutSolidTorus(10, 50, 6, 20);
    glPopMatrix();

    glPushMatrix();
    glColor3f(0.78, 0.84, 0.8);
    glTranslatef(-73, -42.1, 33);
    glScalef(0.1, 0.3, 0.4);
    glutSolidSphere(60, 360, 360);
    glPopMatrix();
}
void bangunankiri()
{
    glBegin(GL_POLYGON);        //depan
    glColor3f(1, 0.7, 0);
    glVertex3f(-60, -121, 16);
    glVertex3f(-86, -121, 16);
    glVertex3f(-86, -180, 16);
    glVertex3f(-60, -180, 16);
    glEnd();

    glBegin(GL_POLYGON);        //belakang
    glColor3f(0.72, 0.51, 0);
    glVertex3f(-60, -121, -109);
    glVertex3f(-86, -121, -109);
    glVertex3f(-86, -180, -109);
    glVertex3f(-60, -180, -109);
    glEnd();

    glBegin(GL_POLYGON);        //kanan
    glColor3f(0.92, 0.64, 0);
    glVertex3f(-60, -121, 16);
    glVertex3f(-60, -121, -109);
    glVertex3f(-60, -180, -109);
    glVertex3f(-60, -180, 16);
    glEnd();

    glBegin(GL_POLYGON);        //kiri
    glColor3f(1, 0.74, 0.14);
    glVertex3f(-86, -121, 16);
    glVertex3f(-86, -121, -109);
    glVertex3f(-86, -180, -109);
    glVertex3f(-86, -180, 16);
    glEnd();

    float listx = 0, listy = 0, listz = 0;
    for (int i = 0; i <= 1; i++)        //perulangan list depan belakang
    {
        for (int j = 0; j <= 2; j++)
        {
            glPushMatrix();
            glTranslatef(0, listy, listz);
            listputih1();
            glPopMatrix();

            listy -= 18;
        }
        listy = 0;
        listz -= 126;
    }
    listy = 0;
    for (int i = 0; i <= 1; i++)        //perulangan list kanan kiri
    {
        for (int j = 0; j <= 2; j++)
        {
            glPushMatrix();
            glTranslatef(listx, listy, 0);
            listputih2();
            glPopMatrix();

            listy -= 18;
        }
        listy = 0;
        listx -= 26.5;
    }
    glBegin(GL_POLYGON);        //base jendela
    glColor3f(0.9, 0.63, 0);
    glVertex3f(-66, -121, 39);
    glVertex3f(-65, -121, 16.5);
    glVertex3f(-65, -180, 16.5);
    glVertex3f(-66, -180, 39);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.9, 0.63, 0);
    glVertex3f(-79, -121, 39);
    glVertex3f(-81, -121, 16.5);
    glVertex3f(-81, -180, 16.5);
    glVertex3f(-79, -180, 39);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.92, 0.64, 0);
    glVertex3f(-70, -121, 61.5);
    glVertex3f(-66, -121, 39);
    glVertex3f(-66, -180, 39);
    glVertex3f(-70, -180, 61.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.92, 0.64, 0);
    glVertex3f(-76, -121, 61.5);
    glVertex3f(-79, -121, 39);
    glVertex3f(-79, -180, 39);
    glVertex3f(-76, -180, 61.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(1, 0.7, 0);
    glVertex3f(-70, -121, 61.5);
    glVertex3f(-76, -121, 61.5);
    glVertex3f(-76, -180, 61.5);
    glVertex3f(-70, -180, 61.5);
    glEnd();

    //sekat base jendela
    glPushMatrix();
    glTranslatef(-73, -119, -1);
    glColor3f(0.97, 0.47, 0.07);
    glScalef(3, 2.5, 65);
    glutSolidCube(2);
    glPopMatrix();

    glBegin(GL_POLYGON);
    glColor3f(0.97, 0.47, 0.07);
    glVertex3f(-70, -116.5, 64);
    glVertex3f(-65.5, -116.5, 39.5);
    glVertex3f(-65.5, -121.5, 39.5);
    glVertex3f(-70, -121.5, 64);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.97, 0.47, 0.07);
    glVertex3f(-70, -116.5, 64);
    glVertex3f(-65.5, -116.5, 39.5);
    glVertex3f(-66, -116, 39.5);
    glVertex3f(-70.5, -116, 64);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.97, 0.47, 0.07);
    glVertex3f(-70, -121.5, 64);
    glVertex3f(-65.5, -121.5, 39.5);
    glVertex3f(-66, -121.5, 39.5);
    glVertex3f(-70.5, -121.5, 64);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.97, 0.47, 0.07);
    glVertex3f(-65.5, -116.5, 39.5);
    glVertex3f(-64.5, -116.5, 16.5);
    glVertex3f(-64.5, -121.5, 16.5);
    glVertex3f(-65.5, -121.5, 39.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.97, 0.47, 0.07);
    glVertex3f(-66, -116, 39.5);
    glVertex3f(-65, -116, 16.5);
    glVertex3f(-64.5, -121.5, 16.5);
    glVertex3f(-65.5, -121.5, 39.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.97, 0.47, 0.07);
    glVertex3f(-66, -121.5, 39.5);
    glVertex3f(-65, -121.5, 16.5);
    glVertex3f(-64.5, -121.5, 16.5);
    glVertex3f(-65.5, -121.5, 39.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.97, 0.47, 0.07);
    glVertex3f(-79.5, -116.5, 39);
    glVertex3f(-81.5, -116.5, 16.5);
    glVertex3f(-81.5, -121.5, 16.5);
    glVertex3f(-79.5, -121.5, 39);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.97, 0.47, 0.07);
    glVertex3f(-79.5, -116.5, 39);
    glVertex3f(-81.5, -116.5, 16.5);
    glVertex3f(-80, -116.5, 16.5);
    glVertex3f(-78, -116.5, 39);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.97, 0.47, 0.07);
    glVertex3f(-79.5, -121.5, 39);
    glVertex3f(-81.5, -121.5, 16.5);
    glVertex3f(-80, -121.5, 16.5);
    glVertex3f(-78, -121.5, 39);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.97, 0.47, 0.07);
    glVertex3f(-76, -116.5, 64);
    glVertex3f(-79.5, -116.5, 39);
    glVertex3f(-79.5, -121.5, 39);
    glVertex3f(-76, -121.5, 64);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.97, 0.47, 0.07);
    glVertex3f(-76, -116.5, 64);
    glVertex3f(-79.5, -116.5, 39);
    glVertex3f(-79, -116, 39);
    glVertex3f(-75.5, -116, 64);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.97, 0.47, 0.07);
    glVertex3f(-76, -121.5, 64);
    glVertex3f(-79.5, -121.5, 39);
    glVertex3f(-79, -121.5, 39);
    glVertex3f(-75.5, -121.5, 64);
    glEnd();

    glBegin(GL_POLYGON);        //kaca
    glColor3f(0.6, 0.6, 1);
    glVertex3f(-65.7, -129.5, 36.5);
    glVertex3f(-64.7, -129.5, 19.5);
    glVertex3f(-64.7, -171.5, 19.5);
    glVertex3f(-65.7, -171.5, 36.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.6, 0.6, 1);
    glVertex3f(-79.5, -129.5, 36.5);
    glVertex3f(-81, -129.5, 19.5);
    glVertex3f(-81, -171.5, 19.5);
    glVertex3f(-79.5, -171.5, 36.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.6, 0.6, 1);
    glVertex3f(-69.5, -129.5, 59.5);
    glVertex3f(-66, -129.5, 39);
    glVertex3f(-66, -171.5, 39);
    glVertex3f(-69.5, -171.5, 59.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.6, 0.6, 1);
    glVertex3f(-76.5, -129.5, 59.5);
    glVertex3f(-79, -129.5, 39);
    glVertex3f(-79, -171.5, 39);
    glVertex3f(-76.5, -171.5, 59.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.6, 0.6, 1);
    glVertex3f(-70.5, -129.5, 61.7);
    glVertex3f(-75.5, -129.5, 61.7);
    glVertex3f(-75.5, -171.5, 61.7);
    glVertex3f(-70.5, -171.5, 61.7);
    glEnd();

    glPushMatrix();        //list kaca 1
    glTranslatef(0, 0, 0);
    listkaca();
    glPopMatrix();

    //papan tulis
    glPushMatrix();        //papantulis
    glScalef(0.3, 1, 1);
    glTranslatef(-262.9, -162, 33);
    papantulis();
    glPopMatrix();
}
void alasbangunankiri()
{
    glBegin(GL_POLYGON);        //depan
    glColor3f(0.7, 0.8, 0.8);
    glVertex3f(-60, -180, 16);
    glVertex3f(-86, -180, 16);
    glVertex3f(-86, -191, 16);
    glVertex3f(-60, -191, 16);
    glEnd();

    glBegin(GL_POLYGON);        //belakang
    glColor3f(0.58, 0.64, 0.64);
    glVertex3f(-60, -180, -109);
    glVertex3f(-86, -180, -109);
    glVertex3f(-86, -191, -109);
    glVertex3f(-60, -191, -109);
    glEnd();

    glBegin(GL_POLYGON);        //kanan
    glColor3f(0.64, 0.73, 0.73);
    glVertex3f(-60, -180, 16);
    glVertex3f(-60, -180, -109);
    glVertex3f(-60, -191, -109);
    glVertex3f(-60, -191, 16);
    glEnd();

    glBegin(GL_POLYGON);        //kiri
    glColor3f(0.64, 0.73, 0.73);
    glVertex3f(-86, -180, 16);
    glVertex3f(-86, -180, -109);
    glVertex3f(-86, -191, -109);
    glVertex3f(-86, -191, 16);
    glEnd();

    glBegin(GL_POLYGON); //alas base jendela
    glColor3f(0.64, 0.73, 0.73);
    glVertex3f(-66, -180, 39);
    glVertex3f(-65, -180, 16.5);
    glVertex3f(-65, -191, 16.5);
    glVertex3f(-66, -191, 39);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.64, 0.73, 0.73);
    glVertex3f(-79, -180, 39);
    glVertex3f(-81, -180, 16.5);
    glVertex3f(-81, -191, 16.5);
    glVertex3f(-79, -191, 39);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.67, 0.75, 0.75);
    glVertex3f(-70, -180, 61.5);
    glVertex3f(-66, -180, 39);
    glVertex3f(-66, -191, 39);
    glVertex3f(-70, -191, 61.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.67, 0.75, 0.75);
    glVertex3f(-76, -180, 61.5);
    glVertex3f(-79, -180, 39);
    glVertex3f(-79, -191, 39);
    glVertex3f(-76, -191, 61.5);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3f(0.7, 0.8, 0.8);
    glVertex3f(-70, -180, 61.5);
    glVertex3f(-76, -180, 61.5);
    glVertex3f(-76, -191, 61.5);
    glVertex3f(-70, -191, 61.5);
    glEnd();
}
void FULLSETBANGUNANKIRI()
{
    glPushMatrix();     //alas bangunan kiri
    glTranslatef(0, 0, 0);
    alasbangunankiri();
    glPopMatrix();

    glPushMatrix();     //bangunan kiri 1
    glTranslatef(0, 0, 0);
    bangunankiri();
    glPopMatrix();

    glPushMatrix();     //meja kursi lt 1
    glTranslatef(0, 0, 0);
    mejakursi();
    glPopMatrix();

    glPushMatrix();     //meja kursi lt 2
    glTranslatef(0, 73.5, 0);
    mejakursi();
    glPopMatrix();

    glPushMatrix();     //sekat bangunan
    glTranslatef(-73, -119, -46.5);
    glColor3f(0.97, 0.47, 0.07);
    glScalef(14, 2.5, 65);
    glutSolidCube(2);
    glPopMatrix();

    glPushMatrix();     //sekat bangunan
    glTranslatef(-73, -55.5, -46.5);
    glColor3f(0.97, 0.47, 0.07);
    glScalef(14, 2.5, 65);
    glutSolidCube(2);
    glPopMatrix();

    glPushMatrix();        //bangunan kiri 2
    glTranslatef(0, 63, 0);
    bangunankiri();
    glPopMatrix();

    glPushMatrix();        //atas bangunan
    glTranslatef(0, 0, 0);
    atasbangunan();
    glPopMatrix();

    int xlist = 0, zlist = 0, zlistdep = 0;

    for (int i = 0; i <= 1; i++)        //list kanan kiri atas bangunan
    {
        for (int j = 0; j <= 12; j++)
        {
            glPushMatrix();
            glTranslatef(xlist, 0, zlist);
            listatasbangunan();
            glPopMatrix();

            zlist -= 10;
        }
        glPushMatrix();         //list atas panjang kanan kiri
        glTranslatef(xlist, 0, 0);
        listataspanjang();
        glPopMatrix();

        glPushMatrix();         //list atas panjang kanan kiri
        glTranslatef(xlist, -9.8, 0);
        listataspanjang();
        glPopMatrix();

        glPushMatrix();         //list atas panjang depan belakang
        glTranslatef(0, 0, zlistdep);
        listataspanjangdepan();
        glPopMatrix();

        glPushMatrix();
        glTranslatef(0, -9.8, zlistdep);
        listataspanjangdepan();
        glPopMatrix();

        zlist = 0;
        xlist -= 26;

        zlistdep -= 126;
    }

    glPushMatrix();         //segitiga cover depan
    glTranslatef(0, 0, 0);
    coversegitiga();
    glPopMatrix();

    glPushMatrix();             //jendela atas
    glTranslatef(0, 133.5, -45);
    jendelaatas();
    glPopMatrix();

    glPushMatrix();         //segitiga cover belakang
    glTranslatef(0, 0, -125.5);
    coversegitiga();
    glPopMatrix();

    glPushMatrix();         //atap semua
    glTranslatef(0, 0, 0);
    ataptotal();
    glPopMatrix();
}
void bangunanbelakang()
{
    glPushMatrix();         //bangunan belakang 1
    glColor3f(1, 0.7, 0);
    glTranslatef(-43.5, -195, -192);
    glRotatef(90, -1, 0, 0);
    glScalef(1.2, 4.4, 0.1);
    gluCylinder(gluNewQuadric(), 10, 10, 2000, 8, 10);
    glPopMatrix();

    glPushMatrix();         //sekat 1
    glColor3f(0.3, 0.3, 0.3);
    glTranslatef(-43.5, 1.5, -192);
    glRotatef(90, -1, 0, 0);
    glScalef(0.23, -0.97, 0.5);
    glutSolidTorus(12, 50, 8, 8);
    glPopMatrix();

    glPushMatrix();         //bangunan belakang 2
    glColor3f(1, 0.7, 0);
    glTranslatef(-43.5, 7.25, -192);
    glRotatef(90, -1, 0, 0);
    glScalef(1.25, 4.54, 0.1);
    gluCylinder(gluNewQuadric(), 10, 10, 500, 8, 10);
    glPopMatrix();

    glPushMatrix();         //sekat 2
    glColor3f(0.3, 0.3, 0.3);
    glTranslatef(-43.5, 62.5, -192);
    glRotatef(90, -1, 0, 0);
    glScalef(0.23, -0.97, 0.5);
    glutSolidTorus(12, 50, 8, 8);
    glPopMatrix();

    glPushMatrix();         //bangunan belakang 3 (pagar)
    glColor3f(0.3, 0.3, 0.3);
    glTranslatef(-43.5, 57, -192);
    glRotatef(90, -1, 0, 0);
    glScalef(1.44, 6.15, 0.1);
    gluCylinder(gluNewQuadric(), 10, 10, 150, 8, 10);
    glPopMatrix();

    glPushMatrix();             //tombak atas pagar 1
    glTranslatef(-58.1, -67.71, -201.3);
    glScalef(-0.1, 1, -0.5);
    tombakatassegitiga();
    glPopMatrix();

    glPushMatrix();             //tombak atas pagar 2
    glTranslatef(-53.6, -67.71, -242.4);
    glScalef(-0.1, 1, -0.5);
    tombakatassegitiga();
    glPopMatrix();

    glPushMatrix();             //tombak atas pagar 3
    glTranslatef(-34.7, -67.71, -157.6);
    glScalef(-0.1, 1, -0.5);
    tombakatassegitiga();
    glPopMatrix();

    glPushMatrix();             //tombak atas pagar 4
    glTranslatef(-30.2, -67.71, -198.7);
    glScalef(-0.1, 1, -0.5);
    tombakatassegitiga();
    glPopMatrix();

    glPushMatrix();             //tombak atas pagar 5
    glTranslatef(-53.8, -67.71, -156.6);
    glScalef(-0.1, 1, -0.5);
    tombakatassegitiga();
    glPopMatrix();

    glPushMatrix();             //tombak atas pagar 6
    glTranslatef(-44.2, -67.71, -140.2);
    glScalef(-0.1, 1, -0.5);
    tombakatassegitiga();
    glPopMatrix();

    glPushMatrix();             //tombak atas pagar 7
    glTranslatef(-43.9, -67.71, -258.3);
    glScalef(-0.1, 1, -0.5);
    tombakatassegitiga();
    glPopMatrix();

    glPushMatrix();             //tombak atas pagar 7
    glTranslatef(-34.1, -71.41, -240.5);
    glScalef(-0.1, 1, -0.5);
    tombakatassegitiga();
    glPopMatrix();

    glPushMatrix();         //bangunan belakang 4
    glColor3f(0.6, 0.6, 1.0);
    glTranslatef(-43.5, 56, -192);
    glRotatef(90, -1, 0, 0);
    glScalef(0.98, 3.82, 0.1);
    gluCylinder(gluNewQuadric(), 10, 10, 500, 8, 10);
    glPopMatrix();

    glPushMatrix();         //sekat 3
    glColor3f(0.3, 0.3, 0.3);
    glTranslatef(-43.5, 109.5, -192);
    glRotatef(90, -1, 0, 0);
    glScalef(0.19, -0.68, 0.5);
    glutSolidTorus(12, 50, 8, 8);
    glPopMatrix();

    glPushMatrix();             //atap belakang 1
    glColor3f(0.53, 0.64, 0.56);
    glTranslatef(-43.5, 119.5, -192);
    glScalef(-0.18, 0.66, 0.72);
    glRotatef(90.0f, -1.0f, 0.0f, 0.0f);
    glutSolidTorus(10, 50, 6, 20);
    glPopMatrix();

    glPushMatrix();         //bangunan belakang 5
    glColor3f(0.6, 0.6, 1.0);
    glTranslatef(-43.5, 99.5, -192);
    glRotatef(90, -1, 0, 0);
    glScalef(0.82, 3.04, 0.09);
    gluCylinder(gluNewQuadric(), 10, 10, 500, 8, 10);
    glPopMatrix();

    glPushMatrix();             //atap belakang 2
    glColor3f(0.53, 0.64, 0.56);
    glTranslatef(-43.5, 148.5, -192);
    glScalef(-0.14, 0.42, 0.51);
    glRotatef(90.0f, -1.0f, 0.0f, 0.0f);
    glutSolidTorus(10, 50, 6, 20);
    glPopMatrix();

    glPushMatrix();         //bangunan belakang 6
    glColor3f(0.6, 0.6, 1.0);
    glTranslatef(-43.5, 143, -192);
    glRotatef(90, -1, 0, 0);
    glScalef(0.62, 2.47, 0.09);
    gluCylinder(gluNewQuadric(), 10, 10, 500, 8, 10);
    glPopMatrix();

    glPushMatrix();             //atap belakang 3
    glColor3f(0.53, 0.64, 0.56);
    glTranslatef(-43.5, 192, -192);
    glScalef(-0.12, 0.42, 0.51);
    glRotatef(90.0f, -1.0f, 0.0f, 0.0f);
    glutSolidTorus(10, 50, 6, 20);
    glPopMatrix();

    glPushMatrix();             //atap end
    glColor3f(0.78, 0.84, 0.8);
    glTranslatef(-43.5, 199, -192);
    glScalef(0.1, 0.3, 0.4);
    glutSolidSphere(60, 360, 360);
    glPopMatrix();

    glPushMatrix();             //tombak atas atap end
    glTranslatef(-46.6, 54.09, -205);
    glScalef(-0.52, 1.03, -0.97);
    tombakatassegitiga();
    glPopMatrix();

    glBegin(GL_POLYGON);            //kaca bangunan belakang
    glColor3f(0.6, 0.6, 1);
    glVertex3f(-42, 53.5, -148.8);
    glVertex3f(-36, 53.5, -157.5);
    glVertex3f(-36, 11.5, -157.5);
    glVertex3f(-42, 11.5, -148.8);
    glEnd();

    glBegin(GL_POLYGON);            //list kaca bangunan belakang
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-41.9, 34.4, -147.8);
    glVertex3f(-35.8, 34.4, -157.5);
    glVertex3f(-35.8, 32.4, -157.5);
    glVertex3f(-41.9, 32.4, -147.8);
    glEnd();

    glBegin(GL_POLYGON);            //list kaca bangunan belakang
    glColor3f(1, 0.6, 0.5);
    glVertex3f(-39.4, 53.6, -152.6);
    glVertex3f(-38.9, 54.4, -153.2);
    glVertex3f(-38.9, 12.4, -153.2);
    glVertex3f(-39.4, 11.6, -152.6);
    glEnd();

}

void depansebelahkiri()
{
    glTranslatef(55, -165, 0);
    ///Bangunan mepet
        ///DEPAN SEBELAH KIRI
        //Pondasi
    glPushMatrix();
    glTranslatef(-160, -20, -75);
    glColor3f(0.7,0.8,0.8);
    glScalef(40,3,40);
    glutSolidCube(4);
    glPopMatrix();

    ///Jendela Depan Kiri Bawah
    for (int tiang = -236; tiang <=-47; tiang+=38)
    {
        glPushMatrix();
        glTranslatef(tiang,20,-38.5);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7,50,7);
        glutSolidCube(1);
        glPopMatrix();
    }
    //kaca 1
    glPushMatrix();
    glTranslatef(-160,20,-39);
    glColor3f(0.6, 0.6, 1.0);
    glScalef(156,50,7);
    glutSolidCube(1);
    glPopMatrix();

    //frame kaca 1
    glPushMatrix();
    glTranslatef(-160,5,-37.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 2
    glPushMatrix();
    glTranslatef(-160,15,-37.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 3
    glPushMatrix();
    glTranslatef(-160,25,-37.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 4
    glPushMatrix();
    glTranslatef(-160,35,-37.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 5
    glPushMatrix();
    glTranslatef(-160,45,-37.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();

    //frame kaca keatas 1
    glPushMatrix();
    glTranslatef(-222,20,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 2
    glPushMatrix();
    glTranslatef(-212,20,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 3
    glPushMatrix();
    glTranslatef(-183,20,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 4
    glPushMatrix();
    glTranslatef(-173,20,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 5
    glPushMatrix();
    glTranslatef(-144,20,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 6
    glPushMatrix();
    glTranslatef(-134,20,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 7
    glPushMatrix();
    glTranslatef(-107,20,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 8
    glPushMatrix();
    glTranslatef(-97,20,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();

        //tembok
    glPushMatrix();
    glTranslatef(-160, 45, -88);
    glColor3f(1.0, 0.7, 0.0);
    glScalef(39.8,36,-26);
    glutSolidCube(4);
    glPopMatrix();

    ///atap
        //Genteng Depan
    float gentengy = 118;
    for (int gntngz=-46;gntngz>=-88;gntngz-=1)
      {
        glPushMatrix();
        glTranslatef(-160,gentengy,gntngz);
        glColor3f(0.5,0.8,1.0);
        glScalef(160,1,5);
        glutSolidCube(1);
        glPopMatrix();
        gentengy+=1.5;
      }
        //Genteng Belakang
    float gentengyx = 118;
    for (int gentengzx=-135;gentengzx<=-93;gentengzx+=1)
      {
        glPushMatrix();
        glTranslatef(-160,gentengyx,gentengzx);
        glColor3f(0.5,0.8,1.0);
        glScalef(160,1,5);
        glutSolidCube(1);
        glPopMatrix();
        gentengyx+=1.5;
      }
    //Dekorasi
       ///1
    glPushMatrix();
    glTranslatef(-130, 140, -45);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(8, 10, 5);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-130, 148.5, -45);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(4, 4, 4);
    glutSolidSphere(1, 36, 36);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-130,140,-45);
    glRotatef(-90, 1.0, 0.0, 0.0);
    glColor3f(0.9, 0.9, 0.9);
    glScalef(2, 2, 30);
    glutSolidCone(1, 1, 16, 16);
    glPopMatrix();

        ///2
    glPushMatrix();
    glTranslatef(-170, 140, -45);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(8, 10, 5);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-170, 148.5, -45);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(4, 4, 4);
    glutSolidSphere(1, 36, 36);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-170,140,-45);
    glRotatef(-90, 1.0, 0.0, 0.0);
    glColor3f(0.9, 0.9, 0.9);
    glScalef(2, 2, 30);
    glutSolidCone(1, 1, 16, 16);
    glPopMatrix();

        ///3
    glPushMatrix();
    glTranslatef(-210, 140, -45);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(8, 10, 5);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-210, 148.5, -45);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(4, 4, 4);
    glutSolidSphere(1, 36, 36);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-210,140,-45);
    glRotatef(-90, 1.0, 0.0, 0.0);
    glColor3f(0.9, 0.9, 0.9);
    glScalef(2, 2, 30);
    glutSolidCone(1, 1, 16, 16);
    glPopMatrix();

    ///Pagar Atas
    for (int pgr=-237;pgr<=-80;pgr+=2)
        {
            glPushMatrix();
            glTranslatef(pgr,122.5,-35);
            glColor3f(1.0, 1.0, 1.0);
            glScalef(1,10,2);
            glutSolidCube(1);
            glPopMatrix();
        }

    glPushMatrix();
    glTranslatef(-146.9,127.5,-35);
    glColor3f(1.0, 1.0, 1.0);
    glScalef(160,1,1);
    glutSolidCube(1);
    glPopMatrix();

    ///Tembok Belakang
    glPushMatrix();
    glTranslatef(-160.5,15.5,-148);
    glColor3f(0.7,0.6,0.6);
    glScalef(155,59.5,14);
    glutSolidCube(1);
    glPopMatrix();

    ///Jendela Belakang kanan
    for (int tiang = -236; tiang <=-47; tiang+=38)
    {
        glPushMatrix();
        glTranslatef(tiang,90,-138.5);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7,50,7);
        glutSolidCube(1);
        glPopMatrix();
    }
    //kaca 1
    glPushMatrix();
    glTranslatef(-160,90,-137.5);
    glColor3f(0.6, 0.6, 1.0);
    glScalef(156,50,7);
    glutSolidCube(1);
    glPopMatrix();

    //frame kaca 1
    glPushMatrix();
    glTranslatef(-160,75,-139.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 2
    glPushMatrix();
    glTranslatef(-160,85,-139.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 3
    glPushMatrix();
    glTranslatef(-160,95,-139.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 4
    glPushMatrix();
    glTranslatef(-160,105,-139.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 5
    glPushMatrix();
    glTranslatef(-160,115,-139.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();

    //frame kaca keatas 1
    glPushMatrix();
    glTranslatef(-222,90,-139.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 2
    glPushMatrix();
    glTranslatef(-212,90,-139.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 3
    glPushMatrix();
    glTranslatef(-183,90,-139.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 4
    glPushMatrix();
    glTranslatef(-173,90,-139.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 5
    glPushMatrix();
    glTranslatef(-144,90,-139.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 6
    glPushMatrix();
    glTranslatef(-134,90,-139.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 7
    glPushMatrix();
    glTranslatef(-107,90,-139.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 8
    glPushMatrix();
    glTranslatef(-97,90,-139.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();

    ///Jendela depan kiri
    for (int tiang = -236; tiang <=-47; tiang+=38)
    {
        glPushMatrix();
        glTranslatef(tiang,90,-38.5);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7,50,7);
        glutSolidCube(1);
        glPopMatrix();
    }
    //kaca 1
    glPushMatrix();
    glTranslatef(-160,90,-39);
    glColor3f(0.6, 0.6, 1.0);
    glScalef(156,50,7);
    glutSolidCube(1);
    glPopMatrix();

    //frame kaca 1
    glPushMatrix();
    glTranslatef(-160,75,-37.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 2
    glPushMatrix();
    glTranslatef(-160,85,-37.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 3
    glPushMatrix();
    glTranslatef(-160,95,-37.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 4
    glPushMatrix();
    glTranslatef(-160,105,-37.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 5
    glPushMatrix();
    glTranslatef(-160,115,-37.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(145,1,5);
    glutSolidCube(1);
    glPopMatrix();

    //frame kaca keatas 1
    glPushMatrix();
    glTranslatef(-222,90,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 2
    glPushMatrix();
    glTranslatef(-212,90,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 3
    glPushMatrix();
    glTranslatef(-183,90,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 4
    glPushMatrix();
    glTranslatef(-173,90,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 5
    glPushMatrix();
    glTranslatef(-144,90,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 6
    glPushMatrix();
    glTranslatef(-134,90,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 7
    glPushMatrix();
    glTranslatef(-107,90,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 8
    glPushMatrix();
    glTranslatef(-97,90,-37.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1,50,5);
    glutSolidCube(1);
    glPopMatrix();
}

void display()
{

    glEnable(GL_DEPTH_TEST);
    glEnable(GL_LIGHTING);
    glEnable(GL_LIGHT0);
    glEnable(GL_NORMALIZE);
    glEnable(GL_COLOR_MATERIAL);

    glClearColor(0.0, 1.0, 1, 0);
    glLoadIdentity();
    glTranslatef(0, 0, -200);
    glRotatef(sudut, xx1, yy1, zz1);
    glRotatef(xrot, 1.0, 0.0, 0.0);
	glRotatef(yrot, 0.0, 1.0, 0.0);
	glTranslatef(xxx1, yyy1, zzz1);
    glEnable(GL_DEPTH_TEST);
    glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
    GLfloat ambientLight[] = { 0.3f, 0.3f, 0.3f, 1.0f };
    glLightModelfv(GL_LIGHT_MODEL_AMBIENT, ambientLight);

    GLfloat lightColor[] = { 0.7f, 0.7f, 0.7f, 1.0f };
    GLfloat lightPos[] = { -2 * BOX_SIZE, BOX_SIZE, 4 * BOX_SIZE, 1.0f };
    glLightfv(GL_LIGHT0, GL_DIFFUSE, lightColor);
    glLightfv(GL_LIGHT0, GL_POSITION, lightPos);

    ///Genteng Panjang 1
    float gntngy = 135;
    for (int gntngz=-30;gntngz>=-82.5;gntngz-=1)
      {
        glPushMatrix();
        glTranslatef(20,gntngy,gntngz);
        glColor3f(0.5,0.8,1.0);
        glScalef(200,1,5);
        glutSolidCube(1);
        glPopMatrix();
        gntngy+=1.5;
      }
    ///Genteng Panjang 2
    float gntngyx = 135;
    for (int gntngzx=-135;gntngzx<=-82.5;gntngzx+=1)
      {
        glPushMatrix();
        glTranslatef(20,gntngyx,gntngzx);
        glColor3f(0.5,0.8,1.0);
        glScalef(200,1,5);
        glutSolidCube(1);
        glPopMatrix();
        gntngyx+=1.5;
      }
    ///Genteng Pendek 1
    float gntngyy = 135;
    float gntngyy3 = 80;
    for (int gntngzy=-20;gntngzy<=0;gntngzy+=1)
      {
        glPushMatrix();
        glTranslatef(gntngzy,gntngyy,-80);
        glColor3f(0.3,0.6,0.8);
        glScalef(gntngyy3,1,115);
        glutSolidCube(1);
        glPopMatrix();
        gntngyy+=3;
        gntngyy3-=1.1;
      }
    ///Genteng Pendek 2
    float gntngyy1 = 135;
    float gntngyy2 = 80;
    for (int gntngzy1=60;gntngzy1>=40;gntngzy1-=1)
      {
        glPushMatrix();
        glTranslatef(gntngzy1,gntngyy1,-80);
        glColor3f(0.3,0.6,0.8);
        glScalef(gntngyy2,1,115);
        glutSolidCube(1);
        glPopMatrix();
        gntngyy1+=3;
        gntngyy2-=1.1;
      }

    ///kubah kecil kanan
    for(int kubah = 100; kubah<=140; kubah+=1)
    {
        glPushMatrix();
        glTranslatef(123,kubah,-30);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7,7, 7);
        glutSolidSphere(1, 36, 36);
        glPopMatrix();
    }

    ///lingkaran kubah kanan
    glPushMatrix();
    glTranslatef(123,155,-30);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(4, 4, 4);
    glutSolidSphere(1, 36, 36);
    glPopMatrix();

    ///cone kubah kanan
    glPushMatrix();
    glTranslatef(123,140,-30);
    glRotatef(-90, 1.0, 0.0, 0.0);
    glColor3f(0.9, 0.9, 0.9);
    glScalef(4, 4, 30);
    glutSolidCone(1, 1, 16, 16);
    glPopMatrix();

    ///kubah kecil kiri
    for(int kubah = 100; kubah<=140; kubah+=1)
    {
        glPushMatrix();
        glTranslatef(-83,kubah,-30);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7,7, 7);
        glutSolidSphere(1, 36, 36);
        glPopMatrix();
    }

    ///lingkaran kubah kiri
    glPushMatrix();
    glTranslatef(-83,155,-30);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(4, 4, 4);
    glutSolidSphere(1, 36, 36);
    glPopMatrix();

    ///cone kubah kiri
    glPushMatrix();
    glTranslatef(-83,140,-30);
    glRotatef(-90, 1.0, 0.0, 0.0);
    glColor3f(0.9, 0.9, 0.9);
    glScalef(4, 4, 30);
    glutSolidCone(1, 1, 16, 16);
    glPopMatrix();

    ///Tanah
    glPushMatrix();
    glTranslatef(20, -27, -40);
    glColor3f(0.5, 0.8, 0.2);
    glScalef(450, 1, 150);
    glutSolidCube(4);
    glPopMatrix();

    ///Lantai
    glPushMatrix();
    glTranslatef(20, -20, -75);
    glColor3f(0.7, 0.8, 0.8);
    glScalef(50, 3, 40);
    glutSolidCube(4);
    glPopMatrix();

    ///Tangga
    float pgrU = -25;
    float pgrU1 = 1;
    for (int pgr2 = 25; pgr2 >= 7; pgr2 -= 1.1)
    {
        glPushMatrix();
        glTranslatef(20, pgrU, pgr2);
        glColor3f(0.7, 0.8, 0.8);
        glScalef(90, pgrU1, 5);
        glutSolidCube(1);
        glPopMatrix();
        pgrU += 0.5;
        pgrU1 += 1;
    }

    ///tangga kanan
    float pgr = -25;
    float pgr1 = 1;

    for (int pg2 = 40; pg2 >= 22; pg2 -= 1.1)
    {
        glPushMatrix();
        glRotatef(15, 0.0, 1.0, 0.0);
        glTranslatef(85, pgr, pg2);
        glColor3f(0.7, 0.8, 0.8);
        glScalef(60, pgr1, 5);
        glutSolidCube(1);
        glPopMatrix();
        pgr += 0.5;
        pgr1 += 1;
    }

    ///tangga kiri
    float pg = -25;
    float pg1 = 1;

    for (int p2 = 30; p2 >= 12; p2 -= 1.1)
    {
        glPushMatrix();
        glRotatef(345, 0.0, 1.0, 0.0);
        glTranslatef(-45, pg, p2);
        glColor3f(0.7, 0.8, 0.8);
        glScalef(60, pg1, 5);
        glutSolidCube(1);
        glPopMatrix();
        pg += 0.5;
        pg1 += 1;
    }

    ///tiang
    for (int tiang = -73; tiang <= 100; tiang += 38)
    {
        glPushMatrix();
        glTranslatef(tiang, 10, -2);
        glColor3f(0.7, 0.6, 0.6);
        glScalef(7, 50, 7);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(113, 10, -2);
    glColor3f(0.7, 0.6, 0.6);
    glScalef(7, 50, 7);
    glutSolidCube(1);
    glPopMatrix();

    ///tiang (dalam)
    for (int tiang = -73; tiang <= 100; tiang += 38)
    {
        glPushMatrix();
        glTranslatef(tiang, 10, -35);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 50, 7);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(113, 10, -35);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(7, 50, 7);
    glutSolidCube(1);
    glPopMatrix();

    ///tiang ke dalam (kiri)
    glPushMatrix();
    glTranslatef(-73, 10, -35);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(7, 50, 7);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-73, -10, -35);
    glColor3f(1.0, 1.0, 1.0);
    glScalef(13, 10, 13);
    glutSolidCube(1);
    glPopMatrix();

    float bataxx = 4;
    for (int batayy = 35; batayy <= 45; batayy += 1)
    {
        glPushMatrix();
        glRotatef(90, 0.0, 1.0, 0.0);
        glTranslatef(bataxx, batayy, -72.5);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        bataxx += 1.5;
    }

    float bataxx1 = 20;
    for (int batayy1 = 45; batayy1 >= 35; batayy1 -= 1)
    {
        glPushMatrix();
        glRotatef(90, 0.0, 1.0, 0.0);
        glTranslatef(bataxx1, batayy1, -73);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        bataxx1 += 1.5;
    }

    ///tiang ke dalam (kanan)
    glPushMatrix();
    glTranslatef(113, 10, -35);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(7, 50, 7);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(113, -10, -35);
    glColor3f(1.0, 1.0, 1.0);
    glScalef(13, 10, 13);
    glutSolidCube(1);
    glPopMatrix();

    float bataxxx = 4;
    for (int batayyy = 35; batayyy <= 45; batayyy += 1)
    {
        glPushMatrix();
        glRotatef(90, 0.0, 1.0, 0.0);
        glTranslatef(bataxxx, batayyy, 113);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        bataxxx += 1.5;
    }

    float bataxxx1 = 20;
    for (int batayyy1 = 45; batayyy1 >= 35; batayyy1 -= 1)
    {
        glPushMatrix();
        glRotatef(90, 0.0, 1.0, 0.0);
        glTranslatef(bataxxx1, batayyy1, 113);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        bataxxx1 += 1.5;
    }

    ///bawah tiang
    for (int tiangb = -73; tiangb <= 100; tiangb += 38)
    {
        glPushMatrix();
        glTranslatef(tiangb, -10, -2);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(13, 10, 13);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(113, -10, -2);
    glColor3f(1.0, 1.0, 1.0);
    glScalef(13, 10, 13);
    glutSolidCube(1);
    glPopMatrix();

    ///bawah tiang (dalam)
    for (int tiangb = -73; tiangb <= 100; tiangb += 38)
    {
        glPushMatrix();
        glTranslatef(tiangb, -10, -35);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(13, 10, 13);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(113, -10, -35);
    glColor3f(1.0, 1.0, 1.0);
    glScalef(13, 10, 13);
    glutSolidCube(1);
    glPopMatrix();

    ///atas tiang
    glPushMatrix();
    glTranslatef(20, 55, -2);
    glColor3f(1.0, 0.7, 0.0);
    glScalef(200, 20, 7);
    glutSolidCube(1);
    glPopMatrix();

    ///Atas Stengah Lingkaran
    float batax = -71;
    for (int batay = 35; batay <= 45; batay += 1)
    {
        glPushMatrix();
        glTranslatef(batax, batay, -2);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax += 1.5;
    }

    float batax1 = -52;
    for (int batay1 = 45; batay1 >= 35; batay1 -= 1)
    {
        glPushMatrix();
        glTranslatef(batax1, batay1, -2);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax1 += 1.5;
    }

    float batax2 = -33;
    for (int batay2 = 35; batay2 <= 45; batay2 += 1)
    {
        glPushMatrix();
        glTranslatef(batax2, batay2, -2);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax2 += 1.5;
    }

    float batax12 = -14;
    for (int batay12 = 45; batay12 >= 35; batay12 -= 1)
    {
        glPushMatrix();
        glTranslatef(batax12, batay12, -2);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax12 += 1.5;
    }

    float batax3 = 5;
    for (int batay3 = 35; batay3 <= 45; batay3 += 1)
    {
        glPushMatrix();
        glTranslatef(batax3, batay3, -2);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax3 += 1.5;
    }

    float batax13 = 24;
    for (int batay13 = 45; batay13 >= 35; batay13 -= 1)
    {
        glPushMatrix();
        glTranslatef(batax13, batay13, -2);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax13 += 1.5;
    }

    float batax4 = 43;
    for (int batay4 = 35; batay4 <= 45; batay4 += 1)
    {
        glPushMatrix();
        glTranslatef(batax4, batay4, -2);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax4 += 1.5;
    }

    float batax14 = 62;
    for (int batay14 = 45; batay14 >= 35; batay14 -= 1)
    {
        glPushMatrix();
        glTranslatef(batax14, batay14, -2);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax14 += 1.5;
    }

    float batax5 = 81;
    for (int batay5 = 35; batay5 <= 45; batay5 += 1)
    {
        glPushMatrix();
        glTranslatef(batax5, batay5, -2);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax5 += 1.5;
    }

    float batax15 = 96;
    for (int batay15 = 45; batay15 >= 35; batay15 -= 1)
    {
        glPushMatrix();
        glTranslatef(batax15, batay15, -2);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax15 += 1.5;
    }

    ///Atas Stengah Lingkaran (dalam)
    float bataxy = -71;
    for (int batayx = 35; batayx <= 45; batayx += 1)
    {
        glPushMatrix();
        glTranslatef(bataxy, batayx, -35);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        bataxy += 1.5;
    }

    float batax1y = -52;
    for (int batay1x = 45; batay1x >= 35; batay1x -= 1)
    {
        glPushMatrix();
        glTranslatef(batax1y, batay1x, -35);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax1y += 1.5;
    }

    float batax2y = -33;
    for (int batay2x = 35; batay2x <= 45; batay2x += 1)
    {
        glPushMatrix();
        glTranslatef(batax2y, batay2x, -35);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax2y += 1.5;
    }

    float batax12y = -14;
    for (int batay12x = 45; batay12x >= 35; batay12x -= 1)
    {
        glPushMatrix();
        glTranslatef(batax12y, batay12x, -35);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax12y += 1.5;
    }

    float batax3y = 5;
    for (int batay3x = 35; batay3x <= 45; batay3x += 1)
    {
        glPushMatrix();
        glTranslatef(batax3y, batay3x, -35);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax3y += 1.5;
    }

    float batax13y = 24;
    for (int batay13x = 45; batay13x >= 35; batay13x -= 1)
    {
        glPushMatrix();
        glTranslatef(batax13y, batay13x, -35);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax13y += 1.5;
    }

    float batax4y = 43;
    for (int batay4x = 35; batay4x <= 45; batay4x += 1)
    {
        glPushMatrix();
        glTranslatef(batax4y, batay4x, -35);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax4y += 1.5;
    }

    float batax14y = 62;
    for (int batay14x = 45; batay14x >= 35; batay14x -= 1)
    {
        glPushMatrix();
        glTranslatef(batax14y, batay14x, -35);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax14y += 1.5;
    }

    float batax5y = 81;
    for (int batay5x = 35; batay5x <= 45; batay5x += 1)
    {
        glPushMatrix();
        glTranslatef(batax5y, batay5x, -35);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax5y += 1.5;
    }

    float batax15y = 96;
    for (int batay15x = 45; batay15x >= 35; batay15x -= 1)
    {
        glPushMatrix();
        glTranslatef(batax15y, batay15x, -35);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 2, 7);
        glutSolidCube(1);
        glPopMatrix();
        batax15y += 1.5;
    }

    ///lantai balkon
    glPushMatrix();
    glTranslatef(20, 55, 11);
    glColor3f(0.8, 0.7, 0.7);
    glScalef(125, 2, 20);
    glutSolidCube(1);
    glPopMatrix();

    ///depan balkon
    glPushMatrix();
    glTranslatef(20, 60, 20);
    glColor3f(0.8, 0.7, 0.7);
    glScalef(125, 8, 2);
    glutSolidCube(1);
    glPopMatrix();

    ///samping balkon
    //kanan
    glPushMatrix();
    glTranslatef(82, 58, 10);
    glColor3f(0.8, 0.7, 0.7);
    glScalef(2, 5, 18);
    glutSolidCube(1);
    glPopMatrix();
    //kiri
    glPushMatrix();
    glTranslatef(-42, 58, 10);
    glColor3f(0.8, 0.7, 0.7);
    glScalef(2, 5, 18);
    glutSolidCube(1);
    glPopMatrix();

    ///bawah balkon
    for (int tiangb = -35; tiangb <= 100; tiangb += 38)
    {
        glPushMatrix();
        glTranslatef(tiangb, 45, 8);
        glRotatef(45.0, 1.0, 0.0, 0);
        glColor3f(0.8, 0.7, 0.7);
        glScalef(6, 30, 6);
        glutSolidCube(1);
        glPopMatrix();
    }

    ///gagang pintu
    glPushMatrix();
    glTranslatef(18, 10, -35);
    glColor3f(0.2, 0.2, 0.2);
    glScalef(1.5, 1.5, 1.5);
    glutSolidSphere(1, 36, 36);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(26, 10, -35);
    glColor3f(0.2, 0.2, 0.2);
    glScalef(1.5, 1.5, 1.5);
    glutSolidSphere(1, 36, 36);
    glPopMatrix();

    ///pintu
    for (int pintu = -55; pintu <= 100; pintu += 30)
    {
        glPushMatrix();
        glTranslatef(pintu, 10, -37);
        glColor3f(0.6, 0.6, 1.0);
        glScalef(35, 70, 2);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(-53.5, 10, -35);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(1, 65, 1);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-16, 10, -35);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(1, 65, 1);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(22, 10, -34);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(1, 65, 1);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(60, 10, -34.5);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(1, 65, 1);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(96, 10, -34.5);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(1, 65, 1);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(20, 30, -34.5);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(180, 1, 1);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(20, 15, -34.5);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(180, 1, 1);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(20, 0, -34.5);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(180, 1, 1);
    glutSolidCube(1);
    glPopMatrix();

    ///pagar bawah kiri
    for (int pgr = -65; pgr <= -42; pgr += 2)
    {
        glPushMatrix();
        glTranslatef(pgr, -10, 0);
        glColor3f(0.3, 0.3, 0.3);
        glScalef(1, 10, 2);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(-54, -5, 0);
    glColor3f(0.3, 0.3, 0.3);
    glScalef(23, 1, 1);
    glutSolidCube(1);
    glPopMatrix();

    ///pagar bawah kiri (rotate)
    for (int pgr = 30; pgr >= 7; pgr -= 2)
    {
        glPushMatrix();
        glRotatef(90, 0.0, 1.0, 0.0);
        glTranslatef(pgr, -10, -73);
        glColor3f(0.3, 0.3, 0.3);
        glScalef(1, 10, 2);
        glutSolidCube(1);
        glPopMatrix();
    }

    ///tembok kiri
    glPushMatrix();
    glTranslatef(-74, 15.5, -95);
    glColor3f(0.7, 0.6, 0.6);
    glScalef(12, 59.5, 120);
    glutSolidCube(1);
    glPopMatrix();

    ///tembok kanan
    glPushMatrix();
    glTranslatef(114, 15.5, -95);
    glColor3f(0.7, 0.6, 0.6);
    glScalef(12, 59.5, 120);
    glutSolidCube(1);
    glPopMatrix();

    ///tembok belakang
    glPushMatrix();
    glTranslatef(20, 15.5, -148);
    glColor3f(0.7, 0.6, 0.6);
    glScalef(176, 59.5, 14);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-73, -5, -19);
    glRotatef(90, 0.0, 1.0, 0.0);
    glColor3f(0.3, 0.3, 0.3);
    glScalef(20, 1, 1);
    glutSolidCube(1);
    glPopMatrix();

    ///pagar bawah kanan
    for (int pgr = 85; pgr <= 105; pgr += 2)
    {
        glPushMatrix();
        glTranslatef(pgr, -10, 0);
        glColor3f(0.3, 0.3, 0.3);
        glScalef(1, 10, 2);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(96, -5, 0);
    glColor3f(0.3, 0.3, 0.3);
    glScalef(19, 1, 1);
    glutSolidCube(1);
    glPopMatrix();

    ///pagar bawah kanan (rotate)
    for (int pgr = 30; pgr >= 7; pgr -= 2)
    {
        glPushMatrix();
        glRotatef(90, 0.0, 1.0, 0.0);
        glTranslatef(pgr, -10, 113);
        glColor3f(0.3, 0.3, 0.3);
        glScalef(1, 10, 2);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(113, -5, -19);
    glRotatef(90, 0.0, 1.0, 0.0);
    glColor3f(0.3, 0.3, 0.3);
    glScalef(20, 1, 1);
    glutSolidCube(1);
    glPopMatrix();

    ///Lantai 2
    glPushMatrix();
    glTranslatef(20, 85, -70);
    glColor3f(1.0, 0.7, 0.0);;
    glScalef(50, 20, 33);
    glutSolidCube(4);
    glPopMatrix();

    ///Atasnya Lantai 2
    glPushMatrix();
    glTranslatef(20, 130, -75);
    glColor3f(1.0, 0.9, 0.0);;
    glScalef(200, 10, 122);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-77.5, 130, -9);
    glColor3f(0.3, 0.3, 0.3);;
    glScalef(5, 10, 10);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-70, 130, -6.5);
    glColor3f(0.3, 0.3, 0.3);;
    glScalef(10, 10, 5);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(17.5, 130, -6.5);
    glColor3f(0.3, 0.3, 0.3);;
    glScalef(120, 10, 5);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(108, 130, -6.5);
    glColor3f(0.3, 0.3, 0.3);;
    glScalef(15, 10, 5);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(117.5, 130, -9);
    glColor3f(0.3, 0.3, 0.3);;
    glScalef(5, 10, 10);
    glutSolidCube(1);
    glPopMatrix();

    ///pagar atasnya lantai 2
    for (int pgr = -65; pgr <= -42; pgr += 2)
    {
        glPushMatrix();
        glTranslatef(pgr, 130, -5);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(1, 10, 2);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(-54, 135, -5);
    glColor3f(1.0, 1.0, 1.0);
    glScalef(23, 1, 1);
    glutSolidCube(1);
    glPopMatrix();

    ///pagar atasnya lantai 2 (kanan)
    for (int pgr = 100; pgr >= 77; pgr -= 2)
    {
        glPushMatrix();
        glTranslatef(pgr, 130, -5);
        glColor3f(1.0, 1.0, 1.0);
        glScalef(1, 10, 2);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(90, 135, -5);
    glColor3f(1.0, 1.0, 1.0);
    glScalef(23, 1, 1);
    glutSolidCube(1);
    glPopMatrix();

    ///Jendela
    for (int tiang = -73; tiang <= 100; tiang += 38)
    {
        glPushMatrix();
        glTranslatef(tiang, 90, -5);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 50, 7);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(113, 90, -5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(7, 50, 7);
    glutSolidCube(1);
    glPopMatrix();

    //kaca 1
    glPushMatrix();
    glTranslatef(20, 90, -5.5);
    glColor3f(0.6, 0.6, 1.0);
    glScalef(180, 50, 7);
    glutSolidCube(1);
    glPopMatrix();

    //frame kaca 1
    glPushMatrix();
    glTranslatef(20, 75, -4);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 2
    glPushMatrix();
    glTranslatef(20, 85, -4);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 3
    glPushMatrix();
    glTranslatef(20, 95, -4);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 4
    glPushMatrix();
    glTranslatef(20, 105, -4);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 5
    glPushMatrix();
    glTranslatef(20, 115, -4);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 1
    glPushMatrix();
    glTranslatef(-59, 90, -4);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 2
    glPushMatrix();
    glTranslatef(-49, 90, -4);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 3
    glPushMatrix();
    glTranslatef(-20, 90, -4);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 4
    glPushMatrix();
    glTranslatef(-10, 90, -4);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 5
    glPushMatrix();
    glTranslatef(17, 90, -4);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 6
    glPushMatrix();
    glTranslatef(27, 90, -4);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 7
    glPushMatrix();
    glTranslatef(55, 90, -4);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 8
    glPushMatrix();
    glTranslatef(65, 90, -4);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 9
    glPushMatrix();
    glTranslatef(91, 90, -4);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 10
    glPushMatrix();
    glTranslatef(101, 90, -4);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();

    ///Jendela Belakang
    for (int tiang = -73; tiang <= 100; tiang += 38)
    {
        glPushMatrix();
        glTranslatef(tiang, 90, -134);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 50, 7);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(113, 90, -134);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(7, 50, 7);
    glutSolidCube(1);
    glPopMatrix();

    //kaca 1
    glPushMatrix();
    glTranslatef(20, 90, -133.5);
    glColor3f(0.6, 0.6, 1.0);
    glScalef(180, 50, 7);
    glutSolidCube(1);
    glPopMatrix();

    //frame kaca 1
    glPushMatrix();
    glTranslatef(20, 75, -135);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 2
    glPushMatrix();
    glTranslatef(20, 85, -135);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 3
    glPushMatrix();
    glTranslatef(20, 95, -135);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 4
    glPushMatrix();
    glTranslatef(20, 105, -135);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 5
    glPushMatrix();
    glTranslatef(20, 115, -135);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 1
    glPushMatrix();
    glTranslatef(-59, 90, -135);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 2
    glPushMatrix();
    glTranslatef(-49, 90, -135);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 3
    glPushMatrix();
    glTranslatef(-20, 90, -135);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 4
    glPushMatrix();
    glTranslatef(-10, 90, -135);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 5
    glPushMatrix();
    glTranslatef(17, 90, -135);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 6
    glPushMatrix();
    glTranslatef(27, 90, -135);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 7
    glPushMatrix();
    glTranslatef(55, 90, -135);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 8
    glPushMatrix();
    glTranslatef(65, 90, -135);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 9
    glPushMatrix();
    glTranslatef(91, 90, -135);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 10
    glPushMatrix();
    glTranslatef(101, 90, -135);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();

    ///atas tiang belakang
    glPushMatrix();
    glTranslatef(20, 55, -138);
    glColor3f(1.0, 0.7, 0.0);
    glScalef(200, 20, 7);
    glutSolidCube(1);
    glPopMatrix();

    ///Papan tulis
    glPushMatrix();
    glTranslatef(20, 15, -139.5);
    glColor3f(0.0, 0.0, 0.0);
    glScalef(13, 8, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(20, 15, -139);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(12.5, 7.5, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    ///Laptop
    glPushMatrix();
    glTranslatef(-45, 5, -120);
    glColor3f(0.0, 0.0, 0.0);
    glScalef(2, 1.7, 0.2);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-45, 5, -119.5);
    glColor3f(0.8, 0.8, 0.8);
    glScalef(1.7, 1.4, 0.3);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-45, 2.5, -117);
    glColor3f(0.0, 0.0, 0.0);
    glScalef(1.7, 0.2, 2);
    glutSolidCube(4);
    glPopMatrix();

    ///Lampu
    glPushMatrix();
    glTranslatef(90, -4, -125);
    glColor3f(0.5, 0.5, 0.0);
    glScalef(0.5, 10, 0.5);
    glutSolidCube(2);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(90, 8, -125);
    glColor3f(1, 1, 1);
    glScalef(3, 4, 4);
    glutSolidSphere(1, 36, 36);
    glPopMatrix();

    ///Meja
    glPushMatrix();
    glTranslatef(-45, 0, -125);
    glColor3f(0.5, 0.5, 0.0);
    glScalef(9, 1, 7);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-58, -6, -115);
    glColor3f(0.5, 0.5, 0.0);
    glScalef(0.5, 4, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-58, -6, -135);
    glColor3f(0.5, 0.5, 0.0);
    glScalef(0.5, 4, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-32, -6, -115);
    glColor3f(0.5, 0.5, 0.0);
    glScalef(0.5, 4, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-32, -6, -135);
    glColor3f(0.5, 0.5, 0.0);
    glScalef(0.5, 4, 0.5);
    glutSolidCube(4);
    glPopMatrix();

    ///Jendela Belakang (bawah)
    for (int tiang = -73; tiang <= 100; tiang += 38)
    {
        glPushMatrix();
        glTranslatef(tiang, 21, -158);
        glColor3f(0.9, 0.5, 0.0);
        glScalef(7, 70, 7);
        glutSolidCube(1);
        glPopMatrix();
    }

    glPushMatrix();
    glTranslatef(113, 21, -158);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(7, 70, 7);
    glutSolidCube(1);
    glPopMatrix();

    //kaca 1
    glPushMatrix();
    glTranslatef(20, 18, -152.5);
    glColor3f(0.6, 0.6, 1.0);
    glScalef(180, 50, 7);
    glutSolidCube(1);
    glPopMatrix();

    //frame kaca 1
    glPushMatrix();
    glTranslatef(20, 3, -155.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 2
    glPushMatrix();
    glTranslatef(20, 13, -155.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 3
    glPushMatrix();
    glTranslatef(20, 23, -155.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 4
    glPushMatrix();
    glTranslatef(20, 33, -155.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 5
    glPushMatrix();
    glTranslatef(20, 43, -155.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 6
    glPushMatrix();
    glTranslatef(20, -7, -155.5);
    glColor3f(1.0, 0.6, 0.5);
    glScalef(180, 1, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 1
    glPushMatrix();
    glTranslatef(-59, 18, -155.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 2
    glPushMatrix();
    glTranslatef(-49, 18, -155.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 3
    glPushMatrix();
    glTranslatef(-20, 18, -155.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 4
    glPushMatrix();
    glTranslatef(-10, 18, -155.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 5
    glPushMatrix();
    glTranslatef(17, 18, -155.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 6
    glPushMatrix();
    glTranslatef(27, 18, -155.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 7
    glPushMatrix();
    glTranslatef(55, 18, -155.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 8
    glPushMatrix();
    glTranslatef(65, 18, -155.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 9
    glPushMatrix();
    glTranslatef(91, 18, -155.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca keatas 10
    glPushMatrix();
    glTranslatef(101, 18, -155.5);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(1, 50, 5);
    glutSolidCube(1);
    glPopMatrix();

    ///lantai 3
    glPushMatrix();
    glTranslatef(20, 155, -25);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(65, 50, 20);
    glutSolidCube(1);
    glPopMatrix();
    //tiang kecil 1
    glPushMatrix();
    glTranslatef(-6.5, 160, -15);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(3, 60, 5);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-6.5, 190, -15);
    glRotatef(-90.0, 1, 0, 0);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(3, 3, 10);
    glutSolidCone(1, 1, 16, 16);
    glPopMatrix();
    //tiang kecil 2
    glPushMatrix();
    glTranslatef(11, 160, -15);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(3, 60, 5);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(11, 190, -15);
    glRotatef(-90.0, 1, 0, 0);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(3, 3, 10);
    glutSolidCone(1, 1, 16, 16);
    glPopMatrix();
    //tiang kecil 3
    glPushMatrix();
    glTranslatef(28.5, 160, -15);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(3, 60, 5);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(28.5, 190, -15);
    glRotatef(-90.0, 1, 0, 0);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(3, 3, 10);
    glutSolidCone(1, 1, 16, 16);
    glPopMatrix();
    //tiang kecil 4
    glPushMatrix();
    glTranslatef(46, 160, -15);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(3, 60, 5);
    glutSolidCube(1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(46, 190, -15);
    glRotatef(-90.0, 1, 0, 0);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(3, 3, 10);
    glutSolidCone(1, 1, 16, 16);
    glPopMatrix();
    ///lantai4
    glPushMatrix();
    glTranslatef(20, 190, -28);
    glColor3f(0.9, 0.5, 0.0);
    glScalef(30, 30, 15);
    glutSolidCube(1);
    glPopMatrix();
    //kaca
    glPushMatrix();
    glTranslatef(20, 150, -15);
    glColor3f(0.6, 0.6, 1.0);
    glScalef(10, 20, 1);
    glutSolidCube(1);
    glPopMatrix();

    //frame kaca 1
    glPushMatrix();
    glTranslatef(20, 150, -14.5);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(1, 20, 1);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 2
    glPushMatrix();
    glTranslatef(15, 150, -14.5);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(1, 20, 1);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 3
    glPushMatrix();
    glTranslatef(25, 150, -14.5);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(1, 20, 1);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 4
    glPushMatrix();
    glTranslatef(20, 140, -14.5);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(10, 1, 1);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 4
    glPushMatrix();
    glTranslatef(20, 150, -14.5);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(10, 1, 1);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca 4
    glPushMatrix();
    glTranslatef(20, 160, -14.5);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(10, 1, 1);
    glutSolidCube(1);
    glPopMatrix();
    //frame kaca segitiga
    glPushMatrix();
    glTranslatef(20, 162, -14.5);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(8, 1, 1);
    glutSolidCube(1);
    glPopMatrix();
    glPushMatrix();
    glTranslatef(20, 164, -14.5);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(6, 1, 1);
    glutSolidCube(1);
    glPopMatrix();
    glTranslatef(20, 166, -14.5);
    glColor3f(0.8, 0.9, 0.9);
    glScalef(4, 1, 1);
    glutSolidCube(1);
    glPopMatrix();

    //-------------------------------bangunan kiri------------------

    glPushMatrix();         //FULLSET BANGUNAN KIRI TINGGAL GESER PINDAH
    glTranslatef(-124, 0, -25);
    FULLSETBANGUNANKIRI();
    glPopMatrix();

    glPushMatrix();         //FULLSET BANGUNAN BELAKANG TINGGAL GESER PINDAH
    glTranslatef(-84, 0, 0);
    bangunanbelakang();
    glPopMatrix();

    glPushMatrix();         //FULLSET BANGUNAN KIRI TINGGAL GESER PINDAH
    glTranslatef(269, 0, -25);
    FULLSETBANGUNANKIRI();
    glPopMatrix();



    depansebelahkiri();

    glTranslatef(154, 165 ,0);
    depansebelahkiri();


    glTranslatef(-105, -165, 0);


    glutSwapBuffers();
}

void keyboard(unsigned char key, int x, int y)
{
    switch (key)
    {
    ///s dan w untuk rotasi depan dan belakang
    case 's':
    case 'S':
        xx1 = 1;
        yy1 = 0;
        zz1 = 0;
        sudut+=-10;
        break;
    case 'w':
    case 'W':
        xx1 = -1;
        yy1 = 0;
        zz1 = 0;
        sudut+=-10;
        break;
    ///a dan d untuk rotasi kiri dan kanan
    case 'd':
    case 'D':
        xx1 = 0;
        yy1 = 1;
        zz1 = 0;
        sudut+=-10;
        break;
    case 'a':
    case 'A':
        xx1 = 0;
        yy1 = -1;
        zz1 = 0;
        sudut+=-10;
        break;
    ///x dan z untuk translate posisi ke kanan dan kiri
    case 'z':
    case 'Z':
        xxx1+=10;
        break;
    case 'x':
    case 'X':
        xxx1+=-10;
        break;
    ///c dan v untuk translate posisi ke atas dan bawah
    case 'v':
    case 'V':
        yyy1+=10;
        break;
    case 'c':
    case 'C':
        yyy1+=-10;
        break;
    ///b dan n untuk translate posisi ke depan dan belakang (zoom in zoom out)
    case 'b':
    case 'B':
        zzz1+=10;
        break;
    case 'n':
    case 'N':
        zzz1+=-10;
        break;
    ///e dan q untuk rotasi dengan poros sumbu z
    case 'e':
    case 'E':
        xx1 = 0;
        yy1 = 0;
        zz1 = 1;
        sudut+=-10;
        break;
    case 'q':
    case 'Q':
        xx1 = 0;
        yy1 = 0;
        zz1 = -1;
        sudut+=-10;
        break;
    case 'i':
        zzz1+=240;
        break;
    case 'I':
        zzz1-=240;
        break;
    case 'u':
        xxx1+=760;
        zzz1+=228;
        break;
    case 'U':
        xxx1-=760;
        zzz1-=228;
        break;
    case 'o':
        xxx1+=-310;
        zzz1+=198;
        break;
    case 'O':
        xxx1-=-310;
        zzz1-=198;
        break;
    }
    glutPostRedisplay();
}

void mouse(int button, int state, int x, int y) {
    if (button == GLUT_LEFT_BUTTON && state == GLUT_DOWN) {
        mouseDown = true;
        xdiff = x - yrot;
        ydiff = -y + xrot;
    }
    else
        mouseDown = false;
}

void mouseMotion(int x, int y) {
    if (mouseDown) {
        yrot = x - xdiff;
        xrot = y + ydiff;
        glutPostRedisplay();
    }
}

int main(int argc, char** argv)
{
    glutInit(&argc, argv);
    glutInitDisplayMode(GLUT_DOUBLE | GLUT_RGB | GLUT_DEPTH);
    glutInitWindowPosition(100, 100);
    glutInitWindowSize(1200, 700);
    glutCreateWindow("TR Asdos");
    glutDisplayFunc(display);
    glutKeyboardFunc(keyboard);
    glutMouseFunc(mouse);
    glutMotionFunc(mouseMotion);
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluPerspective(440.0, 1.5, 1.0, 1000.0);
    glMatrixMode(GL_MODELVIEW);
    glLoadIdentity();
    glutMainLoop();
}
