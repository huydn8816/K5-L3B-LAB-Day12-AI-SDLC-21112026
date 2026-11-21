# vindpd203 — phản tư cá nhân

- **Tôi đã làm:**
  - P1: lát 1 gather (oxy, ngạt, ngất, giỏ LIFO) `a515a0c`, test `c4c8325`, test lát 2 `6850e8c`, TEAM.md `47c9fd0`.
  - P2: số chuẩn v1.1 `eb1b4a2`, cá bơi/sinh `b61343c`, test `acda2bd`.
  - P3: giỏ cá thể và độ tươi `8f955ce`, gộp conflict kho v1.2 `3547386`.
- **Tôi đã review:** gộp bản cá của `khanhdev` vào `vinh`, chạy bộ test chung 99/99 (`72ecb9c`).
- **AI sai ở đâu và tôi phát hiện thế nào:**
  - Đổi `lost` về mảng kind theo PRD v1.1, trái TICKET-03 → 5 test lỗi `TypeError`, đổi lại.
  - Validate quái đọc `tuning.get("monsters")` thay vì `tuning["gather"]` → fixture quái bị mã 2, lộ khi chạy `test_gather_monster`.
  - Test Cá Sấu dùng dung sai 1e-6 dù JSONL làm tròn 3 số; patrol trượt waypoint tick 240 do drift float.
- **Điều tôi học được:** spec mới có thể thay PRD cũ, nên chạy test hộp đen trước khi sửa theo chữ. Test tick biên cần dung sai float. Gộp hai bản song song thì để bộ test chung làm trọng tài.
