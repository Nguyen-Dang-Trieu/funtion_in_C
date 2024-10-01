## Reference
- https://www-geeksforgeeks-org.translate.goog/strcmp-in-c/?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=vi

## Syntax of strcmp() in C
`strcmp(first_str, second_str );`

Note: The reason arguments are taken as const char *instead of only char* is so that the function could not modify the string and also make them applicable for constant strings.

`Example:`
~~~c
#include <stdio.h>

int main()
{
  const char *str1 = "Hello";
  const char *str2 = "World";

  int result = strcmp(str1, str2);
  ...
  do_SomeThing()
  ...
}
~~~

Return: 
- ' =0 ': Khi first_str = second_str
- ' >0 ': Khi first_str > second_str
- ' <0 ': Khi first_str < second_str
