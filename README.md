Meet AI Platform 🚀

Nền tảng hội nghị video thế hệ tiếp theo được hỗ trợ bởi AI: thông minh hơn, hiệu quả hơn và được tổ chức một cách dễ dàng.

🌟 Tính năng

Chức năng cốt lõi

Khả năng AI

Gọi video thời gian thực

Trợ lý AI tùy chỉnh

Ghi lại và phát lại cuộc họp

Hỏi đáp AI về nội dung cuộc họp

Tóm tắt cuộc họp thông minh

Tích hợp OpenAI

Tìm kiếm trong bản ghi (Transcript)

Tạo bản ghi thông minh

Mô hình SaaS với thanh toán

Xử lý nền cho các tác vụ AI

🛠️ Công nghệ sử dụng

Lĩnh vực

Công nghệ

Framework

Next.js 15, React 19, Tailwind CSS v4

UI Components

shadcn/ui

Xác thực

Better Auth

API & Type Safety

tRPC

Real-time

Stream Video SDK, Stream Chat SDK

Background Jobs

Ingest (background jobs)

Thanh toán

Polar subscriptions

Cơ sở dữ liệu & ORM

Drizzle ORM, PostgreSQL (Neon)

Quản lý gói

pnpm, npm, hoặc yarn

Triển khai

Vercel

📐 Sơ đồ kiến trúc

flowchart TD
    User[Người dùng] -->|Đăng nhập/Đăng ký| NextJS[Ứng dụng Next.js]
    NextJS -->|Gọi API| AuthAPI[Better Auth API]
    NextJS -->|Video/Chat| StreamSDK[Stream Video/Chat SDK]
    NextJS -->|AI| OpenAI[OpenAI API]
    NextJS -->|Thanh toán| Polar[Polar API]
    NextJS -->|Xử lý nền| Ingest[Ingest Jobs]
    NextJS -->|Cơ sở dữ liệu| Drizzle[Drizzle ORM]


🔐 Luồng xác thực

sequenceDiagram
    participant U as Người dùng
    participant FE as Next.js Frontend
    participant BA as Better Auth API
    participant DB as Cơ sở dữ liệu

    U->>FE: Gửi thông tin đăng nhập/đăng ký
    FE->>BA: POST /api/auth
    BA->>DB: Xác thực hoặc tạo người dùng mới
    DB-->>BA: Dữ liệu người dùng / Token
    BA-->>FE: Token xác thực (Session)
    FE-->>U: Thiết lập session, chuyển hướng đến trang chính


📦 Các Endpoints chính (API)

Vì dự án sử dụng tRPC, các "endpoints" được quản lý thông qua các procedure được định nghĩa sẵn thay vì các API RESTful truyền thống. Dưới đây là mô tả các procedure chính:

Procedure

Loại

Mô tả

meetings.getAll

Query

Lấy danh sách các cuộc họp của người dùng

meetings.create

Mutation

Tạo một cuộc họp mới

agents.getAll

Query

Lấy danh sách các trợ lý AI của người dùng

agents.create

Mutation

Tạo một trợ lý AI mới

payments.subscribe

Mutation

Xử lý việc đăng ký gói dịch vụ qua Polar

meetings.summary

Query

Lấy tóm tắt AI của một cuộc họp

⚙️ Biến môi trường

Bạn cần cấu hình các biến môi trường trong tệp .env.local:

Biến

Mô tả

DATABASE_URL

Chuỗi kết nối đến PostgreSQL từ Neon

BETTER_AUTH_SECRET

Khóa bí mật cho Better Auth

BETTER_AUTH_URL

URL của ứng dụng cho Better Auth

POLAR_ACCESS_TOKEN

Khóa truy cập cho Polar (sandbox)

NEXT_PUBLIC_STREAM_VIDEO_API_KEY

Khóa API public của Stream Video

STREAM_VIDEO_SECRET_KEY

Khóa bí mật của Stream Video

NEXT_PUBLIC_STREAM_CHAT_API_KEY

Khóa API public của Stream Chat

STREAM_CHAT_SECRET_KEY

Khóa bí mật của Stream Chat

INGEST_EVENT_KEY

Khóa sự kiện của Ingest

INGEST_SIGNING_KEY

Khóa ký của Ingest

OPENAI_API_KEY

Khóa API của OpenAI

🚀 Bắt đầu

Yêu cầu

Node.js 18.18+

pnpm (khuyến nghị)

Tài khoản và API keys từ các dịch vụ: Neon, Better Auth, Polar, Stream, Ingest, OpenAI.

Cài đặt

# Clone kho lưu trữ
git clone [https://github.com/lmt12335channel/meet-ai-saas.git](https://github.com/lmt12335channel/meet-ai-saas.git)
cd meet-ai-saas

# Cài đặt các gói phụ thuộc (chọn một)
pnpm install
# hoặc
npm install
# hoặc
yarn

# Thiết lập biến môi trường
cp .env.example .env.local

# Chạy máy chủ phát triển
pnpm dev

# Chạy Ingest Dev Server trong một terminal khác
npx inngest-cli dev


Mở http://localhost:3000 trên trình duyệt để xem kết quả.

🧩 Sử dụng shadcn/ui

Các component có thể tái sử dụng được đặt tại src/components/ui/.

Ví dụ:

import { Button } from "@/components/ui/button";

<Button variant="primary">Bắt đầu cuộc họp</Button>;
