---
title: 数据迁移（从 SQLite 到 MySQL）
description: 您可以将 SQLite 本地数据迁移到 MySQL 数据库，而不会丢失玩家的数据。
group: setup
keywords: 数据迁移, 数据库迁移, sqlite 到 mysql
topics:
 - 数据迁移
 - 数据库迁移
 - sqlite 到 mysql
---

将数据从 SQLite 迁移到当前已连接的 MySQL 数据库。

## 要求
* 插件已连接到 MySQL 数据库。
* MySQL 数据库与 MC 服务器之间的网络连接稳定。
* 迁移过程中请勿停止服务器。
* 在进行迁移之前，请确保您已经做好备份。
* 建议（但非必须）使用一个不含任何 GadgetsMenu 数据的 MySQL 数据库。

## 步骤
1. 确保您的服务器没有处于高负载状态。（服务器中没有玩家时最佳）
2. 在游戏内命令面板或控制台中执行命令 `/gmenu migrate confirm`。
3. 等待迁移完成。（完成后会显示一条成功消息）

## 输出消息示例
![数据迁移](/assets/gadgetsmenu-docs/images/others/data-migration-migrate-data-from-sqlite-to-mysql.png "[Wrapper] Data migration")
