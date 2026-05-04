# Chương 8: Từ React đến Next.js (From React to Next.js)

Cho đến nay, chúng ta đã tìm hiểu cách bắt đầu với React thông qua ba khái niệm thiết yếu: **Components**, **Props**, và **State**. Nắm vững các nền tảng này sẽ giúp bạn xây dựng bất kỳ ứng dụng React nào.

## Xem lại mã nguồn cuối cùng

Dưới đây là mã nguồn hoàn chỉnh của ứng dụng React đơn giản mà chúng ta đã xây dựng trong các chương trước:

```html
<!-- index.html -->
<html>
  <body>
    <div id="app"></div>
    <!-- Nạp các thư viện cần thiết -->
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

    <script type="text/jsx">
      const app = document.getElementById("app")

      // Thành phần Header với Props
      function Header({ title }) {
        return <h1>{title ? title : "Default title"}</h1>
      }

      // Thành phần HomePage với State
      function HomePage() {
        const names = ["Ada Lovelace", "Grace Hopper", "Margaret Hamilton"]
        const [likes, setLikes] = React.useState(0)

        function handleClick() {
          setLikes(likes + 1)
        }

        return (
          <div>
            <Header title="Develop. Preview. Ship." />
            <ul>
              {names.map((name) => (
                <li key={name}>{name}</li>
              ))}
            </ul>
            <button onClick={handleClick}>Like ({likes})</button>
          </div>
        )
      }

      const root = ReactDOM.createRoot(app);
      root.render(<HomePage />);
    </script>
  </body>
</html>
```

## Tại sao cần Next.js?

Mặc dù React rất xuất sắc trong việc xây dựng UI, nhưng để biến UI đó thành một ứng dụng hoàn chỉnh, có khả năng mở rộng và hiệu suất cao thì cần khá nhiều công sức cấu hình. 

Ngoài ra, các tính năng mới nhất của React như **Server Components** và **Client Components** yêu cầu một framework để hoạt động. Next.js giải quyết vấn đề này bằng cách xử lý phần lớn việc thiết lập và cung cấp thêm các tính năng như:
- **Routing**: Tự động hóa hệ thống định tuyến.
- **Data Fetching**: Tối ưu hóa việc lấy dữ liệu.
- **Rendering**: Hỗ trợ kết xuất phía máy chủ (SSR) và tạo trang tĩnh (SSG).

Trong các chương tiếp theo, chúng ta sẽ di chuyển ví dụ này từ React thuần sang Next.js và tìm hiểu cách nó hoạt động.

---

**Tổng kết:** Bạn đã hoàn thành phần nền tảng về React. Bây giờ là lúc bước vào thế giới của Next.js để xây dựng các ứng dụng thực tế chuyên nghiệp hơn.
