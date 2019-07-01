# Blog của DevOpsViet
---
## Hướng dẫn chạy trên local


## Hướng dẫn build Source phục vụ triển khai

Tạo thư mục build
```
cd <repo blog>/
mkdir -p build/
sudo hugo -s . -d build/ -b "<domain or ip>"
```

Lưu ý:
- `<domain or ip>` sẽ là domain của trang web muốn triển khai, site blgo của devopsviet là `blog.devopsviet.com`

Ví dụ
```
cd blog/
mkdir -p build/
sudo hugo -s . -d build/ -b "http://30.0.0.15/"
```