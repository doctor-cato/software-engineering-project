# Danh sách Prompts cho AI Agent (Tuần 4)

Tài liệu này tổng hợp các câu lệnh (prompts) đã được tinh chỉnh để giao tiếp và giao việc cho AI Agent (như Cursor, GitHub Copilot, Gemini) thực hiện các GitHub Issues đã được gán trên repo.

---

## Prompt cho US02: Sơ đồ phòng chiếu & Khóa ghế thời gian thực
```text
Act as a Senior Frontend Developer. 
Read the documentation in `UX_PROTOTYPE.md` and the existing codebase for the booking feature.
I need you to implement Issue #2: Real-time Seat Locking.

Requirements:
1. When a user clicks an available seat, mark it as 'locked' locally and start a 5-minute countdown.
2. Use BroadcastChannel API to send a 'LOCK_SEAT' message to other open tabs so they mark the seat as gray (disabled).
3. If the countdown expires or the user triggers 'beforeunload', unlock the seat and broadcast 'UNLOCK_SEAT'.
4. Do not use external libraries for the state management, stick to Vanilla JS as documented.

Please generate the implementation plan first. Do not modify the database schema directly without confirmation.
```

---

## Prompt cho US12: [AI Feature] Tóm tắt đánh giá phim
```text
Act as an AI Integration Specialist.
We need to implement Issue #12: AI Sentiment Summarizer for movie reviews.

Requirements:
1. Read the `reviews_db` array from `storage.js` for a given movie.
2. Design a system prompt to send these reviews to an LLM via Vercel AI SDK (or similar API).
3. The LLM must return a JSON object containing: 
   - `summary_positive` (string)
   - `summary_negative` (string)
   - `overall_sentiment` (percentage number)
4. Implement the UI component to display this AI-generated summary. Critically, mark it clearly as "AI Generated" to inform the users.
5. Provide a fallback mechanism if the AI API fails (e.g. rate limit).

Write the required code in chunks and wait for my review after generating the service file.
```

---

## Prompt cho Refactor & Clean Code (Dùng cho mọi Issue)
```text
Review the code you just wrote. 
Identify any duplicated logic, unnecessarily long functions, or missing error handlers.
Refactor the code to adhere strictly to the rules defined in `AGENT_GUIDE.md`. 
Ensure all variable names are self-explanatory and DOM manipulation is kept inside Controller files, not Service files.
```
