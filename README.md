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
                        تحلیل جامع پروژه‌های آتی آواجنرال برای سال‌های ۱۴۰۴ و ۱۴۰۵ و چشم‌انداز تبدیل شدن به مرجع نخست زنجیره تأسیساتی ساختمان و صنایع مکمل.
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
                        <!-- Thematic groupings for projects based on uploaded content -->
                        <div class="theme-card bg-white rounded-lg shadow-md p-6 text-center cursor-pointer border-t-4 border-blue-500">
                            <div class="text-4xl mb-4">⚙️</div>
                            <h3 class="text-xl font-bold text-gray-800">تحول دیجیتال و بازاریابی</h3>
                            <p class="text-gray-500 mt-2">6 پروژه</p>
                        </div>
                        <div class="theme-card bg-white rounded-lg shadow-md p-6 text-center cursor-pointer border-t-4 border-purple-500">
                            <div class="text-4xl mb-4">💡</div>
                            <h3 class="text-xl font-bold text-gray-800">توسعه کسب‌وکار و نوآوری</h3>
                            <p class="text-gray-500 mt-2">5 پروژه</p>
                        </div>
                        <div class="theme-card bg-white rounded-lg shadow-md p-6 text-center cursor-pointer border-t-4 border-teal-500">
                            <div class="text-4xl mb-4">👥</div>
                            <h3 class="text-xl font-bold text-gray-800">تجربه مشتری و جامعه‌سازی</h3>
                            <p class="text-gray-500 mt-2">5 پروژه</p>
                        </div>
                        <div class="theme-card bg-white rounded-lg shadow-md p-6 text-center cursor-pointer border-t-4 border-amber-500">
                            <div class="text-4xl mb-4">🏢</div>
                            <h3 class="text-xl font-bold text-gray-800">برندینگ و مدیریت محیطی</h3>
                            <p class="text-gray-500 mt-2">5 پروژه</p>
                        </div>
                        <div class="theme-card bg-white rounded-lg shadow-md p-6 text-center cursor-pointer border-t-4 border-red-500">
                            <div class="text-4xl mb-4">📊</div>
                            <h3 class="text-xl font-bold text-gray-800">هوشمندی کسب‌وکار و تحلیل داده</h3>
                            <p class="text-gray-500 mt-2">3 پروژه</p>
                        </div>
                    </div>
                </div>

                <div class="mt-12">
                    <h3 id="projects-title" class="text-2xl font-bold text-gray-900 text-center mb-8 hidden"></h3>
                    <div id="projects-container" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                        <!-- Projects dynamically populated here -->
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
                    <!-- Partnership details here -->
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
        // Code to handle dynamic rendering of project data
    </script>
</body>
</html>
