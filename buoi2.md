# Buổi 2
## Object
### I. Giới thiệu về Object trong Java
![Alt Text](https://quochung.cyou/wp-content/uploads/2023/11/image-6.png)
Trong lập trình hướng đối tượng, **Object** (đối tượng) là một thực thể có trạng thái và hành vi. Object đại diện cho các thực thể trong thế giới thực như `Xe`, `Người`, `Con vật`, v.v. Mỗi Object đều thuộc  một **lớp** (class) nhất định và được tạo ra từ lớp đó.
 **Sự khác biệt chính giữa một Class và một Object trong Java**: 
    - Class là một mô hình chi tiết để bạn sử dụng tạo ra các Object. Class định nghĩa tất cả các thuộc tính và các phương thức cần thiết của một Object.
    - Mỗi Object phải thuộc một Class nào đó. Và một Object là một thể hiện của Class. Tất cả các Object thuộc về cùng một Class có cùng các thuộc tính và các phương thức. 
### II. Đặc điểm của Object
Object trong Java có các đặc điểm chính sau:
    - **Thuộc tính (Attributes/Properties)**: Là các đặc điểm của Object, đại diện cho trạng thái của Object. Trong Java, các thuộc tính này thường là các biến thành viên của lớp.
    - **Phương thức (Methods)**: Là các hành vi của Object, đại diện cho những hành động mà Object có thể thực hiện. Trong Java, các phương thức được định nghĩa trong lớp của Object.

### III. Cách tạo Object trong Java
Để tạo một Object trong Java, cần phải:
    1. Định nghĩa lớp (class) cho Object.
    2. Sử dụng từ khóa `new` để khởi tạo Object từ lớp đó.
#### Ví dụ
```java
// Định nghĩa lớp Person
class Person {
    String name;
    int age;

    // Phương thức khởi tạo
    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Phương thức hiển thị thông tin
    void display() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }
}

// Tạo Object từ lớp Person
public class Main {
    public static void main(String[] args) {
        // Tạo một Object của lớp Person
        Person person1 = new Person("Alice", 25);
        
        // Gọi phương thức display() của Object
        person1.display();
    }
}
```
### IV. Object được lưu thế nào trong Java
#### 1. Bộ Nhớ Trong Java
Java phân bổ bộ nhớ thành hai khu vực chính:
   - **Stack**: Lưu trữ các biến cục bộ và các tham chiếu đến đối tượng.
   - **Heap**: Lưu trữ các đối tượng được tạo ra trong quá trình chạy chương trình.

**Stack**: Stack là vùng nhớ đặc biệt dùng để lưu trữ các biến cục bộ và các tham chiếu đến đối tượng. Khi một phương thức được gọi, một block nhớ sẽ được tạo trên stack, và khi phương thức kết thúc, block đó sẽ được thu hồi.

**Heap**: Heap là vùng nhớ lớn hơn, nơi các đối tượng được lưu trữ. Khi bạn sử dụng từ khóa `new` để tạo đối tượng, Java phân bổ một không gian trong heap để lưu trữ đối tượng này và trả về một tham chiếu của nó.
#### 2. Lưu Trữ Đối Tượng Trong Java
khi khai báo object thì object đó sẽ được lưu trong Stack, ta chỉ lưu địa chỉ đến object đó và từ địa chỉ này ta có thể truy cập vào để lấy các thuộc tính và phương thức của object đó.
**Vậy nên ta không thể so sánh 2 object với nhau bằng toán tử ==, mà phải dùng phương thức equals().**
### V. Wrapper class
Trong Java, các kiểu dữ liệu nguyên thủy (primitive types) như `int`, `double`, `boolean`, v.v. không thể sử dụng trực tiếp như các đối tượng. Java cung cấp các **wrapper class** để bọc các kiểu nguyên thủy thành đối tượng, giúp chúng có thể được sử dụng như các đối tượng trong những tình huống yêu cầu. Các **wrapper class** cũng cung cấp các phương thức tiện ích cho phép thao tác với các giá trị nguyên thủy dễ dàng hơn.

| Primitive data types | Wrapper Class |
|----------------------|---------------|
| `int`                | `Integer`     |
| `double`             | `Double`      |
| `float`              | `Float`       |
| `long`               | `Long`        |
| `short`              | `Short`       |
| `byte`               | `Byte`        |
| `boolean`            | `Boolean`     |
| `char`               | `Character`   |
----------------------------------------
**Các kiểu dữ liệu lưu dạng object này tuân theo cách Java lưu trữ object tức là không lưu trực tiếp object, mà chỉ lưu địa chỉ tới object đó.**
|Ưu điểm                                     | Nhược điểm   |
|--------------------------------------------|--------------|
|Có thể sử dụng các phương thức của object	 |Tốn bộ nhớ hơn|
-------------------------------------------------------------
### VI.  Autoboxing và Unboxing
**1. Autoboxing**: Là quá trình tự động chuyển đổi từ kiểu nguyên thủy sang đối tượng wrapper.
**2. Unboxing**: Là quá trình tự động chuyển đổi từ đối tượng wrapper về kiểu nguyên thủy.
khi sử dụng Auto-boxing và Auto-unboxing, cần phải cẩn thận, vì nó có thể gây ra lỗi.Vì vậy cần phải kiểm tra giá trị null trước khi sử dụng.
`Autoboxing` và `Auto-unboxing` giúp cho việc sử dụng các kiểu dữ liệu nguyên thuỷ và object trở nên dễ dàng hơn
### VII. String và StringBuilder trong Java
**1. String**: 
- String trong Java là immutable tức là không thể thay đổi.Còn khi mà bạn thay đổi 1 String Object trong Java thì 1 String object mới hoàn toàn sẽ được tạo ra mỗi lần bạn thay đổi.
- Có 2 cách để khai báo một String Object
```java
public class HelloWorld {
	public static void main(String[] args) {
		String s1 = "hello!"; // khai báo dùng String literal
		String s2 = new String("hi!"); //khai báo dùng new operator
	}
}
```
- **Sự khác nhau giữa 2 phương thức này là**: khi sử dụng "new" operator, 1 String Object mới sẽ được tạo ra trong bộ nhớ heap. Nhưng khi sử dụng 1 literal object `khai báo thuần tuý`, nếu đối tượng này đã tồn tại trong bộ nhớ heap rồi thì sẽ không tạo mới đối tượng nữa, sử dụng lại sẽ giúp tiết kiệm bộ nhớ heap hơn. Khi sử dụng String literal thì String Object được lưu ở nơi nào đó được gọi là `String Pool` trong Java. Nó nằm bên trong bộ nhớ heap, giúp tiết kiệm rất nhiều space cho Java Runtime mặc dù nó khá tốn thời gian để tạo ra 1 String Object. Vì thế nếu muốn tạo mới một String Object mỗi lần gọi, thì sử dụng "new" operator, còn nếu muốn tiết kiệm bộ nhớ heap, thì sử dụng literal string để tạo 1 String Object.
- Java String class còn cho phép truy cập với rất nhiều phương thức để áp dụng vào String. Một số phương thức như là: **substring(), charAt(), length(), equals(), concat(), replace(), trim(), split(), toUpperCase() and toLowerCase()**. Các phương thức này có thể sử dụng độc lập, cũng như kết hợp với nhau, tùy vào mục đích sử dụng.
**2. StringBuilder**: 
- `StringBuilder Class` làm cho String class trở nên linh động hơn vì nó có thể tạo ra một set của các chuỗi kí tự có thể thay đối tượng. StringBuilder Class cũng có một loạt các methods để tương tác hay tác động lên các String objects như trong String Class.
- **Đặc điểm của StringBuilder** : 
  - Hiệu suất cao hơn so với String khi thực hiện các thao tác nối chuỗi hoặc chỉnh sửa chuỗi thường xuyên.
  - Không thread-safe: StringBuilder không đồng bộ (non-synchronized), do đó không an toàn trong môi trường đa luồng. Nếu cần thread-safe, hãy sử dụng StringBuffer.
  - Có thể thay đổi (mutable): Nội dung của StringBuilder có thể thay đổi trực tiếp mà không cần tạo ra đối tượng mới.
- **Khởi tạo StringBuilder**:
``` java
StringBuilder sb = new StringBuilder();          // Khởi tạo rỗng
StringBuilder sb = new StringBuilder("Hello");   // Khởi tạo với nội dung
StringBuilder sb = new StringBuilder(50);        // Khởi tạo với dung lượng ban đầu 50 ký tự
```
- **Các phương thức thông dụng của StringBuilder**:
  - `append(String str):` Thêm chuỗi vào cuối` StringBuilder.`
    ```java
    append(String str): Thêm chuỗi vào cuối StringBuilder.
    ```
  - `insert(int offset, String str):` Chèn chuỗi vào vị trí chỉ định.
    ```java
    sb.insert(5, " Java");
    ```
  - `delete(int start, int end):` Xóa chuỗi từ vị trí `start` đến `end.`
    ```java
    sb.insert(5, " Java");
    ```
  - `replace(int start, int end, String str)`: Thay thế chuỗi từ vị trí `start` đến` end `bằng chuỗi mới.
    ```java
    sb.replace(0, 5, "Hi");
    ```
  - reverse(): Đảo ngược chuỗi trong StringBuilder.
  - toString(): Chuyển StringBuilder thành String.
### VIII. equals và hashcode, toán tử ==
**1. equals**:
- `equals()` là một phương thức được định nghĩa trong lớp Object và thường được ghi đè trong các lớp con để so sánh nội dung (giá trị) của hai đối tượng.
  - Mặc định, `equals()` trong Object hoạt động giống với `==` **(so sánh tham chiếu)**.
  - Các lớp như` String, Integer, Double, v.v.` đã ghi đè `equals()` để so sánh giá trị thực sự bên trong thay vì so sánh tham chiếu.
**2. hashCode**: 
    - `hashCode() `cũng là một phương thức trong Object, được sử dụng để sinh ra một mã băm (hash code) cho đối tượng. hashCode() thường được sử dụng trong các cấu trúc dữ liệu như HashMap, HashSet, HashTable, nơi cần truy xuất dữ liệu nhanh.
      - **Nguyên tắc quan trọng:** Nếu hai đối tượng bằng nhau theo equals(), chúng phải có cùng mã băm (hashCode). Tuy nhiên, hai đối tượng có cùng mã băm không nhất thiết phải bằng nhau theo equals().
      - Nếu ghi đè equals(), bạn nên ghi đè cả hashCode() để đảm bảo tính nhất quán.
**3. Toán tử ==**:
    - Toán tử == so sánh địa chỉ **(tham chiếu)** của hai đối tượng, nghĩa là kiểm tra xem cả hai tham chiếu có trỏ đến cùng một vùng nhớ trong bộ nhớ hay không.
      - Khi sử dụng với các kiểu dữ liệu nguyên thủy (`int, char, boolean, v.v.`), `==` so sánh trực tiếp giá trị của chúng.
      - Khi sử dụng với các đối tượng,` ==` so sánh xem hai đối tượng có cùng tham chiếu `(địa chỉ bộ nhớ)` không.

####  Tóm tắt
| So sánh             | Mục đích                                       | Kết quả                                                  |
|---------------------|------------------------------------------------|----------------------------------------------------------|
| `==`                | So sánh tham chiếu, kiểm tra cùng vùng nhớ     | Trả về `true` nếu cùng vùng nhớ                           |
| `equals()`          | So sánh nội dung giữa các đối tượng            | Trả về `true` nếu các giá trị nội dung giống nhau        |
| `hashCode()`        | Tạo mã băm cho đối tượng                       | Đối tượng bằng nhau thì mã băm phải giống nhau (ngược lại không bắt buộc) |

#### Khi nào nên dùng từng cái?
- Sử dụng `==` khi bạn muốn kiểm tra xem hai biến tham chiếu có trỏ đến cùng một đối tượng hay không.
- Sử dụng `equals()` khi bạn cần so sánh nội dung của hai đối tượng.
- Sử dụng `hashCode()` khi làm việc với các cấu trúc dữ liệu dựa trên băm (`HashMap`, `HashSet`, v.v.), hoặc khi muốn tối ưu hóa truy xuất dữ liệu trong các tập hợp lớn.
### IX. Cách Java Truyền Tham Số: 
- **Pass by Value**: 
  - Trong Java, khi ta truyền tham số vào một hàm, thì tham số đó sẽ được copy ra một vùng nhớ khác, và hàm sẽ thao tác với tham số ở vùng nhớ mới này.
  - Vậy nên, khi ta thay đổi giá trị của tham số trong hàm, thì giá trị của tham số bên ngoài hàm không bị thay đổi.
  - Tuy nhiên, nó sẽ lại thay đổi được các thuộc tính của object.
- **Tại sao pass-by-value mà String lại thay đổi được?**:
  - khi truyền 1 biến nguyên thủy, việc này giống như là ta chỉ tạo 1 bản sao của tờ giấy bình thường, dù ta thay đổi nội dung trên bản sao ra sao thì nội dung trên bản gốc vẫn sẽ k thay đổi.
  - Tuy nhiên, khi ta truyền một biến reference (tham chiếu) của Object person, ta đang truyền bản sao của “tham chiếu” của nó. Hay đơn giản là, ta đang tạo ra bản sao của một cái điều khiển,
    vậy thì cái điều khiển bản sao này khi đưa cho người khác, vẫn sẽ bật tắt được tivi ban đầu của mình
### X. Các Khái Niệm Cơ Bản về Garbage Collector
`Garbage Collector` (GC) là một quá trình tự động quản lý bộ nhớ trong các ngôn ngữ lập trình. GC giúp giải phóng bộ nhớ không còn sử dụng, từ đó tối ưu hóa việc sử dụng bộ nhớ và ngăn ngừa tình trạng rò rỉ bộ nhớ.
#### 1. Khái Niệm Chính
- **Bộ Nhớ Heap**: Là vùng nhớ dùng để lưu trữ đối tượng. Khi các đối tượng được tạo ra trong chương trình, chúng sẽ được lưu trữ trong heap. Bộ nhớ này được quản lý tự động bởi GC.
- **Vòng Đời Đối Tượng**: Đối tượng trong bộ nhớ heap sẽ tồn tại cho đến khi không còn bất kỳ tham chiếu nào đến chúng. Lúc này, GC sẽ thu hồi bộ nhớ của đối tượng để cấp phát lại cho đối tượng khác.
- **Bộ Nhớ Rác (Garbage)**: Là bộ nhớ chứa các đối tượng không còn được sử dụng, nghĩa là không có tham chiếu nào trỏ đến đối tượng đó.
#### 2. Cách Thức Hoạt Động của Garbage Collector
Garbage Collector hoạt động dựa trên các thuật toán khác nhau để xác định và thu hồi bộ nhớ của các đối tượng không còn sử dụng. Các thuật toán GC phổ biến bao gồm:
-  Mark and Sweep (Đánh Dấu và Quét)
   -  **Mark (Đánh Dấu)**: `GC` xác định các đối tượng vẫn đang sử dụng và đánh dấu `mark bit` của chúng thành `true`. Việc tìm kiếm bắt đầu với một tập hợp gốc các tham chiếu được giữ trong các biến cục bộ trong Stack, hoặc biến toàn cục. Bắt đầu từ các tham chiếu gốc, `GC` sẽ tiến hành tìm kiếm sâu cho các đối tượng có reference tới các gốc này, bất kì đối tượng nào giữ reference tới đối tượng khác, GC giữ cho đối tượng đó tồn tại.
   - **Sweep (Quét)**: Quét qua toàn bộ heap, tất cả các đối tượng không được đánh dấu từ giai đoạn `Mark` sẽ bị xóa khỏi bộ nhớ, giải phóng không gian của HEAP.
-  Reference Counting (Đếm Tham Chiếu)
   - `GC` đếm số tham chiếu đến mỗi đối tượng. Khi số tham chiếu bằng 0, đối tượng đó sẽ bị giải phóng.
   - Phương pháp này có nhược điểm là không giải phóng được các đối tượng bị rò rỉ do vòng tham chiếu.
-  Generational Garbage Collection (Thu Gom Thế Hệ)
   - Bộ nhớ heap được chia thành nhiều thế hệ như "Young", "Old" và "Permanent Generation".
   - Đối tượng mới tạo thường được lưu trữ trong "Young Generation". Nếu tồn tại đủ lâu, đối tượng sẽ được chuyển đến "Old Generation".
   - "Young Generation" thường được thu gom thường xuyên, giúp tối ưu hóa hiệu suất.
#### 3. Các Khái Niệm và Thuật Ngữ Liên Quan
- **Roots**: Là các điểm bắt đầu để GC truy xuất các đối tượng còn được sử dụng. Các roots bao gồm biến toàn cục, biến cục bộ, các tham số hàm, v.v.
- **Heap Compaction (Tái cấu trúc Heap)**: Sau quá trình thu gom, GC sẽ nén lại vùng nhớ để lấp đầy khoảng trống, giúp bộ nhớ liên tục và tối ưu hóa việc cấp phát.
- **Stop-the-World (Dừng Tạm Thời)**: Trong quá trình GC, ứng dụng có thể tạm thời bị dừng lại để tiến hành thu gom bộ nhớ.
#### 4. Ưu Điểm và Nhược Điểm của Garbage Collector
- **Ưu Điểm**
  - **Giải phóng bộ nhớ tự động**: Giảm bớt gánh nặng quản lý bộ nhớ thủ công cho lập trình viên.
  - **Tránh rò rỉ bộ nhớ**: GC giúp thu hồi các đối tượng không còn được sử dụng, giảm thiểu tình trạng rò rỉ bộ nhớ.
- **Nhược Điểm**
  - **Chi phí hiệu suất**: GC có thể làm giảm hiệu suất vì ứng dụng có thể bị tạm dừng khi GC hoạt động.
  - **Không kiểm soát hoàn toàn**: Lập trình viên không thể quyết định chính xác khi nào GC sẽ chạy, dẫn đến thiếu kiểm soát trong một số trường hợp yêu cầu hiệu năng cao.
#### 5. Một số Loại Garbage Collector Thông Dụng
- **Serial GC**: Hoạt động tuần tự, thường dùng trong các ứng dụng nhỏ.
- **Parallel GC**: Sử dụng nhiều luồng để thu gom bộ nhớ, thích hợp cho ứng dụng đa luồng.
- **CMS (Concurrent Mark-Sweep)**: Thu gom rác song song, giảm thiểu thời gian tạm dừng của ứng dụng.
- **G1 GC (Garbage-First)**: Được thiết kế để giảm thiểu độ trễ, sử dụng các vùng nhớ nhỏ và gom chúng khi cần.
---


















