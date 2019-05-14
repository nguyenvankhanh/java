### Maven là gì và mục đích sử dụng

1. maven là một tool build tự động sử dụng chủ yếu cho các java project, nó dùng để đóng gói và deloy lên các server
2. nó dựa trên concept của pom (project object model)
3. nó sẽ download tự động các librarie và các plugin 1 cách tự động (khai báo trong file pom)
4. giúp team phát triển tập trung vào business code mà không cần bận tâm nhiều đến configuration và dependency (các libraries)  -> tức là ô pm hay leader chỉ cần define các dependency... rồi sau đó các developer chỉ cần chạy lệnh maven thì từ đó sẽ load toàn bộ các libraries về (đồng nhất version cho toàn bộ các developer) 

### Cài đặt Maven

1. Cài java trước -> video 7/maven/fresher academy
2. Cài maven -> video 8

### Configuration Maven

-> video 9

### Tạo Maven project

1. Sử dụng lệnh mvn -> video 12, 13

### POM - Project Object Model

Đây là file khai báo chi tiết các nội dung configure về java project và maven -> video 14

### Maven Plugins

1. Được khai báo trong file POM

2. Gồm 2 loại Build plugins và Reporting plugins

-> video 16

### Sử dụng Maven trong Eclipse

- có 2 cách sử dụng: tải eclipse có sẵn maven hoặc tải eclipse trước rồi tải plugin maven cho bản eclipse đó

  -> xem video 19

### Cách tạo 1 maven project trong Eclipse

1. Import 1 project maven có sẵn vào trong eclipse -> video 20

2. Convert từ project bình thường sang maven project -> video 21

### Configure POM 

-> video 22

### Maven Commands

1. validate: để kiểm tra xem các thông tin có chính xác hay không
2. clean: để xóa đi các compile sau khi thực hiện các lệnh khác
3. compile: biên dịch
4. test: để chạy các unit test framework (junit...)
5. install: load các libararies và các plugin cần thiết
6. package: đóng gói thành gói jar hoặc war
7. deploy: cho phép copy file jar đến 1 folder nào đấy hoặc 1 responsitory nào đấy. hoặc cũng có thể deloy gói war lên web server như tomcat 

**Cách gọi lệnh maven ở trên command line**: mvn ten_lenh

vd: mvn clean 

hoặc cũng có thể viết gộp lệnh:

vd: mvn clean install -> sẽ hiểu là clean trước và install sau

mvn compile: tiến hành thực thi code -> sẽ sinh ra thư mục target

mvn clean: sẽ xóa thư mục target

mvn test: sẽ thực thi file test trong folder test

mvn package: chạy lệnh này sẽ sinh ra file .jar, chạy file jar này cũng chính là thực thi code đã viết -> video 28

mvn install: là lệnh để load những libraries và plugins cần thiết cho project đó - những phần đó khai báo ở file pom

deploy: hướng dẫn deloy project sử dụng tomcat -> video 30