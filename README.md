4. Vị trí khai báo biến
  Khái niệm: Trong C++, bạn có thể khai báo biến ở bất kỳ vị trí nào trong code trước khi nó được sử dụng (không bắt buộc phải khai báo ở đầu hàm như C cũ).
VD:
#include <isotream.h>
int main() {
    // Các dòng code khác...
    int x = 10; // Khai bao ngay truoc khi dung
    cout << x;
    return 0;
}
5. Kiểu cấu trúc (Struct)
  Khái niệm: Dùng để gom nhóm nhiều biến có kiểu dữ liệu khác nhau thành một thực thể duy nhất.
#include <isotream.h>
typedef struct {
    string ten;
    int tuoi;
}sv;
6. Toán tử phạm vi (::)
  Khái niệm: Dùng để truy xuất biến toàn cục, hàm của một namespace hoặc phương thức/biến tĩnh của một lớp.
VD:
#include <isotream.h>
int x = 10; //Bien toan cung
int main() {
    int x = 5; // bien cuc bo
    cout << ::x; // In ra 10 thay vi 5
}
8. Cấp phát và giải phóng bộ nhớ (new và delete)
Khái niệm: Quản lý bộ nhớ động trong C++ (tương tự malloc và free của C).

Ví dụ:

C++
int *p = new int; // cap phat dong 1 so nguyen
*p = 100;
delete p;         //Giai phong bo nho
8. Hàm Inline (Inline Functions)
  Khái niệm: Gợi ý trình biên dịch thay thế trực tiếp thân hàm vào vị trí gọi hàm nhằm giảm thời gian gọi hàm (tăng tốc độ).
VD:
inline int tinhBinhPhuong(int x) {
    return x * x;
}
