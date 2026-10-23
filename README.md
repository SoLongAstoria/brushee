# Brushee 落地页（GitHub Pages）

纯静态、无 JS 追踪、无外部字体请求。整个目录就是站点根目录。

## 文件

```
landing/
├── index.html              产品主页
├── printables/index.html   三张可打印图表（Pinterest 的落点）
└── assets/
    ├── icon.png            512×512 应用图标
    ├── og.png              1024×500 分享图
    ├── 01-brushing.png     刷牙页截图
    └── 03-report-week.png  家长周报截图
```

## 部署（新建 `brushee` 仓库）

1. 在 GitHub 新建仓库 **`SoLongAstoria/brushee`**，公开（Pages 免费版要求公开）。
2. 把 `landing/` 里的**内容**（不是 `landing` 这一层目录）推到仓库根：
   ```bash
   cd landing
   git init
   git add .
   git commit -m "Brushee landing page"
   git branch -M main
   git remote add origin https://github.com/SoLongAstoria/brushee.git
   git push -u origin main
   ```
3. 仓库 → Settings → Pages → Source: **Deploy from a branch** → `main` / `/ (root)`。
4. 等 1–2 分钟，访问 `https://solongastoria.github.io/brushee/`。

> 如果仓库名不是 `brushee`，把 `index.html` 里的三处
> `https://solongastoria.github.io/brushee/` 一起改掉（canonical、og:url、printables 的 canonical）。

## 部署后自检

- [ ] 首页图片全部显示（图标、两张截图）
- [ ] `Get it on Google Play` 能跳到正确商店页
- [ ] `/printables/` 能打开，点 `Print these` 能出打印预览
- [ ] 页脚 Privacy / Terms / Discord 三个链接都能打开
- [ ] 手机宽度下没有横向滚动
- [ ] 用无痕窗口打开，确认没有登录墙

## 之后把链接用在哪

| 位置 | 怎么用 |
|---|---|
| Pinterest | 每条 Pin 的链接指向首页或 `/printables/` |
| Reddit / Product Hunt / Show HN | 帖子正文用落地页链接，不直接放 Play（便于统计点击） |
| Play Console | 商店列表的「网站」字段可以填首页 |
| Discord | 服务器简介里放首页，不放邀请链接 |
| 邮件签名 | `Brushee — brushee.app`（如果以后买域名） |

## 不做的事

- 不加 Google Analytics / Meta Pixel / 任何第三方脚本 —— 落地页说「无追踪」，自己先做到。
- 不买域名之前，不要在任何地方写 `brushee.app`；现在只有 GitHub Pages 地址是真实的。
- 不把儿童照片放上来；现有截图里的孩子是卡通形象。
