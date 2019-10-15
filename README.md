# CGDN-Bootstrap
###  Meta là gì ? Viewport ? content ? initial-scale ?
```
<meta name = "viewport" content = "width=device-width, initial-scale = 1, shrink-to-fit = no">
```
+ Viewport
Viewport tạm dịch là khung nhìn, là khu vực có thể nhìn thấy của người dùng về nội dung trong một trang web. Viewport sẽ khác nhau với các thiết bị khác nhau, và sẽ nhỏ hơn trên điện thoại di động so với trên màn hình máy tính. Trước khi thiết kế cho máy tính bảng và điện thoại di động, các trang web chỉ được thiết kế cho màn hình máy tính và thông thường các trang web có thiết kế tĩnh và có kích thước cố định. Sau đó, khi chúng ta bắt đầu lướt web bằng cách sử dụng máy tính bảng và điện thoại di động, các trang web có kích thước cố định đã quá lớn để phù hợp với người dùng. Để khắc phục điều này, các trình duyệt trên các thiết bị này tự động thu nhỏ toàn bộ trang web để vừa với màn hình. Khi chiều ngang của thiết bị quá nhỏ, người dùng phải vuốt ngang để xem hết nội dung của trang web hoặc xem trang web với nội dung quá nhỏ và cần phải zoom để đọc được nội dung 
+ Thẻ <meta> viewport thiết lập cho trang web hiển thị tương ứng với kích thước của từng thiết bị khác nhau.
+ Thuộc tính width=device-width đặt chiều rộng của trang web theo chiều rộng màn hình của thiết bị.
+ Thuộc tính initial-scale=1.0 thiết lập mức độ phóng ban đầu khi trang được trình duyệt tải lần đầu tiên, người dùng sẽ không thể zoom khi thuộc tính này có giá trị bằng 1

## Container Class
+ Có 2 loại container
+ Loại container sẽ hiển thị website với giá trị fixed width (lập trình viên tự định nghĩa giá trị như sau
```
<style>
         .container {
            background: #a52c644a;
            text-align: center;
            padding-top: 100px;
            padding-bottom: 100px;
         }   
      </style>
```
```
<div class = "container">
   ...
</div>
```
+ Loại container-fluid sẽ hiện thị full chiều rộng màn hình
```
<div class = "container-fluid">
   ...
</div>
```
## Responsive breakpoints
+ Tuỳ vào kích thướt màn hình mà màu H3 sẽ thay đổi là đỏ , vàng , xanh , tím.
+ Nếu màn hình điện thoại sẽ là đỏ
+ Nếu tablets là vàng
+ Nếu là desktop là xanh
```
/* Small devices (landscape phones, 576px and up) */
@media (min-width: 576px) {
  h3 {
      background-color: red;
  }

}

/*  Medium devices (tablets, 768px and up) */
@media (min-width: 768px) {
    h3 {
        background-color: yellow;
    }
}

/*  Large devices (desktops, 992px and up) */
@media (min-width: 992px) {
    h3 {
        background-color: green;
    }
}

/*  Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1200px) {
    h3 {
        background-color: purple;
    }
}
```
# The Bootstrap 4 grid system has five classes:
+ .col- (extra small devices - screen width less than 576px)
+ .col-sm- (small devices - screen width equal to or greater than 576px)
+ .col-md- (medium devices - screen width equal to or greater than 768px)
+ .col-lg- (large devices - screen width equal to or greater than 992px)
+ .col-xl- (xlarge devices - screen width equal to or greater than 1200px)
+ xs = extra small screens (mobile phones)
+ sm = small screens (tablets)
+ md = medium screens (some desktops)
+ lg = large screens (remaining desktops)
+ a div with classes **col-xs-6** and **col-sm-4** will span **half the screen on the mobile phone (xs) and 1/3 of the screen on tablets(sm)**
```
<!-- 50%/50% split on extra small devices and 75%/25% split on larger devices -->
<div class="row">
  <div class="col-6 col-sm-9">col-6 col-sm-9</div>
  <div class="col-6 col-sm-3">col-6 col-sm-3</div>
</div>

<!-- 58%/42% split on extra small, small and medium devices and 66.3%/33.3% split on large and xlarge devices -->
<div class="row">
  <div class="col-7 col-lg-8">col-7 col-lg-8</div>
  <div class="col-5 col-lg-4">col-5 col-lg-4</div>
</div>

<!-- 25%/75% split on small devices, a 50%/50% split on medium devices, and a 33%/66% split on large and xlarge devices. On extra small devices, it will automatically stack (100%) -->
<div class="row">
  <div class="col-sm-3 col-md-6 col-lg-4">col-sm-3 col-md-6 col-lg-4</div>
  <div class="col-sm-9 col-md-6 col-lg-8">col-sm-9 col-md-6 col-lg-8</div>
</div>


```

## Quy tắc khi thực hiện Responsive Web Design
1. Không sử dụng các HTML element có chiều rộng cố định quá lớn - Ví dụ: Một hình ảnh có chiều rộng quá lớn so với chiều rộng của các thiết bị nhỏ thì khi hiển thị trên các thiết bị này hình ảnh sẽ bị tràn ra ngoài và cần phải cuộn ngang để xem được toàn bộ ảnh. Vì vậy, cần phải điều chỉnh hỉnh ảnh sao cho phù hợp với chiều rộng của từng thiết bị. <br>

2. Sử dụng CSS media queries để style cho từng thiết bị có chiều rộng khác nhau - Không nên sử dụng các giá trị tuyệt đối như px, pt cho các phần tử mang tính bao quát trong trang, điều này sẽ làm cho nội dung của trang web sẽ bị tràn khi xem ở thiết bị có chiều rộng nhỏ hơn giá trị đã thiết lập. Thay vì vậy, hãy sử dụng các giá trị mang tính tương đối như %, ví dụ như width: 100%. <br>

3. Sử dụng icon SVG thay cho icon hỉnh ảnh thông thường (JPG, PNG,...) Các icon, hình ảnh dạng SVG sẽ không bị mờ khi thu phóng ở bất kỳ kích thước nào, điều này sẽ giúp nội dung của trang web hiển thị tốt nhất trên các thiết bị Retina như iPhone, iPad, Macbook
