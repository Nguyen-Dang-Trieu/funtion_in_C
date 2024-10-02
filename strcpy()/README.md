# Copy Functions
- https://codingbison.com/c/c-string-library-copying-functions.html
~~~c
 char *strcpy(char *dest, const char *src);
 char *strncpy(char *dest, const char *src, size_t n);
 void *memcpy(void *dest, void *src, size_t n); 
 void *memmove(void *dest, void *src, size_t n); 
~~~

## Function strcpy()
The function prototype of `strcpy()` is:
~~~c
char* strcpy(char* destination, const char* source);
~~~
- The strcpy() function copies the string pointed by source (including the null character) to the destination.
- The strcpy() function also returns the copied string.

---
The `strcpy()` function is defined in the `string.h` header file.

`Example`:
~~~c
#include <stdio.h>
#include <string.h>

int main() {
  char str1[20] = "C programming";
  char str2[20];

  // copying str1 to str2
  strcpy(str2, str1);

  puts(str2); // C programming

  return 0;
}
~~~
**Output:**
~~~
C programming
~~~

## Function strncpy()
- https://www.scaler.com/topics/strncpy-in-c/
  
The `strncpy()` function in C is used to copy the specified number of characters from one string to another string contiguously. The function will not modify the source string from which the value is copied.

The header `string.h` must be included to use the library in which the strncpy function is present.

The syntax of the `strncpy()` function according to `C99 standards` is,
~~~c
char* strncpy(char *restrict destination, char *restrict source, size_t size);
~~~

The syntax of the `strncpy()` function before the introduction of `C99 standards` is,
~~~c
char *strncpy(char *destination, const char *source, size_t size);
~~~

Parameters of `strncpy()` Function in C
- The `destination` specifies a pointer that contains the address of the first character of the character array to which the string is to be copied.
- The `source` specifies a pointer that contains the address of the first character of the character array from which the string is to be copied.
- The `size` denotes the number of characters that should be copied from source to destination.
