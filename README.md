[README.md](https://github.com/user-attachments/files/32895092/README.md)
# 轻奢IP智能剪辑🧠

一个以句意和上下文为先的口播剪辑 Skill：从粗剪视频＋SRT，规划并执行基础字幕、重点词、标题、动态排版，以及按需的画面与声音包装。

**不是每句话都强调，也不是把克制做成寡淡。** 先决定信息层级，再设计对齐、留白、颜色和运动。

## 能做什么

- 确认居中基础字幕、安全区与字体；按语义断句，保留完整短句。
- 区分普通字幕、句内重点、独立四字短语、手写金句、标题和流程。
- 完整二段式开场、编号主副标题、并列关键词、逐节点流程路线。
- 上下式、前后式、左右式同步缓动，按口播节点进入，控制滚动密度。
- 按授权使用画面推拉、真实人物后方大字、蒙版；匹配语义音效和BGM。
- 按信息匹配浏览器式人物窗口、胶囊标签、案例卡和圆形讲解窗；区分圆形裁切与人物出圈。
- 在具备兼容运行时的环境导出独立可编辑剪映草稿，不覆盖旧工程。

## 安装

展示名：**轻奢IP智能剪辑🧠**；机器标识：`luxury-ip-smart-editing`。

将 `skills/luxury-ip-smart-editing` 整个目录放入你使用的 Agent 的技能目录，保留 `SKILL.md`、`agents`、`references`、`scripts`。例如 Codex 的 `$CODEX_HOME/skills/`，或支持通用技能发现的 `~/.agents/skills/`；以实际客户端配置为准。

上传到你自己的 GitHub 仓库后，可尝试：

```sh
npx -y skills add 你的账号/你的仓库 -g --all
```

上面是待替换模板，仓库尚未由此文件创建或发布，也未声称远程安装测试通过。

## 使用

> 使用 $luxury-ip-smart-editing。这里是已经剪好气口、未烧录字幕的视频和对应SRT。先确认基础字幕，随后完成标题、重点、动态排版、适合的画面和声音包装，生成新的独立剪映草稿，保留已有工程。

也可以只要求“分析哪些词值得强调”“更新规则”“测试一段字幕包装”。教程和成片参考不会自动变成待剪素材。

## 依赖与能力边界

规则层可由能读取本地文档/视频的Agent使用。实际制作需要文件访问、视频检查/语音定位、字体和素材，以及可用的剪映转换器。下载模型、外部服务和付费资源按实际权限处理；本包不含用户媒体、商业字体、模型、音效或歌曲。

提供两个Python脚本（Python 3.10+）：

```sh
python -X utf8 skills/luxury-ip-smart-editing/scripts/validate_plan.py plan.json --check-files
python -X utf8 skills/luxury-ip-smart-editing/scripts/export_jianying.py plan.json --output ./drafts --runtime-root /你的/JyWrapper技能目录
```

导出器依赖外部 `jianying-editor` / JyWrapper 的 `scripts/jy_wrapper.py` 及其兼容 `pyJianYingDraft`。本仓库不捆绑、不自动安装该第三方运行时。它能写入基础媒体/文字/关键帧/音频字段；不直接调用剪映智能抠像、不自动下载预设、不保证任意软件版本可播放。原生软件验收仍需完成。

## 文件导航

- [Skill入口](skills/luxury-ip-smart-editing/SKILL.md)
- [基础字幕与句意](skills/luxury-ip-smart-editing/references/base-and-semantics.md)
- [标题、分类、流程与金句](skills/luxury-ip-smart-editing/references/titles-and-information.md)
- [动态排版与节奏](skills/luxury-ip-smart-editing/references/layout-and-timing.md)
- [画面、抠像和蒙版](skills/luxury-ip-smart-editing/references/picture-and-matting.md)
- [多元包装与圆形讲解窗](skills/luxury-ip-smart-editing/references/diverse-packaging.md)
- [草稿与预览一致性](skills/luxury-ip-smart-editing/references/native-preview-parity.md)
- [音效与BGM](skills/luxury-ip-smart-editing/references/sound-and-music.md)
- [剪映交付](skills/luxury-ip-smart-editing/references/jianying-handoff.md)
- [可执行计划格式](skills/luxury-ip-smart-editing/references/plan-contract.md)
- [验收案例](skills/luxury-ip-smart-editing/references/acceptance-cases.md)

## 发布与许可

上传本仓库内容即可，不要上传个人工程、缓存、字体、下载模型、音视频或运行记录。源码中的实际文件路径由使用者输入，分享包不含作者私人路径。

本包未替作者选择开源许可证。上传GitHub不等同于授予任意再分发权限；正式分享时由仓库所有者选择并添加适合的 `LICENSE`。

验证范围见 [VALIDATION.md](VALIDATION.md)。未经过软件内验收的能力不会标为已验证。
