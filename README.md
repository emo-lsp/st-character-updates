# st-character-updates

SillyTavern 角色卡自动更新资源仓库 | Auto-update resources for SillyTavern character cards

## 简介 | Introduction

本仓库用于托管 SillyTavern 角色卡的更新文件，配合[酒馆助手](https://github.com/StageDog/tavern_resource)的自动更新脚本，实现角色卡的远程自动更新。

This repository hosts update files for SillyTavern character cards. Works with [Tavern Helper](https://github.com/StageDog/tavern_resource)'s auto-update script to enable remote automatic updates.

## 使用方式 | Usage

### 1. 上传角色卡 | Upload Character Card

将导出的角色卡 PNG 文件和更新日志放入仓库：

Place the exported character card PNG and changelog into this repository:

```
st-character-updates/
├── 角色卡名.png
└── 更新日志.md
```

### 2. 配置脚本 | Configure Script

在角色卡的 `index.yaml` 中添加自动更新脚本：

Add the auto-update script to your character card's `index.yaml`:

```yaml
- 名称: 自动更新角色卡
  启用: true
  类型: 脚本
  内容: |-
    import 'https://testingcf.jsdelivr.net/gh/StageDog/tavern_resource/dist/酒馆助手/自动更新角色卡/index.js';
  数据:
    角色卡名称: <角色卡名称 | card name>
    角色卡链接: https://testingcf.jsdelivr.net/gh/emo-lsp/st-character-updates/<角色卡文件名.png>
    更新日志链接: https://testingcf.jsdelivr.net/gh/emo-lsp/st-character-updates/更新日志.md
```

### 3. 发布更新 | Publish Updates

每次更新角色卡时：

When updating a character card:

1. 从酒馆导出最新的角色卡 PNG | Export the latest character card PNG from SillyTavern
2. 替换仓库中的 PNG 文件 | Replace the PNG file in this repository
3. 更新 `更新日志.md` | Update the changelog
4. 推送到 GitHub | Push to GitHub

用户端会自动检测并提示更新。

Users will be automatically notified of available updates.

## CDN 链接格式 | CDN URL Format

```
https://testingcf.jsdelivr.net/gh/emo-lsp/st-character-updates/<文件路径>
```

## 许可 | License

MIT
