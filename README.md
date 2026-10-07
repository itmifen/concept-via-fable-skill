# concept-via-fable-skill

> 用现代都市 / 职场 / 科技寓言，把研究生水平的概念讲清楚。

一个 Claude / OpenClaw Skill。给它一个高阶概念，它会先讲一个 600–900 字的故事，**直到故事的揭晓段才说出概念名**；故事结束后再给「概念解释 + 隐喻对照表 + 边界说明」三件套。

设计目标：让一个读过研究生的知识工作者，对一个概念产生**先感受、后定义**的双重理解——先有物理直觉，再有学术定义。

---

## 特点

| 特点 | 说明 |
|---|---|
| **概念名延后揭晓** | 揭晓段之前禁止出现概念原名（含英文、缩写、变体、谐音） |
| **禁止元叙述** | 故事里不出现「这个故事在讲……」「读者会发现……」 |
| **原生隐喻** | 隐喻场景与概念必须共享同一物理结构，不是找形象套概念 |
| **一一对应** | 对照表每行都有具体对应物，不允许「对应整体」这种空话 |
| **强制边界说明** | 哪怕只写一句，也要诚实标出隐喻哪里不严密 |

## 安装

把整个目录放到任一 skill 目录下：

```bash
# Claude Code
git clone https://github.com/itmifen/concept-via-fable-skill.git ~/.claude/skills/concept-via-fable

# 或直接复制
cp -r .claude/skills/concept-via-fable ~/.claude/skills/
```

OpenClaw 用户放到 `~/.agents/skills/` 下同样可用。

## 用法

直接说触发词即可：

- 用故事讲讲 XX
- 来段寓言解释一下 XX
- 讲个故事让人理解 XX
- 隐喻一下 XX 概念
- fable 讲讲 XX

**输入槽位**

| 槽位 | 是否必填 | 默认 |
|---|---|---|
| concept | 必填 | — |
| domain | 可选 | 未指定领域 |
| reader_hint | 可选 | 知识工作者，读过研究生 |
| length_hint | 可选 | 700 字 |

## 示例

[`examples/01-antifragility.md`](.claude/skills/concept-via-fable/examples/01-antifragility.md) —「不受伤的人」

用健身房老板王宇的观察，讲清楚了**反脆弱**（Antifragility）：老客户每受一次小伤，恢复后训练重量都会涨 5%；而一疼就停的新手，受伤后力量平均下降 11%。故事的揭晓段才点出概念名。

## 目录结构

```
concept-via-fable-skill/
├── README.md
└── .claude/
    └── skills/
        └── concept-via-fable/
            ├── SKILL.md
            └── examples/
                └── 01-antifragility.md
```

## License

MIT，见 [LICENSE](LICENSE)。
