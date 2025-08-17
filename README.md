# GitHub Issue Parser MCP Server

一个用于解析 GitHub Issues 并返回格式化文本内容的 MCP (Multi-agent Collaboration Protocol) 服务器。该服务可与支持 MCP 的 AI 助手（如 Claude）集成，使其能够读取和分析 GitHub Issue。

## 功能

- 解析 GitHub Issue URL，获取完整的 Issue 内容
- 返回格式化的纯文本内容，包括：
  - Issue 标题和基本信息
  - Issue 描述
  - Issue 标签
  - 所有评论
  - 反应（如 👍、❤️ 等）
- 提供 Issue 分析提示功能，支持不同类型的分析
- 实现为 MCP 资源，可通过 `github-issue://` URL 方案访问

## 使用方法

### 使用 MCP 服务

在 `mcp-config.json` 中配置：

```json
{
  "mcpServers": {
    "github-issue-parser": {
      "command": "uvx",
      "args": [
        "--from",
        "github-issue-parser-mcp",
        "github-issue-parser"
      ]
    }
  }
}
```

## 依赖项

- Python >= 3.8
- fastmcp >= 0.1.0
- requests >= 2.28.0
- beautifulsoup4 >= 4.11.0

## 许可证

MIT 许可证
