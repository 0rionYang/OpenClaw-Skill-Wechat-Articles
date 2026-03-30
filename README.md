# WeChat Article Search Skill for OpenClaw 微信公众号文章搜索
**一个用于 OpenClaw 的微信公众号文章搜索技能，支持搜索公众号、关键词和在特定公众号中搜索文章。**
## 功能特性
🔍 关键词搜索：搜索微信公众号文章

📰 公众号搜索：搜索特定公众号的所有文章

🎯 公众号内搜索：在指定公众号中搜索特定关键词

🛡️ 智能反爬：内置反爬机制，避免 IP 被封

🔄 自动重试：网络错误时自动重试

🍪 Cookie 管理：自动管理会话 Cookie

## 安装
### 1. 安装依赖
```
pip install beautifulsoup4 requests miku-ai
```
### 2. 安装 skill
将本技能文件夹放入 OpenClaw 的 skills 目录中：
```
openclaw/
├── skills/
│   └── wechat_search/
│       ├── __init__.py
│       ├── spider.py
│       ├── skill.py
│       └── requirements.txt
└── config/
```

## 主要方法
* get_wexin_article(query, top_num=5, page=1)
关键词搜索微信公众号文章
返回：文章列表，每篇文章包含 title, snippet, url, source, date
* search_by_account(account_name, top_num=5, page=1)
搜索特定公众号的所有文章
自动过滤非目标公众号的结果
* search_in_account(query, account_name, top_num=5, page=1)
在特定公众号中搜索文章
先搜索关键词，然后过滤结果
* search_articles_with_filter(query, account_filter=None, top_num=5, page=1)
搜索文章并可选择过滤公众号

提示：使用本技能时，请合理控制请求频率，避免对微信公众号和搜狗搜索造成过大压力。建议用于学习和研究目的
