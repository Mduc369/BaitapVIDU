CÁC MỞ RỘNG CỦA C++ SO VỚI C

1. Chú thích

Khái niệm:
Chú thích (comment) là phần nội dung dùng để giải thích chương trình cho người đọc. Trình biên dịch sẽ bỏ qua phần chú thích và không thực hiện nó.

Trong C:
    /* Đây là chú thích */

Trong C++:
    /* Đây là chú thích nhiều dòng */
    // Đây là chú thích một dòng

Ví dụ:

#include <iostream>
using namespace std;

int main() {
    // Khai báo biến a
    int a = 10;

    /*
        In giá trị của a
        ra màn hình
    */
    cout << a;

    return 0;
}

C++ mở rộng thêm kiểu chú thích một dòng bằng //.


2. Nhập / Xuất

Khái niệm:
Nhập là đưa dữ liệu từ bên ngoài vào chương trình.
Xuất là đưa dữ liệu hoặc kết quả từ chương trình ra màn hình.

Trong C thường sử dụng:
    scanf()  → nhập
    printf() → xuất

Trong C++ sử dụng:
    cin  → nhập
    cout → xuất

Ví dụ trong C:

#include <stdio.h>

int main() {
    int a;

    printf("Nhap a: ");
    scanf("%d", &a);

    printf("a = %d", a);

    return 0;
}

Ví dụ trong C++:

#include <iostream>
using namespace std;

int main() {
    int a;

    cout << "Nhap a: ";
    cin >> a;

    cout << "a = " << a;

    return 0;
}

Nếu nhập:
    10

Kết quả:
    a = 10


3. Chuyển đổi kiểu dữ liệu

Khái niệm:
Chuyển đổi kiểu dữ liệu là việc chuyển một giá trị từ kiểu dữ liệu này sang kiểu dữ liệu khác.

Ví dụ:
    float → int
    int → float
    char → int

Trong C thường dùng:

float a = 3.14;
int b = (int)a;

Kết quả:
    b = 3

Trong C++ có thể sử dụng:

float a = 3.14;
int b = static_cast<int>(a);

Kết quả:
    b = 3

Ví dụ khác:

int a = 5;
float b = static_cast<float>(a);

Kết quả:
    b = 5.0

C++ vẫn cho phép cách ép kiểu của C:

int b = (int)a;

nhưng có thêm cách viết rõ ràng hơn:

int b = static_cast<int>(a);


4. Vị trí khai báo biến

Khái niệm:
Khai báo biến là việc xác định tên và kiểu dữ liệu của biến trước khi sử dụng biến đó.

Ví dụ:

int a;
float b;
char c;

Trong C theo chuẩn C90, biến thường phải được khai báo ở đầu khối lệnh, trước các câu lệnh thực thi.

Ví dụ:

int main() {
    int a;
    int b;
    int sum;

    a = 10;
    b = 20;

    sum = a + b;

    printf("%d", sum);

    return 0;
}

Trong C++, có thể khai báo biến tại vị trí cần sử dụng.

Ví dụ:

int main() {
    int a = 10;

    cout << a;

    int b = 20;

    cout << b;

    return 0;
}

C++ cũng cho phép khai báo biến ngay trong vòng lặp:

for (int i = 0; i < 5; i++) {
    cout << i;
}

Biến i được khai báo ngay trong câu lệnh for và chỉ có phạm vi trong vòng lặp.

      
     
