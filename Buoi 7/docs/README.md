<!-- CSS Grid
Responsive -->

# Nội dung buổi 7

## **I. CSS Grid**

![grid](./grid.png)

-   **CSS Grid** là một hệ thống layout mạnh mẽ, linh hoạt, giúp chúng ta xây dựng layout web một cách dễ dàng và nhanh chóng.

-   **Cú pháp**:

    ```css
    .container {
        display: grid;
        grid-template-columns: value;
        grid-template-rows: value;
        grid-template-areas: value;
        grid-gap: value;
    }
    ```

### 1. Tổng quan về CSS Grid

-   **Grid Container**: Phần tử chứa grid, được thiết lập thuộc tính `display: grid`.

-   **Grid Item**: Các phần tử con của grid container.

-   **Grid Row**: Hàng trong grid.

-   **Grid Column**: Cột trong grid.

-   **Grid Line**: Đường dọc hoặc ngang chia grid thành các phần bằng nhau.

-   **Grid Track**: Khoảng giữa hai grid line.

-   **Grid Cell**: Một ô trong grid.

-   **Grid Area**: Một nhóm các ô trong grid.

-   **Grid Gap**: Khoảng cách giữa các ô trong grid.

-   **Grid Template**: Xác định layout của grid.

![grid-terms](./grid-terms.png)

### 2. Cách sử dụng CSS Grid

-   **Khai báo một grid container**:

    ```css
    .container {
        display: grid;
    }
    ```

-   **Khai báo số cột và số hàng**:

    Cú pháp: `grid-template-columns: value;` và `grid-template-rows: value;`.

    ```css
    .container {
        display: grid;
        grid-template-columns: 100px 100px 100px;
        grid-template-rows: 100px 100px 100px;
    }
    ```

    Có thể sử dụng các đơn vị đo lường khác nhau như `px`, `%`, `fr`, ...

    **Note**: Trong Grid, **`fr` - fractional unit** là một đơn vị đo lường linh hoạt, tự động chia đều không gian còn lại.

    Ví dụ về sử dụng `fr`:

    ```css
    .container {
        display: grid;
        grid-template-columns: 1fr 2fr 1fr;
    }
    ```

    Shorthand: `grid-template: rows / columns;`.

    repeat() function: `grid-template-columns: repeat(3, 1fr);`.

-   **Khoảng cách giữa các ô trong grid**:

    Gồm 2 thuộc tính: `grid-row-gap` và `grid-column-gap`.

    Shorthand: `grid-gap: row-gap column-gap;` hoặc `grid-gap: value;`.

    ```css
    .container {
        display: grid;
        grid-gap: 10px;
    }
    ```

-   **Khai báo layout của grid**:

    -   **`grid-area`**: Xác định vị trí của một ô trong grid.

        ```css
        .item {
            grid-column: column-start / column-end;
            grid-row: row-start / row-end;
            grid-area: row-start / column-start / row-end / column-end;
        }
        ```

        Ví dụ:

        ```css
        .item {
            grid-area: 1 / 1 / 3 / 3;
        }
        ```

        Span rows hoặc columns:

        ```css
        .item {
            grid-row: 1 / span 2;
            grid-column: 1 / span 2;
            grid-area: 1 / 1 / span 2 / span 2;
        }
        ```

    -   **`grid-template-areas`**: Xác định layout của grid bằng cách đặt tên cho các ô.

        ```css
        .container {
            display: grid;
            grid-template-areas:
                'header header header'
                'main main sidebar'
                'footer footer footer';
        }

        .header {
            grid-area: header;
        }

        .main {
            grid-area: main;
        }

        .sidebar {
            grid-area: sidebar;
        }

        .footer {
            grid-area: footer;
        }
        ```

-   Ngoài ra, còn có sử dụng `align-items`, `justify-items`, `align-content`, `justify-content`, `align-self`, `justify-self` để căn chỉnh vị trí của các ô trong grid.

### 3. Luyện tập

[CSS Grid Complete Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)

[CSS Grid Example](https://gridbyexample.com/examples/)

[CSS Grid Garden](https://cssgridgarden.com/#vi)

## **II. Responsive Web Design**

![rwd](./rwd.png)

-   **Responsive Web Design (RWD)** là một phương pháp thiết kế web giúp trang web hiển thị tốt trên mọi thiết bị và kích thước

-   **Cách thức hoạt động**:

    -   Sử dụng các đơn vị đo lường linh hoạt như `%`, `em`, `rem`, ...

    -   Sử dụng Media Queries để thay đổi layout, font-size, màu sắc, ...

    -   Sử dụng Flexbox hoặc CSS Grid để xây dựng layout linh hoạt.

-   **Media Queries**:

    -   **Cú pháp**:

        ```css
        @media screen and (max-width: value) {
            /* CSS properties */
        }
        ```

    -   **Ví dụ**:

        ```css
        @media screen and (max-width: 768px) {
            .container {
                grid-template-columns: 1fr;
            }
        }
        ```

    -   **Breakpoints**:

        -   **Extra small devices**: `0px` - `575px`.

        -   **Small devices**: `576px` - `767px`.

        -   **Medium devices**: `768px` - `991px`.

        -   **Large devices**: `992px` - `1199px`.

        -   **Extra large devices**: `1200px` trở lên.
