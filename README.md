Quản Lý Điểm Sinh Viên
=========================

**Quản Lý Điểm Sinh Viên** là một chương trình C++ giúp quản lý thông tin sinh viên, môn học, và điểm số.  
Dự án được thiết kế theo nguyên tắc *clean code*, dễ mở rộng và phù hợp cho các nhóm học lập trình C++.

Ví dụ sử dụng:
```cpp
#include "student.h"
#include "subject.h"
#include "score.h"

int main() {
    // Khởi tạo chương trình
    StudentManager system;
    system.run(); // Bắt đầu giao diện quản lý
    return 0;
}
```

## Features

- Quản lý danh sách sinh viên, môn học, và điểm.

- Tìm kiếm, thêm, chỉnh sửa, và xóa thông tin.

- Xuất báo cáo điểm trung bình và thống kê.

- Lưu dữ liệu ra file hoặc đọc dữ liệu từ file.

- Code tuân thủ quy tắc clean code, dễ đọc, dễ bảo trì.


## Installation

Clone dự án từ GitLab hoặc GitHub và biên dịch bằng trình biên dịch C++ (g++, clang++, hoặc MSVC).

```cpp
git clone https://gitlab.com/your-group/student-management-system.git
cd student-management-system
g++ -std=c++17 -o sms main.cpp
./sms
```

## Contribute

Issue Tracker: https://gitlab.com/your-group/student-management-system/issues

Source Code: https://gitlab.com/your-group/student-management-system


Hướng dẫn đóng góp:

1. Fork dự án.


2. Tạo nhánh mới (git checkout -b feature/tên-tính-năng).


3. Commit code của bạn.


4. Gửi merge request.



## Support

Nếu bạn gặp lỗi hoặc muốn góp ý, hãy liên hệ qua email nhóm:
📧 student.management.group@gmail.com

Hoặc tham gia group hỗ trợ:
💬 Google Group

## License

Dự án được phát hành dưới giấy phép MIT License.
