
## 2. Nguyên tắc cơ bản
* **Đọc quan trọng hơn viết:** Code sẽ được đọc nhiều hơn viết. Hãy ưu tiên sự rõ ràng.* **Tính nhất quán:** Trong một nhóm, mọi người phải theo cùng một quy tắc.* **Tối giản nhưng chặt chẽ:** Viết ít hơn, hiểu nhanh hơn, ít lỗi hơn.
---
## 3. Định dạng (Formatting)
### 3.1 Indentation
* Dùng **4 spaces**, không dùng tab.
**Good:**
```cppif (is_valid) {    processData();}```
**Bad:**
```cppif (is_valid){	processData();}```
### 3.2 Dấu ngoặc (Braces)
* Dấu `{` nằm **cùng dòng với câu lệnh mở**, và `}` xuống dòng riêng.
**Good:**
```cppif (ready) {    start();}```
**Bad:**
```cppif (ready){    start();}```
### 3.3 Giới hạn độ dài dòng
* Mỗi dòng **không quá 100 ký tự**.
### 3.4 Khoảng trắng
* Có khoảng trắng sau dấu phẩy, quanh toán tử.
**Good:**
```cppint sum = a + b;process(x, y);```
**Bad:**
```cppint sum=a+b;process(x,y);```
---
## 4. Đặt tên (Naming Conventions)
### 4.1 Biến và hàm
* **camelCase** cho biến và hàm.
```cppint studentCount;void processInput();```
### 4.2 Lớp và struct
* **PascalCase** cho class, struct, enum.
```cppclass StudentRecord {    ...};```
### 4.3 Hằng số
* Dùng `k` + PascalCase.
```cppconst int kMaxStudents = 100;```
### 4.4 Biến thành viên lớp
* Có hậu tố `_`.
```cppclass Example {private:    int value_;};```
---
## 5. Cấu trúc tệp (File Structure)
* Mỗi file chỉ chứa **một class hoặc nhóm hàm liên quan**.* Sử dụng **#pragma once** trong header.* Thứ tự include:
  1. Thư viện chuẩn (`<iostream>`, `<vector>`)  2. Thư viện bên thứ ba  3. Header nội bộ
**Good:**
```cpp#include <iostream>#include <vector>#include "student.h"```
---
## 6. Quy tắc viết hàm
* Mỗi hàm thực hiện **một nhiệm vụ duy nhất**.* Đặt tên thể hiện **hành động** (động từ đầu tiên).
**Good:**
```cppvoid calculateAverage();void printReport();```
**Bad:**
```cppvoid average();void reportPrint();```
* Nếu hàm dài hơn 40 dòng, nên tách nhỏ.
---
## 7. Quy tắc về class
* Constructor nên **rõ ràng mục đích khởi tạo**.* Ưu tiên **smart pointer (unique_ptr, shared_ptr)** thay vì con trỏ thô.* Tránh để dữ liệu public nếu không cần thiết.
**Good:**
```cppclass Student {public:    explicit Student(std::string name);    void display() const;private:    std::string name_;};```
**Bad:**
```cppclass Student {public:    std::string name;};```
---
## 8. Comment & tài liệu
* Dùng `//` cho chú thích ngắn, `/** ... */` cho mô tả hàm hoặc class.* Comment phải giải thích **tại sao**, không chỉ **cái gì**.
**Good:**
```cpp// Kiểm tra sinh viên đủ điều kiện để tốt nghiệp.if (credits >= kRequiredCredits) {    graduate();}```
**Bad:**
```cpp// if condition trueif (credits >= kRequiredCredits) {    graduate();}```
---
## 9. Xử lý lỗi & ngoại lệ
* Tránh dùng `goto`.* Dùng `try-catch` nếu thật sự cần.* Nếu có thể, trả về mã lỗi hoặc dùng `std::optional`.
**Good:**
```cppstd::optional<int> findStudent(const std::string& id);```
**Bad:**
```cppint findStudent(const std::string& id);```
---
## 10. Testing & review
* Mỗi hàm quan trọng nên có **unit test**.* Code review không chỉ để tìm lỗi mà còn để kiểm tra **tuân thủ style**.
---
## 11. Ví dụ tổng hợp
**Good Example:**
```cpp#pragma once#include <iostream>#include <string>
class Student {public:    explicit Student(std::string name, int age)        : name_(std::move(name)), age_(age) {}
    void display() const {        std::cout << name_ << " (" << age_ << ")\n";    }
private:    std::string name_;    int age_;};```
**Bad Example:**
```cpp#include <iostream>#include <string>using namespace std;
class student {public:    string name;    int age;    student(string n, int a) { name = n; age = a; }    void Display() { cout << name << age; }};```
---
## 12. Tổng kết
Tuân thủ quy tắc này giúp nhóm học viết code C++:
* Đẹp, dễ đọc, dễ bảo trì* Dễ teamwork và review* Học được tư duy kỹ thuật chuyên nghiệp
> “Code đẹp là code ai cũng hiểu được, kể cả chính bạn sau ba tháng.”