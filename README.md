LÀM ĐI
- Hỏi đáp: facebook.com/luongtopp
- Làm ơn ủng hộ tôi một đăng ký youtube youtube.com/channel/luongtopp
- Nội dung học được:
+ app:popUpTo
  - Cho một thao tác trong sơ đồ điều hướng để kéo điểm đến ra khỏi ngăn xếp lui 
cho đến khi thấy điểm đến được chỉ định trong giá trị thuộc tính.
  - app:popUpToInclusive="true" cho một thao tác khi điểm đến được chỉ định 
  trong app:popUpTo cũng phải được kéo ra khỏi ngăn xếp lui.

  + plurals
  Sử dụng tài nguyên plurals nếu bạn muốn sử dụng các tài nguyên chuỗi khác nhau 
dựa trên số lượng, chẳng hạn như trường hợp số ít hoặc số nhiều.
  - string.xml

<string name="order_details">Quantity: %1$s \n Flavor: %2$s \nPickup date: %3$s \n
Total: %4$s \n\n Thank you!</string>
<plurals name="cupcakes">
<item quantity="one">%d cupcake</item>
<item quantity="other">%d cupcakes</item>
</plurals>

  - SummaryFragment.kt

fun sendOrder() {
val orderSummary = getString(
R.string.order_details,
resources.getQuantityString(R.plurals.cupcakes, numberOfCupcakes, numberOfCupcakes),
sharedViewModel.flavor.value.toString(),
sharedViewModel.date.value.toString(),
sharedViewModel.price.value.toString()

        )}
+ Intent.EXTRA_EMAIL
  Bạn có thể tạo ý định ngầm ẩn để chia sẻ nội dung với một ứng dụng email, 
bằng cách sử dụng Intent.ACTION_SEND và điền sẵn các ý định khác như Intent.EXTRA_EMAIL, 
Intent.EXTRA_SUBJECT và Intent.EXTRA_TEXT, v.v.