# Chương 10: Thành phần Máy chủ và Máy khách (Server and Client Components)

Để hiểu cách thức hoạt động của Server và Client Components, chúng ta cần làm quen với hai khái niệm cơ bản: **Môi trường** (máy chủ và máy khách) và **Ranh giới mạng**.

## Môi trường Máy chủ và Máy khách (Environments)

- **Client (Máy khách)**: Đề cập đến trình duyệt trên thiết bị của người dùng. Nó gửi yêu cầu đến máy chủ, nhận mã ứng dụng và biến nó thành giao diện người dùng tương tác.
- **Server (Máy chủ)**: Đề cập đến máy tính trong trung tâm dữ liệu lưu trữ mã ứng dụng của bạn, nhận yêu cầu từ máy khách và gửi lại phản hồi thích hợp.

Việc di chuyển quá trình kết xuất (rendering) và lấy dữ liệu lên máy chủ có thể giảm lượng mã gửi đến máy khách, giúp cải thiện hiệu suất. Tuy nhiên, để giao diện có tính tương tác (ví dụ: sử dụng `useState`), bạn cần thực hiện việc đó ở phía máy khách.

## Ranh giới Mạng (Network Boundary)

Ranh giới mạng là một đường phân chia trừu tượng giữa hai môi trường. Trong Next.js, bạn chọn nơi đặt ranh giới này trong cây thành phần của mình.

Theo mặc định, Next.js sử dụng **React Server Components**. Để sử dụng các tính năng tương tác của máy khách, bạn phải sử dụng **Client Components**.

## Cách sử dụng Client Components

Nếu bạn cố gắng sử dụng các hook như `useState` trong một Server Component, Next.js sẽ báo lỗi. Để khắc phục, bạn cần thêm chỉ thị `'use client'` ở ngay đầu tệp.

Ví dụ về việc tách nút "Like" thành một Client Component riêng biệt:

```tsx
// like-button.js
'use client'; // Đây là ranh giới mạng

import { useState } from 'react';

export default function LikeButton() {
  const [likes, setLikes] = useState(0);

  function handleClick() {
    setLikes(likes + 1);
  }

  return <button onClick={handleClick}>Like ({likes})</button>;
}
```

Sau đó, bạn có thể nhập và sử dụng nó trong trang chính (vẫn là Server Component):

```tsx
// page.js
import LikeButton from './like-button';

export default function HomePage() {
  return (
    <div>
      <h1>Trang chủ</h1>
      <LikeButton />
    </div>
  );
}
```

## Làm mới nhanh (Fast Refresh)

Next.js đi kèm với tính năng **Fast Refresh**, giúp bạn thấy ngay lập tức kết quả của những thay đổi trong mã nguồn trên trình duyệt mà không làm mất trạng thái của ứng dụng.

---

**Tổng kết:** Bạn đã học được sự khác biệt giữa Server và Client Components, cách xác định ranh giới mạng bằng `'use client'` và lợi ích của việc kết hợp cả hai môi trường để tối ưu hiệu suất và tính tương tác.
