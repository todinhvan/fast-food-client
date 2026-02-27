# FAFO Frontend Client

Chào mừng đến với Front-end của dự án **FAFO**. Đây là ứng dụng phía người dùng (Client) được thiết kế hiện đại, cung cấp giao diện tương tác mượt mà và trực quan.

## 🚀 1. Giới thiệu Project

**FAFO Client** là một Single Page Application (SPA) xây dựng bằng hệ sinh thái React. Dự án tập trung vào việc mang lại trải nghiệm người dùng (UX) tối ưu, hiệu năng cao và dễ dàng bảo trì mở rộng.

## 🛠️ 2. Tài liệu kỹ thuật và công nghệ sử dụng

Dự án sử dụng các công nghệ và thư viện tiên tiến nhất trong hệ sinh thái Front-end hiện nay:

- **Core:**
  - **⚛️ React 19:** Thư viện UI cốt lõi.
  - **⚡ Vite:** Build tool cực kỳ nhanh nhẹn, tối ưu hóa quá trình phát triển.
  - **📘 TypeScript:** Đảm bảo type-safety, giảm thiểu lỗi runtime và cải thiện trải nghiệm Developer (DX).

- **Styling & UI Components:**
  - **🎨 Tailwind CSS v4:** Utility-first CSS framework để styling nhanh chóng và linh hoạt.
  - **🧩 Radix UI:** Các component unstyled có khả năng truy cập (accessibility) cao, là nền tảng cho hệ thống UI (Dialog, Select, Tabs, Popover...).
  - **💅 Class Variance Authority & Tailwind Merge:** Quản lý và gộp các class CSS linh hoạt.
  - **🌙 Next Themes:** Quản lý giao diện Sáng/Tối (Light/Dark mode) dễ dàng.

- **State Management & Data Fetching:**
  - **📡 React Query (TanStack Query):** Cache và đồng bộ dữ liệu server state. Áp dụng `@tanstack/react-query`.
  - **🌐 Axios:** HTTP Client để tương tác với các RESTful APIs từ backend.
  - **🧠 Immer:** Xử lý immutable state đơn giản hơn.
- **Form & Validation:**
  - **📝 React Hook Form:** Quản lý state của forms tối ưu hiệu năng.
  - **✅ Zod:** Xác thực schema (schema validation) mạnh mẽ, kết hợp với `@hookform/resolvers`.

- **Các chức năng khác:**
  - **🔄 React Router v7:** Quản lý điều hướng (routing) trong ứng dụng SPA.
  - **🔌 Socket.io-client:** Kết nối WebSockets thời gian thực để nhận cập nhật.
  - **📊 Recharts:** Vẽ biểu đồ thống kê trực quan.
  - **🛡️ DOMPurify:** Sanitize HTML để phòng chống tấn công XSS.
  - **🔔 Sonner:** Hệ thống thông báo toast notification hiện đại.
  - **🗓️ Date-fns & React-day-picker:** Xử lý và hiển thị ngày tháng/lịch.

## 📂 3. Cấu trúc dự án

Dưới đây là cây thư mục (folder tree) chính bên trong thư mục `src/`:

```text
src/
 ├── apis/               # Chứa các hàm gọi HTTP request qua Axios tới Backend
 ├── assets/             # Hình ảnh tĩnh, SVG, fonts và các tài nguyên đa phương tiện khác
 ├── components/         # Các UI components dùng chung trên toàn hệ thống (Button, Input, Table...)
 ├── constants/          # Chứa các hằng số, cấu hình tĩnh của ứng dụng
 ├── hooks/              # Custom React Hooks sử dụng lại logic
 ├── layouts/            # Layout bao bọc các page (vd: MainLayout, AuthLayout, DashboardLayout)
 ├── lib/                # Chứa các hàm utility xử lý chung, cấu hình thư viện
 ├── pages/              # Các trang/màn hình chính của hệ thống được load dựa trên Route
 │    ├── client/        # App Khách hàng (B2C)
 │    │    ├── Home/           # Trang chủ giới thiệu
 │    │    ├── Product/        # Danh sách sản phẩm
 │    │    ├── ProductDetail/  # Chi tiết một sản phẩm
 │    │    ├── Cart/           # Giỏ hàng
 │    │    ├── Checkout/       # Đặt hàng và thanh toán
 │    │    ├── Reservation/    # Đặt bàn trước
 │    │    ├── Profile/        # Trang cá nhân của user
 │    │    ├── Login/, Register/, ForgotPassword/ # Luồng xác thực
 │    │    └── OAuth/, PaymentCallback/            # Xử lý Callback
 │    ├── employee/      # App Nhân viên (POS & Operations)
 │    │    ├── Order/          # Quản lý Đơn hàng (Tiếp nhận/Hủy)
 │    │    ├── Kitchen/        # Màn hình cho Bếp (Trạng thái món)
 │    │    ├── Delivery/       # Vận chuyển/Giao hàng
 │    │    ├── Table/          # Quản lý Trạng thái Bàn ăn thực tế
 │    │    ├── Reservation/    # Quản lý danh sách Đặt bàn
 │    │    └── More/           # Các thiết lập mở rộng khác
 │    └── manage/        # App Quản trị hệ thống (Admin Dashboard)
 │         ├── Dashboard/      # Trang tổng quan thống kê
 │         ├── Product/        # Quản lý Sản phẩm
 │         ├── Category/       # Quản lý Danh mục
 │         ├── Tag/            # Quản lý Nhãn/Tag
 │         ├── Order/          # Tổng quan toàn bộ đơn hàng
 │         ├── Table/ & Reservation/ # Quản lý bàn và đặt bàn hệ thống
 │         ├── Coupon/         # Quản lý mã giảm giá
 │         ├── User/           # Quản lý người dùng
 │         ├── Role/           # Quản lý vai trò (Roles & Permissions)
 │         ├── Setting/        # Cài đặt hệ thống
 │         └── Login/          # Đăng nhập Admin
 ├── queries/            # Khai báo React Query Hooks (useQuery, useMutation) để lấy và cập nhật dữ liệu
 ├── schemaValidations/  # Chứa các Zod Schema dùng cho Form Validation
 ├── types/              # Khai báo TypeScript Interfaces và Types của dự án
 ├── App.tsx             # Root component của ứng dụng
 ├── index.css           # File CSS toàn cục chính, import Tailwind directives
 ├── main.tsx            # Điểm entry chính của Vite để render React App
 └── useRouteElements.tsx # Cấu hình và khai báo các Routes cho ứng dụng
```

## ⚙️ 4. Hướng dẫn cài đặt và sử dụng

### 📌 Yêu cầu môi trường

- NodeJS (Khuyến nghị bản LTS như 20.x hoặc 22.x)

### 🚀 Các bước cài đặt

**1. Cài đặt các thư viện (Dependencies):**
Di chuyển vào thư mục `fafo_client` và chạy lệnh sau để tải các packages cần thiết:

```bash
npm install
```

**2. Khởi chạy ở môi trường phát triển (Development):**
Khởi động development server bằng Vite:

```bash
npm run dev
```

> Trình duyệt có thể tự động mở hoặc bạn truy cập đường dẫn hiển thị trên terminal (VD: `http://localhost:5173`).

**3. Khởi chạy bằng mạng LAN:**
Nếu bạn cần xem client qua các thiết bị khác trong LAN (VD: Kiểm tra trên điện thoại):

```bash
npm run dev -- --host
```

**4. Build ứng dụng cho môi trường Production:**

```bash
npm run build
```

Lệnh này sẽ dùng TypeScript kiểm tra lỗi (`tsc -b`) trước khi Vite tiến hành build source code. Phiên bản build sẽ nằm ở thư mục `dist/`.

**5. Chạy thử bản production build:**

```bash
npm run preview
```

Để kiểm tra lại kết quả build nội bộ trước khi publish lên các server như Nginx, Vercel, hay Netlify.
