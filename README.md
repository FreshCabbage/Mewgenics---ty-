# Mewgenics《ty中文翻译》汉化包



适合：

- 已经有原版游戏
- 不想下载完整替换包
- 愿意在自己电脑上本地生成汉化版 `resources.gpak`

## 这个包包含什么

- `mewgenics_gpak.py`
- `mewgenics_import_ty_translation_csv.py`
- `mewgenics_ty_zh_translation_v17.csv`
- `应用_ty中文翻译.bat`

## 你需要准备什么

1. 你自己的原版游戏目录
2. 游戏目录里有：
   - `Mewgenics.exe`
   - `resources.gpak`
3. 电脑安装了 Python 3

## 最简单用法

### 第 1 步

把这个轻量包里的所有文件，复制到你的游戏目录里。

也就是复制到和下面这些文件同一个目录：

- `Mewgenics.exe`
- `resources.gpak`

### 第 2 步

双击运行：

- `应用_ty中文翻译.bat`

### 第 3 步

脚本跑完后，游戏目录里会多出一个新文件：

- `resources_ty中文翻译.gpak`

### 第 4 步

把原来的：

- `resources.gpak`

先备份一份，比如改名成：

- `resources_backup.gpak`

然后把新生成的：

- `resources_ty中文翻译.gpak`

改名成：

- `resources.gpak`

最后启动游戏。

## 语言显示名

进入游戏设置后，语言里应该显示：

- `ty中文翻译`

这样可以和未来可能出现的官方中文区分开。

## 注意

- 这个包不会联网
- 它只会读取你本地的原版 `resources.gpak`
- 然后在本地生成一个新的汉化版资源包
- 默认不会直接覆盖原文件

## 如果运行失败

最常见原因是：

- 没装 Python 3
- 没把文件放进游戏目录
- 游戏目录里没有 `resources.gpak`

## 最后一条提醒

这是玩家汉化，不是官方汉化。
