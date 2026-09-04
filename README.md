Các ví dụ về mở rộng trong C++

Ví Dụ 1
#include<iostream.h>
class Dagiac {
protected: 
int Day, Cao;
public:
void GanGiaTri(int a, int b)  {
Day=a;
Cao=b;
}
};
class Tamgiac:public Dagiac {
public:
int Dientich(void) {
return Day*Cao/2;
}
};
class Hcn:public Dagiac {
public:
int Dientich(void) {
return Day*Cao;
}
};
void main() {
Tamgiac A;
Hcn B;
A.GanGiaTri(4,5);
B.GanGiaTri(4,5);
cout<<A.Diẹntich()<<endl<<B.Dientich()<<endl;
}


Ví dụ 2
#include<iostream.h>
class A {
public:
A(){
cout<<"A: khong tham so \n";
}
A(int a) {
cout<<"A: tham so kieu int \n";
}
};
class B:public A{
public:
B(int a) {
cout<<"B: tham so kieu int \n"
}
};
class C:public A{
public:
C(int a) {
cout<<"C: tham so kieu int \n";
}
void main () {
B b1(1);
C c1(1);
}


Ví dụ 3
#include<iosteam.h>
class Dagiac {
protected:
int Day, Caoo;
public:
void GanGiaTri(int a, int b) {
Day=a;
Cao=b;
}
};
class Inmh{
public:
void In(int i){
cout<<i<<endl;
}
};
class Hcn:public Dagiac, public Inmh	{
public:
int Dientich(void)	{
cout<<"Dien tich hinh chu nhat la:";
return (Day*Cao);
}
};
class Tamgiac:public Dagiac, public Inmh	{
public:
int Dientich(void)	{
cout<<"Dien tich tam giac la:";
return (Day*Cao/2);
}
};
void	main()	{
Tamgiac	A;
Hcn	B;
A.GanGiaTri(4,5);
B.GanGiaTri(4,5);
A.In(A.Dientich());
B.In(B.Dientich());
}

Ví dụ 4
#include<iostream.h>
class Dagiac {
protected:
int Day, Cao;
public:
void GanGiaTri(int a, int b) {
Day=a;
Cao=b;
}
};
class Hcn:public Dagiac{
public;
int Dientich(void) {
cout<<"Dien tich hinh chu nhat la: ";
return (Day*cao);
}
};
class Tamgiac:public Dagiac {
public:
int Dientich(void) {
cout<<"Dien tich tam giac la: ";
return (Day*Cao/2);
}
};
void main(){
Tamgiac T;
Hcn H;
Dagiac *D1=&H;
Dagiac *D2=&T;
D1->GanGiatri(4,5);
D2->GanGiaTri(4,5);
cout<<H.Dientich()<<endl;
cout<<T>Dientich()<<endl;
}


Ví dụ 5
#include<iostream.h>
class Dagiac {
protected: 
int Day, Cao;
public:
void GanGiaTri(int a, int b) {
Day=a;
Cao=b;
}
virtual int Dientich(void) {
cout<<"Dien tich duoc tinh trong ham ao:";
return 0;
}
};
claa Hcn:public Dagiac{
public: 
int Dientich(void){
cout<<"Dien tich hinh chu nhat la:";
return (Day*Cao);
}
};
class Tamgiac:public Dagiac{
public:
int Dientich(void){
cout<<"Dien tich tam giac la:";
return (Day*Cao/2);
}
};
void main(){
Dagiac P;
Tamgiac T;
Hcn H;
Dagiac *D1=&H;
Dagiac *D2=&T;
Dagiac *D3=&P;
D1->GanGiaTri(4,5);
D2->GanGiaTri(4,5);
D3->GanGiaTri(4,5);
cout<<D1->Dientich()<<endl;
cout<<D2->Dientich()<<endl;
cout<<D3->Dientich()<<endl;
}


Ví dụ 6
#include<iostream.h>
class Dagiac {
protected:
int Day, Cao;
public:
void GanGiaTri(int a, int b) {
Day=a;
Cao=b;
}
vỉtual int Dientich(void)=0:
};
class Hcn:public Dagiac{
public:
int Dientich(void){
cout<<"Dien tich hinh chu nhat la:";
return (Day*Cao);
}
};
class Tamgiac:public Dagiac{
public:
int Dientich(void){
cout<<"Dien tich hinh chu nhat la:";
return (Day*Cao/2);
}
};
void main(){
Tamgiac T;
Hcn H;
Dagiac *D1=&H;
Dagiac *D2=&T;
D1->GanGiaTri(4,5);
D2->GanGiaTri(4,5);
cout<<D1->Dientich()<<endl;
cout<D2->Dientich()<<endl;
}


Ví dụ 7
#include<iostream.h>
#include<conio.h>
class Dagiac {
protected:
int Day, Cao;
public:
void GanGiaTri(int a, int b) {
Day=a;
Day=b;
}
vỉtual int Dientich(void)=0;
void InKQ(void){
cout<<Dientich()<<endl;
}
};
class Hcn:public Dagiac{
public:
int Dientich(void){
cout<<"Dien tich hinh chu nhat la:";
return(Day*Cao);
}
};
class Tamgiac: public Dagiac {
public:
int Dientich(void) {
cout<<"Dien tich hinh tam giac la:";
return (Day*Cao/2);
}
};
void main(){
Tamgiac T;
Hcn H;
Dagiac *D1=&H;
Dagiac *D2=&T;
clrscr();
D1->GanGiaTri(4,5);
D2->GanGiaTri(4,5);
D1->InKQ();
D2->InKQ();
}
  
