# AWS Identity and Access Management (IAM)
#iam #accessmanagement

***AWS Identity and Access Management (IAM)*** là 1 hệ thống cho phép bạn quản lý truy cập vào các dịch vụ và tài nguyên của AWS một cách bảo mật.

### Có 4 loại permission:
 - ***Users***: End User giống như nhân viên trong 1 tổ chức (organization) trên AWS
 - ***Groups***: 1 Tập hợp các User có cùng 1 mục đích.
 - ***Policies***: Các quyền hạn, truy cập, xóa, sửa các tài nguyên trên AWS. Được viết dưới định dạng Json.
 - ***Roles***: 1 Nhóm Quyền hạn  ( Admin, DEVOps, Tester) có thể truy cập và làm những gì trên AWS Resources.

### Những đặc điểm của IAM
- IAM là Universal, nó không phụ thuộc vào region
- ***Root account*** là account được tạo ra khi lần đầu setup AWS account. ***Root Account*** là Admin có toàn quyền.
- Khi một User được tạo ra, nó không có bất cứ quyền hạn gì.
- New User phải được gắn với 1 ***Access Key ID*** & ***Secret Access Keys*** khi mới được tạo ra.
- Không thể sử dụng ***Access Key ID*** & ***Secret Access Keys*** để đăng nhập bằng console. Chỉ có thể dùng để truy cập AWS bằng API hoặc bằng command line.
- Nếu quên ***Access Key ID*** & ***Secret Access Keys*** chỉ có thể regenerate.
- Nên setting Multifactor Authentication trên account Root ex: Google Authentication. *Lưu ý : 1 phương thức Authentication của account Root chỉ có thể setup với 1 app google Authen cho 1 administrator dùng. nếu có trên 1 admin, dùng sẽ rất bất tiện
