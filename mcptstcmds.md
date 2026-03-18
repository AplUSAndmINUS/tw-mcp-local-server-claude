Curl (Non-Windows)
curl -X POST "https://api.anthropic.com/v1/messages" -H "x-api-key: sk-ant-api03-meOZ0EVTGs0gj8Ry4KmaxUNe5d4iGDJ_e9qDTM-fCAxFxim_dvA4Wk1r9fNi3FLqf_oXJE5JY-3h7C-0kYzHaQ-\_BmZvAAA" -H "anthropic-version: 2023-06-01" -H "content-type: application/json" -d "{\"model\": \"claude-sonnet-4-20250514\", \"max_tokens\": 1024, \"messages\": [{\"role\": \"user\", \"content\": \"Hello, world\"}]}"`

---

Powershell:
curl.exe -X POST "https://api.anthropic.com/v1/messages" `-H "x-api-key: YOUR_API_KEY"`
-H "anthropic-version: 2023-06-01" `-H "content-type: application/json"`
-d "@request.json"

$headers = @{
"x-api-key" = "YOUR_API_KEY"
"anthropic-version" = "2023-06-01"
"content-type" = "application/json"
}

$body = @{
model = "claude-sonnet-4-20250514"
max_tokens = 1024
messages = @(
@{
role = "user"
content = "Hello, world"
}
)
} | ConvertTo-Json

Invoke-RestMethod -Uri "https://api.anthropic.com/v1/messages" -Method Post -Headers $headers -Body $body

---

request.json:
{
"model": "claude-sonnet-4-20250514",
"max_tokens": 1024,
"messages": [
{"role": "user", "content": "Hello, world"}
]
}
