# 猫猫龙的空间
个人网站大作业
MyPersonalWebsite/
├── index.html
├── articles.html
├── media.html
├── comments.html
├── search.html
├── links.html
├── style.css
├── script.js
├── images/
│   ├── ad.jpg
│   ├── example.jpg
├── videos/
│   ├── example.mp4
└── README.md
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>个人网站</title>
    <link rel="stylesheet" href="style.css">
    <script src="script.js" defer></script>
</head>
<body>
    <header>
        <h1>个人网站</h1>
        <nav>
            <ul>
                <li><a href="index.html">首页</a></li>
                <li><a href="articles.html">文章</a></li>
                <li><a href="media.html">图片/视频</a></li>
                <li><a href="comments.html">留言</a></li>
                <li><a href="search.html">搜索</a></li>
                <li><a href="links.html">友情连接</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section id="personal-info">
            <h2>个人信息</h2>
            <p>姓名: 阮诗婷</p>
            <p>简介: 一位热爱小说和游戏的宅女。</p>
            <p>爱好: 看小说, 打游戏, 旅游</p>
        </section>
        <section id="daily-article">
            <h2>每日文章</h2>
            <form id="article-form">
                <input type="text" id="article-title" placeholder="文章标题" required>
                <textarea id="article-content" placeholder="文章内容" required></textarea>
                <button type="submit">提交文章</button>
            </form>
            <article id="latest-article">
                <h3>文章标题</h3>
                <p>这是文章内容的示例。</p>
                <p>发布日期: 2024-05-30</p>
            </article>
        </section>
        <section id="daily-media">
            <h2>每日图片/视频</h2>
            <form id="media-form">
                <input type="text" id="media-title" placeholder="媒体标题" required>
                <input type="file" id="media-file" required>
                <button type="submit">提交媒体</button>
            </form>
            <div id="latest-media">
                <h3>图片标题</h3>
                <img src="images/example.jpg" alt="示例图片">
                <h3>视频标题</h3>
                <video controls>
                    <source src="videos/example.mp4" type="video/mp4">
                    您的浏览器不支持视频标签。
                </video>
            </div>
        </section>
    </main>
    <footer>
        <p>© 2024 个人网站</p>
    </footer>
</body>
</html>
