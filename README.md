# ORO_AutoQuiz
# HƯỚNG DẪN SỬ DỤNG ORO AUTOMATION TOOL V1.0 (PRO)

## 1. YÊU CẦU HỆ THỐNG
- Đã cài đặt Node.js (Phiên bản 16 trở lên).
- Các thư viện cần thiết: axios, https-proxy-agent, @cosmjs/amino, colors, node-machine-id, bip39.
  Cài Đặt : npm install Hoặc npm install axios https-proxy-agent @cosmjs/amino colors node-machine-id bip39

--------------------------------------------------

## 2. CHI TIẾT CÁC FILE ĐẦU VÀO (INPUT)

Bạn cần tạo các file sau trong cùng thư mục với file tool (index.js):

### A. Config.json (Cấu hình luồng và delay)
{
  "threads": 5,             // Số luồng chạy cùng lúc
  "numAccounts": 500,       // Tổng số ví mục tiêu cần hoàn thành
  "minDelayOp": 3000,       // Delay tối thiểu giữa các bước (ms)
  "maxDelayOp": 10000,      // Delay tối đa giữa các bước (ms)
  "minDelayAcc": 30000,     // Delay tối thiểu khi chuyển ví (ms)
  "maxDelayAcc": 60000,     // Delay tối đa khi chuyển ví (ms)
  "prefix": "zig",          // Tiền tố địa chỉ ví
  "addressType": "cosmos"   // Loại địa chỉ
}

### B. proxy.txt (Danh sách Proxy)
- Định dạng: http://user:pass@ip:port hoặc http://ip:port
- Tool hỗ trợ Hot-reload: Bạn có thể thêm proxy mới khi tool đang chạy.

### C. User_agents.txt (Danh sách trình duyệt giả lập)
- Mỗi dòng một User-Agent (Lấy từ trình duyệt của bạn).

### D. quiz.txt (Dữ liệu giải Quiz)
- Định dạng: Câu hỏi|Đáp án (Phải khớp 100% nội dung trên web)
- Ví dụ:
Before we begin, how would you describe your Web3 experience?|Deep in the trenches. I build or trade actively
When you hear 'Avalanche,' what comes to mind first?|A platform for launching many custom blockchains

--------------------------------------------------

## 3. CHI TIẾT CÁC FILE ĐẦU RA (OUTPUT)

### A. Pk.txt (Danh sách ví thành công)
- Định dạng: Mnemonic (12 từ khóa)|Địa chỉ ví (zig1...)
- LƯU Ý: Chỉ những ví đã hoàn thành 100% nhiệm vụ (đã nhận Credits và ORE) mới được lưu vào file này.

### B. license.txt (Lưu trữ Key)
- Lưu key bản quyền bạn đã nhập lần đầu để không phải nhập lại.

--------------------------------------------------

 HỆ THỐNG LICENSE HWID: 
   Mỗi Key sẽ được khóa chặt vào ID phần cứng (HWID) máy tính của bạn để đảm bảo an toàn.

### CÁCH CHẠY TOOL
1. Chuẩn bị đầy đủ các file đầu vào (txt, json).
2. Mở Terminal/CMD tại thư mục tool.
3. Gõ lệnh: node main.js (hoặc tên file bạn đã lưu).
4. Nhập License Key khi được yêu cầu và nhấn Enter.
