# PRODUCT MANAGEMENT SYSTEM stack overflow in search_item function target parameter



## supplier



[Product Management System In C Programming With Source Code - Source Code & Projects](https://code-projects.org/product-management-system-c-programming-source-code/)

## Vulnerability file



target parameter in search_item function.

## describe



There is a stack overflow vulnerability in search_item function And target parameter of Product management system. it cause ddos and rce.



**Code analysis**

In the search_item function, the target variable is 40 bytes long, but it is possible to enter data into the target variable without a limit on the length. Causing a stack overflow.

![image-20250325211219435](https://raw.githubusercontent.com/zzzxc643/images/main/image/image-20250325211219435.png)





## POC

input username and password

![image-20250325211317864](https://raw.githubusercontent.com/zzzxc643/images/main/image/image-20250325211317864.png)



enter 3 after   "Enter your choice[1-6]"

![image-20250325211449182](https://raw.githubusercontent.com/zzzxc643/images/main/image/image-20250325211449182.png)



enter payload to cause the stack overflow to crash

```
aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
```

![image-20250325211732102](https://raw.githubusercontent.com/zzzxc643/images/main/image/image-20250325211732102.png)



Result

we can see EXCEPTION_ACCESS_VIOLATION.

![image-20250325211931747](https://raw.githubusercontent.com/zzzxc643/images/main/image/image-20250325211931747.png)