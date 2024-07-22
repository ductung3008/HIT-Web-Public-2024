<!-- CSS selector
Thứ tự ưu tiên trong CSS
Block Element Modifier (BEM)
Nhúng icon, font -->

# Nội dung buổi 3

## **I. CSS Selector**

[**CSS Selector - w3schools**](https://www.w3schools.com/cssref/css_selectors.php)

CSS Selector là cách chúng ta chọn phần tử HTML mà chúng ta muốn áp dụng CSS.

![CSS](./selector.png)

### 1. Selector cơ bản

-   **Element Selector**: chọn tất cả các phần tử có tên là `element`

```css
p {
    color: red;
}
```

-   **ID Selector**: chọn phần tử có `id` là `id`

```css
#id {
    color: red;
}
```

-   **Class Selector**: chọn tất cả các phần tử có `class` là `class`

```css
.class {
    color: red;
}
```

-   **Universal Selector**: chọn tất cả các phần tử

```css
* {
    color: red;
}
```

### 2. Selector kết hợp

```html
<div class="wrapper">
    <div class="heading">
        <h1 class="title">Title</h1>
        <h2 class="sub-title">Sub title</h2>
    </div>
    <div class="content">
        <p class="para first-para">First paragraph</p>
        <p class="para second-para">Second paragraph</p>
        <p class="third-para">Third paragraph</p>
    </div>
</div>
<p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatum, nulla!
</p>
```

#### 2.1. **Grouping Selector**: chọn tất cả các phần tử có tên là `element1` hoặc `element2` hoặc `element3`

```css
h1,
h2,
p {
    color: red;
}
```

#### 2.2. **Descendant Selector**: chọn tất cả các phần tử con của phần tử có tên là `element`

```css
div p {
    color: red;
}
```

#### 2.3. **Child Selector**: chọn tất cả các phần tử con trực tiếp của phần tử có tên là `element`

```css
div > p {
    color: red;
}
```

#### 2.4. **Sibling Selector**

-   **Adjacent Sibling Selector**: chọn phần tử cùng cấp đầu tiên sau phần tử có tên là `element`

```css
h1 + p {
    color: red;
}
```

-   **General Sibling Selector**: chọn tất cả các phần tử cùng cấp sau phần tử có tên là `element`

```css
h1 ~ p {
    color: red;
}
```

#### 2.5. **Pseudo-class Selector**: chọn phần tử trong trạng thái cụ thể

```html
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
    <li>Item 4</li>
    <li>Item 5</li>
</ul>
```

-   Sử dụng `:first-child` để chọn phần tử đầu tiên

```css
li:first-child {
    color: red;
}
```

-   Sử dụng `:last-child` để chọn phần tử cuối cùng

```css
li:last-child {
    color: red;
}
```

-   Sử dụng `:nth-child(n)` để chọn phần tử thứ `n`

```css
li:nth-child(3) {
    color: red;
}
li:nth-child(odd) {
    color: red;
}
li:nth-child(even) {
    color: red;
}
```

-   Sử dụng `:not(selector)` để chọn tất cả các phần tử không phải là `selector`

```css
li:not(:first-child) {
    color: red;
}
```

-   Sử dụng `:hover` để chọn phần tử sẽ được style khi di chuột vào

```css
li:hover {
    color: red;
}
```

## **II. Thứ tự ưu tiên trong CSS**

[CSS Specificity - w3schools](https://www.w3schools.com/css/css_specificity.asp)

| Selector     | Thứ tự ưu tiên | Điểm |
| ------------ | -------------- | ---- |
| !important   | 1              | ∞    |
| Inline style | 2              | 1000 |
| ID           | 3              | 100  |
| Class        | 4              | 10   |
| Element      | 5              | 1    |

## **III. Block Element Modifier (BEM)**

### 1. Khái niệm

-   BEM là một quy ước đặt tên class giúp chúng ta quản lý CSS dễ dàng hơn
-   BEM bao gồm 3 phần chính: Block, Element, Modifier
-   **Block**: tên của thành phần
-   **Element**: tên của phần tử bên trong block
-   **Modifier**: trạng thái của block hoặc element

![BEM](./bem.png)

### 2. Tại sao cần sử dụng BEM?

-   Dễ dàng quản lý CSS
-   Tăng khả năng tái sử dụng CSS
-   Trong một dự án, có thể có nhiều người cùng làm việc, việc đặt tên class đồng nhất sẽ giúp dễ dàng hơn trong việc hiểu code của người khác

### 3. Cú pháp đặt tên class

-   .block
-   .block\_\_element
-   .block--modifier
-   .block\_\_element--modifier

```html
<div class="card">
    <img class="card__image" src="image.jpg" alt="Image" />
    <div class="card__content">
        <h2 class="card__title">Title</h2>
        <p class="card__description">Description</p>
        <button class="card__button card__button--red">Click me</button>
        <button class="card__button card__button--disable">
            Disable button
        </button>
    </div>
</div>
```

```css
.card {
    width: max-content;
    background-color: #f1f1f1;
}
.card__image {
    width: 100%;
    max-width: 200px;
}
.card__content {
    padding: 10px;
}
.card__title {
    font-size: 20px;
}
.card__description {
    font-size: 16px;
}
.card__button {
    padding: 5px 10px;
}
.card__button--red {
    background-color: red;
    color: white;
}
.card__button--disable {
    background-color: gray;
    color: white;
    cursor: not-allowed;
}
```

## **IV. Nhúng icon, font**

### 1. Nhúng icon

-   Sử dụng thư viện [Font Awesome](https://fontawesome.com/)

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>Document</title>
        <link
            rel="stylesheet"
            href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css"
        />
    </head>
</html>
```

```html
<i class="fas fa-home"></i>
```

### 2. Nhúng font

-   Sử dụng thư viện [Google Fonts](https://fonts.google.com/)

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>Document</title>
        <link
            rel="stylesheet"
            href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap"
        />
    </head>
</html>
```

```css
body {
    font-family: "Roboto", sans-serif;
}
```
