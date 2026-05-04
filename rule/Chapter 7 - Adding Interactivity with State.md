# Chương 7: Thêm tính tương tác với State (Adding Interactivity with State)

Trong chương này, chúng ta sẽ tìm hiểu cách React giúp thêm tính tương tác vào ứng dụng thông qua **State** (trạng thái) và **Event Handlers** (trình xử lý sự kiện).

## Lắng nghe sự kiện (Listening to events)

Để làm cho các phần tử UI phản hồi lại hành động của người dùng (ví dụ: nhấp chuột), bạn có thể sử dụng các thuộc tính sự kiện như `onClick`.

**Lưu ý:** Trong React, tên các sự kiện được viết theo kiểu **camelCase** (ví dụ: `onClick` thay vì `onclick`). Các sự kiện phổ biến khác bao gồm `onChange` cho các trường nhập liệu và `onSubmit` cho biểu mẫu.

## Xử lý sự kiện (Handling events)

Bạn có thể định nghĩa một hàm để xử lý sự kiện khi nó được kích hoạt:

```tsx
function HomePage() {
  function handleClick() {
    console.log("Đã nhấp vào nút!");
  }

  return (
    <div>
      {/* Gọi hàm handleClick khi sự kiện onClick xảy ra */}
      <button onClick={handleClick}>Like</button>
    </div>
  );
}
```

## State và Hooks

React cung cấp các hàm đặc biệt gọi là **Hooks**. Hooks cho phép bạn thêm các logic bổ sung như "trạng thái" (state) vào các thành phần của mình. State là thông tin trong UI có thể thay đổi theo thời gian, thường là do tương tác của người dùng.

Để quản lý trạng thái, chúng ta sử dụng hook `useState()`.

```tsx
function HomePage() {
  // useState trả về một mảng gồm 2 phần tử:
  // 1. likes: giá trị trạng thái hiện tại
  // 2. setLikes: hàm để cập nhật giá trị đó
  const [likes, setLikes] = React.useState(0); // Khởi tạo với giá trị 0

  function handleClick() {
    // Cập nhật trạng thái mới
    setLikes(likes + 1);
  }

  return (
    <div>
      <button onClick={handleClick}>Likes ({likes})</button>
    </div>
  );
}
```

## Quản lý State (Managing state)

- **State** được khởi tạo và lưu trữ bên trong một thành phần.
- Khác với **Props** (được truyền từ bên ngoài vào), logic cập nhật state nên được giữ bên trong thành phần nơi nó được tạo ra ban đầu.
- Bạn có thể truyền thông tin state cho các thành phần con dưới dạng props.

Khi bạn gọi hàm cập nhật trạng thái (`setLikes`), React sẽ tự động kết xuất (render) lại thành phần đó để cập nhật UI với giá trị mới nhất.

---

**Tổng kết:** Bạn đã học cách thêm tính tương tác cơ bản bằng cách lắng nghe sự kiện và quản lý dữ liệu động bằng State. Tiếp theo, chúng ta sẽ xem cách chuyển đổi từ React thuần sang Next.js.
