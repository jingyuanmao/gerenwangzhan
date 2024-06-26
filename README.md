# 猫猫龙的空间
个人网站大作业
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
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #333;
    color: white;
    padding: 1em 0;
    text-align: center;
}

nav ul {
    list-style-type: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin: 0 1em;
}

nav ul li a {
    color: white;
    text-decoration: none;
}

main {
    padding: 1em;
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 1em 0;
    position: fixed;
    bottom: 0;
    width: 100%;
}

h1, h2, h3 {
    color: #333;
}

form textarea, form input[type="text"], form input[type="file"] {
    width: 100%;
    margin-bottom: 1em;
}

form button {
    display: block;
    margin-top: 1em;
}
document.addEventListener("DOMContentLoaded", function() {
    if (document.getElementById('article-form')) {
        document.getElementById('article-form').addEventListener('submit', function(event) {
            event.preventDefault();
            submitArticle();
        });
    }

    if (document.getElementById('media-form')) {
        document.getElementById('media-form').addEventListener('submit', function(event) {
            event.preventDefault();
            submitMedia();
        });
    }

    if (document.getElementById('comment-form')) {
        document.getElementById('comment-form').addEventListener('submit', function(event) {
            event.preventDefault();
            submitComment();
        });
    }

    if (document.getElementById('search-form')) {
        document.getElementById('search-form').addEventListener('submit', function(event) {
            event.preventDefault();
            searchContent();
        });
    }

    loadContent();
});

function loadContent() {
    fetchLatestContent();
    fetchArticlesList();
    fetchMediaList();
    fetchCommentsList();
    fetchLinksList();
}

function fetchLatestContent() {
    // 模拟从服务器获取最新内容
    document.getElementById('latest-article').innerHTML = `
        <h3>示例文章标题</h3>
        <p>这是示例文章的内容。</p>
        <p>发布日期: 2024-05-30</p>
    `;

    document.getElementById('latest-media').innerHTML = `
        <h3>图片标题</h3>
        <img src="images/example.jpg" alt="示例图片">
        <h3>视频标题</h3>
        <video controls>
            <source src="videos/example.mp4" type="video/mp4">
            您的浏览器不支持视频标签。
        </video>
    `;
}

function submitArticle() {
    const title = document.getElementById('article-title').value;
    const content = document.getElementById('article-content').value;
    const latestArticle = document.getElementById('latest-article');

    latestArticle.innerHTML = `
        <h3>${title}</h3>
        <p>${content}</p>
        <p>发布日期: ${new Date().toISOString().split('T')[0]}</p>
    `;
}

function submitMedia() {
    const title = document.getElementById('media-title').value;
    const fileInput = document.getElementById('media-file');
    const file = fileInput.files[0];
    const latestMedia = document.getElementById('latest-media');
    const reader = new FileReader();

    reader.onload = function(e) {
        if (file.type.startsWith('image/')) {
            latestMedia.innerHTML = `
                <h3>${title}</h3>
                <img src="${e.target.result}" alt="${title}">
            `;
        } else if (file.type.startsWith('video/')) {
            latestMedia.innerHTML = `
                <h3>${title}</h3>
                <video controls>
                    <source src="${e.target.result}" type="${file.type}">
                    您的浏览器不支持视频标签。
                </video>
            `;
        }
    };
    reader.readAsDataURL(file);
}

function fetchArticlesList() {
    // 模拟从服务器获取文章列表
    if (document.getElementById('articles-list')) {
        document.getElementById('articles-list').innerHTML = `
            <h3>文章标题1</h3>
            <p>文章内容1</p>
            <p>发布日期: 2024-05-30</p>
            <h3>文章标题2</h3>
            <p>文章内容2</p>
            <p>发布日期: 2024-05-29</p>
        `;
    }
}

function fetchMediaList() {
    // 模拟从服务器获取图片和视频列表
    if (document.getElementById('media-list')) {
        document.getElementById('media-list').innerHTML = `
            <h3>图片标题</h3>
            <img src="images/example.jpg" alt="示例图片">
            <p>发布日期: 2024-05-30</p>
            <h3>视频标题</h3>
            <video controls>
                <source src="videos/example.mp4" type="video/mp4">
                您的浏览器不支持视频标签。
            </video>
            <p>发布日期: 2024-05-30</p>
        `;
    }
}

function fetchCommentsList() {
    // 模拟从服务器获取留言列表
    if (document.getElementById('comments-list')) {
        document.getElementById('comments-list').innerHTML = `
            <p>留言内容1</p>
            <p>日期: 2024-
