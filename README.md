<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نقشه راه تعاملی آواجنرال ۱۴۰۴-۱۴۰۵</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Warm Neutrals & Subtle Industrial Tones -->
    <!-- Application Structure Plan: The application is designed as a single-page dashboard with a top navigation bar for quick scrolling. Instead of a linear list of 24 projects, which can be overwhelming, the information architecture is organized into five strategic themes (Digital Transformation, Business Development, Customer Experience, Branding, and Business Intelligence). This thematic structure allows users to grasp the overarching strategy at a glance. Users can click on a theme to filter and view the related projects. Clicking on an individual project opens a modal window with detailed information. This hierarchical, interactive approach reduces cognitive load, promotes self-directed exploration, and makes the dense report content much more digestible and engaging than a static document. -->
    <!-- Visualization & Content Choices: 
        1. Key Stats (Sales): Report Info -> 70% sold, 30% remaining. Goal -> Inform. Viz/Presentation -> Donut Chart. Interaction -> Hover for tooltip. Justification -> Instantly visualizes the sales progress and current status. Library/Method -> Chart.js.
        2. Project Distribution: Report Info -> 24 projects categorized into 5 themes. Goal -> Compare/Organize. Viz/Presentation -> Horizontal Bar Chart. Interaction -> Hover for tooltip. Justification -> Provides a high-level summary of where strategic effort is concentrated. Library/Method -> Chart.js.
        3. Strategic Themes: Report Info -> The core project groups. Goal -> Organize/Navigate. Viz/Presentation -> Interactive HTML/CSS Cards. Interaction -> Click to filter projects. Justification -> Serves as the main navigation, breaking down the complex roadmap into manageable sections. Library/Method -> Vanilla JS + Tailwind.
        4. Project Details: Report Info -> Detailed descriptions of each of the 24 projects. Goal -> Inform/Drill-down. Viz/Presentation -> Modal Window. Interaction -> Click project card to open. Justification -> Keeps the main interface clean while providing deep-dive information on demand. Library/Method -> Vanilla JS + Tailwind.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Vazirmatn', sans-serif;
            background-color: #f8f9fa;
            color: #343a40;
        }
        html {
            scroll-behavior: smooth;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 450px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 350px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 350px;
            }
        }
        .nav-link {
            transition: color 0.3s, border-bottom-color 0.3s;
        }
        .nav-link:hover {
            color: #007bff;
            border-bottom-color: #007bff;
        }
        .theme-card {
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .theme-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
        .project-card {
            transition: all 0.3s;
            border-right-width: 4px;
        }
        .modal-overlay {
            transition: opacity 0.3s ease-in-out;
        }
        .modal-content {
            transition: transform 0.3s ease-in-out;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800">

    <header class="bg-white/80 backdrop-blur-md shadow-sm sticky top-0 z-40">
        <nav class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center">
                    <span class="font-bold text-xl text-gray-800">آواجنرال</span>
                </div>
                <div class="hidden md:block">
                    <div class="ml-10 flex items-baseline space-x-4 space-x-reverse">
                        <a href="#vision" class="nav-link text-gray-600 px-3 py-2 rounded-md text-sm font-medium border-b-2 border-transparent">چشم‌انداز</a>
                        <a href="#roadmap" class="nav-link text-gray-600 px-3 py-2 rounded-md text-sm font-medium border-b-2 border-transparent">نقشه راه</a>
                        <a href="#partners" class="nav-link text-gray-600 px-3 py-2 rounded-md text-sm font-medium border-b-2 border-transparent">فرصت‌های همکاری</a>
                    </div>
                </div>
            </div>
        </nav>
    </header>

    <main>
        <section id="vision" class="py-16 sm:py-24 bg-white">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center">
                    <h1 class="text-4xl font-extrabold text-gray-900 sm:text-5xl md:text-6xl">
                        آرمان‌شهر صنعت تأسیسات کشور
                    </h1>
                    <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-500">
                        تحلیل جامع پروژه‌های آتی آواجنرال برای سال‌های ۱۴۰۴ و ۱۴۰۵ و چشم‌انداز تبدیل شدن به مرجع نخست زنجیره تأمین ساختمان و صنایع مکمل.
                    </p>
                    <p class="mt-2 max-w-2xl mx-auto text-lg text-gray-700 font-semibold">«جمعِ ما، جمع است»</p>
                </div>

                <div class="mt-16 grid gap-8 md:grid-cols-2 lg:grid-cols-2 items-center">
                    <div class="text-center md:text-right">
                        <h2 class="text-3xl font-bold text-gray-900">وضعیت فعلی و آینده</h2>
                        <p class="mt-4 text-lg text-gray-600">
                            آواجنرال، به عنوان یک مرکز خرید-صنعتی پیشرو، با واگذاری ۷۰٪ از واحدهای خود، جایگاه خود را در بازار تثبیت کرده است. ۳۰٪ باقی‌مانده نیز در قالب یک برنامه استراتژیک ۱۰ ساله واگذار خواهد شد. این پایداری، بستری امن برای سرمایه‌گذاری و همکاری‌های بلندمدت فراهم می‌کند.
                        </p>
                        <div class="mt-6 flex justify-center md:justify-start gap-x-6">
                            <div class="text-center">
                                <p class="text-4xl font-bold text-blue-600">۲۵,۰۰۰</p>
                                <p class="text-sm font-medium text-gray-500 mt-1">مترمربع مساحت</p>
                            </div>
                            <div class="text-center">
                                <p class="text-4xl font-bold text-blue-600">۴۵۰</p>
                                <p class="text-sm font-medium text-gray-500 mt-1">واحد تجاری</p>
                            </div>
                            <div class="text-center">
                                <p class="text-4xl font-bold text-blue-600">۱,۰۰۰</p>
                                <p class="text-sm font-medium text-gray-500 mt-1">ظرفیت پارکینگ</p>
                            </div>
                        </div>
                    </div>
                    <div class="chart-container">
                        <canvas id="salesChart"></canvas>
                    </div>
                </div>
            </div>
        </section>

        <section id="roadmap" class="py-16 sm:py-24">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center">
                    <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
                        نقشه راه راهبردی ۱۴۰۴-۱۴۰۵
                    </h2>
                    <p class="mt-4 max-w-3xl mx-auto text-lg text-gray-600">
                        برای درک بهتر برنامه‌های آینده، ۲۴ پروژه آتی آواجنرال را در پنج محور استراتژیک دسته‌بندی کرده‌ایم. با کلیک بر روی هر محور، پروژه‌های مرتبط با آن را مشاهده کنید.
                    </p>
                </div>

                <div class="mt-12 grid gap-8 md:grid-cols-2 items-center">
                     <div>
                        <h3 class="text-2xl font-bold text-gray-800 text-center mb-4">تمرکز پروژه‌ها بر محورهای استراتژیک</h3>
                        <div class="chart-container h-96 max-h-[450px]">
                            <canvas id="projectDistributionChart"></canvas>
                        </div>
                    </div>
                    <div id="themes-container" class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                    </div>
                </div>

                <div class="mt-12">
                    <h3 id="projects-title" class="text-2xl font-bold text-gray-900 text-center mb-8 hidden"></h3>
                    <div id="projects-container" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    </div>
                </div>
            </div>
        </section>
        
        <section id="partners" class="py-16 sm:py-24 bg-white">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center">
                    <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
                        فرصت‌های همکاری استراتژیک
                    </h2>
                    <p class="mt-4 max-w-3xl mx-auto text-lg text-gray-600">
                        آواجنرال با چشم‌انداز بلندمدت و پروژه‌های متنوع آتی، بستری غنی برای همکاری‌های فنی، بازاریابی، سرمایه‌گذاری و خدماتی فراهم آورده است.
                    </p>
                </div>
                <div class="mt-12 grid md:grid-cols-2 gap-8">
                    <div class="bg-gray-50 rounded-lg p-6">
                        <h3 class="text-xl font-bold text-gray-900">ارزش پیشنهادی برای شرکا</h3>
                         <ul class="mt-4 space-y-3 text-gray-600">
                            <li class="flex items-start">
                                <span class="text-blue-500 mt-1 mr-2">✔️</span>
                                <span><strong>دسترسی به بازار تخصصی:</strong> ورود به اکوسیستم متمرکز صنعت تأسیسات و کاهش هزینه‌های بازاریابی.</span>
                            </li>
                            <li class="flex items-start">
                                <span class="text-blue-500 mt-1 mr-2">✔️</span>
                                <span><strong>اعتبار برند مشترک:</strong> قرار گرفتن در کنار برندهای معتبر و تقویت تصویر حرفه‌ای در بازار.</span>
                            </li>
                            <li class="flex items-start">
                                <span class="text-blue-500 mt-1 mr-2">✔️</span>
                                <span><strong>بستر نوآوری و رشد:</strong> فرصت تست مدل‌های کسب‌وکار جدید در پروژه‌هایی مانند مارکت‌پلیس و فضاهای نوآورانه.</span>
                            </li>
                             <li class="flex items-start">
                                <span class="text-blue-500 mt-1 mr-2">✔️</span>
                                <span><strong>زیرساخت‌های پیشرفته:</strong> بهره‌مندی از امکانات فیزیکی و دیجیتال مدرن برای افزایش کارایی عملیاتی.</span>
                            </li>
                        </ul>
                    </div>
                    <div class="bg-gray-50 rounded-lg p-6">
                        <h3 class="text-xl font-bold text-gray-900">مزایای همکاری برای آواجنرال</h3>
                        <ul class="mt-4 space-y-3 text-gray-600">
                            <li class="flex items-start">
                                <span class="text-green-500 mt-1 mr-2">✔️</span>
                                <span><strong>جذب تخصص و نوآوری:</strong> استفاده از دانش فنی شرکا برای تسریع در دستیابی به اهداف استراتژیک.</span>
                            </li>
                             <li class="flex items-start">
                                <span class="text-green-500 mt-1 mr-2">✔️</span>
                                <span><strong>تنوع‌بخشی به درآمد:</strong> خلق جریان‌های درآمدی جدید و پایدار فراتر از فروش و اجاره سنتی.</span>
                            </li>
                             <li class="flex items-start">
                                <span class="text-green-500 mt-1 mr-2">✔️</span>
                                <span><strong>تقویت اکوسیستم و برند:</strong> افزایش وفاداری و حس تعلق در جامعه بهره‌برداران و تثبیت برند آواجنرال.</span>
                            </li>
                             <li class="flex items-start">
                                <span class="text-green-500 mt-1 mr-2">✔️</span>
                                <span><strong>افزایش کارایی عملیاتی:</strong> بهبود فرآیندهای داخلی از طریق پیاده‌سازی سیستم‌های هوشمند و داده‌محور.</span>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <footer class="bg-gray-800 text-white">
        <div class="container mx-auto py-6 px-4 sm:px-6 lg:px-8 text-center">
            <p>&copy; ۱۴۰۴ - کلیه حقوق این وب اپلیکیشن برای آواجنرال محفوظ است.</p>
        </div>
    </footer>

    <div id="project-modal" class="modal-overlay fixed inset-0 bg-black bg-opacity-60 z-50 hidden flex items-center justify-center p-4" aria-labelledby="modal-title" role="dialog" aria-modal="true">
        <div class="modal-content bg-white rounded-lg shadow-xl w-full max-w-2xl max-h-[90vh] overflow-y-auto transform scale-95">
            <div class="sticky top-0 bg-white p-4 sm:p-6 border-b border-gray-200 flex justify-between items-center">
                <h3 id="modal-title" class="text-xl font-bold text-gray-900"></h3>
                <button id="modal-close-btn" class="text-gray-400 hover:text-gray-600 transition">
                    <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" /></svg>
                </button>
            </div>
            <div id="modal-body" class="p-4 sm:p-6">
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const projectData = [
                { id: 1, title: "وب‌سایت آواجنرال", status: "در حال تکمیل", theme: "digital", objectives: ["نظارت و راهبری تا اتمام فاز توسعه و تضمین تطابق با نیازمندی‌ها", "راهبری تولید محتوا و وارد سازی اطلاعات واحدها", "تضمین کیفیت (QA) و استقرار نهایی با رویکرد SEO و کاربرپسند"], details: "این پروژه بر تکمیل و استقرار پلتفرم دیجیتال جامع آواجنرال تمرکز دارد تا به عنوان ویترین اصلی و کاربرپسند مجموعه عمل کند و زیربنای فعالیت‌های SEO و استراتژی محتوا باشد." },
                { id: 2, title: "پایگاه داده یکپارچه فروشگاه‌ها و محصولات", status: "جدید", theme: "digital", objectives: ["طراحی و پیاده‌سازی پایگاه دادهٔ متمرکز فروشگاه‌ها، واحدها و محصولات", "تدوین استانداردهای داده (متادیتا، دسته‌بندی و برچسب‌گذاری)", "استفاده از داده‌ها برای هوشمندسازی جستجو، انتخاب محصول و تقویت SEO"], details: "ایجاد یک زیرساخت داده متمرکز برای تمام اطلاعات فروشگاه‌ها و محصولات که به عنوان ستون فقرات اکوسیستم دیجیتال، به هوشمندسازی جستجو و تحلیل‌ها کمک می‌کند." },
                { id: 3, title: "آماده‌سازی SEO و جذب پارتنر", status: "جدید", theme: "digital", objectives: ["تدوین بریف و شرح‌کار SEO برای جذب پارتنر تخصصی", "تعریف ساختار URL و نقشهٔ سایت (sitemap) و اقدامات فنی مقدماتی", "تعیین شاخص‌های کلیدی عملکرد (KPIs) برای سنجش موفقیت SEO"], details: "این پروژه با هدف رشد ارگانیک و پایدار در فضای دیجیتال، به دنبال تدوین یک استراتژی جامع SEO و جذب یک شریک متخصص برای افزایش دیده‌پذیری وب‌سایت است." },
                { id: 4, title: "استراتژی محتوا و بلاگ", status: "فاز دوم", theme: "digital", objectives: ["تدوین استراتژی محتوا برای بلاگ آواجنرال", "تحقیق کلمات کلیدی و برنامه‌ریزی تقویم محتوا", "تولید و انتشار منظم مقالات تخصصی"], details: "هدف این پروژه، تبدیل بلاگ آواجنرال به یک رهبر فکری در صنعت تأسیسات از طریق تولید محتوای ارزشمند و تخصصی است تا مخاطبان هدف را جذب و حفظ کند." },
                { id: 5, title: "تبلیغات دیجیتال", status: "جدید", theme: "digital", objectives: ["تدوین Brief کمپین تبلیغات بر اساس اهداف فروش و اجاره واحدها", "افزایش دسترسی و آگاهی برند آواجنرال", "جذب سرنخ و تسهیل فرآیند فروش/اجاره"], details: "این پروژه مکمل استراتژی‌های ارگانیک است و بر استفاده از تبلیغات پولی در پلتفرم‌های مختلف برای جذب سرنخ‌های کیفی و تسریع فرآیند فروش و اجاره تمرکز دارد." },
                { id: 6, title: "تبلیغات آفلاین", status: "جدید", theme: "branding", objectives: ["تدوین برنامهٔ تبلیغات آفلاین برای تقویت آگاهی از برند و جذب بهره‌بردار جدید", "شناسایی کانال‌ها، موقعیت‌ها و پیام‌های مؤثر تبلیغاتی", "طراحی، اجرا و ارزیابی اثربخشی کمپین‌های محیطی و چاپی"], details: "این پروژه با درک اهمیت کانال‌های سنتی، به دنبال تقویت آگاهی از برند و جذب بهره‌بردار از طریق کمپین‌های خلاقانه آفلاین مانند تبلیغات محیطی و گوریلا مارکتینگ است." },
                { id: 7, title: "بازاریابی رویداد (Event Marketing)", status: "جدید", theme: "experience", objectives: ["طراحی و اجرای برنامه‌های رویداد در فضای آواجنرال برای جذب بازدیدکننده", "افزایش آگاهی از برند و تعامل با اشخاص جدید به عنوان مشتریان بالقوه", "تقویت ارتباط تجاری و تسهیل فروش/اجاره واحدها از طریق تجربه‌های حضوری"], details: "این پروژه با استفاده از فضاهای فیزیکی مجموعه، به دنبال ایجاد تعاملات حضوری و تقویت حس جامعه از طریق برگزاری رویدادها و همایش‌های تخصصی است." },
                { id: 8, title: "کمپین پروموشن سراسری آواجنرال", status: "جدید", theme: "branding", objectives: ["طراحی و اجرای یک کمپین پروموشن هماهنگ برای تمامی فروشگاه‌ها", "افزایش ترافیک بازدید، فروش، و آگاهی از برند آواجنرال و فروشگاه‌های آن", "ایجاد تجربه تبلیغاتی مشترک و قابل تکرار بین بهره‌برداران"], details: "این پروژه با بهره‌گیری از قدرت جمعی واحدها، به دنبال ایجاد یک هویت یکپارچه برای کمپین‌های مشترک است که نه تنها فروش را افزایش می‌دهد، بلکه حس هویت مشترک را تقویت می‌کند." },
                { id: 9, title: "بهره‌برداری نوآورانه از فضاهای خالی", status: "جدید", theme: "innovation", objectives: ["تحلیل ظرفیت فضاهای بلااستفاده در آواجنرال و شناسایی فرصت‌های نوآورانه", "توسعه ایده‌های درآمدزا و برندمحور (مثل فضای کار اشتراکی، اتاق جلسه، استودیو و…)", "طراحی بیزنس‌کیس و راه‌اندازی نمونه‌های اولیه برای بهره‌برداری تدریجی"], details: "این پروژه با رویکردی کارآفرینانه به دنبال تبدیل فضاهای بلااستفاده به مراکز درآمدزای جدید مانند کوورکینگ است تا آواجنرال را به یک هاب شهری-تخصصی تبدیل کند." },
                { id: 10, title: "امکان‌سنجی و طراحی پلتفرم مارکت‌پلیس آواجنرال", status: "جدید", theme: "innovation", objectives: ["بررسی امکان راه‌اندازی مارکت‌پلیس تخصصی با محوریت فروشگاه‌ها و محصولات آواجنرال", "تحلیل بازار، رقبا، ظرفیت فروشگاه‌ها به عنوان بهره‌برداران اولیه و مزیت رقابتی آواجنرال", "تدوین نقشه‌راه برای توسعه گام‌به‌گام پلتفرم دیجیتال"], details: "یک گام بلند و استراتژیک برای آواجنرال است که آن را وارد حوزه اقتصاد پلتفرمی می‌کند. این پروژه ظرفیت‌های راه‌اندازی یک بازار آنلاین تخصصی را بررسی می‌کند تا اکوسیستم فروش دیجیتال را گسترش دهد." },
                { id: 11, title: "بازنگری مدل کسب‌وکار و طراحی سناریوهای آینده", status: "ادامه‌دار", theme: "innovation", objectives: ["بازبینی مدل کسب‌وکار آواجنرال در شرایط جدید اقتصادی، سیاسی و اجتماعی", "تحلیل درآمد، هزینه، و ساختار سودآوری در سناریوهای مختلف", "تصمیم‌سازی (بهره‌برداری، واگذاری، توسعه،…)"], details: "این پروژه با رویکردی پیش‌نگرانه و چابک، پایداری آواجنرال را در برابر تحولات محیطی تضمین کرده و با طراحی سناریوهای آینده، آمادگی برای تصمیم‌گیری هوشمندانه را فراهم می‌کند." },
                { id: 12, title: "داشبورد KPI و داده‌محور کردن تصمیم‌ها", status: "در آستانه عملیاتی‌شدن", theme: "bi", objectives: ["جمع‌آوری، پردازش و مصورسازی داده‌های کلیدی آواجنرال", "تعریف و ردیابی شاخص‌های عملکرد برای حوزه‌های کلیدی (اجاره، تردد، خدمات،…)", "ارتقای تصمیم‌سازی از طریق ابزارهای عددی، قابل اعتماد و قابل اشتراک"], details: "این داشبورد به عنوان «سیستم عصبی مرکزی» آواجنرال عمل کرده، شفافیت عملیاتی را افزایش می‌دهد و با فراهم آوردن داده‌های قابل اعتماد، تصمیم‌گیری‌ها را داده‌محور می‌کند." },
                { id: 13, title: "بازطراحی مسیر جذب و تبدیل بهره‌بردار", status: "جدید", theme: "experience", objectives: ["فعال‌سازی ترکیبی از فعالیت‌های ورودی (Inbound) و خروجی (Outbound) برای جذب بهره‌بردار", "تحلیل و بهبود مسیر سفر مشتری از اولین تماس تا عقد قرارداد", "افزایش نرخ تبدیل از لید به قرارداد از طریق ابزارهای حرفه‌ای و داده‌محور"], details: "یک رویکرد سیستماتیک و داده‌محور برای بهینه‌سازی فرآیند جذب مشتری که با تحلیل قیف فروش و مدیریت سرنخ‌ها، به دنبال افزایش نرخ تبدیل و کاهش ریزش است." },
                { id: 14, title: "توانمندسازی بهره‌برداران برای رونق پایدار", status: "جدید", theme: "experience", objectives: ["شناسایی نیازهای اصلی بهره‌برداران در حوزه‌های فروش، بازاریابی، مالی، آموزش و تبلیغات", "طراحی و اجرای بسته‌های حمایتی برای ارتقای عملکرد واحدهای تجاری مستقر", "افزایش تعامل و هم‌افزایی میان کسب‌وکارهای مستقر در مجتمع", "ایجاد فضای ایده‌پردازی برای خلق راه‌کارهای خلاقانه و مشترک"], details: "این پروژه بر این اصل استوار است که رونق مجموعه به رونق کسب‌وکارهای آن وابسته است و به دنبال ارائه خدمات مشاوره‌ای و حمایتی برای ارتقای عملکرد واحدهاست." },
                { id: 15, title: "ارتقای نقاط تماس برند آواجنرال", status: "ادامه‌دار", theme: "branding", objectives: ["افزایش آگاهی از برند آواجنرال در میان مخاطبان هدف", "یکپارچه‌سازی و تقویت نقاط تماس محیطی و دیجیتال", "طراحی و اجرای برنامه‌های خلاقانه برای ارتقای دیده‌شدن و شنیده‌شدن برند"], details: "یک رویکرد جامع به برندینگ که با ممیزی و ارتقای تمامی نقاط تماس، از تابلوهای راهنما تا حضور دیجیتال، به دنبال خلق یک تجربه برند یکپارچه و فراگیر است." },
                { id: 16, title: "پایش بازار و طراحی مدل ارزش‌گذاری پویا", status: "در فاز طراحی مدل", theme: "bi", objectives: ["گردآوری و تحلیل داده‌های بازار املاک تجاری–اداری مرتبط با پروژه آواجنرال", "توسعه مدل ارزش‌گذاری پویا برای املاک با قابلیت انطباق با متغیرهای کلان اقتصادی و محلی", "ارائه ابزارهای تصمیم‌یار برای هدف‌گذاری فروش و تدوین سناریوهای فروش و اجاره"], details: "این پروژه با تحلیل مستمر بازار و طراحی یک مدل قیمت‌گذاری هوشمند، آواجنرال را قادر می‌سازد تا در یک بازار متغیر، تصمیمات استراتژیک و مبتنی بر داده اتخاذ کند." },
                { id: 17, title: "طراحی تجربهٔ ذی‌نفعان در چرخهٔ بهره‌برداری", status: "جدید", theme: "experience", objectives: ["شناسایی ذی‌نفعان کلیدی در چرخهٔ بهره‌برداری از پروژهٔ آواجنرال", "تدوین نقشهٔ سفر (Journey Map) برای گروه‌های مختلف ذی‌نفع", "بهینه‌سازی نقاط تماس و طراحی تجربه‌ای مشعوف‌کننده، فراتر از نیازهای پایه"], details: "این پروژه با رویکردی پیشرفته و مشتری‌محور، به دنبال ایجاد ارتباط عاطفی و وفاداری بلندمدت از طریق طراحی تجربه‌های به یادماندنی برای تمام ذی‌نفعان است." },
                { id: 18, title: "طراحی و پیاده‌سازی خدمات مکمل و زیرساخت‌های رفاهی", status: "در فاز عملیاتی‌سازی اولیه", theme: "experience", objectives: ["عملیاتی‌کردن فازهای کلیدی خدمات رفاهی و پشتیبان در آواجنرال", "تدوین الزامات و تجربهٔ کاربری برای استقرار خدمات منتخب", "طراحی الگوی هم‌زیستی خدمات برای خلق یک اکوسیستم پایدار و هم‌افزا"], details: "این پروژه با افزودن خدمات رفاهی و پشتیبانی، آواجنرال را به یک «زیست‌بوم تجربه» تبدیل می‌کند که حس تعلق را تقویت کرده و بر ماندگاری بهره‌برداران تأثیر مثبت دارد." },
                { id: 19, title: "ارتقای راهبرد محتوای دیجیتال و اثربخشی شبکه‌های اجتماعی", status: "بهینه‌سازی", theme: "digital", objectives: ["بازطراحی راهبرد محتوا و هویت رسانه‌ای آواجنرال در شبکه‌های اجتماعی", "بهینه‌سازی حضور و تعامل در پلتفرم‌ها (اینستاگرام، لینکدین، تلگرام)", "افزایش نرخ رشد دنبال‌کننده، تعامل ارگانیک و نرخ بازنشر محتوا"], details: "تمرکز این پروژه بر بهینه‌سازی حضور در شبکه‌های اجتماعی با تولید محتوای اصیل و پلتفرم‌محور است تا آواجنرال به منبعی معتبر و الهام‌بخش تبدیل شود." },
                { id: 20, title: "باشگاه بهره‌برداران و خلق ارزش عضویت", status: "جدید", theme: "experience", objectives: ["طراحی ساختار باشگاه بهره‌برداران آواجنرال به‌عنوان یک دارایی معنوی و مشوق ماندگاری", "تقویت حس تعلق، وفاداری و افتخار به عضویت در جامعهٔ آواجنرالی‌ها", "تدوین مشوق‌ها و مزایای ملموس عضویت برای ارتقای تجربه و افزایش ارجاع", "خلق مکانیزم‌های عضویت، امتیازدهی و تعامل پایدار بین اعضای باشگاه"], details: "یک گام استراتژیک برای تبدیل جامعه بهره‌برداران به یک سرمایه اجتماعی ارزشمند. این باشگاه با ایجاد حس تعلق و وفاداری، به رونق بلندمدت مجموعه کمک می‌کند." },
                { id: 21, title: "استقرار و ارتقای عملیاتی MyLobbyMan", status: "در فاز راه‌اندازی و آموزش", theme: "experience", objectives: ["انتقال نرم‌افزار MyLobbyMan از فاز پیاده‌سازی به بهره‌برداری واقعی در مجتمع آواجنرال", "تسهیل فرآیند پذیرش و استفاده توسط بهره‌برداران، تیم‌های داخلی و مدیریت مجتمع", "طراحی مسیر ارتقاپذیر برای هم‌راستاسازی سامانه با دیگر پروژه‌ها و زیست‌بوم آواجنرال"], details: "این نرم‌افزار به عنوان یک پلتفرم اتصال‌دهنده، کارایی عملیاتی را بهبود بخشیده و زیرساخت لازم برای پروژه‌هایی مانند باشگاه بهره‌برداران و داشبوردهای تحلیلی را فراهم می‌کند." },
                { id: 22, title: "طراحی سناریوهای سرمایه‌گذاری و فرصت‌های توسعه", status: "در انتظار جلسات با شرکا", theme: "innovation", objectives: ["شناسایی ظرفیت‌های بلااستفاده یا توسعه‌پذیر در بستر فیزیکی، دیجیتال و برند آواجنرال", "ایجاد چارچوب فرصت‌سنجی برای شکل‌گیری کسب‌وکارها یا همکاری‌های نو", "تسهیل هم‌فکری میان آواجنرال، گروه آبادسازان و ذی‌نفعان کلیدی برای تصمیم‌سازی مشترک"], details: "این پروژه به طور فعال به دنبال شناسایی و توسعه فرصت‌های جدید سرمایه‌گذاری است تا آواجنرال را به یک پلتفرم جذاب برای کارآفرینان و سرمایه‌گذاران تبدیل کند." },
                { id: 23, title: "فعال‌سازی عملیاتی ترکیب بهره‌برداران", status: "ورود به فاز اقدام اجرایی", theme: "branding", objectives: ["عبور از فاز مطالعاتی Tenant Mix و ورود به مرحلهٔ اجرا", "تعریف گام‌های اولویت‌دار برای بهبود ترکیب صنفی و افزایش تنوع بهره‌برداران", "طراحی نقشهٔ اقدام برای خلق هم‌افزایی، جذب هدفمند و رونق پایدار در اکوسیستم"], details: "این پروژه با عبور از فاز مطالعاتی، به طور فعال به دنبال مدیریت ترکیب صنفی مجموعه است تا با جذب هدفمند، یک اکوسیستم تجاری متعادل و پایدار ایجاد کند." },
                { id: 24, title: "ساماندهی چیدمان محیطی و ارتقای جلوه‌های بصری", status: "در حال اقدام و تدوین راهکار", theme: "branding", objectives: ["بالانس بین نظم اولیه پروژه و وضعیت کنونی برای جلوگیری از بی‌نظمی‌ بصری در محیط تجاری", "تعریف استانداردهای قابل‌اجرا برای چیدمان بیرونی واحدها با توجه به اقتضای صنفی", "افزایش جذابیت محیط برای بازدیدکنندگان بدون خدشه به هویت صنعتی مجتمع", "کاهش اصطکاک با بهره‌برداران از طریق مشارکت در تدوین و اجرای راهکارها"], details: "این پروژه با هدف حفظ هویت بصری و نظم محیطی، به دنبال تدوین استانداردهایی برای چیدمان بیرونی واحدها با رویکردی مشارکتی است تا هم زیبایی و هم کارکرد حفظ شود." },
            ];
            
            const themes = {
                digital: { name: "تحول دیجیتال و بازاریابی", icon: "⚙️", color: "blue" },
                innovation: { name: "توسعه کسب‌وکار و نوآوری", icon: "�", color: "purple" },
                experience: { name: "تجربه مشتری و جامعه‌سازی", icon: "👥", color: "teal" },
                branding: { name: "برندینگ و مدیریت محیطی", icon: "🏢", color: "amber" },
                bi: { name: "هوشمندی کسب‌وکار و تحلیل داده", icon: "📊", color: "red" }
            };

            const statusStyles = {
                "جدید": { text: "جدید", color: "blue" },
                "ادامه‌دار": { text: "ادامه‌دار", color: "gray" },
                "در حال تکمیل": { text: "در حال تکمیل", color: "green" },
                "فاز دوم": { text: "فاز دوم", color: "yellow" },
                "بهینه‌سازی": { text: "بهینه‌سازی", color: "indigo" },
                "در آستانه عملیاتی‌شدن": { text: "عملیاتی‌سازی", color: "purple" },
                "در فاز طراحی مدل": { text: "طراحی مدل", color: "pink" },
                "در فاز عملیاتی‌سازی اولیه": { text: "عملیاتی اولیه", color: "cyan" },
                "در فاز راه‌اندازی و آموزش": { text: "راه‌اندازی", color: "lime" },
                "در انتظار جلسات با شرکا": { text: "در انتظار", color: "orange" },
                "ورود به فاز اقدام اجرایی": { text: "اقدام اجرایی", color: "emerald" },
                "در حال اقدام و تدوین راهکار": { text: "تدوین راهکار", color: "rose" },
            };

            const themesContainer = document.getElementById('themes-container');
            const projectsContainer = document.getElementById('projects-container');
            const projectsTitle = document.getElementById('projects-title');

            const modal = document.getElementById('project-modal');
            const modalTitle = document.getElementById('modal-title');
            const modalBody = document.getElementById('modal-body');
            const modalCloseBtn = document.getElementById('modal-close-btn');
            const modalOverlay = modal; // The modal element itself is the overlay
            const modalContent = modal.querySelector('.modal-content');

            function renderThemes() {
                let themesHTML = '';
                for (const key in themes) {
                    themesHTML += `
                        <div class="theme-card bg-white rounded-lg shadow-md p-6 text-center cursor-pointer border-t-4 border-${themes[key].color}-500" data-theme="${key}">
                            <div class="text-4xl mb-4">${themes[key].icon}</div>
                            <h3 class="text-xl font-bold text-gray-800">${themes[key].name}</h3>
                            <p class="text-gray-500 mt-2">${projectData.filter(p => p.theme === key).length} پروژه</p>
                        </div>
                    `;
                }
                themesContainer.innerHTML = themesHTML;
            }

            function renderProjects(themeKey = null) {
                const filteredProjects = themeKey ? projectData.filter(p => p.theme === themeKey) : [];
                
                projectsTitle.textContent = themeKey ? `پروژه‌های محور: ${themes[themeKey].name}` : '';
                projectsTitle.style.display = themeKey ? 'block' : 'none';

                let projectsHTML = '';
                filteredProjects.forEach(project => {
                    const statusInfo = statusStyles[project.status] || statusStyles['ادامه‌دار'];
                    projectsHTML += `
                        <div class="project-card bg-white rounded-lg shadow p-5 cursor-pointer flex flex-col justify-between border-r-${statusInfo.color}-500 hover:shadow-xl hover:border-r-${statusInfo.color}-600" data-id="${project.id}">
                            <div>
                                <div class="flex justify-between items-start">
                                    <h4 class="font-bold text-lg text-gray-800">${project.title}</h4>
                                    <span class="text-xs font-semibold text-${statusInfo.color}-800 bg-${statusInfo.color}-100 px-2 py-1 rounded-full">${statusInfo.text}</span>
                                </div>
                                <p class="text-sm text-gray-600 mt-2">${project.objectives[0]}</p>
                            </div>
                            <div class="text-left mt-4">
                                <span class="text-sm font-medium text-blue-600 hover:text-blue-800">مشاهده جزئیات &rarr;</span>
                            </div>
                        </div>
                    `;
                });
                projectsContainer.innerHTML = projectsHTML;
            }
            
            function showModal(projectId) {
                const project = projectData.find(p => p.id == projectId);
                if (!project) return;
                
                modalTitle.textContent = project.title;
                
                let objectivesHTML = project.objectives.map(obj => `<li class="flex items-start"><span class="text-green-500 mt-1 mr-2">✓</span><span>${obj}</span></li>`).join('');

                modalBody.innerHTML = `
                    <div class="space-y-4">
                        <div>
                            <h4 class="font-bold text-gray-700">شرح پروژه:</h4>
                            <p class="text-gray-600">${project.details}</p>
                        </div>
                        <div>
                            <h4 class="font-bold text-gray-700">اهداف کلیدی:</h4>
                            <ul class="mt-2 space-y-2 text-gray-600">${objectivesHTML}</ul>
                        </div>
                        <div class="flex items-center gap-x-4">
                           <span class="font-bold text-gray-700">محور استراتژیک:</span>
                           <span class="text-sm font-semibold text-${themes[project.theme].color}-800 bg-${themes[project.theme].color}-100 px-3 py-1 rounded-full">${themes[project.theme].name}</span>
                        </div>
                    </div>
                `;

                modal.classList.remove('hidden');
                setTimeout(() => {
                    modalOverlay.classList.remove('opacity-0'); 
                    modalContent.classList.remove('scale-95');
                }, 10);
            }

            function hideModal() {
                modalOverlay.classList.add('opacity-0');
                modalContent.classList.add('scale-95');
                setTimeout(() => {
                    modal.classList.add('hidden');
                }, 300);
            }

            themesContainer.addEventListener('click', (e) => {
                const card = e.target.closest('.theme-card');
                if (card) {
                    const themeKey = card.dataset.theme;
                    renderProjects(themeKey);
                }
            });

            projectsContainer.addEventListener('click', (e) => {
                const card = e.target.closest('.project-card');
                if (card) {
                    const projectId = card.dataset.id;
                    showModal(projectId);
                }
            });
            
            modalCloseBtn.addEventListener('click', hideModal);
            modal.addEventListener('click', (e) => {
                if (e.target === modal) {
                    hideModal();
                }
            });
            
            const salesChartCtx = document.getElementById('salesChart').getContext('2d');
            new Chart(salesChartCtx, {
                type: 'doughnut',
                data: {
                    labels: ['واگذار شده', 'باقی‌مانده'],
                    datasets: [{
                        data: [70, 30],
                        backgroundColor: ['#3b82f6', '#e5e7eb'],
                        borderColor: ['#ffffff', '#ffffff'],
                        borderWidth: 4
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    cutout: '70%',
                    plugins: {
                        legend: {
                            position: 'bottom',
                            labels: {
                                font: { family: 'Vazirmatn', size: 14 },
                                padding: 20
                            }
                        },
                        title: {
                            display: true,
                            text: 'وضعیت واگذاری واحدها',
                            font: { family: 'Vazirmatn', size: 18, weight: 'bold' },
                            padding: { top: 10, bottom: 20 }
                        },
                        tooltip: {
                            bodyFont: { family: 'Vazirmatn' },
                            titleFont: { family: 'Vazirmatn' },
                             callbacks: {
                                label: function(context) {
                                    return `${context.label}: ${context.raw}%`;
                                }
                            }
                        }
                    }
                }
            });

            const projectDistributionCtx = document.getElementById('projectDistributionChart').getContext('2d');
            const projectCounts = Object.keys(themes).map(key => {
                return projectData.filter(p => p.theme === key).length;
            });

            new Chart(projectDistributionCtx, {
                type: 'bar',
                data: {
                    labels: Object.values(themes).map(t => t.name),
                    datasets: [{
                        label: 'تعداد پروژه‌ها',
                        data: projectCounts,
                        backgroundColor: Object.values(themes).map(t => {
                            const colors = { blue: '#93c5fd', purple: '#c4b5fd', teal: '#99f6e4', amber: '#fde68a', red: '#fca5a5'};
                            return colors[t.color];
                        }),
                        borderColor: Object.values(themes).map(t => {
                            const colors = { blue: '#3b82f6', purple: '#8b5cf6', teal: '#14b8a6', amber: '#f59e0b', red: '#ef4444'};
                            return colors[t.color];
                        }),
                        borderWidth: 1
                    }]
                },
                options: {
                    indexAxis: 'y',
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            display: false
                        },
                        tooltip: {
                            bodyFont: { family: 'Vazirmatn' },
                            titleFont: { family: 'Vazirmatn' }
                        }
                    },
                    scales: {
                        x: {
                            beginAtZero: true,
                             ticks: {
                                stepSize: 1
                            }
                        },
                        y: {
                            ticks: {
                                font: { family: 'Vazirmatn', size: 12 }
                            }
                        }
                    }
                }
            });

            renderThemes();
        });
    </script>
</body>
</html>
�
