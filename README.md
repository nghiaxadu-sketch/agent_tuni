# agent_tuni

Đội 11 subagent cho Claude Code, dựng khung bằng `/harness:harness`, dùng cho project "code".

## 4 mảng
- Office tool: tool Python đọc/ghi Excel, PDF, Word, đóng gói .exe
- ESP32: BOM, pinmap (kiểm bằng check_gpio.py), firmware Arduino/ESP-IDF
- AI agent: system prompt XML, subagent, skill, bộ EVALS
- Cyberdeck: làm theo từng phase, dừng chờ xác nhận

## Quy trình
spec-planner → (py-tool-coder | hardware-designer + firmware-coder | agent-architect)
→ test-runner → review-correctness + review-safety + review-usability → packager

Việc văn phòng làm một lần thì `office-operator` làm thẳng, không chạy cả dây chuyền.

## Cấu trúc
.claude/agents/   11 định nghĩa agent
.claude/skills/   code-orchestrator, esp32-hardware-rules, office-file-safety...
