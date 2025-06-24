<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ديوان الشعراء</title>
    <style>
        /* CSS ستايلات الموقع */
        :root {
            --primary-color: #FFF2E0;
            --secondary-color: #F8E5C0;
            --accent-color: #D4B483;
            --text-color: #3A2D1F;
            --transition: all 0.4s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--primary-color);
            color: var(--text-color);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        header {
            background-color: var(--secondary-color);
            padding: 1rem;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .search-container {
            max-width: 600px;
            margin: 0 auto;
        }

        #searchInput {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid var(--accent-color);
            border-radius: 4px;
            font-size: 1rem;
            background-color: white;
        }

        main {
            flex: 1;
            padding: 2rem;
            max-width: 1200px;
            margin: 0 auto;
            width: 100%;
        }

        .layer {
            display: grid;
            gap: 1.5rem;
            animation: fadeIn 0.5s ease;
        }

        .section-title {
            text-align: center;
            margin-bottom: 1.5rem;
            color: var(--text-color);
            font-size: 1.8rem;
            position: relative;
            padding-bottom: 0.5rem;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 40%;
            right: 40%;
            height: 3px;
            background-color: var(--accent-color);
        }

        .categories, .poets {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 1rem;
        }

        .category-btn, .poet-btn {
            background-color: var(--secondary-color);
            border: none;
            padding: 1rem;
            border-radius: 8px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .category-btn:hover, .poet-btn:hover {
            background-color: var(--accent-color);
            transform: translateY(-3px);
        }

        .poems-container {
            display: grid;
            gap: 1.5rem;
        }

        .poem-card {
            background-color: white;
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 3px 6px rgba(0,0,0,0.1);
            transition: var(--transition);
        }

        .poem-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .poem-title {
            font-size: 1.4rem;
            margin-bottom: 0.5rem;
            color: var(--text-color);
        }

        .poem-author {
            font-style: italic;
            color: #6D5D45;
            margin-bottom: 1rem;
        }

        .poem-text {
            line-height: 1.8;
            white-space: pre-line;
        }

        .back-btn {
            background-color: var(--accent-color);
            border: none;
            padding: 0.6rem 1.2rem;
            border-radius: 4px;
            cursor: pointer;
            margin-bottom: 1.5rem;
            font-size: 1rem;
            transition: var(--transition);
        }

        .back-btn:hover {
            background-color: #C19A5B;
        }

        footer {
            background-color: var(--secondary-color);
            padding: 1.5rem;
            text-align: center;
            margin-top: 2rem;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 1rem;
        }

        .footer-links a {
            color: var(--text-color);
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--accent-color);
            text-decoration: underline;
        }

        .copyright {
            color: #5C4E3A;
        }

        /* للطبقات */
        #second-layer {
            display: none;
        }

        /* للرسوم المتحركة */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* تصميم متجاوب */
        @media (max-width: 768px) {
            .categories, .poets {
                grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            }
            
            .section-title {
                font-size: 1.5rem;
            }
        }

        @media (max-width: 480px) {
            main {
                padding: 1rem;
            }
            
            .categories, .poets {
                grid-template-columns: repeat(2, 1fr);
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="search-container">
            <input type="text" id="searchInput" placeholder="ابحث عن شاعر أو قصيدة...">
        </div>
    </header>

    <main>
        <!-- الطبقة الأولى -->
        <section id="first-layer" class="layer">
            <h1 class="section-title">فهرس الشعر</h1>
            
            <div class="categories-section">
                <h2>التصنيفات</h2>
                <div class="categories">
                    <!-- سيتم ملؤها بالجافاسكريبت -->
                </div>
            </div>
            
            <div class="poets-section">
                <h2>الشعراء</h2>
                <div class="poets">
                    <!-- سيتم ملؤها بالجافاسكريبت -->
                </div>
            </div>
        </section>

        <!-- الطبقة الثانية -->
        <section id="second-layer" class="layer">
            <button class="back-btn">← العودة</button>
            <h2 class="section-title" id="layer-title">قصائد</h2>
            <div class="poems-container" id="poems-container">
                <!-- سيتم ملؤها بالجافاسكريبت -->
            </div>
        </section>
    </main>

    <footer>
        <div class="footer-links">
            <a href="#">تواصل معنا</a>
            <a href="#">فيسبوك</a>
            <a href="#">تويتر</a>
            <a href="#">انستغرام</a>
        </div>
        <div class="copyright">
            © 2025 ديوان الشعراء. جميع الحقوق محفوظة.
        </div>
    </footer>

    <!-- ملف البيانات -->
    <script>
        // بيانات الشعراء والقصائد
        const poets = [
            { id: 1, name: "نزار قباني" },
            { id: 2, name: "بدر شاكر السياب" },
            { id: 3, name: "مظفر النواب" },
            { id: 4, name: "أحمد مطر" },
            { id: 5, name: "الجواهري" }
        ];

        const categories = [
            { id: 1, name: "حب" },
            { id: 2, name: "غزل" },
            { id: 3, name: "حكمة" },
            { id: 4, name: "فخر" },
            { id: 5, name: "دين" },
            { id: 6, name: "حنين" }
        ];

        const poems = [
            {
                id: 1,
                title: "قصيدة الحب",
                poetId: 1,
                categoryId: 1,
                text: "أحبكِ حتى الثمالة\nأحبكِ مثل الأطفال\nأحبكِ مثل الفراشات\nأحبكِ دون حدود"
            },
            {
                id: 2,
                title: "الغربة",
                poetId: 2,
                categoryId: 6,
                text: "يا دجلة الخير يا أم البساتين\nيا حاضنة المجد من عهد العصور\nكم بت أشكو إليك الهم والكمد\nوأبثك آلام قلبي والضمير"
            },
            {
                id: 3,
                title: "يا ظلام",
                poetId: 3,
                categoryId: 4,
                text: "يا ظلام السجن خيّم\nإننا نهوى الظلاما\nليس بعد الليل إلا\nفجر مجد يتسامى"
            },
            {
                id: 4,
                title: "الحكمة",
                poetId: 5,
                categoryId: 3,
                text: "وما نيل المطالب بالتمني\nولكن تؤخذ الدنيا غلابا\nوما استعصى على قوم منال\nإذا الإقدام كان لهم ركابا"
            }
        ];
    </script>

    <!-- ملف الجافاسكريبت -->
    <script>
        // عناصر DOM
        const firstLayer = document.getElementById('first-layer');
        const secondLayer = document.getElementById('second-layer');
        const backBtn = document.querySelector('.back-btn');
        const layerTitle = document.getElementById('layer-title');
        const poemsContainer = document.getElementById('poems-container');
        const searchInput = document.getElementById('searchInput');
        const categoriesContainer = document.querySelector('.categories');
        const poetsContainer = document.querySelector('.poets');

        // تهيئة التصنيفات
        categories.forEach(category => {
            const btn = document.createElement('button');
            btn.className = 'category-btn';
            btn.textContent = category.name;
            btn.dataset.id = category.id;
            btn.addEventListener('click', () => showPoems('category', category.id, category.name));
            categoriesContainer.appendChild(btn);
        });

        // تهيئة الشعراء
        poets.forEach(poet => {
            const btn = document.createElement('button');
            btn.className = 'poet-btn';
            btn.textContent = poet.name;
            btn.dataset.id = poet.id;
            btn.addEventListener('click', () => showPoems('poet', poet.id, poet.name));
            poetsContainer.appendChild(btn);
        });

        // عرض القصائد
        function showPoems(type, id, title) {
            let filteredPoems = [];
            
            if (type === 'poet') {
                filteredPoems = poems.filter(poem => poem.poetId == id);
                layerTitle.textContent = `قصائد ${title}`;
            } else {
                filteredPoems = poems.filter(poem => poem.categoryId == id);
                layerTitle.textContent = `قصائد ${title}`;
            }
            
            poemsContainer.innerHTML = '';
            
            if (filteredPoems.length === 0) {
                poemsContainer.innerHTML = '<p>لا توجد قصائد متاحة</p>';
            } else {
                filteredPoems.forEach(poem => {
                    const poet = poets.find(p => p.id === poem.poetId);
                    const category = categories.find(c => c.id === poem.categoryId);
                    
                    const poemCard = document.createElement('div');
                    poemCard.className = 'poem-card';
                    poemCard.innerHTML = `
                        <h3 class="poem-title">${poem.title}</h3>
                        <p class="poem-author">${poet.name} - ${category.name}</p>
                        <div class="poem-text">${poem.text}</div>
                    `;
                    poemsContainer.appendChild(poemCard);
                });
            }
            
            firstLayer.style.display = 'none';
            secondLayer.style.display = 'block';
        }

        // زر العودة
        backBtn.addEventListener('click', () => {
            secondLayer.style.display = 'none';
            firstLayer.style.display = 'grid';
        });

        // وظيفة البحث
        searchInput.addEventListener('input', (e) => {
            const term = e.target.value.toLowerCase().trim();
            
            if (term === '') return;
            
            const filteredPoems = poems.filter(poem => 
                poem.title.toLowerCase().includes(term) || 
                poets.find(p => p.id === poem.poetId).name.toLowerCase().includes(term)
            );
            
            poemsContainer.innerHTML = '';
            layerTitle.textContent = `نتائج البحث عن: "${term}"`;
            
            if (filteredPoems.length === 0) {
                poemsContainer.innerHTML = '<p>لا توجد نتائج</p>';
            } else {
                filteredPoems.forEach(poem => {
                    const poet = poets.find(p => p.id === poem.poetId);
                    const category = categories.find(c => c.id === poem.categoryId);
                    
                    const poemCard = document.createElement('div');
                    poemCard.className = 'poem-card';
                    poemCard.innerHTML = `
                        <h3 class="poem-title">${poem.title}</h3>
                        <p class="poem-author">${poet.name} - ${category.name}</p>
                        <div class="poem-text">${poem.text}</div>
                    `;
                    poemsContainer.appendChild(poemCard);
                });
            }
            
            firstLayer.style.display = 'none';
            secondLayer.style.display = 'block';
        });
    </script>
</body>
</html>
