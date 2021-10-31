Có 2 kiểu chuỗi kí tự trong C++, 1 là kiểu *string* của C++, 2 là chuỗi kí tự C (*C-string*).

String của C++ là 1 chuỗi kí tự không kết thúc bằng **NULL**, còn C-string là chuỗi kí tự kết thúc bằng **NULL** (NULL-terminated).

**NULL** (hay còn hiểu là '\0') đứng ở vị trí 0 trong bảng ASCII.

Để phân biệt *string* của C++ và *C-string*, xét ví dụ sau:

 	cout << "abc\0def";
  
trình biên dịch (*compiler*) sẽ hiểu đây là chuỗi *C-string* và vì thế đọc chuỗi kí tự đến '\0' thì dừng, tức xuất ra: *abc*.

Nhưng nếu ta khởi tạo biến kiểu string của C++ và in nó:

	string str = "abc\0def";
	cout << str;
	
trình biên dịch biết str là string của C++, chỉ không đọc '\0' và hiểu đây là khoảng trắng, tức xuất ra: *abc def*.
### Bài này xin nói về C-string 

C-string thực chất là 1 mảng, nhưng đặc biệt, vì được hiểu là mảng của những kí tự. Nếu ta khởi tạo 1 biến C-string:
	
	char my_name[] = "John Sweet";

"John Sweet" là 1 chuỗi hằng (const char), có địa chỉ ô nhớ riêng. Còn biến my_name có 1 ô nhớ khác, copy từng phần tử của "John Sweet", và có thể thay đổi được. Con trỏ kiểu char (char* ) trỏ tới "John Sweet" và trỏ tới my_name là 2 trường hợp khác nhau.
	
	char *p_name = my_name;
	p_name[1] = 'O';
	cout << my_name << endl;

Đoạn code trên chỉ thay đổi phần tử thứ 2 của my_name và khi xuất là "JOhn Sweet" của my_name, không thay đổi gì tới con trỏ hằng "John Sweet". Nếu p_name trỏ trực tiếp tới con trỏ hằng "John Sweet" thì chỉ được phép đọc chứ không được thay đổi.
Lệnh cout đối với 1 con trỏ sẽ in ra địa chỉ vùng nhớ, nhưng vì con trỏ chuỗi được hiểu theo 1 nghĩa khác, 
