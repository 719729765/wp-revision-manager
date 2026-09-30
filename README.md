# wp-revision-manager
wordpress文章修订版本批量删除小插件

修订版本管理

WordPress 小插件，用于：

- 后台查看文章与 revision 数量
- 查看平均每篇 revision
- 查看 revision 在“文章 + revision”记录中的占比
- 估算 revision 相关数据库空间
- 后台开关：禁止文章（post）生成新的 revision
- 后台分批清理历史 revision
- 使用 `manage_options` 权限和 WordPress Nonce 安全校验

## 安装

1. 将 `sky-revision-manager.zip` 上传到 WordPress 后台“插件 → 安装插件 → 上传插件”。
2. 安装并启用。
3. 进入“工具 → SKY 修订管理”。

## 说明

“估算占用空间”不是 MySQL 对某个 post_type 的精确空间统计，而是根据整张数据库表的大小和 revision 行数/相关 postmeta 行数进行估算，仅用于判断规模。

清理历史 revision 时，插件按每批 5000 条进行处理，避免一次性删除几十万条记录产生过大的数据库压力。

插件长期启用即可。若关闭“禁止文章生成新的修订版本”，将恢复 WordPress 默认修订行为。
