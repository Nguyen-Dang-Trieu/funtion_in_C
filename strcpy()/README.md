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
