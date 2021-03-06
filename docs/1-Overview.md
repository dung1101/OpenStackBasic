# I) Virtualization (Ảo hóa) 
## 1) Ảo hóa là gì ?
Ảo Hóa là kỹ thuật tạo ra phần cứng, thiết bị mạng, thiết bị lưu trữ … ẢO – không có thật (và ở góc độ nào đó có thể hiểu là “giả lập” và “mô phỏng” lại các thành phần này)

Đi kèm với Ảo hóa thường có các cụm từ Hardware Virtualization, Platform Virtualization: các cụm từ này ám chỉ việc tạo ra các thành phần phần cứng (ảo) để tạo ra các máy ảo (Virtual Machine), chúng có gần như đầy đủ các thành phần như máy thật (physical machine ) và có thể cài đặt hệ điều hành (Linux, Windows, ….trong network thì có thể có các Router ảo và Switch ảo ) và tất nhiên người dùng có thể sử dụng và khai thác được các máy ảo, thiết bị ảo này.

## 2) Các loại ảo hóa
- Full-virtualization là công nghệ ảo hóa để cung cấp 1 loại hình máy ảo dưới dạng mô phỏng của 1 máy chủ thật với đầy đủ tất cả các tính năng bao gồm input/output operations, interrupts, memory access, … Tuy nhiên mô hình ảo hóa này không thể khai thác tốt hiệu năng khi phải thông qua một trình quản lý máy ảo (Virtual Machines monitor hay hypervisor) để tương tác đến tài nguyên hệ thống 
- Para-virtualization hay còn gọi là ảo hóa “một phần” là kỹ thuật ảo hóa được hỗ trợ và điều khiển bởi 1 hypervisor nhưng các Os của guest thực thi các lệnh không phải thông qua Hypervisor (hay bất kỳ 1 trình quản lý máy ảo nào) nên không bị hạn chế về quyền hạn. Tuy nhiên nhược điểm của loại ảo hóa này là các OS biết đang chạy trên 1 nền tảng phần cứng ảo và khó cấu hình cài đặt.
- OS level virtualization, còn gọi là containers Virtualization hay Isolation: là phương pháp ảo hóa mới cho phép nhân của hệ điều hành hỗ trợ nhiều instances được cách ly dựa trên một HĐH có sẵn cho nhiều users khác nhau, hay nói cách khác là tạo và chạy được nhiều máy ảo cách ly và an toàn (secure) dùng chung 1 HĐH. Ưu điểm của ảo hóa này là bảo trì nhanh chóng nên được ứng dụng rộng rãi trong các lĩnh vực hosting.

## 3) Hypervisor
Tất cả các loại ảo hóa được quản lý bởi VMM (Virtual Machine Monitor). VMM về bản chất cũng được chia làm 2 loại là:
- VMM đóng vai trò như một phần mềm trung gian chạy trên HĐH để chia sẻ tài nguyên với HĐH. Ví dụ: VMware workstation, Virtual PC, KVM.
- VMM đóng vai trò là một hypervisor chạy trên phần cứng. Ví dụ: VMware ESXi, Hyper-V, Xen.
Hypervisor là một phần mềm nằm ngay trên phần phần cứng hoặc bên dưới HĐH nhằm mục đích cung cấp các môi trường tách biệt gọi là các phân vùng – partition. Mỗi phân vùng ứng với mỗi máy ảo-VM có thể chạy các OS độc lập.

# II) Cloud computing
## 1) Tổng quan
`Điện toán đám mây, thường được gọi đơn giản là "đám mây", là phân phối các tài nguyên máy tính theo yêu cầu - mọi thứ từ các ứng dụng đến các trung tâm dữ liệu - qua internet trên cơ sở trả tiền để sử dụng.`
## 2) Mô hình cung cấp cloud computing
- Infrastructure as a Service (IaaS): Hạ tầng được cung cấp như một dịch vụ.
- Platform as a Service (PaaS): Nền tảng được cung cấp như một dịch vụ.
- Software as a Service (SaaS): Phần mềm được cung cấp như một dịch vụ.

### 2.1) Infrastructure as a Service (IaaS): Hạ tầng được cung cấp như một dịch vụ
Theo Amazon thì nó là mức cơ bản nhất của điện toán đám mây, và thường thì nhà cung cấp dịch vụ IaaS sẽ bán cho bạn các thứ về mạng, về máy tính (máy ảo hoặc máy thật tùy nhu cầu), cũng như nơi lưu trữ dữ liệu. Cụ thể hơn, bạn có thể thuê một cái "máy chủ trên mây" với CPU, RAM, ổ cứng ( SSD hoặc HDD) tùy theo nhu cầu. Như vậy, IaaS không được thiết kế cho người dùng cuối, mà chủ yếu cho những người muốn có một nơi để triển khai phần mềm của mình, có thể là lập trình viên, một công ty, hay một đơn vị phát hành web chẳng hạn
#### Lợi ích:
- Không cần đầu tư cho phần cứng
- Quy mô của hạ tầng có thể thay đổi theo yêu cầu để hỗ trợ khối lượng công việc
- Dịch vụ linh hoạt, sáng tạo có sẵn theo yêu cầu

### 2.2) Platform as a Service (PaaS): Nền tảng được cung cấp như một dịch vụ 
 Trong trường hợp bạn mua dịch vụ IaaS bạn sẽ được cung cấp một máy chủ. Nhưng để triển khai ứng dụng Web của bạn, bạn phải tự cài đặt nhiều thứ liên quan, chẳng hạn Web Server, Database, ... các cài đặt này phụ thuộc vào ứng dụng web của bạn được phát triển trên ngôn ngữ lập trình nào ( Java, .Net, PHP, ..), và rồi sau khi các cài đặt hoàn tất bạn mới có thể triển khai ứng dụng của bạn.
 
PaaS cung cấp môi trường dựa trên đám mây với mọi thứ cần thiết để hỗ trợ toàn bộ vòng đời xây dựng và cung cấp các ứng dụng dựa trên web - không có chi phí và sự phức tạp của việc mua và quản lý phần cứng, phần mềm, cung cấp và lưu trữ cơ bản.
#### Lợi ích:
- Phát triển ứng dụng và đưa ra thị trường nhanh hơn
- Triển khai một ứng dụng web mới nhanh gọn
- Giảm độ phức tạp với phần mềm trung gian như một dịch vụ

### 2.3) Software as a Service (SaaS): Phần mềm được cung cấp như một dịch vụ
Đây là một mức độ cao nhất trong các loại hình dịch vụ đám mây. Nó là một sản phẩm hoàn thiện được vận hành và quản lý bởi một nhà cung cấp. Và nói đơn giản, trong hầu hết trường hợp thì dịch vụ SaaS sẽ cung cấp các phần mềm hoặc ứng dụng chạy trên Internet và có thể được dùng ngay bởi người dùng cuối (end-user).

#### Lợi ích:
- Bạn có thể đăng ký và nhanh chóng bắt đầu sử dụng các ứng dụng
- Ứng dụng và dữ liệu có thể truy cập được từ mọi máy tính được kết nối 
- Không có dữ liệu bị mất nếu máy tính của bạn bị hỏng, vì dữ liệu nằm trong đám mây
- Dịch vụ có thể tự động mở rộng theo nhu cầu sử dụng

## 3) Mô hình triển khai Cloud computing
- Public Cloud: Đám mây công cộng (là các dịch vụ trên nền tảng Cloud Computing để cho các cá nhân và tổ chức thuê, họ dùng chung tài nguyên).
- Private Cloud: Đám mây riêng (dùng trong một doanh nghiệp và không chia sẻ với người dùng ngoài doanh nghiệp đó)
- Community Cloud: Đám mây cộng đồng (là các dịch vụ trên nền tảng Cloud computing do các công ty cùng hợp tác xây dựng và cung cấp các dịch vụ cho cộng đồng
- Hybrid Cloud : Là mô hình kết hợp (lai) giữa các mô hình Public Cloud và Private Cloud
# III) Open Stack
## 1) Open Stack là gì
```
   OpenStack là một phần mềm mã nguồn mở, dùng để triển khai Cloud Computing, bao gồm private cloud và public cloud (nhiều tài liệu giới thiệu là Cloud Operating System)
```

```
   OpenStack is a cloud operating system that controls large pools of compute, storage, and networking resources throughout a datacenter, all managed through a dashboard that gives administrators control while empowering their users to provision resources through a web interface.
```

<img src="http://i.imgur.com/KcI8Fq0.png">

- Phía dưới là phần cứng đã được ảo hóa để chia sẻ cho ứng dụng, người dùng
- Trên cùng là các ứng dụng của bạn, tức là các phần mềm mà bạn sử dụng
- Và OpenStack là phần ở giữa 2 phần trên, trong OpenStack có các thành phần, module khác nhau nhưng trong hình minh họa các thành phần cơ bản: Dashboard, Compute, Networking, API, Storage …

## 2) Thành phần
OpenStack không phải là một dự án đơn lẻ mà là một nhóm các dự án nguồn mở nhằm mục đích cung cấp các dịch vụ cloud hoàn chỉnh. OpenStack chứa nhiều thành phần:
- OpenStack compute (code-name Nova): là module quản lý và cung cấp máy ảo. Tên phát triển của nó Nova. Nó hỗ trợ nhiều hypervisors gồm KVM, QEMU, LXC, XenServer... Compute là một công cụ mạnh mẽ mà có thể điều khiển toàn bộ các công việc: networking, CPU, storage, memory, tạo, điều khiển và xóa bỏ máy ảo, security, access control. Bạn có thể điều khiển tất cả bằng lệnh hoặc từ giao diện dashboard trên web.
- OpenStack Glance (code-name Glance): là OpenStack Image Service, quản lý các disk image ảo. Glance hỗ trợ các image Raw, Hyper-V (VHD), VirtualBox (VDI), Qemu (qcow2) và VMWare (VMDK, OVF). Bạn có thể thực hiện: cập nhật thêm các virtual disk images, cấu hình các public và private image và điều khiển việc truy cập vào chúng, và tất nhiên là có thể tạo và xóa chúng.
- OpenStack Object Storage (code-name Swift): dùng để quản lý lưu trữ. Nó là một hệ thống lưu trữ phân tán cho quản lý tất cả các dạng của lưu trữ như: archives, user data, virtual machine image … Có nhiều lớp redundancy và sự nhân bản được thực hiện tự động, do đó khi có node bị lỗi thì cũng không làm mất dữ liệu, và việc phục hồi được thực hiện tự động.
- Identity Server(code-name Keystone): quản lý xác thực cho user và projects.
- OpenStack Netwok (code-name Neutron): là thành phần quản lý network cho các máy ảo. Cung cấp chức năng network as a service. Đây là hệ thống có các tính chất pluggable, scalable và API-driven.
- OpenStack dashboard (code-name Horizon): cung cấp cho người quản trị cũng như người dùng giao diện đồ họa để truy cập, cung cấp và tự động tài nguyên cloud. Việc thiết kế có thể mở rộng giúp dễ dàng thêm vào các sản phẩm cũng như dịch vụ ngoài như billing, monitoring và các công cụ giám sát khác.

**Nguồn:**<br>
[https://www.ibm.com/cloud/](https://www.ibm.com/cloud/)<br>
[https://github.com/meditechopen/meditech-thuctap/tree/master/ThaoNV](https://github.com/meditechopen/meditech-thuctap/tree/master/ThaoNV)<br>
