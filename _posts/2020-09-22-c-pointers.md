---
layout: post
title:  "C pointers"
image: assets/images/17.jpg
tags: [ C, programming ]
author: Sumeet Mathpati
github: "https://github.com/sumeetmathpati"
linkedin: "https://linkedin.com/in/sumeet221b"
---

Pointers in C are the way to store address of data/variables present in memory in the new variable. Pointer is also a data type in C. As C uses pass by value, we can use pointers and pass it to the function, that's how we can implement pass by reference in C. So, **pointer is just a memory address.**

## Using pointers

### Declaring pointers

```
int main() {

	char *cptr;
	int *iptr;

	char ch = 'a';
	int i = 1;

	cptr = &ch;
	iptr = &i;

	return 0;
}
```
- To declare pointer to type T, we used syntx:
	- `T *ptr_name;`
- In above code we've created character pointer `cptr` and interger pointer `iptr`.
- We have stored the address of character `ch` integer `i` into respective pointers using `&` operator.
	- When we use `&` as a prefix to any variable it, returns address of that variable.
	- Hence we've stored the address of variable into the their respective pointers.
- We can also initialize pointers while declaring, with:
	- `char *cptr = &ch;`

### Pointers are associated with types

Different pointers are needed to be declared for different types. We can't store address of one data type to the pointer of different data type.

- Hence, follwoing code will generate error,
	- `char *cptr = &i;`
		- Error would be `assignment to ‘char *’ from incompatible pointer type ‘int *’`.

### Accessing data pointer by pointers

We've stores the address of the variables int the pointer, but how can we access data through the pointer?. We have to use `*` operator as a prefix to the pointer, then we will get the data stored in the location pointed by that pointer.

Pinter is just 	

```
int main() {

	char *cptr;
	int *iptr;

	char ch = 'a';
	int i = 1;

	cptr = &ch;
	iptr = &i;

	printf("%p\n", cptr); // Prints the address stored in ch
	printf("%p\n", i); // Prints the address stored in pointer i

	printf("%c\n", *cptr);
	printf("%d\n", *iptr);

	return 0;
}
```