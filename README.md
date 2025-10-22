
# Coding rules
## Định dạng (Formatting)
---
### Indentation
* Dùng **4 spaces**, không dùng tab.
**Good:**
```cppif (is_valid) {    processData();}```
**Bad:**
```cppif (is_valid){	processData();}```
### Dấu ngoặc (Braces)
* Dấu `{` nằm **cùng dòng với câu lệnh mở**, và `}` xuống dòng riêng.
**Good:**
```cppif (ready) {    start();}```
**Bad:**
```cppif (ready){    start();}```
### Giới hạn độ dài dòng
* Mỗi dòng **không quá 100 ký tự**.
### Khoảng trắng
* Có khoảng trắng sau dấu phẩy, quanh toán tử.
**Good:**
```cppint sum = a + b;process(x, y);```
**Bad:**
```cppint sum=a+b;process(x,y);```

## Đặt tên (Naming Conventions)
---
### Biến và hàm
* **camelCase** cho biến và hàm.
```cppint studentCount;void processInput();```
### Lớp và struct
* **PascalCase** cho class, struct, enum.
```cppclass StudentRecord {    ...};```
### Hằng số
* Dùng `k` + PascalCase.
```cppconst int kMaxStudents = 100;```
### Biến thành viên lớp
* Có hậu tố `_`.
```cppclass Example {private:    int value_;};```

## Cấu trúc tệp (File Structure)
---
* Mỗi file chỉ chứa **một class hoặc nhóm hàm liên quan**.* Sử dụng **#pragma once** trong header.* Thứ tự include:
  1. Thư viện chuẩn (`<iostream>`, `<vector>`)  2. Thư viện bên thứ ba  3. Header nội bộ
**Good:**
```cpp#include <iostream>#include <vector>#include "student.h"```

## Quy tắc viết hàm
---
* Mỗi hàm thực hiện **một nhiệm vụ duy nhất**.* Đặt tên thể hiện **hành động** (động từ đầu tiên).
**Good:**
```cppvoid calculateAverage();void printReport();```
**Bad:**
```cppvoid average();void reportPrint();```
* Nếu hàm dài hơn 40 dòng, nên tách nhỏ.

## Quy tắc về class
---
* Constructor nên **rõ ràng mục đích khởi tạo**.* Ưu tiên **smart pointer (unique_ptr, shared_ptr)** thay vì con trỏ thô.* Tránh để dữ liệu public nếu không cần thiết.
**Good:**
```cppclass Student {public:    explicit Student(std::string name);    void display() const;private:    std::string name_;};```
**Bad:**
```cppclass Student {public:    std::string name;};```

## Comment & tài liệu
---
* Dùng `//` cho chú thích ngắn, `/** ... */` cho mô tả hàm hoặc class.* Comment phải giải thích **tại sao**, không chỉ **cái gì**.
**Good:**
```cpp// Kiểm tra sinh viên đủ điều kiện để tốt nghiệp.if (credits >= kRequiredCredits) {    graduate();}```
**Bad:**
```cpp// if condition trueif (credits >= kRequiredCredits) {    graduate();}```