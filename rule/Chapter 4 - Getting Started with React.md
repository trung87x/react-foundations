# Chương 4: Bắt đầu với React (Getting Started with React)

Trong chương này, chúng ta sẽ tìm hiểu cách tích hợp React vào dự án của mình bằng cách sử dụng các tệp script từ bên ngoài.

## Thêm React vào dự án của bạn

Để sử dụng React, bạn cần tải hai tệp script từ [unpkg.com](https://unpkg.com/):
- **react**: Thư viện React cốt lõi.
- **react-dom**: Cung cấp các phương thức dành riêng cho DOM để sử dụng React với DOM.

```html
<html>
  <body>
    <div id="app"></div>
    <!-- 1. Tải thư viện React và ReactDOM -->
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    
    <script type="text/javascript">
      const app = document.getElementById('app');
      // 2. Tạo một root cho React
      const root = ReactDOM.createRoot(app);
      // 3. Render nội dung
      root.render(<h1>Develop. Preview. Ship.</h1>);
    </script>
  </body>
</html>
```

Tuy nhiên, nếu bạn chạy mã này, bạn sẽ gặp lỗi `SyntaxError`. Đó là vì trình duyệt không hiểu cú pháp `<h1>...</h1>` bên trong JavaScript. Đây chính là **JSX**.

## JSX là gì?

JSX là một phần mở rộng cú pháp cho JavaScript, cho phép bạn mô tả giao diện người dùng (UI) bằng cú pháp giống như HTML. 

Vì trình duyệt không hiểu JSX một cách trực tiếp, bạn cần một trình biên dịch JavaScript như **Babel** để chuyển đổi mã JSX của bạn thành JavaScript thông thường.

## Thêm Babel vào dự án

Thêm script Babel vào tệp `index.html` và thay đổi kiểu script thành `type="text/jsx"` để thông báo cho Babel biết đoạn mã nào cần chuyển đổi.

```html
<html>
  <body>
    <div id="app"></div>
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    
    <!-- 1. Thêm Babel Script -->
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    
    <!-- 2. Thay đổi type thành text/jsx -->
    <script type="text/jsx">
      const domNode = document.getElementById('app');
      const root = ReactDOM.createRoot(domNode);
      root.render(<h1>Develop. Preview. Ship.</h1>);
    </script>
  </body>
</html>
```

## Tại sao sử dụng React?

So với cách tiếp cận mệnh lệnh (imperative) bằng JavaScript thuần, React giúp bạn cắt giảm rất nhiều mã lặp lại. Thay vì phải viết các bước hướng dẫn máy tính tạo và thêm từng phần tử, bạn chỉ cần mô tả UI bạn muốn và React sẽ tự động cập nhật DOM cho bạn.

---

**Tổng kết:** Bạn đã tích hợp thành công React và Babel để bắt đầu viết UI bằng JSX. Tiếp theo, chúng ta sẽ tìm hiểu về các Thành phần (Components) trong React.
