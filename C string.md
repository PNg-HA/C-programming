Có 2 kiểu chuỗi kí tự trong C++, 1 là kiểu string của C++, 2 là chuỗi kí tự C (C-string).
String của C++ là 1 chuỗi kí tự không kết thúc bằng NULL, còn C-string là chuỗi kí tự kết thúc bằng NULL (NULL-terminated).
NULL (hay còn hiểu là '\0') đứng ở vị trí 0 trong bảng ASCII.
Để phân biệt string của C++ và C-string, xét ví dụ sau:
  *cout << "abc\0def"*;
trình biên dịch (compiler) sẽ hiểu đây là chuỗi C-string và vì thế đọc chuỗi kí tự đến '\0' thì dừng, tức xuất ra: abc.

Nhưng nếu ta khởi tạo biến kiểu string của C++ và in nó:
  *string str = "abc\0def";
	*cout << str;*
trình biên dịch biết str là string của C++, chỉ không đọc '\0' và hiểu đây là khoảng trắng, tức xuất ra: abc def.
