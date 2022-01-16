## Policy
  - Policy là 1 object trong AWS mà định nghĩa các permissions.
  - Tức là chọn service và các action thực hiện service đó theo `nhu cầu` của nghiệp vụ.
  - Có 2 loại policy là `inline policy` và `IAM policy`
  - `IAM policy` có thể do mình customize `Customer managed` hoặc AWS có sẵn `AWS managed`
  - `inline policy` chỉ được sử dụng một lần duy nhất khi create và không được tái sử dụng. Còn `IAM policy` thì có thể tái sử dụng được
## User Group
  - Giống như folder chứa các `IAM User`
  - Có thể attach `IAM policy` hoặc create `inline policy`
## IAM User
  - Có thể thuộc `User Group` hoặc không
  - Có thể có `IAM Role` hoặc không.
## IAM Role
  - IAM Role dùng để nâng cao tính bảo mật trên AWS, và sử dụng để gán quyền `tạm thời` cho các `IAM User`
  - Các `IAM User`có thể attach `inline policty` để alias tới `IAM Role`. Sau đó `IAM User` có thể switch role để sử dụng các quyền của role đó
  - `IAM Role` còn để gán quyền cho `EC2` hoặc `Lambda` (Ví dụ EC2 truy cập S3)