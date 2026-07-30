# Fork 配置说明

本 Fork 仅保留以下自定义配置。同步上游后逐项核对即可。

## 默认 API 地址

文件：`web/src/stores/use-config-store.ts`

```text
OPENAI_BASE_URL=https://api.zhangyuapi.com
```

## 官网入口

文件：`web/src/components/layout/github-link.tsx`

- 链接：`https://zhangyuapi.com`
- 图标：`LinkOutlined`
- `aria-label` 和 `title`：`官网`

## Docker 镜像

| 文件 | 镜像 |
|------|------|
| `.github/workflows/docker-image.yml` | `ghcr.io/qzq00767/painting-canvas` |
| `.github/workflows/docs-docker-image.yml` | `ghcr.io/qzq00767/painting-canvas-docs` |
| `docker-compose.yml` | `ghcr.io/qzq00767/painting-canvas:latest` |
| `docs/docker-compose.yml` | `ghcr.io/qzq00767/painting-canvas-docs:latest` |
