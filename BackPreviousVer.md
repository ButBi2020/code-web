HOÀN TOÀN ĐƯỢC! Đây chính là lý do Git ra đời. Bạn có thể lấy lại code ở bất kỳ thời điểm nào trong quá khứ mà không bao giờ sợ mất code hiện tại.

Dựa vào ảnh bạn gửi, mình thấy có một điểm thú vị về cách đặt tên:

Commit "V1" (mã 63e7d1f) đang nằm trên cùng -> Nghĩa là nó là bản MỚI NHẤT (làm cách đây 11 phút).

Commit "V2 and V3" (mã 69ed50f) nằm dưới -> Nghĩa là nó là bản CŨ HƠN (làm cách đây 15 phút).

Dưới đây là 3 cách để bạn lấy lại code của một bản commit bất kỳ (ví dụ bạn muốn lấy bản cũ 69ed50f) mà vẫn giữ nguyên bản mới nhất.

Cách 1: Xem và tải code trực tiếp trên Web (An toàn nhất)
Cách này giúp bạn xem lại code cũ, copy đoạn cần thiết mà không sợ gõ lệnh sai làm hỏng dự án trên máy.

Tại danh sách Commits như trong ảnh bạn chụp.

Bấm vào nút < > nằm ở bên phải của dòng commit bạn muốn xem (Nút này tên là "Browse the repository at this point").

GitHub sẽ đưa bạn đến giao diện xem toàn bộ file code tại thời điểm quá khứ đó. Bạn có thể tải về hoặc copy code thoải mái.

Cách 2: Tạo một "Nhánh" riêng cho bản cũ (Khuyên dùng)
Cách này giúp bạn có 2 phiên bản song song: Một bản main (hiện tại) và một bản backup-cu (quá khứ). Bạn có thể chuyển qua lại giữa 2 bản này bất cứ lúc nào.

Hãy mở VS Code (Terminal) và gõ lệnh sau:

Bash

# Cú pháp: git checkout -b [tên-nhánh-mới] [mã-SHA-của-commit]

# Ví dụ: Lấy lại bản "V2 and V3" (mã 69ed50f) ra một nhánh riêng tên là 'ban-cu'
git checkout -b ban-cu 69ed50f
Kết quả: Code trên máy bạn sẽ quay về y hệt lúc đó.

Muốn quay lại hiện tại: Chỉ cần gõ git checkout main.

Ưu điểm: Cả bản cũ và bản mới đều được giữ an toàn, không ai đụng ai.

Cách 3: Chỉ lấy lại đúng 1 file bị lỗi (Thực tế hay dùng)
Giả sử bản hiện tại (V1) bị lỗi file index.html, bạn muốn lấy lại file index.html của bản cũ (V2/V3) đè vào hiện tại.

Bash

# Cú pháp: git checkout [mã-SHA] -- [tên-file]

# Ví dụ:
git checkout 69ed50f -- index.html
Lệnh này có nghĩa là: "Git ơi, hãy về quá khứ 69ed50f, copy file index.html và đem về đây cho tôi".

⚠️ Lưu ý quan trọng về "Detached HEAD"
Nếu bạn dùng lệnh git checkout 69ed50f (mà không tạo nhánh mới), Git sẽ hiện cảnh báo "Detached HEAD".

Đừng hoảng sợ! Nó chỉ báo là bạn đang ở chế độ "Tham quan bảo tàng" (chỉ xem, không nên sửa).

Để thoát khỏi chế độ này và về lại hiện tại, chỉ cần gõ: git checkout main.

Bạn muốn thử cách nào? Mình khuyên nên dùng Cách 1 để xem trước, hoặc Cách 2 nếu muốn chạy thử code cũ.
