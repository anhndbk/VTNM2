# Data dictionary

Mỗi dòng là một thuê bao tại thời điểm quan sát. Các chỉ số sử dụng là **trung bình theo tháng** trong giai đoạn quan sát, trừ khi ghi khác. Đơn vị tiền: **nghìn VND**.

## Định danh và nhãn

| Cột | Kiểu | Mô tả |
|---|---|---|
| `customer_id` | string | Mã dòng dữ liệu, dùng trong file nộp |
| `churn` | int (0/1) | 1 nếu thuê bao rời mạng trong khoảng 31–60 ngày sau thời điểm quan sát. Chỉ có trong `train.csv`. Nhãn không hoàn hảo |

## Cước và mức sử dụng

| Cột | Kiểu | Mô tả |
|---|---|---|
| `monthly_revenue` | float | Doanh thu trung bình mỗi tháng (nghìn VND) |
| `monthly_minutes` | float | Số phút sử dụng trung bình mỗi tháng |
| `total_recurring_charge` | float | Cước cố định hàng tháng (nghìn VND) |
| `director_assisted_calls` | float | Số cuộc gọi qua tổng đài viên hỗ trợ |
| `overage_minutes` | float | Số phút vượt hạn mức gói |
| `roaming_calls` | float | Số cuộc gọi chuyển vùng |
| `perc_change_minutes` | float | Mức thay đổi số phút sử dụng tháng hiện tại so với trung bình các tháng trước |
| `perc_change_revenues` | float | Mức thay đổi doanh thu tháng hiện tại so với trung bình các tháng trước |

## Chất lượng cuộc gọi và hành vi gọi

| Cột | Kiểu | Mô tả |
|---|---|---|
| `dropped_calls` | float | Số cuộc gọi bị rớt |
| `blocked_calls` | float | Số cuộc gọi bị chặn / không kết nối được |
| `unanswered_calls` | float | Số cuộc gọi không được trả lời |
| `dropped_blocked_calls` | float | Tổng cuộc gọi rớt + bị chặn |
| `customer_care_calls` | float | Số cuộc gọi đến chăm sóc khách hàng |
| `threeway_calls` | float | Số cuộc gọi hội nghị 3 bên |
| `received_calls` | float | Số cuộc gọi nhận |
| `outbound_calls` | float | Số cuộc gọi đi (đã kết nối) |
| `inbound_calls` | float | Số cuộc gọi đến (đã kết nối) |
| `peak_calls` | float | Số cuộc gọi giờ cao điểm (đi + đến) |
| `offpeak_calls` | float | Số cuộc gọi ngoài giờ cao điểm (đi + đến) |
| `call_forwarding_calls` | float | Số cuộc gọi chuyển tiếp |
| `call_waiting_calls` | float | Số cuộc gọi chờ |

## Tài khoản và thiết bị

| Cột | Kiểu | Mô tả |
|---|---|---|
| `months_in_service` | int | Số tháng đã sử dụng dịch vụ |
| `unique_subs` | int | Số thuê bao (SIM) khác nhau thuộc tài khoản |
| `active_subs` | int | Số thuê bao đang hoạt động thuộc tài khoản |
| `service_area` | string | Mã khu vực phục vụ, dạng `Rxx-Ayyy` (`Rxx` là vùng) |
| `handsets` | int | Số máy điện thoại khách đã từng dùng với nhà mạng |
| `handset_models` | int | Số mẫu máy khác nhau đã dùng |
| `current_equipment_days` | int | Số ngày đã dùng máy hiện tại |
| `handset_refurbished` | 0/1 | Máy hiện tại là máy tân trang |
| `handset_web_capable` | 0/1 | Máy hiện tại truy cập web được |
| `handset_price` | float | Giá máy hiện tại (nghìn VND), trống nếu không rõ |
| `new_cellphone_user` | 0/1 | Khách lần đầu dùng di động |
| `not_new_cellphone_user` | 0/1 | Khách đã từng dùng di động trước đó |

## Nhân khẩu học và hộ gia đình

| Cột | Kiểu | Mô tả |
|---|---|---|
| `age_hh1` | int | Tuổi thành viên thứ nhất trong hộ |
| `age_hh2` | int | Tuổi thành viên thứ hai trong hộ |
| `children_in_hh` | 0/1 | Hộ có trẻ em |
| `homeownership` | string | Thông tin sở hữu nhà (`Known` / `Unknown`) |
| `marital_status` | string | Tình trạng hôn nhân (`Yes` / `No` / `Unknown`) |
| `occupation` | string | Nghề nghiệp |
| `income_group` | int | Nhóm thu nhập |
| `area_type` | string | Loại khu vực sinh sống (Suburban, Town, Rural, Other) |
| `truck_owner`, `rv_owner`, `owns_motorcycle` | 0/1 | Sở hữu xe tải / xe nhà di động / xe máy |
| `owns_computer`, `has_credit_card` | 0/1 | Có máy tính / thẻ tín dụng |
| `buys_via_mail_order`, `responds_to_mail_offers`, `opt_out_mailings` | 0/1 | Hành vi với thư tiếp thị |
| `travels_abroad` | 0/1 | Có đi nước ngoài |

## Tín dụng và chăm sóc giữ chân

| Cột | Kiểu | Mô tả |
|---|---|---|
| `credit_rating` | string | Hạng tín dụng, dạng `1-Highest` … `7-Lowest` |
| `credit_rating_adjustments` | int | Số lần điều chỉnh hạng tín dụng |
| `referrals_made` | int | Số người khách đã giới thiệu |
| `retention_calls` | int | Số lần khách gọi đến đội giữ chân khách hàng |
| `retention_offers_accepted` | int | Số ưu đãi giữ chân khách đã nhận trước đây |
| `made_call_to_retention_team` | 0/1 | Khách đã từng gọi đến đội giữ chân |

## Lưu ý

- Dữ liệu có giá trị thiếu, giá trị bất thường, bản ghi trùng, category chưa đồng nhất (hoa/thường, khoảng trắng thừa) và nhãn không hoàn hảo.
- Một số cột dùng `0` với nghĩa "không rõ". Hãy tự kiểm tra.
- Không phải cột nào cũng chắc chắn có sẵn **trước** thời điểm cần dự đoán trong thực tế. Đây là việc của nhóm phải đánh giá.
