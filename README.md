# office-word-excel-skill

一个 [Claude Code](https://claude.ai/code) skill,把办公室里重复的 Word/Excel 劳动交给 AI:名单整理、成绩统计、证书批量生成、申请表信息汇总、模板套打、文件批量重命名……教师/行政场景优先,**macOS / Windows 通用**。

## 能干什么

- **名单/表格整理**:去重、合并、抽子集、按双主键(姓名+电话/学号)对齐回填,只填空缺不覆盖已有数据
- **文档信息汇总**:从几百份 doc/docx/pdf 申请表里提取字段,自动填进 Excel 汇总表
- **模板套打**:按名单批量生成证书、通知、合同、座位表,中文字体、排版细节都处理
- **成绩单统计**:求和、平均、排名(会先和你确认并列规则)
- **文件批量归档**:按名单挑文件、按序号重命名

更重要的是它带一套**办公交付纪律**:先看样本再动手、规则一次问清、试跑几条确认口径后才全量、失败清单落盘、交付时附校验报告——按"老师丢来一堆文件"的方式干活,而不是按程序员的方式。

## 安装

前提:已安装 [Claude Code](https://claude.ai/code)。

把 `office-word-excel` 文件夹整个复制到你的 skills 目录:

**macOS / Linux**

```bash
mkdir -p ~/.claude/skills
cp -r office-word-excel ~/.claude/skills/
```

**Windows (PowerShell)**

```powershell
mkdir -force "$env:USERPROFILE\.claude\skills"
copy -r office-word-excel "$env:USERPROFILE\.claude\skills\"
```

重启 Claude Code(或新开会话)即生效。

## 使用

不需要任何特殊命令,直接用自然语言描述任务即可,Claude 会自动触发这个 skill。例如:

> 这份 Excel 是班级名单,这 40 份是学生的申请表,帮我把每个人的申请表信息提取出来填到 Excel 对应行里

> 按名单里的 120 个名字,从这份 Word 模板生成奖状,文件名叫「1_张三」

第一次用建议先给 1~2 个样例文件,AI 会先确认结构和规则再动手。

## 文件说明

```
office-word-excel/
└── SKILL.md    # skill 本体,纯 Markdown 指令,无代码依赖
```

skill 是给 AI 读的指令文档,不是可执行程序;其中用到的工具(openpyxl、python-docx 等)会在干活时按需安装。

## License

MIT
