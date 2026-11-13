# 电子书转抖音解说合集

douyin-book-series 把 PDF、EPUB 或 Word 电子书改编成可直接配音、剪辑的系列脚本。默认覆盖全书，先规划分集，再一次制作原书的一章。一章可以拆成多集。每章交付前核对旁白、分镜、出处和预计时长。

## 让 AI 安装

把下面这句话发给有权访问本仓库的 Codex：

> 请读取 https://github.com/ZhiBoLingXi/douyin-book-series 的 README，按其中的安装说明，为我安装 skills/douyin-book-series，并核对技能入口和引用文件。

### 使用 Codex 的技能安装器

向内置的 skill-installer 提供仓库 `ZhiBoLingXi/douyin-book-series` 和路径 `skills/douyin-book-series`。安装器默认把技能装到当前用户的 Codex 技能目录。访问受限仓库时，使用有读取权限的 GitHub 账号。

### 从本地副本安装

也可以用 Git 克隆仓库，在仓库根目录运行以下命令（macOS、Linux 或兼容 shell）。若目标目录已存在，命令会停止，以便先检查已安装的版本。

```sh
(
  set -eu
  skills_dir="${CODEX_HOME:-$HOME/.codex}/skills"
  mkdir -p "$skills_dir"
  target="$skills_dir/douyin-book-series"
  mkdir "$target"
  cp -R skills/douyin-book-series/. "$target/"
  test -s "$target/SKILL.md"
  test -s "$target/references/delivery-and-review.md"
  test -s "$target/references/interview-and-format.md"
  test -s "$target/agents/openai.yaml"
)
```

## 第一次使用

安装后在 Codex 新会话中附上电子书，输入：

> 使用 $douyin-book-series，先看全书结构，再只制作第一章的视频脚本。给出完整旁白、分镜、原书出处和预计时长。

成稿默认保存在当前工作区的 `视频策划/<作品名>/`。首集可作为全书入口；明确指定章节时，按指定范围交付。

## 项目结构

- [SKILL.md](skills/douyin-book-series/SKILL.md) 定义全书规划、逐章制作和编辑反馈处理流程。
- [分集交付与检查](skills/douyin-book-series/references/delivery-and-review.md) 说明每集如何交给配音和剪辑。
- [编导取舍](skills/douyin-book-series/references/interview-and-format.md) 说明如何按书型、收听场景和目标组织故事。
- [Codex 展示配置](skills/douyin-book-series/agents/openai.yaml) 提供技能名称和默认提示词。
