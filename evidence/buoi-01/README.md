# Minh chứng Buổi 1

Thư mục này dùng để nộp minh chứng thiết lập môi trường lab.

## Sinh viên điền thông tin

- Họ tên: Nguyễn Hữu Hưng
- Mã sinh viên: 1771020334
- Nhóm: 7
- Vai trò dự kiến trong nhóm: trưởng nhóm
- Hệ điều hành: window 11
- Ghi chú: em nộp bài ạ. Đã cài đặt Docker Desktop, WSL2, Node.js và chạy smoke test thành công.


## Các file minh chứng nên có

- `tool-versions.txt`
- `docker-version.txt`
- `compose-version.txt`
- `hello-world.txt`
- `smoke-test-result.txt`
- `image-list.txt`
- `git-log.txt`
- `checklist.md`
- `known-issues.md`

## Cách sinh file tự động

macOS/Linux:

```bash
./scripts/collect_session01_evidence.sh
```

Windows:

```powershell
.\scripts\collect_session01_evidence.ps1
```
