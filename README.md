# Clash Dashboard (yacd) 安装配置指南

[yacd](https://github.com/haishanh/yacd) 是一个简洁美观的 Clash Web 面板，支持订阅管理、节点切换、延迟测试。

## 功能特性

- Web 界面 - 浏览器直接访问，无需安装客户端
- 实时状态 - 显示当前节点、速度、流量统计
- 一键切换 - 快速切换代理节点和策略组
- 订阅更新 - 支持自动更新订阅链接
- 深色模式 - 默认深色护眼界面

## 快速部署

### Docker 部署（推荐）

```bash
docker run -d \
  --name yacd \
  -p 9090:9090 \
  --restart always \
  ghcr.io/haishanh/yacd:latest
```

访问 `http://your-server:9090` 即可使用。

### 直接部署

```bash
# 下载 yacd
wget https://github.com/haishanh/yacd/releases/latest/download/yacd.tar.xz
tar -xf yacd.tar.xz
```

## 对接 Clash

1. 打开 yacd 界面
2. 点击顶部设置图标
3. 填入 Clash 控制面板地址：`http://your-clash:9090`
4. 输入 Clash Secret（环境变量 `CLASH_SECRET`）
5. 保存后即可使用

## 对接 Sub-Web

yacd 配合 [Sub-Web](https://github.com/CareyWang/sub-web) 使用，获得更强大的订阅转换功能。

## 常见问题

**Q: 界面打不开？** 检查 Docker 端口映射和防火墙设置。

**Q: 无法连接 Clash？** 确认 Clash 的 `external-controller` 配置和 yacd 地址一致。

---

推荐工具：

- [Clash for Windows](https://clashforwindows.site/) - Windows 最流行 Clash 客户端
- [ClashMI](https://clashmi.site/) - 轻量级多平台 Clash 客户端
- [FlClash](https://flclash.us/) - 现代代理工具，支持多种协议
