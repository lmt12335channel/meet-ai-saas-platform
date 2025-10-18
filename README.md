Meet AI Platform 🚀

Nền tảng hội nghị video thế hệ tiếp theo được hỗ trợ bởi AI: thông minh hơn, hiệu quả hơn và được tổ chức một cách dễ dàng.

🌟 Tính năng : Khả năng AI, gọi video thời gian thực, trợ lý AI tùy chỉnh, ghi lại và phát lại cuộc họp, hỏi đáp AI về nội dung cuộc họp, tóm tắt cuộc họp thông minh, tích hợp OpenAI, tìm kiếm trong bản ghi (Transcript), tạo bản ghi thông minh, mô hình SaaS với thanh toán, xử lý nền cho các tác vụ AI

🛠️ Công nghệ sử dụng

Framework: Next.js 15, React 19, Tailwind CSS v4
UI Components: shadcn/ui
Xác thực: Better Auth
API & Type Safety: tRPC
Real-time: Stream Video SDK, Stream Chat SDK
Background Jobs: Ingest (background jobs)
Thanh toán: Polar subscriptions
Cơ sở dữ liệu & ORM: Drizzle ORM, PostgreSQL (Neon)
Quản lý gói :

pnpm, npm, hoặc yarn

Triển khai :
⚙️ Biến môi trường
Bạn cần cấu hình các biến môi trường trong tệp .env.local:

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
