# Buggy PHP Lab
## Mục tiêu bài tập
### Checkoutboard.phd
- Lỗi logic khiến cho tính tiền sai, discount giá trị là 10 nhưng thực tế là 10%

```php
$discountValue = $subtotal * ($discountPercent / 100)
```
- Lỗi logic free shipp chỉ thực hiện cho đơn có tổng tiền lớn, đơn nhỏ vẫn phải trả tiền

```php
$shippingFee = $subtotal >= 50 ? 0 : 5;
```

- Lỗi logic tính VAT, được tính sau khi đã giảm giá

```php
$vat = ($subtotal - $discountValue) * 0.1;
```

### dashboard.phd
- Lỗi logic tính revenge tings tiền thì phải lấy tiền * giá, trong khi code gốc giá trị tiền = số sản phẩm

```php
foreach ($order['items'] as $item) {
    $totalRevenue += $price * $item['qty'];
}
```
- Lỗi logic low stock: yêu cầu là sản phẩm nhỏ

```php
if ($product['stock'] <= 5)
```

### custome.phd
- Lỗi syntax thiếu ;

```php
$activeCustomers = [];
```

### orders.php
- Lỗi logic xếp sai thứ tự yêu cầu *Only pending items should be listed, newest first*

```php
return $right['id'] <=> $left['id'];
```

### orders.php
- Lỗi syntax thiếu dấu *)*

```php
foreach ($totalsByCategory as $category => $total)
```

- Lỗi syntax chưa khai báo reportRows

### settings.php
- Lỗi syntax thiếu dấu ,

```php
'timezone' => 'Asia/Ho_Chi_Minh',
```
