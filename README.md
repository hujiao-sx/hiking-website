# hiking-website<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hiking Adventures</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="#home">首页</a></li>
                <li><a href="#about">关于</a></li>
                <li><a href="#routes">路线</a></li>
                <li><a href="#tips">技巧</a></li>
                <li><a href="#contact">社区</a></li>
            </ul>
        </nav>
        <div class="hero">
            <h1>开启你的第一次徒步</h1>
            <p>徒步不仅仅是前行 更是发现生活之美</p>
        </div>
    </header>
    <section id="about">
        <h2>关于</h2>
        <div class="founder">
            <img src="images/tom.png" alt="Founder">
            <p>柯雷 - 徒步爱好者和探险家</p>
        </div>
        <p>柯雷是一位徒步爱好者和探险家，他不仅分享了大量的徒步经验和故事，还致力于帮助初学者踏上徒步之旅。</p>
    </section>
    <section id="routes">
        <h2>路线</h2>
        <div class="route-slider">
            <!-- Add image slider here -->
        </div>
        <div class="routes">
            <div class="route">
                <h3>路线1</h3>
                <p>描述</p>
            </div>
            <div class="route">
                <h3>路线2</h3>
                <p>描述</p>
            </div>
            <div class="route">
                <h3>路线3</h3>
                <p>描述</p>
            </div>
        </div>
    </section>
    <section id="tips">
        <h2>徒步技巧与装备</h2>
        <div class="tips">
            <div class="tip">
                <h3>徒步技巧</h3>
                <p>内容</p>
            </div>
            <div class="tip">
                <h3>装备推荐</h3>
                <p>内容</p>
            </div>
            <div class="tip">
                <h3>安全指南</h3>
                <p>内容</p>
            </div>
        </div>
    </section>
    <footer>
        <p>联系信息</p>
        <p>电话: 123-456-7890</p>
        <p>邮箱: info@hikingadventures.com</p>
    </footer>
    <script src="scripts.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

header {
    background: url('images/header-bg.jpg') no-repeat center center/cover;
    color: white;
    text-align: center;
    padding: 100px 0;
}

nav ul {
    list-style: none;
    padding: 0;
    display: flex;
    justify-content: center;
    background-color: rgba(0, 0, 0, 0.5);
}

nav ul li {
    margin: 0 20px;
}

nav ul li a {
    color: white;
    text-decoration: none;
    font-size: 18px;
}

.hero h1 {
    font-size: 50px;
    margin: 0;
}

.hero p {
    font-size: 20px;
}

section {
    padding: 50px 20px;
}

#about {
    background-color: #f9f9f9;
    text-align: center;
}

#about .founder {
    display: flex;
    flex-direction: column;
    align-items: center;
}

#routes {
    background-color: #eef;
}

#routes h2, #tips h2 {
    text-align: center;
}

.routes, .tips {
    display: flex;
    justify-content: space-around;
}

.route, .tip {
    background-color: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 20px 0;
}

footer p {
    margin: 5px 0;
}
document.addEventListener('DOMContentLoaded', () => {
    const slides = document.querySelectorAll('.route-slider img');
    let currentSlide = 0;

    function showSlide(index) {
        slides.forEach((slide, i) => {
            slide.style.display = i === index ? 'block' : 'none';
        });
    }

    function nextSlide() {
        currentSlide = (currentSlide + 1) % slides.length;
        showSlide(currentSlide);
    }

    function prevSlide() {
        currentSlide = (currentSlide - 1 + slides.length) % slides.length;
        showSlide(currentSlide);
    }

    document.querySelector('.next').addEventListener('click', nextSlide);
    document.querySelector('.prev').addEventListener('click', prevSlide);

    showSlide(currentSlide);
});
