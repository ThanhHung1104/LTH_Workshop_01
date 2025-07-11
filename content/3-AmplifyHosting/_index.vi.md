---
title : "Thiết lập AWS Amplify Hosting"
date : 2025-06-15
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

## **Thiết lập AWS Amplify Hosting**

Bạn đã chuẩn bị mã nguồn frontend trên GitHub. Bây giờ, chúng ta sẽ kết nối nó với AWS Amplify Hosting để triển khai ứng dụng.

### **1. Truy cập AWS Amplify và kết nối Repository**

1.  **Đăng nhập vào AWS Management Console.**
2.  Tìm và chọn dịch vụ **AWS Amplify**.
3.  Tại trang chính của Amplify Console, nhấn vào nút **"Deploy an app"**.
![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/ah_1.png) 

#### **Bước 1: Chọn Nhà cung cấp mã nguồn và nhánh**

1.  Trong phần **Connect repository**, chọn nhà cung cấp mã nguồn của bạn (ví dụ: **GitHub**).
2.  Nhấn nút **Next**.
    * *Lưu ý:* Amplify sẽ yêu cầu bạn cấp quyền truy cập vào tài khoản GitHub của bạn. Vui lòng cấp quyền và ủy quyền theo hướng dẫn của GitHub.
  ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/ah_2.png) 

#### **Bước 2: Chọn Repository và Branch**

1.  Sau khi cấp quyền, bạn sẽ thấy danh sách các kho lưu trữ của mình.
2.  Chọn kho lưu trữ của bạn (ví dụ: **`ThanhHung1104/realtime-chat-frontend`**).
3.  Trong phần **Branch**, chọn nhánh mà bạn muốn triển khai (ví dụ: **`main`** hoặc **`master`**).
4.  Nhấn nút **Next**.
    ![ConnectPrivate]https://ThanhHung1104.github.io/LTH_Workshop_01(/images/ah_3.png) 
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/ah_4.png) 

#### **Bước 3: Cấu hình Cài đặt Ứng dụng**

1.  Trong phần **App name**, tên ứng dụng sẽ được điền tự động (ví dụ: **`realtime-chat-app-frontend`**). Bạn có thể thay đổi nếu muốn.
2.  Các cài đặt **Build settings** sẽ được Amplify tự động phát hiện (ví dụ: `Frontend build command: npm run build`, `Build output directory: build`). Vui lòng kiểm tra lại để đảm bảo chính xác.
3.  Nhấn nút **Next**.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/ah_5.png) 

#### **Bước 4: Xem lại và Triển khai**

1.  Kiểm tra lại tất cả các cấu hình bạn đã chọn trong phần **Review**.
2.  Nhấn nút **Save and deploy**.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/ah_6.png) 

### **2. Triển khai Thành công và Truy cập Ứng dụng**

Sau khi nhấn **Save and deploy**, bạn sẽ được chuyển đến trang trạng thái triển khai của ứng dụng.

* Hệ thống sẽ bắt đầu quá trình **Provisioning**, **Building**, và **Deploying**. Vui lòng chờ cho đến khi tất cả các giai đoạn chuyển sang trạng thái **"Deployed"** (màu xanh lá cây). Quá trình này có thể mất vài phút.
* Khi triển khai hoàn tất, bạn sẽ nhận được một **URL Domain** được cấp tự động bởi AWS Amplify.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/ah_7.png) 

* **Truy cập vào Domain được cấp:** `https://master.d285j22zzz8mbh.amplifyapp.com/`
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/ah_8.png) 

**Kết luận:**

Bạn đã **thành công triển khai frontend** của ứng dụng chat thời gian thực và chạy nó bằng công cụ **AWS Amplify Hosting**. Kể từ bây giờ, bạn có thể **cập nhật code** trên kho lưu trữ GitHub của mình, và AWS Amplify Hosting sẽ tự động kích hoạt quá trình build và triển khai mới, giữ cho ứng dụng của bạn luôn được cập nhật.

---