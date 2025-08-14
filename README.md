Larisa Shop - Headless Commerce & Storytelling với Next.js & Crystallize

### Mô tả

Đây là một ứng dụng web cho "Larisa Shop", được xây dựng như một nền tảng thương mại điện tử headless và kể chuyện bằng nội dung phong phú. Dự án tận dụng sức mạnh của **Crystallize** cho việc quản lý thông tin sản phẩm (PIM) và quản lý nội dung (CMS), kết hợp với một frontend hiện đại và tốc độ cao được xây dựng bằng **Next.js**.

Dự án này dựa trên boilerplate "Content and Commerce" chính thức của Crystallize, nhằm minh họa cách xây dựng các trang thương mại điện tử đẹp mắt với các bài viết kể chuyện dạng dài (long-form).

### Các tính năng chính

*   **Kiến trúc Headless:** Frontend (Next.js) được tách biệt hoàn toàn khỏi backend (Crystallize), cho phép phát triển và mở rộng linh hoạt.
*   **Danh mục sản phẩm:** Một trang cửa hàng (`/shop`) đầy đủ tính năng để hiển thị sản phẩm.
*   **Kể chuyện bằng nội dung (Content Storytelling):** Một mục "stories" (`/stories`) chuyên dụng để đăng các bài viết, lookbook, hoặc nội dung marketing khác, có khả năng liên kết liền mạch đến các sản phẩm.
*   **Trang chủ động:** Bố cục trang chủ được quản lý một cách trực quan bằng **Crystallize Grids**, cho phép dễ dàng cập nhật giao diện mà không cần thay đổi mã nguồn.
*   **Hiệu suất cao:** Tận dụng các tính năng của Next.js như Static Site Generation (SSG) và Incremental Static Regeneration (ISR) để tải trang nhanh và tối ưu SEO.
*   **Sử dụng GraphQL:** Toàn bộ dữ liệu được lấy từ các API GraphQL mạnh mẽ của Crystallize.

### Công nghệ sử dụng

*   **Frontend:** [Next.js](https://nextjs.org/) (React Framework)
*   **Backend (Headless CMS/PIM):** [Crystallize](https://crystallize.com/)
*   **Styling:** [styled-components](https://styled-components.com/)
*   **API:** [GraphQL](https://graphql.org/)

### Hướng dẫn cài đặt

Để chạy dự án này trên máy cục bộ (local), hãy làm theo các bước sau:

1.  **Sao chép (clone) repository:**
    ```bash
    git clone https://github.com/ten-cua-ban/larisa-shop.git
    cd larisa-shop/create
    ```

2.  **Cài đặt các gói phụ thuộc:**
    ```bash
    npm install
    ```

3.  **Thiết lập tenant trên Crystallize:**
    *   Tạo một tenant miễn phí trên [Crystallize](https://crystallize.com/).
    *   Bạn nên khởi tạo (bootstrap) tenant của mình với mẫu "Furniture" hoặc một mẫu tương tự để có dữ liệu mẫu.

4.  **Cấu hình biến môi trường:**
    *   Tạo một tệp tin có tên `.env.local` trong thư mục `create`.
    *   Thêm định danh (identifier) tenant Crystallize của bạn vào đó:
        ```
        NEXT_PUBLIC_CRYSTALLIZE_TENANT_IDENTIFIER=dinh-danh-tenant-cua-ban
        ```

5.  **Cập nhật nguồn dữ liệu (Quan trọng):**
    Boilerplate này có thể chứa các đường dẫn (path) hoặc ID được ghi cứng, trỏ đến tenant demo ban đầu. Bạn có thể cần phải cập nhật chúng để khớp với dữ liệu trong tenant của mình:
    *   **Grid Trang chủ:** Trong `pages/index.js`, cập nhật Grid ID trong câu truy vấn GraphQL.
    *   **Trang Shop & Stories:** Trong `pages/shop/index.js` và `pages/stories/index.js`, hãy đảm bảo `path` trong truy vấn GraphQL (`/shop`, `/stories`) khớp với đường dẫn của các thư mục tương ứng trong catalogue Crystallize của bạn.

6.  **Chạy máy chủ phát triển (development server):**
    ```bash
    npm run dev
    ```

Mở [http://localhost:3000](http://localhost:3000) trên trình duyệt để xem kết quả.
