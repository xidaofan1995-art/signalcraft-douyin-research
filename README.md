# SignalCraft · 抖音选题台

一个可通过 GitHub Pages 发布的静态研究工具。入口为 `index.html`，可直接在浏览器打开，也可用 `python3 -m http.server` 从项目目录启动。

## 功能

- 作品筛选、账号检索、热点排行，以及各自的指标排序。
- 关键词任意词、全部词及完整短语匹配。多分类筛选、日期区间及最低指标。
- 本地关注和收藏、保存筛选、导出当前筛选的完整 CSV。
- 导入 JSON 后，数据和收藏保存在当前浏览器。清理站点数据会清掉这些记录。

内置数据为演示。授权接口接入需要服务端管理凭证，前端从服务端读取标准化数据。账号收藏仅记录本地清单，热点按导入的日期与热度显示。

## 导入示例

```json
{
  "videos": [
    {"id":"work-1","title":"智能硬件选型笔记","author":"示例账号","category":"科技数码","date":"2026-11-25","likes":280,"comments":21,"shares":16,"saves":32}
  ],
  "accounts": [
    {"id":"author-1","title":"示例账号","category":"科技数码","posts":24,"followers":5800,"likes":37000}
  ],
  "trends": [
    {"id":"topic-1","title":"智能家居","category":"生活家居","date":"2026-11-25","heat":89000}
  ]
}
```

三个数组按需提供，导入会替换相应模块。每个模块内 ID 唯一，可提供 `url` 作为公开来源链接。标题必填。作品和热点的日期使用 YYYY-MM-DD，指标是非负整数。

## 发布

在 GitHub 仓库的 **Settings → Pages** 中选择 **Deploy from a branch**，发布源选择 **main / (root)**。当前端部署在项目子路径时也可直接运行。
