# 每日英语阅读 Daily English Reading

一个简洁优雅的英语阅读静态网站，文章独立存储，方便每日更新。

## 项目结构

```
daily-english/
├── index.html              # 主页面（不需要修改）
├── articles/               # 文章文件夹
│   ├── index.json          # 文章索引（添加新文章时更新）
│   ├── 2025-01-01.json     # 文章文件（按日期命名）
│   └── ...
└── README.md
```

## 部署到 GitHub Pages

### 1. 创建 GitHub 仓库

1. 登录 GitHub，点击 "New repository"
2. 仓库名：`daily-english`
3. 选择 Public
4. 点击 Create

### 2. 上传文件

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/你的用户名/daily-english.git
git push -u origin main
```

### 3. 启用 GitHub Pages

1. 进入仓库 → Settings → Pages
2. Source 选择 "Deploy from a branch"
3. Branch 选择 "main"，目录选 "/ (root)"
4. 保存后等待几分钟

访问地址：`https://你的用户名.github.io/daily-english/`

---

## 添加新文章（每日操作）

### 步骤 1：创建文章文件

在 `articles/` 文件夹下创建新文件，命名格式：`YYYY-MM-DD.json`

例如：`2025-01-01.json`

```json
{
    "date": "2025-01-01",
    "title": "The Benefits of Reading",
    "english": [
        "First paragraph in English.",
        "Second paragraph in English.",
        "Third paragraph in English."
    ],
    "chinese": [
        "第一段中文翻译。",
        "第二段中文翻译。",
        "第三段中文翻译。"
    ],
    "vocabulary": [
        { "word": "benefit", "phonetic": "/ˈbenɪfɪt/", "meaning": "n. 好处，益处" },
        { "word": "reading", "phonetic": "/ˈriːdɪŋ/", "meaning": "n. 阅读" }
    ]
}
```

### 步骤 2：更新索引文件

编辑 `articles/index.json`，在数组**开头**添加新日期：

```json
[
    "2025-01-02",
    "2025-01-01"
]
```

### 步骤 3：提交到 GitHub

```bash
git add articles/
git commit -m "Add article: 2025-01-01"
git push
```

网站会自动更新，显示最新文章！

---

## 文章模板

复制以下模板使用：

```json
{
    "date": "YYYY-MM-DD",
    "title": "Article Title",
    "english": [
        "Paragraph 1",
        "Paragraph 2",
        "Paragraph 3"
    ],
    "chinese": [
        "段落 1 翻译",
        "段落 2 翻译",
        "段落 3 翻译"
    ],
    "vocabulary": [
        { "word": "word1", "phonetic": "/xxx/", "meaning": "词性。释义" },
        { "word": "word2", "phonetic": "/xxx/", "meaning": "词性。释义" },
        { "word": "word3", "phonetic": "/xxx/", "meaning": "词性。释义" }
    ]
}
```

## 注意事项

1. **文件名必须是日期格式**：`YYYY-MM-DD.json`
2. **index.json 中新日期放最前面**：这样首页会显示最新文章
3. **JSON 格式要正确**：可以用 [JSONLint](https://jsonlint.com/) 检查
4. **段落用数组存储**：每个段落是数组的一个元素

Happy Reading! 📚