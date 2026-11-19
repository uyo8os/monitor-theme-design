# monitor-theme-design

[monitor](https://github.com/uyo8os/monitor) 的公开页主题。

Fork 自 [stqfdyr/monitor-theme-serverstatus](https://github.com/monitor-probe/monitor-theme-serverstatus)，结合 tweakcn(ShadcnUI) Tokens 与 Zen Browser 风格的噪点磨砂效果。

![预览](preview.png)

## 特性

- **配色切换**：均含亮色/暗色模式。
- **噪点与磨砂效果**：两个参数各支持 0%~100% 无级调节。
- **服务器列表**：显示节点的 TCP 连接数和 UDP 套接字数。
- **监控页筛选**：上方按搜索、分组、地区、系统、在线状态筛选节点，下方查看图表（包括 TCP 和 UDP 历史数据），桌面端与移动端布局一致。

## 安装

### 方法一：从 GitHub 安装

先确保本仓库的 Release 已发布 `theme.tar.gz`。登录 monitor hub 后台，进入「主题」管理页面，选择「从 GitHub 安装」，填写本仓库地址：

```text
https://github.com/uyo8os/monitor-theme-design
```

### 方法二：后台上传压缩包

1. 在 [Releases](https://github.com/uyo8os/monitor-theme-design/releases) 页面下载最新的 `theme.tar.gz`。
2. 登录 monitor hub 后台，进入「主题」管理页面。
3. 上传 `theme.tar.gz` 完成安装。卡片上的 ⟳ 按钮可检查本仓库是否有新版本。

### 方法三：解压至目录

将 release 产物解压到 hub 所在主机 `--themes` 目录下的 `Design/` 文件夹，目录名需与 `theme.json` 的 `short` 一致：

```bash
mkdir -p /path/to/monitor/themes/Design
tar -xzf theme.tar.gz -C /path/to/monitor/themes/Design
```

然后在后台「主题」页刷新并选中切换。

## 发布

主题的实际版本由 `theme.json` 的 `version` 决定，必须与发布标签一致（例如 `2.1.2` 对应 `v2.1.2`）。发布新版本前，修改 `theme.json`，并同步修改 `.github/workflows/release.yml` 中 `version` 输入的 `default`，然后提交并推送这些改动。手动发布表单当前默认显示 `v2.1.1`；版本变更后需要手动同步默认值。

可以通过以下任一方式发布，版本标签须符合 `v数字.数字.数字` 格式：

1. 推送版本标签，例如 `git tag v2.1.2`，再执行 `git push origin v2.1.2`。
2. 在 [Actions 页面](https://github.com/uyo8os/monitor-theme-design/actions)选择 **Publish release**，点击 **Run workflow**，选择要发布的分支，确认版本号后运行。

工作流会运行检查、测试和构建，通过后发布 `theme.tar.gz` 及其 `theme.tar.gz.sha256`，并设为最新 Release。手动运行时，不存在的标签会指向所选提交；已有标签如果指向其他提交，工作流会报错而不会移动标签。如果对应 Release 已存在，也会报错。发布前请先确认版本标签和 Release 尚未使用。

工作流使用 GitHub 自动提供的 `GITHUB_TOKEN`，无需手动创建发布用 Secret。仓库需要启用 Actions，发布任务需要仓库内容写入权限。

## 协议与致谢

- 本项目基于 [MIT License](LICENSE) 开源。
- 感谢 [monitor-probe/monitor](https://github.com/monitor-probe/monitor)。
- 感谢 [stqfdyr](https://github.com/stqfdyr) 的原版 [monitor-theme-serverstatus](https://github.com/monitor-probe/monitor-theme-serverstatus) 主题。
- 国旗图标来自 [flag-icons](https://github.com/lipis/flag-icons)，MIT 协议。
