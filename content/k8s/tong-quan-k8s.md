---
title: "Tổng quan về k8s"
date: 2018-12-29T11:02:05+06:00
type: "post"
author: "thanhnb"
---

Tổng quan và các khái niệm quan trọng về cân bằng tải trong HAProxy

<div class="alert rounded-0 alert-primary">
  Tổng quan và các khái niệm quan trọng về cân bằng tải trong HAProxy
</div>

Có rất nhiều thuật ngữ và khái niệm được sử dụng trong HAProxy khi nối về cân bằng tải (Load balancing) và máy chủ. Ở đây, tôi sẽ tập trung vào các khái niệm thông dụng được sử dụng nhiều trong HAProxy


### Tổng quan

HAProxy viết tắt của High Availability Proxy, là công cụ mã nguồn mở nổi tiếng ứng dụng cho giải pháp cân bằng tải TCP/HTTP cũng như giải pháp máy chủ Proxy (Proxy Server). HAProxy có thể chạy trên các mỗi trường Linux, Solaris, FreeBSD. Công dụng phổ biến nhất của HAProxy là cải thiện hiệu năng, tăng độ tin cậy của hệ thống máy chủ bằng cách phân phối khối lượng công việc trên nhiều máy chủ (như Web, App, cơ sở dữ liệu). HAProxy hiện đã và đang được sử dụng bởi nhiều website lớn như GoDaddy, GitHub, Bitbucket, Stack Overflow, Reddit, Speedtest.net, Twitter và trong nhiều sản phẩm cung cấp bởi Amazon Web Service.

![image example](/images/k8s/tong-quan-k8s/img-6.jpg "image")

```
backend web-backend
  balance roundrobin
  server web1 web1.yourdomain.com:80 check
  server web2 web2.yourdomain.com:80 check

backend blog-backend
  balance roundrobin
  mode http
  server blog1 blog1.yourdomain.com:80 check
  server blog1 blog1.yourdomain.com:80 check
```
