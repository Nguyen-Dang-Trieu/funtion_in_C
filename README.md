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

### Ví dụ 1
~~~c
#include <stdio.h>
#include <string.h>

int main()
{
  char str[] = "almost every programmer should know memset!";
  memset(str, '-', 6);
  puts(str);
  
  return 0;
}
~~~
**Đầu ra của chương trình:**
~~~
------ every programmer should know memset!
~~~

`memset()` trả về một con trỏ `void*` tới địa chỉ bắt đầu vùng nhớ mà nó vừa điền (tức là giá trị của tham số đầu tiên `ptr`)
### Ví dụ 2
~~~c
#include <stdio.h>
#include <string.h>

int main()
{
  char str[] = "Nice to meet you";
  
  
  void* addr_str = memset(str, '-', 4);
  printf("%s\n", str);
  
  // Địa chỉ bắt đầu vùng nhớ lưu trữ chuỗi
  printf("Địa chỉ bắt đầu của chuỗi str: %p\n", &str);
  
  printf("Địa chỉ của con trỏ addr_str: %p\n", &addr_str);
  printf("Địa chỉ do memset trả về: %p\n", addr_str); 
  
  return 0;
}
~~~
**Đầu ra của chương trình**
~~~
---- to meet you
Địa chỉ bắt đầu của chuỗi str: 0x7fff31570a20
Địa chỉ của con trỏ addr_str: 0x7fff31570a18
Địa chỉ do memset trả về: 0x7fff31570a20
~~~

## Sự khác nhau giữa việc sử dụng `strcpy` vầ `strncpy`
Hai hàm này đều copy một chuỗi từ `src` sang `dst` nhưng chúng khác nhau về hành vi và an toàn.
- `strcpy`: copy toàn bộ chuỗi `src`, bao gồm kí tự `\0` tới buffer dest. Tuy nhiên hàm này không thực hiện bất kì kiểm tra ranh giới nào cho việc copy chuỗi.
  - Nếu buffer src dài hơn buffer dst thì điều này sẽ gây ra buffer overflow.
- `strncpy`: chỉ copy `n` kí tự từ buffer src sang buffer dst. 

## Hàm memcmp
