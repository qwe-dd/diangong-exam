# 高级电工模拟考试

一个纯前端单页模拟考试应用，无需服务器、无需联网，浏览器打开即可答题、判分、看解析、整理错题。

## 目录结构

```
diangong-exam/
├── index.html          # 考试应用（自包含，双击即可打开）
├── data/
│   └── questions.json  # 题库备份（可在应用内批量导入）
└── README.md
```

## 本地使用

1. 用浏览器直接打开 `index.html`；
2. 首页选择题量与时长，点「开始模拟考试」；
3. 交卷后自动判分，查看正确答案、解析和错题本。

## 题库格式

题目为 JSON 数组，字段如下：

| 字段 | 说明 |
| --- | --- |
| type | `single` 单选 / `multi` 多选 / `judge` 判断 |
| stem | 题干 |
| options | 选项对象 `{A:"",B:"",...}`，判断题可省略 |
| answer | 单选填字母，多选填字母组合，判断填「对 / 错」 |
| analysis | 解析，可留空 |

示例：

```json
[
  {
    "type": "single",
    "stem": "测量交流电流时，电流表应与被测电路（ ）。",
    "options": {"A": "并联", "B": "串联", "C": "混联", "D": "短路"},
    "answer": "B",
    "analysis": "电流表内阻很小，必须串联接入。"
  }
]
```

## 推送到代码平台

### GitHub
1. 登录 GitHub，点 New repository，填仓库名（如 `diangong-exam`），创建；
2. 在本目录执行：

```bash
git init
git add .
git commit -m "初始化高级电工模拟考试应用"
git branch -M main
git remote add origin <你的仓库地址>
git push -u origin main
```

### Gitee
流程相同：新建仓库后把 `remote` 换成 Gitee 仓库地址再 `push`。

> 说明：题目依据通用电工基础知识自编整理，仅供备考练习。
