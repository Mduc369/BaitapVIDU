Tham số giá trị mặc định (Default Arguments)
Dùng để gán giá trị sẵn cho các tham số của hàm. Nếu người dùng không truyền giá trị khi gọi hàm, hàm sẽ tự động lấy giá trị mặc định này.
Quy tắc:
Các tham số có giá trị mặc định phải nằm ở cuối cùng trong danh sách tham số (từ phải sang trái).
Nên khai báo giá trị mặc định ở nguyên mẫu hàm (prototype) thay vì ở phần định nghĩa hàm.
Ví dụ:
#include <iostream>
// Hàm có tham số mặc định b = 10, c = 20
void display(int a, int b = 10, int c = 20) {
    std::cout << "a: " << a << ", b: " << b << ", c: " << c << std::endl;
}
int main() {
    display(5);             // b=10, c=20 -> In: a: 5, b: 10, c: 20
    display(5, 15);         // c=20       -> In: a: 5, b: 15, c: 20
    display(5, 15, 25);     // Không lấy mặc định -> In: a: 5, b: 15, c: 25
    return 0;
}
Biến tham chiếu (Reference Variables)
Biến tham chiếu đóng vai trò là một bí danh (alias) cho một biến đã tồn tại. Mọi thay đổi trên biến tham chiếu đều trực tiếp làm thay đổi giá trị của biến gốc.
Đặc điểm:
Phải được khởi tạo ngay khi khai báo.
Không thể chuyển sang tham chiếu tới biến khác sau khi đã khởi tạo.
Thường dùng làm tham số truyền vào hàm (Pass-by-reference) để tối ưu hiệu năng (tránh sao chép dữ liệu) và thay đổi trực tiếp giá trị của biến gốc.
Ví dụ:
#include <iostream>
// Hàm hoán đổi sử dụng biến tham chiếu
void swap(int &x, int &y) {
    int temp = x;
    x = y;
    y = temp;
}
int main() {
    int a = 10;
    int &ref = a; // ref là bí danh của a
    ref = 20; // Thay đổi ref nghĩa là thay đổi a
    std::cout << "a: " << a << std::endl; // In ra 20
    int num1 = 5, num2 = 10;
    swap(num1, num2); // Truyền trực tiếp biến, không cần truyền địa chỉ &num1
    std::cout << "num1: " << num1 << ", num2: " << num2 << std::endl; // In out: 10, 5
    return 0;
}
Chồng hàm (Function Overloading)
Cho phép định nghĩa nhiều hàm cùng tên trong cùng một phạm vi, miễn là chúng khác nhau về số lượng tham số hoặc kiểu dữ liệu của tham số. Trình biên dịch sẽ tự động chọn đúng hàm dựa vào đối số truyền vào.
Lưu ý: Không thể nạp chồng hàm nếu các hàm chỉ khác nhau ở kiểu trả về.
Ví dụ:
#include <iostream>
// Hàm tính diện tích hình vuông
int area(int side) {
    return side * side;
}
// Hàm tính diện tích hình chữ nhật (khác số lượng tham số)
int area(int length, int width) {
    return length * width;
}
// Hàm tính diện tích hình tròn (khác kiểu dữ liệu tham số)
double area(double radius) {
    return 3.14159 * radius * radius;
}
int main() {
    std::cout << "HV: " << area(5) << std::endl;         // Gọi area(int)
    std::cout << "HCN: " << area(4, 6) << std::endl;     // Gọi area(int, int)
    std::cout << "HT: " << area(3.0) << std::endl;       // Gọi area(double)
    return 0;
}
Chồng toán tử (Operator Overloading)
Cho phép tái định nghĩa hành vi của các toán tử có sẵn trong C++ (như +, -, *, ==, <<,...) khi áp dụng trên các kiểu dữ liệu do người dùng tự định nghĩa (như struct hoặc class).
Ví dụ:
#include <iostream>
class Complex {
public:
    double real, imag;
    Complex(double r = 0, double i = 0) : real(r), imag(i) {}
    // Nạp chồng toán tử + để cộng hai số phức
    Complex operator+(const Complex &other) {
        return Complex(real + other.real, imag + other.imag);
    }
    void display() {
        std::cout << real << " + " << imag << "i" << std::endl;
    }
};
int main() {
    Complex c1(2.5, 3.5), c2(1.5, 2.5);
    // Sử dụng toán tử + đã được nạp chồng
    Complex c3 = c1 + c2; 
    c3.display(); // In ra: 4 + 6i
    return 0;
}


Các ví dụ về bài tập cụ thể 
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
  
