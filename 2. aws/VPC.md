## IP
  - Phân loại thành 5 lớp:
    - Class A có octet đầu tiên từ 1-126 (1.0.0.1 đến 126.0.0.0) => Các tổ chức lớn trên thế giới
    - Class B có octet đầu tiên từ 128-191 (128.1.0.0 đến 191.254.0.0) => Các tổ chức hạng trung trên thế giới
    - Class C có octet đầu tiên từ 192-223 (192.0.1.0 đến 223.255.254.0) => Các tổ chức nhỏ trên thế giới có cả máy tính cá nhân
    - Class D có octet đầu tiên từ 224-239 (224.0.0.0 đến 239.255.255.255) => Dành cho phát các thông tin (multicast/broadcast)
    - Class E có octet đầu tiên từ 240-255 (240.0.0.0 đến 254.255.255.255) => Dành riêng cho việc nhiên cứu.
  - Có 4 loại IP
    - IP Private
    - IP Public
    - IP tĩnh
    - IP động
## CIDR IP
  - Có dạng x.x.x.x/y

  - Class A: 10.0.0.0 to 10.255.255.255
  - Class B: 172.16.0.0 to 172.31.255.255
  - Class C: 192.168.0.0 to 192.168.255.255
## Luồng dữ liệu từ truy cập từ bên ngoài vào
  IGW => Route Table (sơ đồ đi đến subnet) => Subnet => Network ACLs (filter IPs) và Security Group
## Thành phần cơ bản của VPC
  1. Subnets
  2. Route Table
  3. Internet Gateway
  4. NAT Gateway
## Subnets
  - Có 3 loại Pubic, Private, VPN-only
  - Public subnet là subnet có `Route Table` điều hướng lưu lượng bên trong subnet đi tới VPC IGW (thường đặt web server như EC2)
  - Private subnet không có `Route Table` (Ví dụ Database)
  - VPN-only subnet là subnet có `Route Table` điều hướng lưu lượng bên trong subnet đi tới VPG
  - Subnets sử dụng khi tạo VPC dùng để cung cấp dải IP cho các resource AWS chạy bên trong VPC đó.
## Route Table
  - Khi số lượng người dùng và số lượng Node mạng trung chuyển là rất lớn
    => Cần lưu các best route (tuyến đường tốt nhất để đến đích) vào database
    => Database này gọi là route table (bảng định tuyến)
  - Bên trong Route Table có `destination:10.10.0.0/16` và `target:local`
## Internet Gateway
  - là một thành phần Amazon VPC giúp các tài nguyên mà thuộc `Public Subnet` bên trong VPC, cụ thể là EC2, có khả năng giao tiếp với Internet.
  - Hoạt động như là 1 target trong Route Table. Khi gửi data từ EC2 ra Internet thì IGW sẽ biên dịch Private IP của EC2 thành Public IP
## NAT Gateway
  - là một thành phần Amazon VPC giúp các tài nguyên mà thuộc `Private Subnet` bên trong VPC, cụ thể là EC2, có khả năng giao tiếp với Internet.
