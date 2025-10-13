# Funtion in C

Các thư viện có trong C và C++: https://cplusplus.com/reference/cstdarg/


## Blogs
- [Differences between `memcpy`/`memmove` and `strcpy` for copying arrays](https://www.notion.so/Differences-between-memcpy-memmove-and-strcpy-for-copying-arrays-13b555493c6080ffbf46e5601ebc8326)


## Dùng hàm
snprintf(dest, size, format, source)
- dest: con trỏ tới buffer
- size: kích thước của chuỗi
- format: định dạng chuỗi
- source: chuỗi đầu vào

strcmp(const char* s1, const char* s2): hàm so sánh

Return
- 0: nếu s1 = s2
- <0: nếu s1 < s2
- >0: nếu s1 > s2

## memset()
Cú pháp
~~~c
void * memset ( void * ptr, int value, size_t num );
~~~
**Tham số:**
- `ptr`: trỏ đến vùng nhớ cần được set.
- `value`: giá trị sử dụng để set các vùng nhớ.
- `num`: số lượng bytes.
