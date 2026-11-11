# 用一科技 Axure 原型

这个仓库直接保存 Axure 11 导出的完整 HTML 原型。`index.html` 位于仓库根目录，页面、图片、样式和脚本保留 Axure 原有的相对路径，可以直接作为静态网站部署，无需安装项目依赖或执行构建。

## 查看原型

部署后打开网站首页即可使用 Axure 自带的页面目录并操作原型。`start.html` 也是原型播放器入口。预览应使用 HTTP 或 HTTPS；本地直接双击 Axure 原始 HTML 时，浏览器可能要求 Axure 扩展。

## 目录结构

| 路径 | 用途 |
| --- | --- |
| `index.html`、`start.html` | Axure 播放器入口 |
| 根目录其他 `.html` 文件 | 设计页面及 Axure 生成的辅助入口 |
| `data/` | 页面目录、全局样式和原型设置 |
| `files/` | 各页面的样式、数据和交互 |
| `images/` | 原型图片 |
| `resources/`、`plugins/` | Axure 播放器及运行资源 |
| `docs/` | 部署和日常更新说明 |

## 部署到 Vercel

导入 `picmagic/yongyi_product_design`，使用以下配置：

| 配置项 | 设置 |
| --- | --- |
| Root Directory | 仓库根目录 |
| Framework Preset | `Other` |
| Build Command | 开启 Override，留空，跳过构建 |
| Output Directory | `.` |

本项目没有 `package.json` 或安装步骤。不要添加将所有路径改写到首页的规则，Axure 的页面和资源需要通过各自的原始路径访问。

当前约定：日常更新推送到 `dev`，由开发同事审核并合并到 `main`。首次发布时如果还没有 `main`，由开发同事从验收后的 `dev` 创建；生产部署绑定 `main`。

Vercel 无法保证中国大陆网络的访问稳定性，正式使用前请通过实际访问网络验收。公司商业用途应选择适用的 Vercel 套餐。

## 更新原型

1. 在 Axure 中完成设计并重新生成完整 HTML 导出文件。
2. 同步到本目录，保留导出目录结构，以及 `.git/`、`.gitignore`、`README.md` 和 `docs/`。
3. 检查已删除或改名页面的旧文件，预览首页和本次改动涉及的页面。
4. 提交并推送到 `dev`，交由开发同事合并到 `main`。

原型公开链接只提供查看和交互；此仓库未添加在线上传或共享评论服务。完整步骤见 [部署与更新说明](docs/部署与更新.md)。

## 参考

- [Vercel 静态网站构建设置](https://vercel.com/docs/builds/configure-a-build)
- [Vercel 与 Git 集成](https://vercel.com/docs/deployments/git)
- [Vercel 中国大陆访问说明](https://vercel.com/kb/guide/accessing-vercel-hosted-sites-from-mainland-china)
- [Vercel Hobby 套餐用途限制](https://vercel.com/docs/plans/hobby)
