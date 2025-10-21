这需要通过相对路径实现，核心是使用表示 “上一级目录” 的符号 ..。
基础逻辑：路径中，. 表示 “当前目录”，.. 表示 “当前目录的上一级目录”。若要引用 “上一级目录中包含的文件夹”，只需用 ../目标文件夹名 即可。
示例：假设文件结构如下：
plaintext
父目录/          # 上一级目录
├─ 目标文件夹/    # 要引用的文件夹
└─ 当前目录/      # 当前文件所在的目录
   └─ 当前文件.html  # 当前操作的文件
若当前文件在 “当前目录” 中，要引用 “父目录” 下的 “目标文件夹”，路径为：../目标文件夹。
二、如何使用路径指定文件？
指定文件的路径分为相对路径和绝对路径两种，根据场景选择使用：
1. 相对路径（最常用）
相对于 “当前文件所在目录” 的路径，无需完整写出从根目录开始的全部层级。
同一目录下的文件：直接写文件名，如 test.txt；
子目录中的文件：子目录名/文件名，例如 data/report.csv；
上一级目录中的文件：../文件名，例如 ../config.ini；
上两级目录中的文件：../../文件名（以此类推，每多一级上溯就加一个 ../）。
2. 绝对路径
从 “根目录” 开始的完整路径，唯一且固定，不受当前文件位置影响。
本地文件系统中（如 Windows/Linux）：
Windows：以盘符开头，例如 C:\Users\user\docs\file.txt；
Linux：以 /（根目录）开头，例如 /home/user/docs/file.txt。
网络场景中（如 HTML 引用网络资源）：
以协议（http/https）开头的完整 URL，例如 https://example.com/static/image.png。
三、HTML、Linux、Windows 中路径的区别
核心差异体现在路径分隔符、绝对路径格式、大小写敏感性三个方面：
1. 路径分隔符
Windows：默认使用反斜杠 \（但多数程序也兼容正斜杠 /，例如浏览器打开本地 HTML 文件时）。示例：C:\Users\test\file.txt 或 C:/Users/test/file.txt（兼容写法）。
Linux：强制使用正斜杠 /（反斜杠在 Linux 中是转义符，不能用于路径）。示例：/home/test/file.txt。
HTML：无论部署在 Windows 还是 Linux 服务器，均使用正斜杠 /（因 HTML 基于 URL 规范，而 URL 统一用 / 分隔）。示例：<img src="images/pic.jpg"> 或 <link href="/css/style.css">。
2. 绝对路径的表示
Windows：以 “盘符 + 冒号” 开头，代表某个分区的根目录。示例：D:\project\data.csv（D 盘根目录下的路径）。
Linux：以 / 开头，代表系统唯一的根目录（所有文件都挂载在 / 下）。示例：/var/www/html/index.html（根目录下的路径）。
HTML：
本地 HTML 文件：绝对路径格式同操作系统（如 Windows 的 C:/page.html 或 Linux 的 /home/page.html）；
网络 HTML 文件：绝对路径是完整 URL（如 https://site.com/page.html），或基于网站根目录的 “伪绝对路径”（以 / 开头，代表网站部署的根目录，而非系统根目录）。
例如：<script src="/js/main.js"> 中的 / 指网站根目录（如 Linux 服务器的 /var/www/html/ 或 Windows 服务器的 C:\inetpub\wwwroot\），而非系统的 / 或 C:\。
3. 大小写敏感性
Windows：路径默认不区分大小写（File.txt 和 file.txt 视为同一文件）。
Linux：路径严格区分大小写（File.txt 和 file.txt 是两个不同文件）。
HTML：取决于部署的服务器系统：
若服务器是 Linux，路径区分大小写；
若服务器是 Windows，路径不区分大小写。
总结
引用上一级目录的文件夹：用相对路径 ../目标文件夹；
指定文件：根据场景选择相对路径（灵活）或绝对路径（固定）；
差异核心：分隔符（\ vs /）、绝对路径格式（盘符 vs 根目录 / vs URL）、大小写敏感性（Windows 不敏感，Linux 敏感，HTML 取决于服务器）。
