# Chương 9: Cài đặt Next.js (Installing Next.js)

Khi sử dụng Next.js, bạn không cần phải nạp các tệp script từ `unpkg.com` nữa. Thay vào đó, bạn sẽ cài đặt các gói này cục bộ bằng npm.

## Cài đặt cục bộ

1. **Yêu cầu**: Đảm bảo máy tính của bạn đã cài đặt Node.js phiên bản 18.17.0 trở lên.
2. **Khởi tạo**: Tạo một tệp `package.json` với nội dung `{}` trong thư mục dự án của bạn.
3. **Cài đặt**: Chạy lệnh sau trong terminal:
   ```bash
   npm install react@latest react-dom@latest next@latest
   ```

## Cấu trúc lại mã nguồn cho Next.js

Bây giờ bạn có thể xóa các thành phần HTML rườm rà trong tệp `index.html` vì Next.js sẽ tự động xử lý chúng:
- Xóa thẻ `<html>`, `<body>`.
- Xóa thẻ `<div id="app">`.
- Xóa các script React, ReactDOM và Babel.
- Thay đổi phần mở rộng tệp từ `.html` sang `.js` hoặc `.jsx`.

Mã nguồn mới của bạn sẽ bắt đầu bằng việc import:
```tsx
import { useState } from 'react';

function Header({ title }) {
  return <h1>{title ? title : 'Default title'}</h1>;
}

export default function HomePage() {
  const [likes, setLikes] = useState(0);
  // ... phần còn lại của component
}
```

## Tạo trang đầu tiên của bạn

Next.js sử dụng hệ thống định tuyến dựa trên hệ thống tệp (file-system routing):
1. Tạo một thư mục có tên là `app`.
2. Di chuyển tệp JavaScript của bạn vào thư mục `app` và đổi tên nó thành `page.js`.
3. Đảm bảo bạn đã thêm `export default` cho thành phần chính (`HomePage`).

## Chạy máy chủ phát triển (Development Server)

Thêm tập lệnh `dev` vào tệp `package.json`:
```json
{
  "scripts": {
    "dev": "next dev"
  },
  "dependencies": {
    "next": "^latest",
    "react": "^latest",
    "react-dom": "^latest"
  }
}
```

Bây giờ, hãy chạy lệnh `npm run dev` trong terminal và truy cập `http://localhost:3000`.

**Lưu ý:** Bạn có thể gặp lỗi về `useState`. Điều này là do Next.js mặc định sử dụng **React Server Components**. Chúng ta sẽ khắc phục điều này trong chương tiếp theo bằng cách tìm hiểu về Server và Client Components.

---

**Tổng kết:** Bạn đã chuyển đổi thành công từ một ứng dụng React chạy trên trình duyệt sang một dự án Next.js chuyên nghiệp với cấu hình tối giản.
