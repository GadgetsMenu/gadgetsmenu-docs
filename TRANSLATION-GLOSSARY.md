# Translation Glossary (zhCN)

Terminology reference for `content/zhCN`. Terms here are derived from the terms already
shipped in the site UI (`src/assets/language/language_zhCN.json`) so the wiki body text and
the sidebar/menu labels agree. Use these exact renderings — do not introduce synonyms.

## Kept in English (never translated)

Proper nouns, plugin names, and anything a user must type or match against the game.

| Term | Reason |
| --- | --- |
| GadgetsMenu | Plugin name |
| Mystery Dust | In-game currency, kept as a brand term |
| Morphs | Cosmetic category, kept as-is in the UI |
| Spigot, Bukkit, Paper | Server software |
| MySQL, SQLite | Storage engines |
| Vault, PlayerPoints, CoinsAPI, TokenManager, CoinsEngine | Economy plugins |
| PlaceholderAPI, ProtocolLib, WorldGuard, Lib's Disguise, iDisguise | Dependency plugins |
| API, TPS, UUID, YAML, JSON | Technical acronyms |
| Cosmetic item display names (e.g. `Hamburger Hat`, `Infernal Wings`) | Must match the names shown in game |
| Config keys, permission nodes, commands, placeholders, enum values | Copied verbatim by the user |

## Core terms

| English | zhCN |
| --- | --- |
| Cosmetic / Cosmetic Item | 化妆品 |
| Custom Cosmetic Items | 自定义化妆品 |
| Cosmetic Purchase | 化妆品购买 |
| Cosmetic Purchase Price Discount | 化妆品购买价格优惠 |
| Mystery Box / Mystery Boxes | 神秘箱 |
| Custom Mystery Box Loot | 自定义神秘箱战利品 |
| Mystery Vault | 神秘宝库 |
| Mystery Vault Animation | 神秘宝库动画 |
| Mystery Gift | 神秘礼物 |
| Menu Selector | 菜单选择器 |
| Main Menu | 主菜单 |
| Main Menu Custom Item | 主菜单自定义物品 |
| Blacklisted Region | 黑名单地区 |
| Placeholder | 占位符 |
| Permission | 权限 |
| Command | 命令 |
| Configuration / Config | 配置 |
| Changelog | 更新日志 |
| Data Migration | 数据迁移 |
| Custom Economy Storage | 自定义经济存储 |
| Material Syntax | 材料语法 |
| Texture Head | 头颅材质 |
| Head Textures | 头颅材质列表 |
| Why Premium | 为什么选择高级版 |
| Sounds | 音效 |
| Potions | 药水 |
| Banner Patterns | 旗帜图案 |
| Particle Effects | 粒子效果 |
| Installation | 安装 |
| FAQ | 常见问题 |
| Translations | 翻译 |
| Developer API | 开发者 API |

## Cosmetic categories

| English | zhCN |
| --- | --- |
| Hats | 帽子 |
| Animated Hats | 动画帽子 |
| Particles | 粒子效果 |
| Suits | 套装 |
| Gadgets | 小工具 |
| Pets | 宠物 |
| Miniatures | 微缩模型 |
| Morphs | Morphs |
| Banners | 旗帜 |
| Emotes | 表情 |
| Cloaks | 披风 |

Prefix each with 自定义 for the custom variants, e.g. Custom Hats → 自定义帽子.

## Rarity

Rarity words are also config values. Use the Chinese term in prose; keep the English
form verbatim inside code blocks, config samples, and tables of accepted values.

| English | zhCN |
| --- | --- |
| Common | 普通 |
| Rare | 稀有 |
| Epic | 史诗 |
| Legendary | 传说 |

## Recurring wording

| English | zhCN |
| --- | --- |
| player | 玩家 |
| server owner | 服务器管理员 |
| equip / unequip | 装备 / 卸下 |
| unlock | 解锁 |
| purchase | 购买 |
| craft | 合成 |
| loot | 战利品 |
| rarity | 稀有度 |
| duplicate | 重复 |
| chance | 几率 |
| animation | 动画 |
| plugin | 插件 |
| section | 部分 |
| option / setting | 选项 / 设置 |
| default | 默认 |
| enabled / disabled | 启用 / 禁用 |
| supported | 支持 |
| required / requires | 需要 |
| optional | 可选 |
| example | 示例 |
| format | 格式 |
| value | 值 |
| Further reading | 延伸阅读 |
| Relevant Link / Relevant content | 相关链接 / 相关内容 |
| **Note:** | **注意：** |
| **Warning:** | **警告：** |

## Conventions

- Frontmatter: translate `title`, `description`, `keywords`, `topics`. Keep `group`
  unchanged — it is an identifier used by the site.
- Keep every link path, HTML wrapper (`<div class="...">`), code fence, table markup, and
  image URL byte-identical to the enUS source.
- Do not translate text inside code fences, including YAML comments the user copies verbatim.
- Use full-width punctuation (。，：？！（）) in Chinese prose; keep half-width punctuation
  inside code and paths.
- Put a space between Chinese text and adjacent Latin words or numbers.
