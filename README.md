# 💳 Demo Tích Hợp Thanh Toán MoMo trong WebApp Spring Boot

Dự án này minh họa cách tích hợp cổng thanh toán **MoMo** vào một website bán hàng đơn giản sử dụng **Spring Boot (ASP.NET MVC)**.

---

## 🌐 Tính năng

* Giao diện mäu thuọc client ASP.NET
* Giỏ hàng đơn giản (Cart)
* Trang danh sách sản phẩm
* Thanh toán qua cổng **MoMo Payment Gateway**
* Kiểm tra kết quả thanh toán thông qua `returnUrl`/`notifyUrl`

---

## 🚀 Cách chạy local

### 1. Cài đặt

* IDE: Visual Studio 2019+ hoặc Rider
* MoMo Dev account: [https://business.momo.vn/](https://business.momo.vn/)

### 2. Cấu hình trong file `Web.config`

```xml
<appSettings>
  <add key="partnerCode" value="YOUR_PARTNER_CODE" />
  <add key="accessKey" value="YOUR_ACCESS_KEY" />
  <add key="secretKey" value="YOUR_SECRET_KEY" />
  <add key="returnUrl" value="http://localhost:xxxx/Home/ReturnUrl" />
  <add key="notifyUrl" value="http://localhost:xxxx/Home/NotifyUrl" />
</appSettings>
```

### 3. Chạy project

* Build project
* Mở URL: `http://localhost:xxxx`
* Chọn sản phẩm → Thêm vào giỏ hàng → Nhấn "Thanh Toán qua MoMo"

---

## 📄 Cáu trúc

```
ThanhToanMoMo/
├── Controllers/
│   ├── CartController.cs
│   ├── HomeController.cs
│   └── SanPhamController.cs
├── Models/
│   ├── CartItemDetail.cs
│   └── MyData.dbml (DataContext)
├── Views/
│   ├── Home/Index.cshtml
│   └── Cart/Checkout.cshtml
├── Web.config (thông tin MoMo)
└── Global.asax
```

---

## 🔧 Cách test thanh toán

* Dùng tài khoản MoMo Sandbox test
* Xem log/response từ MoMo trong phương thức `PaymentResponse`
* Có thể log ra file hoặc console để debug

---

## 🌟 Mở rộng

* Triển khai webhook thực tế tại `Home/NotifyUrl`
* Thêm gửi mail khi thanh toán thành công
* Lưu lịch sử giao dịch MoMo vào database

---

## 📘 Tài liệu tham khảo

* [MoMo Developer Guide](https://developers.momo.vn/v3/docs/payment/api/overview/)
* [Sample Code từ MoMo](https://github.com/momo-wallet)

---

> ✨ *Repo này được tạo nhằm demo quy trình tích hợp thanh toán MoMo đơn giản nhất cho người mới.*
