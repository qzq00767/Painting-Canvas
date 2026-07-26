# Fork 配置说明

本文件记录本 fork 的所有自定义配置。合并上游更新后，按此文档重新应用配置。

## 品牌信息

| 项目 | 值 |
|------|-----|
| 官网 | https://zhangyuapi.com |
| GitHub | https://github.com/qzq00767/Painting-Canvas |
| 作者名 | zhangyuapi |
| 镜像名 | ghcr.io/qzq00767/painting-canvas |

## 需要修改的文件

### 1. 品牌链接

**文件**: `web/src/components/layout/github-link.tsx`
- 链接改为 `https://zhangyuapi.com`
- 图标改为 `LinkOutlined`
- aria-label 和 title 改为"官网"

### 2. 默认 API 地址

**文件**: `web/src/stores/use-config-store.ts`
- 第 63 行 `OPENAI_BASE_URL` 改为 `https://api.zhangyuapi.com`
- 第 75 行默认渠道 `baseUrl` 改为 `https://api.zhangyuapi.com`

### 3. Docker 镜像名

**文件**: `.github/workflows/docker-image.yml`
- `IMAGE_NAME` 改为 `ghcr.io/qzq00767/painting-canvas`

**文件**: `.github/workflows/docs-docker-image.yml`
- `IMAGE_NAME` 改为 `ghcr.io/qzq00767/painting-canvas-docs`

**文件**: `docker-compose.yml`
- `image` 改为 `ghcr.io/qzq00767/painting-canvas:latest`

**文件**: `docs/docker-compose.yml`
- `image` 改为 `ghcr.io/qzq00767/painting-canvas-docs:latest`

### 4. Git clone 命令

搜索替换以下内容：

```
git clone https://github.com/basketikun/infinite-canvas.git
→ git clone https://github.com/qzq00767/Painting-Canvas.git

git clone git@github.com:basketikun/infinite-canvas.git
→ git clone git@github.com:qzq00767/Painting-Canvas.git

cd infinite-canvas
→ cd Painting-Canvas
```

涉及文件：
- `README.md`
- `docs/content/docs/overview/quick-start.mdx`
- `docs/content/docs/overview/docker.mdx`
- `docs/content/docs/overview/codex-app-plugin.mdx`
- `plugins/infinite-canvas/README.md`

### 5. 仓库地址

搜索替换以下内容：

```
github.com/basketikun/infinite-canvas
→ github.com/qzq00767/Painting-Canvas
```

涉及文件：
- `README.md`
- `docs/src/lib/shared.ts`
- `web/src/constant/env.ts`（插件 registry URL）
- `plugins/canvas/registry/README.md`
- `plugins/infinite-canvas/.codex-plugin/plugin.json`

### 6. 作者信息

**文件**: `plugins/infinite-canvas/.codex-plugin/plugin.json`
- `author.name` 改为 `zhangyuapi`
- `author.url` 改为 `https://zhangyuapi.com`
- `homepage` 改为 `https://zhangyuapi.com`
- `developerName` 改为 `zhangyuapi`

### 7. 删除的文档

合并上游时如果新增了文档，以下目录的文档可以删除：
- `docs/content/docs/progress/`
- `docs/content/docs/support/`
- `docs/content/docs/business/`

保留的核心文档：
- `docs/content/docs/overview/features.mdx`
- `docs/content/docs/overview/quick-start.mdx`
- `docs/content/docs/overview/docker.mdx`
- `docs/content/docs/canvas/canvas-node-manual.mdx`
- `docs/content/docs/canvas/canvas-shortcuts.mdx`
- `docs/content/docs/development/local-development.mdx`
- `docs/content/docs/development/canvas-data-structure.mdx`
