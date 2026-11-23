[![SVG Banners](https://svg-banners.vercel.app/api?type=origin&text1=GKD第三方订阅规则&text2=💖%20GKD_subscription&width=800&height=350)](https://github.com/Lin-arm/GKD_subscription)

[![Release](https://img.shields.io/badge/发行版-v644-blue)](https://github.com/Lin-arm/GKD_subscription/releases/latest)
[![已适配应用](https://img.shields.io/badge/已适配应用-1010-brightgreen)](./dist/README.md#应用规则)
[![全局规则组](https://img.shields.io/badge/全局规则组-3-blueviolet)](./dist/README.md#全局规则)
[![应用规则组](https://img.shields.io/badge/应用规则组-2530-orange)](./dist/README.md#应用规则)
[![Telegram Chat](https://img.shields.io/badge/Telegram-交流群-blue.svg?logo=telegram)](https://t.me/+8L4eHePgYEZmY2M9)

## 📢声明

- **本仓库为原仓库停更后，由社区续更的Fork版**
- **禁止在国内平台传播**
- **本仓库仅供学习交流使用**
- **精力有限，随缘更新**

## 🚀订阅

> [!WARNING]
> `gkd667.vv.ax` 域名的订阅源已停用，请更换其下方的其他源。

复制以下任一链接到 GKD 订阅的右下角 **+** 号那里导入，即可使用

- CloudFlare源 (国内可用)

  ```txt
  https://gkd-subscription-667.pages.dev/gkd.json5
  ```

- GitHub源 (国内需要魔法)

  ```txt
  https://raw.githubusercontent.com/Lin-arm/GKD_subscription/main/dist/gkd.json5
  ```

<details>
<summary>点击展开备用源</summary>

- Xget源 (国内可用)

  ```txt
  https://xget.xi-xu.me/gh/Lin-arm/GKD_subscription/raw/main/dist/gkd.json5
  ```

- jsdelivr源一 (国内可用但可能不稳定)

  ```txt
  https://fastly.jsdelivr.net/gh/Lin-arm/GKD_subscription@main/dist/gkd.json5
  ```

- jsdelivr源二 (国内可用但可能不稳定,更新滞后24h)

  ```txt
  https://cdn.jsdelivr.net/gh/Lin-arm/GKD_subscription@main/dist/gkd.json5
  ```

</details>

## 🔧 Fork 自建源：改完规则后如何刷新订阅链接

本 Fork 的个人订阅地址，内容就是 `main` 分支上的 `dist/gkd.json5`（当前 `v644`）

```txt
https://raw.githubusercontent.com/HeartWardrum/GKD_subscription/main/dist/gkd.json5
https://fastly.jsdelivr.net/gh/HeartWardrum/GKD_subscription@main/dist/gkd.json5
https://cdn.jsdelivr.net/gh/HeartWardrum/GKD_subscription@main/dist/gkd.json5
```

只改 `src/apps/*.ts` 不会让这些链接发生变化 —— 手机读取的是 `dist/gkd.json5`，必须重新构建并把构建产物一起提交

```bash
pnpm run check      # 类型检查 + 订阅校验，不通过不要继续构建

pnpm run build      # 生成 dist/gkd.json5 / dist/README.md / dist/CHANGELOG.md，并刷新本 README

git add src/apps/tv.danmaku.bili.ts README.md dist   # 换成你这次改的源文件
git commit -m "feat: 哔哩哔哩 功能类-xxx规则名"
git push origin main
```

- `raw.githubusercontent.com` 推送后立即生效；jsdelivr 命中旧缓存时访问 `https://purge.jsdelivr.net/gh/HeartWardrum/GKD_subscription@main/dist/gkd.json5` 清理
- 手机 GKD 订阅页下拉就能检测更新；`功能类` 这类分类默认关闭，新增规则组需要手动打开
- 每执行一次 `pnpm run build` 版本号都会 +1（即使规则没改动），不要空跑构建
- 只改文档不动规则时，用下面的命令单独刷新本 README，版本号保持不变

  ```bash
  pnpm exec tsx -e "import('./scripts/updateReadMeMd.ts').then((m) => m.updateReadMeMd())"
  ```

> [!NOTE]
> 本 README 由 `Template.md` 生成，直接改 `README.md` 会在下次构建时被覆盖；要补充说明请改 `Template.md`。

### 用 GitHub Actions 构建（可选，需一次性开权限）

Fork 上 `build_release` 的定时触发默认不执行，且 `GITHUB_TOKEN` 默认只读，产物会在「推送代码到远程仓库」这一步报 `Permission to ... denied to github-actions[bot]`。要用 CI 出产物：

1. 仓库 Settings → Actions → General → Workflow permissions → 选择 **Read and write permissions**
2. `gh workflow run build_release.yml --repo HeartWardrum/GKD_subscription --ref main`
3. 工作流会构建 `dist`、提交 `chore: v<版本号>`、打 tag 并创建 Release

上游的 CloudFlare 源 `gkd-subscription-667.pages.dev` 属于上游自己的部署，不包含本 Fork 的改动。

## 📑说明

- **致力于编写效率最高、误触最低、覆盖最全面的规则**

- **已适配的规则需要等待发布更新才能生效，北京时间每天凌晨2:30后会自动发布更新，如果规则没有改动则不会发布更新，在 `GKD订阅界面` 下拉就能检测是否有更新 -> [点击查看更新日志](https://github.com/Lin-arm/GKD_subscription/releases)**

- **仅启用 `开屏广告` 一类规则，其它所有规则均需用户手动打开，规则类别里可以批量开启某一类规则，建议按需开启规则，不要无脑开启规则，开启过多规则可能造成规则阻塞从而导致规则触发缓慢甚至不触发，并且规则开启越多耗电也越多 -> [点击查看耗电说明](https://gkd.li/guide/faq#power)**

- **请求适配或报告问题 -> [点击反馈](https://github.com/Lin-arm/GKD_subscription/issues/new/choose)**

- **交流讨论（不要在这里反馈） -> [点击查看或开启讨论](https://github.com/Lin-arm/GKD_subscription/discussions)**

- **欢迎贡献规则，提交pr前请确认您已仔细阅读 [贡献指南](./CONTRIBUTING.md) 和 [API文档](https://gkd.li/api/)，规则编写可参考 [个人收集的通用规则以及适用场景](./docs/Selectors.md)**

## 🌈其他

- 在 [GKD官网](https://gkd.li/) 查看 [GKD基础使用教程](https://gkd.li/guide/) 、[常见问题](https://gkd.li/guide/faq) 以及 [API文档](https://gkd.li/api/)

- 使用 [GKD网页审查工具增强脚本](https://github.com/adproqwq/MakeGKDInspectBetter) 可以高度自定义从网页复制出来的规则，提高规则编写效率

- 安装 VS Code 插件 [GKD Toolkit](https://github.com/tianfangyetan1/vscode-gkd-toolkit) ，可以更方便的一次性打开多个快照

- 使用 [GKD订阅模板](https://github.com/gkd-kit/subscription-template) 快速构建自己的订阅

- 相关教程/贡献此项目 -> 查看 [贡献指南](./CONTRIBUTING.md)

## 📜 项目溯源

1. [gkd-kit/subscription](https://github.com/gkd-kit/subscription)
    原始官方订阅源，2023.7~2024.2，最后版本 `v185`

2. [AIsouler/GKD_subscription](https://github.com/AIsouler/GKD_subscription)
    Fork 自官方源，2024.2~2026.2，最后版本 `v406`

3. [Lin-arm/GKD_subscription](https://github.com/Lin-arm/GKD_subscription)
    Fork 自 AIsouler 版本，2026年2月从 `v406` 开始由社区续更至今

## 🥇感谢以下开发者的贡献

![img](https://contrib.rocks/image?repo=Lin-arm/GKD_subscription&max=200&_v=644)

<!-- repobeats 已失效 -->
<!-- ![Alt](https://repobeats.axiom.co/api/embed/db6f46a4bdc4e760fb51976db276f1febef5bdce.svg "报告分析图") -->

## 📈Star History

<!-- [![Star History Chart](https://api.star-history.com/chart?repos=Lin-arm/GKD_subscription&type=date&legend=top-left)](https://www.star-history.com/?repos=Lin-arm%2FGKD_subscription&type=date&legend=top-left) -->

[![Star History Chart](https://starhistory.link/Lin-arm/GKD_subscription.svg?theme=rose&style=glass)](https://starhistory.link/Lin-arm/GKD_subscription)
