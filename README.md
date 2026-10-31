# dsh-anime-guide

[DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness) **番剧**插件：读多源新番表与排行榜，支持搜索、推荐，以及**国内外榜差异对照**。

> 社区插件，与 DeepSeek / 各数据站官方无关。  
> 英文简版：[README.en.md](./README.en.md)

## 安装

```bash
dsh plugin --profile web add github:DSH-Raising-Plan/dsh-anime-guide#plugin/dsh
```

## 数据源

| 区域 | 来源 | 说明 |
| --- | --- | --- |
| 新番表 | [yuc.wiki](https://yuc.wiki) | 当季（或指定季）新番时刻表 |
| 国内 | [番库评分榜](https://fankuhub.com/ratings) | 季度 / 历史评分 |
| 国内 | [Bangumi 排名](https://bgm.tv/anime/browser?sort=rank) | 动画按 Rank 浏览 |
| 国际 | [MyAnimeList Top Anime](https://myanimelist.net/topanime.php) | 全球用户 Top |

国内榜更偏华语社区审美与经典冷门神作；国际榜（MAL）更偏近年热作、英语圈热度与完成度口碑。`anime_contrast` 会做跨源标题匹配，并标出「国内更高 / 国际更高 / 仅一侧 TOP」。

## 工具

| 工具 | 作用 |
| --- | --- |
| `anime_season` | 读取 yuc.wiki 新番表（可写「2026春番」等） |
| `anime_ratings` | 评分榜；`source=fankuhub\|bangumi\|mal\|all` |
| `anime_search` | 跨季表 + 三榜检索 |
| `anime_recommend` | 本季 × 评分交叉推荐 |
| `anime_contrast` | 国内外榜差异对照 |

## 开发

```bash
npm test
npm run check
```

需要 `@deepseek-ai/dsh-tools`（或设置 `DSH_TOOLS_PATH`）才能在 Harness 中注册工具。

> Windows 上 Node 直连 `bgm.tv` 偶发超时：插件会自动回退到 PowerShell `WebClient` 拉取。

## 许可

AGPL-3.0-or-later


---

> **为什么还要开发 Mnemosyne？** [阅读全文 →](WHY_MNEMOSYNE.md)
