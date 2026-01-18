**免责声明：本项目仅供技术学习与交流使用。使用者在使用本项目时应遵守洛谷用户协议。严禁使用本项目进行攻击、高频抓取或任何干扰洛谷正常运行的行为。作者不对使用本项目导致的账号封禁或 Cookie 泄露负责。**
# luogu-sidong-daka
洛谷自动打卡器

## 灵感

灵感来源于 vscode 的 vscode-luogu 插件，这个插件有一个手动打卡的功能，于是就想要一个自动打卡的机器。

首先，要先获取洛谷的打卡 url，在打卡之前，先按下 F12，打开控制台，按下打开按钮时，会增加一个打开成功的命令，找到洛谷新版的打卡 url 的地址是`https://www.luogu.com.cn/index/ajax_punch`;

于是就想到用 cookie 来登录洛谷，不过因为洛谷新版更新，有防 AI 机制，直接用 cookie 来打卡，会显示`418Hi agent, as you see, I am just a cute teapot. Wanna a cup of tea?`

翻看 vscode-luogu 的 extension.js 文件，发现需要模拟浏览器行为，可是不管怎么搞，都是显示`400`错误，于是翻看到了这个文章，把请求头复制过了，就神秘的显示打卡过了！

## 使用方法
首先，fork 我的项目。让后，在`Settings->Secrets and Variables->Actions->Repository secrets->New repository secret`里的标题填入`LUOGU_COOKIE`,下面的值，填入你洛谷的名为`__client_id`的cookie，然后点击 Add secret，增加环境变量。最后，在 Actions
 里点击`I understand my workflows, go ahead and enable them`，同意运行。
