# 项目说明：Coze 流式 API 前端调用示例

本项目演示如何通过前端 JS 脚本调用 Coze 流式对话 API，并实时展示返回内容。

## 主要文件
- `api.js`：封装 API 调用的 JS 脚本，支持流式响应处理。
- `index.html`：测试页面，可输入 content 并实时查看 API 返回内容。

## 使用方法
1. 打开 `index.html`，输入你想发送的内容（content），点击按钮即可发起请求。
2. 返回内容会实时显示在页面下方。

## API 调用说明
- 请求地址：`POST https://api.coze.cn/v3/chat?conversation_id=7374752000116113452`
- Header：
  - `Authorization: Bearer YOUR_API_KEY_HERE`  <!-- ⚠️ 请勿在此处填写真实 API Key，上传前请务必检查并替换 -->
  - `Content-Type: application/json`
- Body 参数：
  - `bot_id`、`user_id`、`stream`、`auto_save_history` 固定。
  - `additional_messages[0].content`：由前端输入。
  - `additional_messages[0].content_type`：固定为 `object_string`。

## 参数说明
| 参数名                | 说明                      |
|----------------------|---------------------------|
| content              | 发送内容，支持图片和文本等 |

## 返回值说明
- 返回为流式文本（SSE），页面会实时展示。

## 注意事项
- 本项目仅供学习和测试。
- 请勿泄露或滥用 API Key。
