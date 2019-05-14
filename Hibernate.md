Nói qua về các database hay được sử dụng trong java nói chung và hibernate nói riêng:

1. Relational Database (csdl quan hệ)

   - SQL Server
   - MySQL
   - ORACLE
   - PostgreSQL

2. In-Memory Database (csdl trên bộ nhớ) - ở dạng portable

   - DB
   - H2

   Dùng để testing

**Hibernate** là một framework **ORM** (**O**bject **R**elational **M**apping) - <https://stackjava.com/uncategorized/orm-la-gi-tong-quan-ve-orm-framework.html>

-> đọc thêm về ORM

### Ưu điểm của Hibernate

1. vì là 1 ORM fw nên sẽ tăng được tính productivity

   -> vì không cần quan tâm việc mapping như thế nào chỉ cần tập trung vào business code (dữ liệu được lấy ra ntn, update ntn, còn mapping ntn là việc của hibernate)

2. dễ maintain vì các đoạn code rất ngắn

3. có tính portability (di động), bởi vì có thể thêm sửa xóa các configuration ở trong hệ thống dễ dàng 

   - có thể thay đổi database hoặc version của db bằng cách khai báo trong file configure

4. Db independent - không phụ thuộc vào db

5. Có thể tận dụng tối đa các đặc điểm của OOP như là tính thừa kế, ...

6. Caching

7. Pooling -  quản lý connection, số lượng connection

8. Lazy load

9. Free

#### Nhược điểm

- Chậm hơn so với JDBC

- Không phù hợp với batch processing

  <https://stackjava.com/hibernate/hibernate-batch-processing-la-gi-batch-processing-trong-hibernate.html>

- Có nhiều API và phải học nhiều thứ như annotation, configuration, session, hql (hibernate query language), caching, pooling...