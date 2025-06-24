<!DOCTYPE html>

<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موقع الشعر العربي</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

```
    body {
        font-family: 'Amiri', 'Georgia', serif;
        direction: rtl;
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        color: #333;
        min-height: 100vh;
        line-height: 1.8;
    }

    .container {
        max-width: 1200px;
        margin: 0 auto;
        padding: 0 20px;
    }

    header {
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(10px);
        border-bottom: 1px solid rgba(255, 255, 255, 0.2);
        padding: 30px 0;
        text-align: center;
        position: relative;
        overflow: hidden;
    }

    header::before {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="stars" x="0" y="0" width="20" height="20" patternUnits="userSpaceOnUse"><circle cx="10" cy="10" r="1" fill="rgba(255,255,255,0.1)"/></pattern></defs><rect width="100" height="100" fill="url(%23stars)"/></svg>');
        animation: twinkle 4s infinite;
    }

    @keyframes twinkle {
        0%, 100% { opacity: 0.3; }
        50% { opacity: 1; }
    }

    h1 {
        font-size: 3rem;
        color: white;
        text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        margin-bottom: 10px;
        position: relative;
        z-index: 1;
    }

    .subtitle {
        color: rgba(255, 255, 255, 0.9);
        font-size: 1.2rem;
        position: relative;
        z-index: 1;
    }

    main {
        padding: 40px 0;
    }

    .poems-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
        gap: 30px;
        margin-top: 30px;
    }

    .poem-card {
        background: rgba(255, 255, 255, 0.95);
        backdrop-filter: blur(10px);
        border-radius: 20px;
        padding: 30px;
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        border: 1px solid rgba(255, 255, 255, 0.3);
        transition: all 0.3s ease;
        position: relative;
        overflow: hidden;
    }

    .poem-card::before {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        height: 4px;
        background: linear-gradient(90deg, #ff6b6b, #4ecdc4, #45b7d1);
        transform: translateX(-100%);
        transition: transform 0.3s ease;
    }

    .poem-card:hover::before {
        transform: translateX(0);
    }

    .poem-card:hover {
        transform: translateY(-5px);
        box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
    }

    .poem-title {
        font-size: 1.8rem;
        color: #6a1b9a;
        margin-bottom: 20px;
        text-align: center;
        position: relative;
    }

    .poem-title::after {
        content: '❋';
        display: block;
        margin: 10px auto;
        color: #ff6b6b;
        font-size: 1.2rem;
    }

    .poem-content {
        font-size: 1.3rem;
        line-height: 2;
        text-align: center;
        color: #2c3e50;
        margin-bottom: 20px;
    }

    .poem-content br {
        margin-bottom: 10px;
    }

    .poem-meta {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-top: 20px;
        padding-top: 20px;
        border-top: 1px solid rgba(0, 0, 0, 0.1);
        font-size: 0.9rem;
        color: #666;
    }

    .like-btn {
        background: linear-gradient(45deg, #ff6b6b, #ff8e8e);
        color: white;
        border: none;
        padding: 8px 16px;
        border-radius: 20px;
        cursor: pointer;
        transition: all 0.3s ease;
        font-size: 0.9rem;
    }

    .like-btn:hover {
        transform: scale(1.1);
    }

    .like-btn.liked {
        background: linear-gradient(45deg, #4ecdc4, #44a08d);
    }

    .stats {
        display: flex;
        gap: 15px;
    }

    .stat {
        display: flex;
        align-items: center;
        gap: 5px;
    }

    .floating-elements {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        pointer-events: none;
        z-index: -1;
    }

    .floating-element {
        position: absolute;
        opacity: 0.1;
        animation: float 6s ease-in-out infinite;
    }

    @keyframes float {
        0%, 100% { transform: translateY(0px) rotate(0deg); }
        50% { transform: translateY(-20px) rotate(180deg); }
    }

    .add-poem-btn {
        position: fixed;
        bottom: 30px;
        left: 30px;
        background: linear-gradient(45deg, #667eea, #764ba2);
        color: white;
        border: none;
        padding: 15px 20px;
        border-radius: 50px;
        cursor: pointer;
        font-size: 1rem;
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        transition: all 0.3s ease;
    }

    .add-poem-btn:hover {
        transform: scale(1.1);
    }

    @media (max-width: 768px) {
        .poems-grid {
            grid-template-columns: 1fr;
        }
        
        h1 {
            font-size: 2rem;
        }
        
        .poem-card {
            padding: 20px;
        }
    }
</style>
```

</head>
<body>
    <div class="floating-elements">
        <div class="floating-element" style="top: 10%; right: 10%; font-size: 2rem;">🌟</div>
        <div class="floating-element" style="top: 30%; right: 80%; font-size: 1.5rem; animation-delay: -2s;">✨</div>
        <div class="floating-element" style="top: 60%; right: 20%; font-size: 2.5rem; animation-delay: -4s;">🌙</div>
        <div class="floating-element" style="top: 80%; right: 70%; font-size: 1.8rem; animation-delay: -1s;">⭐</div>
    </div>

```
<header>
    <div class="container">
        <h1>موقع الشعر العربي</h1>
        <p class="subtitle">حيث تتراقص الكلمات وتنساب المشاعر</p>
    </div>
</header>

<main>
    <div class="container">
        <div class="poems-grid">
            <article class="poem-card">
                <h2 class="poem-title">قصيدة حب</h2>
                <div class="poem-content">
                    أحبك حبًا لو تحكيه الأشعار<br>
                    لأشعلت نارًا في كل الديار<br>
                    وأن تسألي عن مقدار هيامي<br>
                    فإن البحر يعجز عن أن يجاري
                </div>
                <div class="poem-meta">
                    <div class="stats">
                        <div class="stat">
                            <span>👁️</span>
                            <span id="views1">142</span>
                        </div>
                        <div class="stat">
                            <span>❤️</span>
                            <span id="likes1">28</span>
                        </div>
                    </div>
                    <button class="like-btn" onclick="toggleLike(1)">أعجبني</button>
                </div>
            </article>

            <article class="poem-card">
                <h2 class="poem-title">قصيدة حزن</h2>
                <div class="poem-content">
                    في القلب جرح لا يلتئم<br>
                    وفي العين دمعة لا تنتهي<br>
                    يا ليل طال بي السهر<br>
                    وأنا أناجي نجوم السماء
                </div>
                <div class="poem-meta">
                    <div class="stats">
                        <div class="stat">
                            <span>👁️</span>
                            <span id="views2">89</span>
                        </div>
                        <div class="stat">
                            <span>❤️</span>
                            <span id="likes2">15</span>
                        </div>
                    </div>
                    <button class="like-btn" onclick="toggleLike(2)">أعجبني</button>
                </div>
            </article>

            <article class="poem-card">
                <h2 class="poem-title">قصيدة أمل</h2>
                <div class="poem-content">
                    غدًا سيشرق فجر جديد<br>
                    وتزهر في القلب أحلام<br>
                    مهما طال الليل المظلم<br>
                    فإن الصبح قريب المرام
                </div>
                <div class="poem-meta">
                    <div class="stats">
                        <div class="stat">
                            <span>👁️</span>
                            <span id="views3">203</span>
                        </div>
                        <div class="stat">
                            <span>❤️</span>
                            <span id="likes3">45</span>
                        </div>
                    </div>
                    <button class="like-btn" onclick="toggleLike(3)">أعجبني</button>
                </div>
            </article>

            <article class="poem-card">
                <h2 class="poem-title">قصيدة الطبيعة</h2>
                <div class="poem-content">
                    في الروض أزهار تتراقص<br>
                    والطير يشدو بأعذب الألحان<br>
                    والنسيم يحمل عبق الياسمين<br>
                    في أجمل ما خلق الرحمن
                </div>
                <div class="poem-meta">
                    <div class="stats">
                        <div class="stat">
                            <span>👁️</span>
                            <span id="views4">167</span>
                        </div>
                        <div class="stat">
                            <span>❤️</span>
                            <span id="likes4">32</span>
                        </div>
                    </div>
                    <button class="like-btn" onclick="toggleLike(4)">أعجبني</button>
                </div>
            </article>
        </div>
    </div>
</main>

<button class="add-poem-btn" onclick="addNewPoem()">
    ➕ إضافة قصيدة جديدة
</button>

<script>
    let likedPoems = {};

    function toggleLike(poemId) {
        const btn = event.target;
        const likesElement = document.getElementById(`likes${poemId}`);
        let currentLikes = parseInt(likesElement.textContent);
        
        if (likedPoems[poemId]) {
            // Unlike
            likedPoems[poemId] = false;
            btn.classList.remove('liked');
            btn.textContent = 'أعجبني';
            likesElement.textContent = currentLikes - 1;
        } else {
            // Like
            likedPoems[poemId] = true;
            btn.classList.add('liked');
            btn.textContent = 'أعجبني ❤️';
            likesElement.textContent = currentLikes + 1;
        }
    }

    function addNewPoem() {
        const title = prompt('أدخل عنوان القصيدة:');
        if (!title) return;
        
        const content = prompt('أدخل محتوى القصيدة (استخدم \\n للفصل بين الأبيات):');
        if (!content) return;
        
        const poemsGrid = document.querySelector('.poems-grid');
        const poemId = Date.now();
        const formattedContent = content.replace(/\\n/g, '<br>');
        
        const newPoem = document.createElement('article');
        newPoem.className = 'poem-card';
        newPoem.innerHTML = `
            <h2 class="poem-title">${title}</h2>
            <div class="poem-content">${formattedContent}</div>
            <div class="poem-meta">
                <div class="stats">
                    <div class="stat">
                        <span>👁️</span>
                        <span id="views${poemId}">1</span>
                    </div>
                    <div class="stat">
                        <span>❤️</span>
                        <span id="likes${poemId}">0</span>
                    </div>
                </div>
                <button class="like-btn" onclick="toggleLike(${poemId})">أعجبني</button>
            </div>
        `;
        
        poemsGrid.appendChild(newPoem);
        
        // Add entrance animation
        newPoem.style.opacity = '0';
        newPoem.style.transform = 'translateY(20px)';
        setTimeout(() => {
            newPoem.style.transition = 'all 0.5s ease';
            newPoem.style.opacity = '1';
            newPoem.style.transform = 'translateY(0)';
        }, 100);
    }

    // Increment view count when page loads
    document.addEventListener('DOMContentLoaded', function() {
        const viewElements = document.querySelectorAll('[id^="views"]');
        viewElements.forEach(element => {
            let currentViews = parseInt(element.textContent);
            element.textContent = currentViews + 1;
        });
    });

    // Add parallax effect to floating elements
    document.addEventListener('mousemove', function(e) {
        const floatingElements = document.querySelectorAll('.floating-element');
        const mouseX = e.clientX / window.innerWidth;
        const mouseY = e.clientY / window.innerHeight;
        
        floatingElements.forEach((element, index) => {
            const speed = (index + 1) * 0.02;
            const x = (mouseX - 0.5) * speed * 100;
            const y = (mouseY - 0.5) * speed * 100;
            element.style.transform = `translate(${x}px, ${y}px)`;
        });
    });
</script>
```

</body>
</html>
