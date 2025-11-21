```text
# 範例 Prompt 範本（示範性質，請依模型特性微調）

## 1) 小說段落 → 分鏡 (LLM)
你是資深編劇。以下是一段小說，請把它拆成 3 個 scene，每個 scene 給出：
- scene_id (1,2,3)
- 建議時長 (秒)
- 畫面描述（攝影機角度、光線、場景物件）
- 主要角色與簡短動作
- 對白（若有）與字幕文本
- 建議背景音樂風格與 SFX

**Input:** <在此貼上小說段落>
**Output format:** JSON array (scene_id, duration, description, characters, dialogue, mood)

## 2) Scene → 圖像 Prompt (Image model)
你是 prompt 工程師，請根據下列 scene 描述產出 4 個可直接供 Stable Diffusion/SDXL 使用的 prompt 與 4 個 negative prompt。每個 prompt 包含風格（如：動畫、寫實、日漫）、攝影機鏡頭、色彩與細節。

**Input example (scene):**
{
  "scene_id":1,
  "description":"夜晚的港口，霧氣瀰漫，女主靠著木欄望向海面，背後有微弱路燈。",
  "characters":["女主: 20歲, 黑長髮, 皮夾克"],
  "mood":"孤寂, 懸疑"
}

**Output:** JSON with prompts:

[
  {
    "prompt": "...",
    "negative_prompt": "..."
  }, ...
]

## 3) Image assets → 動態短片（拼接）Prompt（Video service)
請提供一段 10–20 秒的 video prompt，用來指示短片產生工具（Pika/Runway）做到：
- 角色動作（如：女主轉頭，風吹亂髮）
- 鏡頭動作（如：慢推近）
- 欲採用的 reference images（若有）
- 配樂 / SFX 時間點

**Output format:** Plain text structured prompt

## 4) TTS Prompt
為角色生成自然語音（語調、情緒、停頓標註）。提供給 ElevenLabs 或 Google TTS 使用。

**Example:**
[女主 - 沉穩且微弱] "（停頓0.5s）我一直在等你...（略帶哽咽）"
