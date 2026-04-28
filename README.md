<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>1 awi store links</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #f8f8f8, #ffe6ea);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        .container {
            background: white;
            padding: 30px;
            max-width: 500px;
            width: 90%;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
            text-align: center;
        }

        .logo {
            width: 140px;
            margin-bottom: 15px;
        }

        h1 { color: #ff2b45; margin-bottom: 10px; font-size: 2.5rem; }
        h2 { color: #444; margin-bottom: 25px; font-size: 1.2rem; }

        ul {
            text-align: left;
            padding-left: 25px;
            color: #333;
            margin-bottom: 30px;
            line-height: 1.8;
        }

        .buttons {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .btn {
            text-decoration: none;
            padding: 14px;
            border-radius: 12px;
            color: white;
            font-size: 18px;
            font-weight: bold;
            transition: transform 0.2s ease, opacity 0.2s ease;
        }

        .btn:hover { transform: scale(1.05); opacity: 0.9; }

        .facebook { background: #1877f2; }
        .whatsapp { background: #25d366; }
        .channel { background: #128c7e; }
        .instagram { 
            background: linear-gradient(45deg, #f58529, #dd2a7b, #8134af, #515bd4);
        }

        footer {
            margin-top: 25px;
            font-size: 14px;
            color: #666;
        }

        /* Language dropdown */
        .lang-select {
            margin-bottom: 15px;
            padding: 8px;
            border-radius: 8px;
        }
    </style>
</head>

<body>

<div class="container">

    <!-- 🌍 Language Selector -->
    <select class="lang-select" onchange="changeLang(this.value)">
        <option value="en">English</option>
        <option value="ar">العربية</option>
    </select>

    <img src="https://raw.githubusercontent.com/AbdallaBadreldin/one_awi_website/refs/heads/main/one_awi_logo.png" class="logo">

    <h1 data-key="title">1 awi</h1>
    <h2 data-key="subtitle">Your Custom Gift Destination 🎁</h2>

    <ul>
        <li data-key="item1">Create custom gifts</li>
        <li data-key="item2">Print mugs</li>
        <li data-key="item3">Print t-shirts</li>
        <li data-key="item4">Print caps</li>
        <li data-key="item5">And more... Contact us and pickup your special gift!</li>
    </ul>

    <div class="buttons">
        <a href="#" class="btn facebook" data-key="facebook">Facebook</a>
        <a href="#" class="btn whatsapp" data-key="whatsapp">WhatsApp</a>
        <a href="#" class="btn channel" data-key="channel">WhatsApp Channel</a>
        <a href="#" class="btn instagram" data-key="instagram">Instagram</a>
    </div>

    <footer data-key="footer">
        Made with ❤️ by 1 awi
    </footer>

</div>

<script>
const translations = {
    en: {
        title: "1 awi",
        subtitle: "Your Custom Gift Destination 🎁",
        item1: "Create custom gifts",
        item2: "Print mugs",
        item3: "Print t-shirts",
        item4: "Print caps",
        item5: "And more... Contact us and pickup your special gift!",
        facebook: "Facebook",
        whatsapp: "WhatsApp",
        channel: "WhatsApp Channel",
        instagram: "Instagram",
        footer: "Made with ❤️ by 1 awi"
    },

    ar: {
        title: "1 awi",
        subtitle: "وجهتك للهدايا المخصصة 🎁",
        item1: "تصميم هدايا مخصصة",
        item2: "طباعة مجات",
        item3: "طباعة تيشيرتات",
        item4: "طباعة كابات",
        item5: "والمزيد... تواصل معنا واستلم هديتك!",
        facebook: "فيسبوك",
        whatsapp: "واتساب",
        channel: "قناة واتساب",
        instagram: "إنستجرام",
        footer: "صُنع بـ ❤️ بواسطة 1 awi"
    }
};

function changeLang(lang) {
    localStorage.setItem("lang", lang);

    document.querySelectorAll("[data-key]").forEach(el => {
        el.textContent = translations[lang][el.getAttribute("data-key")];
    });

    // اتجاه الصفحة
    document.body.dir = (lang === "ar") ? "rtl" : "ltr";
}

// تحميل اللغة المحفوظة
window.onload = () => {
    const savedLang = localStorage.getItem("lang") || "en";
    changeLang(savedLang);
};
</script>

</body>
</html>
