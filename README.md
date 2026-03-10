# Mewgenics《ty中文翻译》数据回填包

这是一份 **ty中文翻译** 数据包，用来区分未来可能出现的官方汉化版本。

对外发布时建议统一称呼为：

- `Mewgenics《ty中文翻译》`
- `Mewgenics《ty中文翻译》`

这个包只包含 3 类东西：

- 你的 DeepSeek 翻译结果 CSV
- 你的 DeepSeek 翻译结果 JSON
- 一个把翻译结果回填到游戏文本资源里的脚本

## 包内文件

- `mewgenics_ty_zh_translation_v17.csv`
  - 主要翻译结果
  - 推荐优先使用这个文件回填

- `mewgenics_ty_zh_translation_v17.json`
  - `key -> zh` 形式的补丁映射
  - 适合做人工查阅或二次处理

- `mewgenics_import_ty_translation_csv.py`
  - 回填脚本
  - 会把 CSV 中的 `zh` 回填到：
    - `data/text/combined.csv`
    - `data/catnames_female_en.txt`
    - `data/catnames_male_en.txt`
    - `data/catnames_neutral_en.txt`

## 前提目录

这个脚本不会自动解包 GPAK。

你需要先有一份已经解包好的资源目录，例如：

```text
extracted/
  data/
    text/
      combined.csv
    catnames_female_en.txt
    catnames_male_en.txt
    catnames_neutral_en.txt
```

如果你已经有当前项目里的解包目录，那就是：

```text
/Users/ty/Documents/New project/work/mewgenics/extracted
```

## 基本用法

```bash
python3 mewgenics_import_ty_translation_csv.py \
  mewgenics_ty_zh_translation_v17.csv \
  /path/to/extracted \
  /path/to/output_patch
```

执行后，会在 `/path/to/output_patch` 生成：

- `data/text/combined.csv`
- `data/catnames_female_en.txt`
- `data/catnames_male_en.txt`
- `data/catnames_neutral_en.txt`

这些文件就是可直接用于回包的补丁目录。

## 推荐用法

如果你已经有一份人工校过、已有部分中文的 `combined.csv`，推荐把它作为基底，这样新翻译只会补空白，不会覆盖你现有的术语和已校对文本。

```bash
python3 mewgenics_import_ty_translation_csv.py \
  mewgenics_ty_zh_translation_v17.csv \
  /path/to/extracted \
  /path/to/output_patch \
  --combined-src /path/to/curated_combined.csv
```

例如当前项目里推荐的基底是：

```text
/Users/ty/Documents/New project/work/mewgenics/patches/data/text/combined.csv
```

## 当前脚本行为

- 对 `combined.csv`
  - 如果基底里某行已经有 `zh`，默认保留
  - 如果基底里该行 `zh` 为空，则用 CSV 里的翻译补上

- 对 3 个名字库
  - 会按行号对应回填中文名称

## 不包含的内容

这个包不包含：

- GPAK 解包脚本
- GPAK 回包脚本
- 发布到 `XDISK` 的脚本
- 发布到 GitHub 的脚本

如果你只是想把自己的翻译数据单独放到 GitHub，这个包已经够用了。
