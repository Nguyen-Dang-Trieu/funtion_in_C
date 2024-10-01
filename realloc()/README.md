Trong C, hàm `realloc()` được sử dụng để thay đổi kích thước bộ nhớ đã được cấp phát trước đó bằng hàm `malloc()`, `calloc()`, hoặc `realloc()`. Nó có thể mở rộng hoặc thu nhỏ kích thước của vùng nhớ mà vẫn 
giữ nguyên dữ liệu đã có nếu kích thước mới lớn hơn hoặc bằng kích thước cũ.
~~~c
void* realloc(void* ptr, size_t new_size);
~~~
- `ptr`: Là con trỏ trỏ đến vùng nhớ đã được cấp phát trước đó (bởi `malloc`, `calloc`, hoặc `realloc`).
- `new_size`: Kích thước mới (tính bằng `byte`) cần cấp phát cho vùng nhớ.

Return: 
- Trả về con trỏ trỏ đến vùng nhớ mới được cấp phát có kích thước `new_size`.
- Nếu không cấp phát được, hàm trả về `NULL`.
