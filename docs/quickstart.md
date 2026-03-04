# 3 分钟快速开始

## 1. 前置条件

- 已安装并运行 OpenClaw。
- 已运行 OneBot v11 服务端（推荐 NapCat 或 Lagrange）。
- OneBot 配置中 `message_post_format` 必须为 `array`。

## 2. 安装插件

```bash
cd openclaw/extensions
git clone https://github.com/constansino/openclaw_qq.git qq
cd ../..
pnpm install && pnpm build
```

> 若你是全局安装 OpenClaw（`npm install -g openclaw`）且仅更新扩展目录，通常只需在 `~/.openclaw/extensions/qq` 执行 `npm install`，然后 `openclaw gateway restart`。

## 3. 最小配置

编辑 `~/.openclaw/openclaw.json`：

```json
{
  "channels": {
    "qq": {
      "wsUrl": "ws://127.0.0.1:3001",
      "accessToken": "your_token",
      "requireMention": true
    }
  },
  "plugins": {
    "entries": {
      "qq": { "enabled": true }
    }
  }
}
```

## 4. 启动验证

```bash
openclaw gateway restart
```

验证项：

- 私聊机器人，是否可正常回复。
- 群聊 @ 机器人，是否可正常回复。
- 日志中无持续重连/鉴权报错。

## 5. 下一步

- 需要管理员/黑白名单控制：看 [配置参考](./config-reference.md)。
- 需要容器化部署：看 [NapCat 部署说明](../deploy/napcat/README.md)。
