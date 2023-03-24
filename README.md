# libft, ft_printf & get_next_line

Library-42 is a collective name for the three projects i made at school:

### **libft**
During this project we needed to recode simple but handy functions of the C standard library as well as some other utility functions. Because of that we learned a lot about how those functions internally worked instead of just blindly relaining on them. We would be using this library during the rest of the cursus.
The following funcitons we made were:

| function | description |
|---------:|------------:|
|isalpha   |this function checks if the given char is a letter |
|isdigit   |this function checks if the given char is a digit |
|isalnum   |this function checks if the given char is a letter or a digit |
|isascii   |this function checks if the given char is a ascii char |
|isprint   |this function checks if the given char is a printable char |
|strlen    |this function returns the length of the given string |
|toupper   |this function converts the given char to uppercase |
|tolower   |this function converts the given char to lowercase |
|bzero     |this function erases the data in the n bytes of the memory starting at the location pointed to by s, by writing zeros (bytes containing '\0') to that area |
|memset    |this function fills the first n bytes of the memory area pointed to by s with the constant byte c |
|memcpy    |this function copies n bytes from memory area src to memory area dest |
|memmove   |this function copies n bytes from memory area src to memory area dest |
|memchr    |this function locates the first occurrence of c (converted to an unsigned char) in string s |
|memcmp    |this function compares the first n bytes (each interpreted as unsigned char) of the memory areas s1 and s2 |
|strlcpy   |this function copies up to size - 1 characters from the NUL-terminated string src to dst, NUL-terminating the result |
|strlcat   |this function appends the NUL-terminated string src to the end of dst |
|strchr    |this function locates the first occurrence of c (converted to a char) in string s |
|strrchr   |this function locates the last occurrence of c (converted to a char) in string s |
|strnstr   |this function locates the first occurrence of the null-terminated string little in the string big, where not more than len characters are searched |
|strncmp   |this function compares not more than n characters. Because strncmp() is designed for comparing strings rather than binary data, characters that appear after a `\0' character are not compared 
|atoi      |this function converts the initial portion of the string pointed to by str to int representation |
|calloc    |this function allocates memory for an array of nmemb elements of size bytes each and returns a pointer to the allocated memory |
|strdup    |this function returns a pointer to a new string which is a duplicate of the string s |
|substr    |this function returns a substring from the string s |
|strjoin   |this function concatenates s1 and s2 |
|strtrim   |this function returns a copy of s1 with the characters specified in set removed from the beginning and the end of the string |
|split     |this function splits s using the character c as a delimiter |
|itoa      |this function allocates (with malloc(3)) and returns a string representing the integer received as an argument |
|putnbr_fd |this function outputs the integer n to the given file descriptor |
|strmapi   |this function applies the function f to each character of the string passed as argument to create a new string (with malloc(3)) resulting from successive applications of f |
striteri  |this function applies the function f to each character of the string passed as argument, and passing its index as first argument. Each character is passed by address to f to be modified if necessary |
|putchar_fd|this function outputs the character c to the given file descriptor |
|putstr_fd |this function outputs the string s to the given file descriptor |
|putendl_fd|this function outputs the string s to the given file descriptor, followed by a newline |
|lstnew    |this function allocates (with malloc(3)) and returns a new element. The variable 'content' is initialized with the value of the parameter 'content'. The variable 'next' is initialized to NULL |
|lstadd_front|this function adds the element 'new' at the beginning of the list |
|lstsize   |this function counts the number of elements in a list |
|lstlast   |this function returns the last element of the list |
|lstadd_back|this function adds the element 'new' at the end of the list |
|lstdelone |this function takes as a parameter an element and frees the memory of the element's content using the function 'del' given as a parameter and free the element. The memory of 'next' must not be freed |
|lstclear  |this function deletes and frees the given element and every successor of that element, using the function 'del' and free(3). Finally, the pointer to the list must be set to NULL |
|lstiter   |this function iterates the list 'lst' and applies the function 'f' to the content of each element |
|lstmap    |this function iterates the list 'lst' and applies the function 'f' to the content of each element. Creates a new list resulting of the successive applications of the function 'f'. The 'del' function is used to delete the content of an element if needed |

### **ft_printf**
`ft_printf` is a custom implementation of the `printf` function. During this project we learned and used Variadic functions, including:\
`va_start` `va_arg` `va_list` and `va_end`

**Supported Conversion Specifiers**\
ft_printf supports the following conversion specifiers:

- %c: prints a single character
- %s: prints a string of characters
- %p: prints a pointer address in hexadecimal notation
- %d and %i: print signed decimal integers
- %u: prints unsigned decimal integers
- %x and %X: print hexadecimal integers
- %f: prints floating-point numbers
- %% prints a percent sign

### **get_next_line**

`get_next_line` is a custom function to read a single line from a file descriptor. The function reads and returns the next line in a file, and can be called repeatedly to read multiple lines.

The most complicated part was the memory management. The function dynamically allocates memory for each line of input that it reads. And to avoid memory leaks, it is important to free this memory after it is no longer needed. To do this you use the free function a lot, this takes a pointer to a string buffer that was previously allocated, and frees the memory associated with that buffer.

My own `get_next_line` is a bit complicated to follow because of the unnessasry use of dubble pointers, I hope to simplify the code in the future.
