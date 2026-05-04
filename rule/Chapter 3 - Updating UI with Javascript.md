# Chương 3: Cập nhật UI bằng JavaScript (Updating UI with JavaScript)

Trong chương này, chúng ta sẽ bắt đầu xây dựng dự án bằng cách sử dụng JavaScript và các phương thức DOM để thêm một thẻ `h1` vào dự án của bạn.

## Thao tác với DOM bằng JavaScript thuần

Hãy xem ví dụ về cách tạo một tiêu đề bằng JavaScript:

```html
<!-- index.html -->
<html>
  <body>
    <div id="app"></div>
    <script type="text/javascript">
      // 1. Chọn phần tử div có id là 'app'
      const app = document.getElementById('app');

      // 2. Tạo một phần tử H1 mới
      const header = document.createElement('h1');

      // 3. Tạo nội dung văn bản cho phần tử H1
      const text = 'Develop. Preview. Ship.';
      const headerContent = document.createTextNode(text);

      // 4. Thêm văn bản vào phần tử H1
      header.appendChild(headerContent);

      // 5. Đặt phần tử H1 vào bên trong div 'app'
      app.appendChild(header);
    </script>
  </body>
</html>
```

## HTML vs. DOM

Có một sự khác biệt quan trọng giữa mã nguồn HTML ban đầu và nội dung được hiển thị:
- **HTML**: Đại diện cho nội dung trang ban đầu.
- **DOM**: Đại diện cho nội dung trang đã được cập nhật bởi mã JavaScript của bạn.

Cập nhật DOM bằng JavaScript thuần rất mạnh mẽ nhưng rất dài dòng (verbose). Khi ứng dụng lớn dần, việc quản lý hàng nghìn dòng lệnh hướng dẫn máy tính từng bước một sẽ trở nên cực kỳ khó khăn.

## Lập trình mệnh lệnh (Imperative) vs. Khai báo (Declarative)

- **Lập trình mệnh lệnh (Imperative)**: Giống như việc đưa cho đầu bếp hướng dẫn từng bước để làm bánh pizza. Bạn viết mã để hướng dẫn máy tính *làm thế nào* (how) để cập nhật UI. Ví dụ trên là lập trình mệnh lệnh.
- **Lập trình khai báo (Declarative)**: Giống như việc gọi một chiếc bánh pizza mà không cần quan tâm đến các bước làm ra nó. Bạn chỉ cần khai báo *cái gì* (what) bạn muốn hiển thị, và để thư viện/framework tự lo liệu các bước cập nhật DOM.

**React** là một thư viện UI khai báo phổ biến. Thay vì phải viết các phương thức DOM phức tạp, bạn chỉ cần mô tả trạng thái cuối cùng của UI mà bạn muốn, và React sẽ thay mặt bạn thực hiện các bước cập nhật DOM hiệu quả nhất.

---

**Tổng kết:** Bạn đã thấy sự khác biệt giữa cách tiếp cận mệnh lệnh truyền thống và cách tiếp cận khai báo hiện đại. Tiếp theo, chúng ta sẽ bắt đầu với React.
