# Document Design

认知友好的专业文档设计 Skill，适用于 DOCX、PDF、Markdown、HTML，以及飞书 / Notion 的导入友好内容。

## 安装

将本仓库放入你的 Agent 技能目录，目录名使用 `document-design`。技能入口是根目录的 `SKILL.md`。

```bash
npx skills add liuanye9-lab/document-design
```

也可以将仓库克隆到你的技能目录。

## 使用

在支持 Skill 的 Agent 中指定 `$document-design`，并说明文档读者、目标与输出格式。

## 渲染示例

```bash
python3 scripts/render_document.py assets/example-document.json --out ./output --formats md,html
python3 scripts/render_document.py assets/example-document.json --out ./output --formats docx,pdf
```

Markdown / HTML 只需要 Python 标准库；DOCX 需要 `python-docx`；PDF 另需 LibreOffice / soffice。

## 测试

```bash
python3 -m unittest discover -s scripts -p 'test_*.py' -v
```

首次安装验证：10 项测试，9 项通过，PDF 转换测试因 LibreOffice 不可用而跳过。静态测试不代表文档视觉验收。

## 内容

- `SKILL.md`：技能定义与工作流
- `scripts/`：渲染器与回归测试
- `references/`：视觉规范、格式映射和质量清单
- `assets/`：源数据与各格式示例
- `agents/`：Agent 界面配置

技能源文件来自 `document-design-v1.zip`，保留原始内容。可选默认规则不会自动写入用户的全局配置。
