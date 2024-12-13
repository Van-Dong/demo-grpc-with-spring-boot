# Tổng kết sau khi demo (mức siêu cơ bản do mới tiếp xúc)
* Cần thêm phụ thuộc `grpc-server-spring-boot-starter` để tạo grpc server và phụ thuộc `javax.annotation-api` để tương thích thì phải
* Ở đây ta thêm plugin maven để tích hợp protoc (Protocol Buffer Compiler) vào maven => khi dùng mvn compiler thì nó biên dịch file `.proto` luôn cho ta
* Vấn đề: Intellij không nhận dạng được các class sau biên dịch (bởi nó trong thư mục /target/ rồi)
  * Chỉ còn con đường `mvn compile` sau đó chạy file .jar thôi (do lười, chưa tìm hiểu cách tích hợp với Intellj thế nào)
* Vấn đề 2: Chưa tạo server thứ 2 để test (grpc-client ý) mà dùng PostMan test trực tiếp luôn => chưa thấy được sự bất tiện của việc phụ thuộc nó
  * Cách dùng Postman để test:
    * Vào New => chọn gRPC => điền URL (mặc định spring boot sẽ cho chạy ở port `9090`)
    * Sau đó import file `.proto` đã định nghĩa
    * Cuối cùng chọn service cần gọi và điền dữ liệu (ở mục Message ý)