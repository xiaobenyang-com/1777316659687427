# 时间感知服务器 

Time MCP Server是一个为大型语言模型提供时间感知能力的服务器实现，支持获取当前时间、相对时间、时间戳转换等功能。
Time MCP Server is a server implementation that provides time aware capabilities for large language models, supporting functions such as obtaining current time, relative time, and timestamp conversion.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| current_time | Get the current date and time. |
| relative_time | Get the relative time from now. |
| days_in_month | Get the number of days in a month. If no date is provided, get the number of days in the current month. |
| get_timestamp | Get the timestamp for the time. |
| convert_time | Convert time between timezones. |
| get_week_year | Get the week and isoWeek of the year. |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659687427](https://mcp.xiaobenyang.com/inspector/1777316659687427)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659687427](https://mcp.xiaobenyang.com/inspector/1777316659687427)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "时间感知服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659687427/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "时间感知服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659687427/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "时间感知服务器": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659687427",
          },
          "transport": "stdio"
        }
      }
}

```
