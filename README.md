# openai-billing
This project provides a quick and easy way to check OpenAI API Key balances, supports multiple key checks, and includes a tutorial for setting up a Cloudflare reverse proxy.这个项目提供了一个快速简便的方式来查询 OpenAI API Key 的余额，支持多个 Key 的查询，并附带了 Cloudflare 反向代理的搭建教程。

## Feature：

1. 纯开源项目，使用 html 内的js 脚本请求内容，不会收集任何数据
2. 支持国内直连，输入 API Key 后自动识别查询
3. 支持自建反向代理查询，让你的查询更安心
4. 支持多个 KEY 查询，自动提取 KEY 并批量查询
5. 包含独立部署反代代码，使用更放心。
6. 单个 html 代码，体积 18KB 极速加载

查询结果样例如下：

| API KEY                                    | 总限额   | 已使用 | 剩余量  | 到期时间    | GPT-4 | 是否绑卡 |
| ----------------------------------------- | ------- | ------ | ------- | ----------- | ----- | -------- |
| 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 | 账户疑似被封禁，请登录 OpenAI 官网确认| | | | ❌    | 🔴      |
| sk-92I2***lVEv0i                          | 5.00    | 0.00   | 5.00    | 2023-09-01 | ❌    | 🟢      |
| sk-6f9R***iHouYS                          | 5000.00 | 144.10 | 4855.90 | 2023-07-01 | ❌    | 🟢      |
| sk-jA6g***3lDJem                          | 18.00   | 0.00   | 🔴过期 | 2023-06-01 | ❌    | 🔴      |

示例图片:
![示例图片](./sample.png)



## 独立部署：

1. 下载 checkbilling.html
2. 本地用浏览器打开，或者上传到服务器打开
3. 网页 footer 添加了指向该项目的超链接，不喜欢可以删掉
4. 网页 footer 添加了umami 访问量统计代码，不喜欢可以去掉

## 反向代理搭建：

1. 注册并登录 Cloudflare
2. 点击 Workers，Create a Service，选择HTTP Router
3. 创建后点击快速编辑按钮，将项目中 cloudflare.worker.js 中的代码复制下来，粘贴到编辑区域，保存并部署即可。
4. 获取反向代理的链接，或者使用自己的 domain 作为反向代理

##鸣谢

这是一个胶水项目，灵感和大部分源码来自于多个项目，在此一并鸣谢，感谢大佬们的付出：
1. 外观界面参考了 @x-dr 大佬的项目：https://github.com/x-dr/chatgptProxyAPI
2. JS代码参考了 @herobrine19 大佬的项目：https://github.com/herobrine19/openai-billing
3. 最后感谢 GPT-4 的辛勤劳动，期间多次用到 PLUS 的 3小时 25 次上限。
