### Spring Framework là gì:

1. Là một ứng dụng được viết trên nền tảng là ngôn ngữ java, nó có thể dùng để viết các ứng dụng trong java, application desktop, enterprise system, support được cả android
2. Là Open Source -> sẽ được cập nhật liên tục nhờ vào cộng đồng
3. Framework này có nhiều các component khác nhau, dùng phần nào thì tìm hiểu phần đó, ví dụ làm về web thì sử dụng core, web, test...

### Ưu điểm của spring:

1. nhẹ, phần core của nó chỉ có hơn 2M
2. Có sẵn các template để người dùng có thể đưa luôn vào trong dự án
3. dễ test
4. dễ khởi tạo project(spring boot)
5. giao tiếp mạnh mẽ
6. hỗ trợ lập trình hướng sự kiện
7. có sẵn spring MVC đơn giản dễ sử dụng
8. có sẵn transaction và secrurity

### Setup project sử dụng spring:

-> cần cài đặt sẵn java và maven, ide có thể sử dụng sts (spring tool suite), ide này xây dựng dựa trên eclipse nên giao diện và cách sử dụng cũng rất dễ dàng

### Contructor trong Spring

Spring sử dụng IOC để khởi tạo object

Khi khởi tạo trực tiếp object từ class tức là ta đang hard code, fix cứng code cho object đó, khi muốn sửa đổi rất khó khăn, thay vào đó sử dụng cách khởi tạo object IOC và DI

IOC (Inversion of Control): có nghĩa là một object không tạo ra một object khác nếu muốn sử dụng, thay vào đó nó sẽ khởi tạo các object thông qua việc truyền vào từ bên ngoài, ví dụ như các thuộc tính của một class sẽ được truyền vào thông qua các hàm khởi tạo hoặc setter thay vì khởi tạo trực tiếp trong class 

DI (Dependency Injection): DI là một dạng của IOC nghĩa là 1 đối tượng được truyền vào 1 object thông qua các hàm khởi tạo/setter/service lookups

### Phân biệt Java Beans với Spring Beans

Java beans:

-  là các class có hàm khởi tạo không tham số được đặt là public và từ đó nó có thể sử dụng các hàm khởi tạo không tham số này để tạo ra object
- Có các getter và setter để truy cập vào các thuộc tính private của nó
- phải thừa kế interface Serializable để có thể truyền qua mạng theo cơ có remote hoặc lưu xuống các file rồi đọc lại

Spring beans

- Là các object được quản lý bởi Spring, bất kỳ object nào được khởi tạo, cấu hình và quản lý bởi Spring container thì đều được hiểu là spring beans nó có thể là responsitory, service hoặc có thể là model
- Có thể được khai báo trong các file configuration, annotations  hoặc references 

Spring beans không nhất thiết phải là Java beans -> nó không cần phải kế thừa interface Serializable hay phải có các hàm khởi tạo không tham số hay public

### Spring Configuration

- sử dụng XML
- sử dụng annotation configuration - từ java 5
- sử dụng Java-based configuration - từ java 4.1