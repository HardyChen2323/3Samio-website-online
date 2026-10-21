# 3SAMIO 赛明欧 — 官网

财经传播与投资者关系服务官网。纯静态站点，无构建步骤、无外部 CDN 依赖，可直接部署。

## 目录结构

```
.
├── index.html                     # 部署入口（当前版本 v4）
├── 3samio-office-site-v4.html     # 同内容版本副本，便于版本追溯
├── images/                        # 全部图片素材（61 个文件，所有页面共用）
├── fonts/Manrope/                 # Manrope 字体（5 个字重，本地加载）
├── .nojekyll                      # GitHub Pages：跳过 Jekyll 处理
└── README.md
```

## 页面结构

单页应用（SPA），使用 hash 路由，所有页面共用同一套 `images/` 与 `fonts/` 资源：

| 路由 | 页面 |
| --- | --- |
| `/` | 首页 |
| `#/about` | 关于我们 |
| `#/services` | 核心服务 |
| `#/cases` | 客户案例 |
| `#/contact` | 联系我们 |

因此**不需要为每个子页面单独建立文件夹**，`images/` 目录下的素材会被所有页面共享引用。

## 本地预览

```bash
python3 -m http.server 8000
```

打开 http://localhost:8000

## 部署到 GitHub Pages

1. 将本目录全部文件推送到仓库默认分支（如 `main`）
2. 仓库 Settings → Pages → Source 选择 `Deploy from a branch`
3. Branch 选择 `main`，目录选择 `/ (root)`
4. 保存后等待 1–2 分钟，访问 `https://<用户名>.github.io/<仓库名>/`

自定义域名：在 Settings → Pages 填写域名，并按提示配置 CNAME 记录。

## 更新流程

修改 `index.html`（以及同名版本副本），同步替换 `images/` 中变更的图片即可。建议每次更新递增版本号并保留历史副本。
