# 动画创作工作区

本仓库是 `fy-code-animation` 技能（fork 自 Akillll-DuoHe/fy-code-animation），已软链为 `~/.claude/skills/fy-code-animation`，在 Claude Code 里直接调用。入口是 [SKILL.md](SKILL.md)，按其中的创作顺序与能力路由加载文件，不要一次全读。

## 三个仓库的分工

| 本地目录 | GitHub | 职责 |
|---|---|---|
| `~/MyProjects/animation` | marvinhny/fy-code-animation（upstream: Akillll-DuoHe） | 需求澄清、语义分镜、导演流程、任务卡、Remotion 落地与返修 |
| `~/MyProjects/code-animation-prompts` | marvinhny/code-animation-prompts（origin: XiaoyeCodes） | 341 风格模板库；本技能的风格库根是其 `skills/code-animation-prompts/assets/library` |
| `~/MyProjects/voice` | marvinhny/breeze-tts（upstream: breezeblue-ai） | 文本转语音（Breeze TTS 2）：口播、配音 |

## 约定

- 风格库路径已写在 `adapters/style-library.config.json`（相对路径）。库更新后跑 `python3.13 scripts/style_library.py build` 再跑 `python3.13 scripts/doctor.py`。
- 本机 pyenv 默认 Python 3.9，本仓库脚本与测试需要 3.10+，用 `/opt/homebrew/bin/python3.13`。
- 口播需要实际音轨时，用 `~/MyProjects/voice` 生成 WAV，再按实际成音卡点（SKILL.md 第 9 步）；没有音轨时只能写计划时间。Breeze TTS 官方只支持 Linux + NVIDIA CUDA，本机是 Apple M4，运行方式见 voice 仓库说明。
- 同步上游：`git fetch upstream && git merge upstream/main`；个人改动推到 `origin`。
