### documents

- anh custom theo waterfall cho phù hợp với anh thôi, mỗi folder chứa doc 1 giai đoạn của project, cần thì tìm lại cũng dễ

##### discovery

- note lại mấy cái đã bàn với khách (nếu làm project cá nhân thì skip)

##### requirement

- overview liệt kê các feature của dự án (mô tả từ góc nhìn user, không phải dev)
  - ví dụ tạo mindmap từ mô tả (kiểu như user story ấy)
- scope cho từng feature
  - làm gì
  - không làm gì, cái này quan trọng, giúp tránh overthinking

##### design

- bây giờ mới đi sâu vào kỹ thuật
  - note ra idea logic xử lý các feature
- design db
  - note ra các table, relationship, index, sample data
- design api
  - note ra các api, request, response, logic xử lý

##### implementation

- phần này thì trong quá trình làm có gì quan trọng thì note, không thì cứ theo design mà code thôi, không quan trọng

##### testing

- vừa code vừa test rồi, có gì thì note thôi

##### deployment

- thông tin vps, các câu lệnh hay dùng để deploy, monitoring thì note lại sau copy cho nhanh

### backend

- source api

### frontend

- source frontend

### script

- script tự động hóa những tác vụ thủ công (thường thì anh dùng AI gen cái này cho nhanh)
  - test api (script call api rồi check response theo cái mình đã định nghĩa), thường thì có thư viện support tùy ngôn ngữ
  - tạo fake data hàng loạt
  - chạy thử code logic mà không muốn sửa src
  - ...
