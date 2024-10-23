## 1. Ngôn ngữ Java là gì?
Java là một ngôn ngữ lập trình bậc cao, hướng đối tượng và đa nền tảng. Nó được phát triển bởi Sun Microsystems (nay thuộc Oracle) vào năm 1995. Java cho phép các lập trình viên phát triển ứng dụng với tiêu chí "viết một lần, chạy mọi nơi" (write once, run anywhere - WORA), tức là có thể chạy trên nhiều nền tảng khác nhau mà không cần phải biên dịch lại. Java thường được sử dụng trong phát triển các ứng dụng web, di động (đặc biệt là Android) và các hệ thống lớn.

## 2. Lý do ra đời của Java
Java ra đời nhằm giải quyết các vấn đề của ngôn ngữ lập trình C và C++ như:
- **Tính bảo mật kém**: C và C++ có những lỗ hổng bảo mật lớn do quản lý bộ nhớ thủ công.
- **Tính phụ thuộc nền tảng**: C và C++ phụ thuộc vào hệ điều hành cụ thể, yêu cầu biên dịch riêng cho từng hệ điều hành.
- **Khó học và sử dụng**: C và C++ có cú pháp phức tạp và yêu cầu nhiều kiến thức về quản lý bộ nhớ.
  
Java đã khắc phục các nhược điểm này bằng cách:
- **Bảo mật** hơn nhờ cơ chế kiểm soát bộ nhớ và không sử dụng con trỏ trực tiếp.
- **Độc lập nền tảng** nhờ bytecode và máy ảo Java (JVM).
- **Đơn giản và dễ học** nhờ cú pháp rõ ràng và tự động quản lý bộ nhớ qua Garbage Collection.
guồn `.java` được biên dịch thành bytecode `.class` bởi trình biên dịch `javac`.
2. **Chạy trên JVM (Java Virtual Machine)**: Bytecode không phụ thuộc vào bất kỳ hệ điều hành nào và được JVM thực thi. JVM sẽ dịch bytecode thành mã máy tùy theo hệ điều hành mà chương trình đang chạy.
3. **Kết quả**: Bytecode có thể chạy trên bất kỳ hệ điều hành nào có JVM cài đặt, mang lại tính độc lập nền tảng.
## 3. Cách Java hoạt động
Java hoạt động theo quy trình gồm ba bước:
1. **Biên dịch (Compilation)**: Mã nguồn `.java` được biên dịch thành bytecode `.class` bởi trình biên dịch `javac`.
2. **Chạy trên JVM (Java Virtual Machine)**: Bytecode không phụ thuộc vào bất kỳ hệ điều hành nào và được JVM thực thi. JVM sẽ dịch bytecode thành mã máy tùy theo hệ điều hành mà chương trình đang chạy.
3. **Kết quả**: Bytecode có thể chạy trên bất kỳ hệ điều hành nào có JVM cài đặt, mang lại tính độc lập nền tảng.
## 4. Cấu trúc một chương trình Java
Một chương trình Java cơ bản thường có cấu trúc như sau:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

- **public class HelloWorld**: Khai báo một lớp có tên `HelloWorld`.
- **public static void main(String[] args)**: Phương thức `main` là điểm bắt đầu của chương trình.
- **System.out.println**: In ra chuỗi "Hello, World!" trên màn hình.
## 5. Package là gì?
**Package:** là một tập hợp các class liên quan với nhau, được sử dụng để nhóm các class có chức năng tương tự và quản lý mã nguồn một cách hợp lý.
- Package giúp tránh xung đột tên giữa các class và cung cấp khả năng bảo mật thông qua việc kiểm soát phạm vi truy cập.
- Một package có thể chứa cả class và các subpackage (package con).
- Package mặc định trong Java là java.lang, nhưng bạn có thể tạo ra các package tùy chỉnh cho dự án của mình.

```java
package com.example;
public class MyClass {
    // Code ở đây
}
```

## 6. Syntax cơ bản

### 6.1. Khai báo biến nguyên thủy
![Alt Text](https://box.edu.vn/wp-content/uploads/2022/05/kieu-du-lieu-java-1-1.jpg)
Java hỗ trợ các kiểu dữ liệu nguyên thủy như: `int`, `float`, `double`, `boolean`, `char`.
 nếu biến có nhiều từ thì từ t2 trở đi viết hoa chữ cái đầu
```java
int age = 25;
float height = 1.75f;
boolean isJavaFun = true;
char grade = 'A';
```

### 6.2. Làm quen với vòng lặp

```java
// Vòng lặp for
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}

// Vòng lặp while
int count = 0;
while (count < 5) {
    System.out.println(count);
    count++;
}
```

### 6.3. Câu lệnh rẽ nhánh

```java
int x = 10;
if (x > 0) {
    System.out.println("x là số dương");
} else {
    System.out.println("x không phải là số dương");
}

// Switch case
int day = 3;
switch (day) {
    case 1:
        System.out.println("Thứ hai");
        break;
    case 2:
        System.out.println("Thứ ba");
        break;
    case 3:
        System.out.println("Thứ tư");
        break;
    default:
        System.out.println("Ngày không hợp lệ");
}
```

### 6.4. Mảng trong Java

```java
int[] numbers = {1, 2, 3, 4, 5};
for (int num : numbers) {
    System.out.println(num);
}
```

## 7. Tổng quan về Class và Object
### Class: 
- Class là một khuôn mẫu `blueprint` để tạo ra các đối tượng `objects`. Một class định nghĩa các thuộc tính `(fields, variables)` và các phương thức `(methods)` để đối tượng có thể thao tác và lưu trữ dữ liệu.
- Một class thường chứa:
Fields `(thuộc tính/biến)`: Lưu trữ trạng thái của đối tượng.
Constructors `(hàm khởi tạo)`: Được sử dụng để tạo ra các đối tượng từ class.
Methods `(phương thức)`: Xác định các hành vi của đối tượng.
Ví dụ về một class trong Java:
```java
public class Person {
    // Fields (thuộc tính)
    private String name;
    private int age;

    // Constructor (hàm khởi tạo)
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Method (phương thức)
    public void sayHello() {
        System.out.println("Hello, my name is " + name + " and I am " + age + " years old.");
    }
}
```
### Object
Trong Java, Object là lớp cơ sở của mọi lớp khác.
 Mọi lớp trong Java đều trực tiếp hoặc gián tiếp kế thừa từ lớp Object. 
 Các phương thức của Object có thể được ghi đè lại trong các lớp con. 

### 7.1. Từ khóa `this`
`this` là một tham chiếu đến đối tượng hiện tại trong một phương thức hoặc constructor. Nó thường được dùng khi các biến thành viên của đối tượng bị trùng tên với tham số của phương thức.

```java
public class MyClass {
    int x;
    MyClass(int x) {
        this.x = x;  // Tham chiếu đến biến thành viên x
    }
}
```

### 7.2. Constructor
Constructor là một phương thức đặc biệt được gọi khi một đối tượng của lớp được khởi tạo. Nó có cùng tên với lớp và không có kiểu trả về.
### Đặc điểm của Constructor:
- Tên của constructor phải giống tên lớp.
- Không có kiểu trả về.
- Được gọi tự động khi đối tượng được khởi tạo.
- Có thể được sử dụng để thiết lập các giá trị ban đầu cho đối tượng.

## Các loại Constructor

### 1. Constructor mặc định (Default Constructor)
Nếu một lớp không có constructor nào được khai báo, Java sẽ cung cấp một constructor mặc định không có tham số. Constructor mặc định không thực hiện gì ngoài việc khởi tạo đối tượng.

```java
public class MyClass {
    public MyClass() {
        System.out.println("Đối tượng được khởi tạo");
    }
    
    public static void main(String[] args) {
        MyClass obj = new MyClass(); // Gọi constructor mặc định
    }
}
```
### 2. Constructor có tham số (Parameterized Constructor)
có thể định nghĩa constructor với tham số để khởi tạo đối tượng với các giá trị cụ thể.
```java
public class MyClass {
    private int id;
    private String name;

    // Constructor có tham số
    public MyClass(int id, String name) {
        this.id = id;
        this.name = name;
    }

    public void display() {
        System.out.println("ID: " + id + ", Name: " + name);
    }

    public static void main(String[] args) {
        MyClass obj = new MyClass(1, "John"); // Gọi constructor có tham số
        obj.display(); // Hiển thị thông tin đối tượng
    }
}
```
### 7.3. Access Modifier (Các từ khóa truy cập)
Java cung cấp các từ khóa truy cập để kiểm soát quyền truy cập vào các thành phần của lớp:
- **public**: Có thể truy cập từ bất kỳ đâu.
- **private**: Chỉ có thể truy cập bên trong lớp đó.
- **protected**: Có thể truy cập từ các lớp trong cùng package hoặc các lớp con.
- **(default)**: Không có từ khóa, chỉ có thể truy cập trong cùng package.

```java
public class MyClass {
    private int x;  // Chỉ có thể truy cập từ bên trong MyClass
}
```

### 7.4. Getter và Setter
Getter và Setter là các phương thức được sử dụng để truy cập và cập nhật giá trị của các thuộc tính private của một lớp.

```java
public class MyClass {
    private int x;

    public int getX() {
        return x;
    }

    public void setX(int x) {
        this.x = x;
    }
}
```

### 7.5. Từ khóa `static`
`static` được sử dụng để khai báo các thuộc tính và phương thức thuộc về lớp thay vì thuộc về các đối tượng của lớp. Thành phần `static` có thể được truy cập mà không cần tạo đối tượng của lớp.

```java
public class MyClass {
    public static int count = 0;  // Biến static
    public static void sayHello() {
        System.out.println("Hello!");
    }
}
```
## 8. Bài tập 
1. 
```java
public class Main {
    public static void main(String[] args) {
      System.out.println("Hello, World.");
      System.out.println("Hello, Java.");
    }
  }
```
2. 
```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;
public class Main {
    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int n = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");
        if(n%2 != 0)
        {
            System.out.println("Weird");
        }
        else 
        {
            if(n >= 2  && (n <= 5))  System.out.println("Not Weird");
            else if((n >= 6) && (n <= 20))  System.out.println("Weird");
            else  System.out.println("Not Weird");
        }
        scanner.close();
    }
}
```
3. 
```java
import java.util.Scanner;

public class Solution {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int a = scan.nextInt();
        int b = scan.nextInt();
        int c = scan.nextInt();
        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
    }
}
```
4.
```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;



public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));
        
        int N = Integer.parseInt(bufferedReader.readLine().trim());
        for(int i = 1; i <= 10; ++i)
        {
          System.out.println(N + " x " + i + " = " + (N*i));
        }
        bufferedReader.close();
    }
}
```
