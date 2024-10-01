## Reference
- https://www.scaler.com/topics/fgets-function-c/
## What is fgets()
Hàm `fgets()` được dùng để đọc 1 chuỗi string từ file or stdin. Sau đó lưu chuỗi đọc được đó vào biến được chỉ đinh.

Hàm `fgets()` tiếp tục đọc dữ liệu đầu vào cho đến khi một trong các điều kiện dươis đây thõa mãn:

- (n-1) characters have been read from the stream. (Số kí tự tối đa)
- a new line character is encountered. (Gặp kí tự xuống dòng `\n`)
- end of file is reached. (Đến khi gặp `EOF`)

`Note:` Mặc dù hàm `fgets()` sẽ ngừng lấy dữ liệu đầu vào khi tìm thấy ký tự xuống dòng `\n` nhưng nó lại thêm ký tự đó vào cuối biến chuỗi của chúng ta.

**Example**:
~~~c
#include <stdio.h>
#include <string.h>

int main()
{
    char buf[10] ="";
    fgets(buf, 10, stdin);
    printf("so luong phan tu: %ld\n", strlen(buf));
    printf("buf: %s\n", buf);
    return 0;
}
~~~
**Output**:
~~~
so luong phan tu: 6
buf: trieu
~~~
Ta thấy được số lượng phần tử ở đây là 6 mặc dù string input: trieu chỉ có 5 kí tự -> Nguyên nhân là kí tự xuống dòng `\n` đã được thêm vào chuỗi: `trieu\n\0`

Để loại bỏ ký tự xuống dòng `\n`, có thể làm như sau:
~~~c
#include <stdio.h>
#include <string.h>

int main() {
    char buffer[100];
    printf("Enter a string: ");
    fgets(buffer, sizeof(buffer), stdin);

    // Kiểm tra và loại bỏ ký tự xuống dòng nếu có
    size_t len = strlen(buffer);
    if (len > 0 && buffer[len-1] == '\n') {
        buffer[len-1] = '\0'; // Thay \n bằng \0
    }

    printf("You entered: %s", buffer);
    return 0;
}

~~~

## Syntax of fgets() Function in C
~~~c
fgets(char *str, int n, FILE *stream)
~~~

In the above syntax, we have
- `char *str`: a pointer to an array of characters where the read values will be stored.
- `int n`: maximum number of characters to be read.
- `FILE *stream`: pointer to the file stream from where the input is to be taken (it can be replaced with stdin when taking input from the standard input ie through the console).

## Return Value of fgets() Function in C
If the reading operation is completed successfully, then the `fgets()` function will return the pointer `str` itself where it stores the input.

If the operation has been unsuccessful, then the `fgets()` function will return a `null` pointer.
- Gặp EOF mà không đọc được ký tự nào.
- Có lỗi trong quá trình đọc dữ liệu từ file.
