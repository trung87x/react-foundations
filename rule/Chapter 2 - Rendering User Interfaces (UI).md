# Chương 2: Kết xuất giao diện người dùng (Rendering User Interfaces - UI)

Để hiểu cách React hoạt động, trước tiên chúng ta cần hiểu cơ bản về cách trình duyệt diễn giải mã của bạn để tạo ra (hoặc kết xuất) giao diện người dùng (UI).

## Cách trình duyệt hiển thị trang web

Khi người dùng truy cập một trang web, máy chủ sẽ trả về một tệp HTML cho trình duyệt. Trình duyệt sau đó đọc HTML này và xây dựng **Mô hình đối tượng tài liệu (Document Object Model - DOM)**.

## DOM là gì?

DOM là một đại diện dưới dạng đối tượng của các phần tử HTML. Nó đóng vai trò là cầu nối giữa mã của bạn và giao diện người dùng, và có cấu trúc dạng cây với các mối quan hệ cha-con.

Bạn có thể sử dụng các phương thức DOM và JavaScript để lắng nghe các sự kiện của người dùng và **thao tác với DOM** bằng cách chọn, thêm, cập nhật và xóa các phần tử cụ thể trong giao diện người dùng. Việc thao tác với DOM không chỉ cho phép bạn nhắm mục tiêu vào các phần tử cụ thể mà còn thay đổi kiểu dáng và nội dung của chúng.

Trong phần tiếp theo, bạn sẽ tìm hiểu cách sử dụng JavaScript và các phương thức DOM để cập nhật giao diện người dùng.

---

**Tổng kết:** Bạn đã nắm được những kiến thức cơ bản về cách UI được kết xuất trên trình duyệt thông qua DOM. Tiếp theo, chúng ta sẽ xem cách cập nhật giao diện bằng JavaScript thuần.
