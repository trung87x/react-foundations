# Chương 5: Xây dựng UI với các Thành phần (Building UI with Components)

Trong chương này, chúng ta sẽ tìm hiểu về khái niệm quan trọng nhất trong React: **Thành phần (Component)**.

## Các khái niệm cốt lõi của React

Có ba khái niệm cốt lõi của React mà bạn cần làm quen:
- **Components** (Thành phần)
- **Props** (Thuộc tính)
- **State** (Trạng thái)

## Thành phần (Components) là gì?

Giao diện người dùng có thể được chia thành các khối xây dựng nhỏ gọi là các thành phần.
Hãy tưởng tượng các thành phần giống như các viên gạch LEGO. Bạn có thể lấy các viên gạch riêng lẻ này và kết hợp chúng lại với nhau để tạo thành các cấu trúc lớn hơn. Nếu bạn cần cập nhật một phần của giao diện, bạn chỉ cần cập nhật thành phần hoặc viên gạch cụ thể đó.

## Tạo các thành phần

Trong React, các thành phần thực chất là các hàm JavaScript trả về các phần tử UI (thường là JSX).

```tsx
function Header() {
  return <h1>Develop. Preview. Ship.</h1>;
}

const root = ReactDOM.createRoot(app);
// Sử dụng thành phần như một thẻ HTML
root.render(<Header />);
```

**Lưu ý quan trọng:**
1. Tên thành phần phải được **viết hoa chữ cái đầu** (ví dụ: `Header`, không phải `header`) để phân biệt với các thẻ HTML thông thường.
2. Bạn sử dụng thành phần bằng cách đặt trong dấu ngoặc nhọn `< />`.

## Lồng các thành phần (Nesting components)

Bạn có thể lồng các thành phần React vào bên trong nhau giống như các phần tử HTML thông thường để tạo thành một "cây thành phần" (component tree).

```tsx
function Header() {
  return <h1>Develop. Preview. Ship.</h1>;
}

function HomePage() {
  return (
    <div>
      {/* Lồng thành phần Header vào HomePage */}
      <Header />
      <p>Chào mừng bạn đến với trang chủ!</p>
    </div>
  );
}

const root = ReactDOM.createRoot(app);
root.render(<HomePage />);
```

Cách tiếp cận theo mô-đun này cho phép mã của bạn dễ bảo trì hơn khi ứng dụng phát triển, vì bạn có thể thêm, cập nhật và xóa các thành phần mà không ảnh hưởng đến phần còn lại của ứng dụng.

---

**Tổng kết:** Bạn đã tạo được các thành phần React đầu tiên và biết cách lồng chúng vào nhau. Tiếp theo, chúng ta sẽ học cách truyền dữ liệu vào các thành phần thông qua Props.
