## The `strdup()` and `strndup()` functions are used to duplicate a string. 
### strdup()  
Syntax : 
~~~c
char *strdup(const char *s);
~~~
This function returns a pointer to a null-terminated byte string, which is a duplicate of the string pointed to by **s**. The memory obtained is done dynamically using `malloc` and hence it can be 
freed using `free()`. It returns a pointer to the duplicated string **s**.

**Example:**
~~~c
// C program to demonstrate strdup()
#include<stdio.h>
#include<string.h>
 
int main()
{
    char source[] = "GeeksForGeeks";
 
    // A copy of source is created dynamically
    // and pointer to copy is returned.
    char* target = strdup(source); 
 
    printf("%s", target);
    return 0;
}
~~~
**Output:**
~~~
GeeksForGeeks
~~~

### strndup() 
Syntax: 
~~~c
char *strndup(const char *s, size_t n);
~~~
This function is similar to `strdup()`, but copies at most `n` bytes. 

**Note:** If s is longer than **n**, then only n bytes are copied, and a NULL (‘\0’) is added at the end.

**Example:**
~~~c
// C program to demonstrate strndup()
#include<stdio.h>
#include<string.h>
 
int main()
{
    char source[] = "GeeksForGeeks";
 
    // 5 bytes of source are copied to a new memory
    // allocated dynamically and pointer to copied
    // memory is returned.
    char* target = strndup(source, 5);
 
    printf("%s", target);
    return 0;
}
~~~
**Output:**
~~~
Geeks
~~~
