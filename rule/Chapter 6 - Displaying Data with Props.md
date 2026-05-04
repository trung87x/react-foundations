# Chương 6: Hiển thị dữ liệu với Props (Displaying Data with Props)

Trong chương này, chúng ta sẽ tìm hiểu cách truyền dữ liệu vào các thành phần React thông qua **Props** (viết tắt của properties - thuộc tính).

## Props là gì?

Tương tự như các phần tử HTML có thuộc tính (ví dụ: `src` cho `<img>`, `href` cho `<a>`), các thành phần React có thể nhận thông tin truyền từ thành phần cha. Props cho phép bạn tạo ra các thành phần có thể tái sử dụng nhưng hiển thị nội dung khác nhau.

**Lưu ý quan trọng:** Trong React, dữ liệu luôn chảy từ trên xuống (từ cha xuống con). Đây được gọi là **luồng dữ liệu một chiều (one-way data flow)**.

## Sử dụng Props

Bạn có thể truyền một prop cho thành phần con giống như truyền thuộc tính HTML:

```tsx
function HomePage() {
  return (
    <div>
      {/* Truyền prop 'title' cho Header */}
      <Header title="React" />
      <Header title="A new title" />
    </div>
  );
}
```

Thành phần con nhận props dưới dạng một đối tượng ở tham số đầu tiên của hàm:

```tsx
// Sử dụng Destructuring để lấy trực tiếp giá trị title
function Header({ title }) {
  return <h1>{title}</h1>;
}
```

## Sử dụng biến trong JSX

Để sử dụng một biến JavaScript bên trong JSX, bạn cần đặt biến đó trong cặp dấu ngoặc nhọn `{}`. 
- Dấu ngoặc nhọn giúp bạn chuyển từ "JSX land" sang "JavaScript land".
- Bạn có thể đặt bất kỳ biểu thức JavaScript nào (thứ gì đó trả về một giá trị duy nhất) vào bên trong `{}`.

Ví dụ sử dụng toán tử ba ngôi (ternary operator):

```tsx
function Header({ title }) {
  return <h1>{title ? title : 'Default title'}</h1>;
}
```

## Kết xuất danh sách (Rendering lists)

Thông thường, bạn sẽ có dữ liệu dưới dạng mảng và muốn hiển thị chúng thành một danh sách. Bạn có thể sử dụng phương thức `array.map()` để thực hiện việc này:

```tsx
function HomePage() {
  const names = ['Ada Lovelace', 'Grace Hopper', 'Margaret Hamilton'];

  return (
    <div>
      <Header title="Develop. Preview. Ship." />
      <ul>
        {names.map((name) => (
          // Cần có thuộc tính 'key' duy nhất cho mỗi phần tử danh sách
          <li key={name}>{name}</li>
        ))}
      </ul>
    </div>
  );
}
```

**Tại sao cần thuộc tính `key`?**
React cần một cách để xác định duy nhất các mục trong mảng để biết phần tử nào cần cập nhật trong DOM khi dữ liệu thay đổi, giúp tối ưu hóa hiệu suất.

---

**Tổng kết:** Bạn đã học cách truyền dữ liệu bằng Props, sử dụng biểu thức JavaScript trong JSX và hiển thị danh sách từ mảng. Tiếp theo, chúng ta sẽ tìm hiểu cách thêm tính tương tác bằng State.
