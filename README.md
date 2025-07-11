# TikZ MCP Server

TikZ图表渲染MCP服务器，将TikZ代码转换为图片。

## 功能特性

- 渲染TikZ图表为PNG图片
- 支持数学公式、流程图、技术图表
- 兼容Cherry Studio客户端

## 安装要求

### 必需依赖

1. **Python 3.10+**
2. **TeX Live** (包含pdflatex)
3. **ImageMagick** (包含convert命令)
4. **MCP库**: `pip install mcp`

### macOS安装

```bash
# 安装TeX Live
brew install --cask mactex

# 安装ImageMagick  
brew install imagemagick

# 安装MCP库
pip install mcp
```

## Cherry Studio配置

1. 打开Cherry Studio设置
2. 找到MCP Servers部分
3. 添加新服务器，使用以下配置：

```json
{
  "mcpServers": {
    "tikz-renderer": {
      "name": "TikZ Renderer",
      "type": "STDIO",
      "command": "/path/to/python3",
      "args": ["/path/to/tikz-mcp-server/tikz_mcp_server.py"],
      "env": {},
      "description": "TikZ diagram renderer"
    }
  }
}
```

**注意**: 请将`/path/to/tikz-mcp-server/tikz_mcp_server.py`替换为实际的文件路径。

## 许可证

MIT License