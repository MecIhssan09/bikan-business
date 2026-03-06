# bikan-business
Une application qui permet de faire des achats en ligne 
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>BIKAN Business | ERP Mondial</title>
    
    <!-- Configuration PWA pour iPhone et Android -->
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="apple-mobile-web-app-title" content="BIKAN">
    <link rel="apple-touch-icon" href="https://files.oaiusercontent.com/file-6fTz8pXN5pXm5S8Z1J2W3Q?se=2026-03-06T11%3A37%3A18Z&sp=r&sv=2024-08-04&sr=b&rscc=max-age%3D604800%2C%20immutable%2C%20private&rscd=attachment%3B%20filename%3D87767.png&sig=4%2BZK8oG/o9YqX7zX9/Y7U/z4p6w7m9J0X0U1e6U1U/U%3D">
    
    <!-- Tailwind CSS & Lucide Icons -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&display=swap');
        
        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            -webkit-tap-highlight-color: transparent;
            overscroll-behavior-y: contain;
        }

        .splash-screen {
            transition: opacity 0.6s ease-out, visibility 0.6s;
        }

        .loader-bar {
            height: 3px;
            width: 140px;
            background: #e2e8f0;
            border-radius: 10px;
            overflow: hidden;
            position: relative;
        }

        .loader-progress {
            position: absolute;
            height: 100%;
            background: #2563eb;
            width: 40%;
            animation: load 1.4s infinite ease-in-out;
        }

        @keyframes load {
            0% { left: -40%; }
            100% { left: 100%; }
        }

        .nav-blur {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
        }

        /* Animation pour les cartes */
        .card-pop {
            animation: pop 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        @keyframes pop {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }
    </style>
</head>
<body class="bg-[#F8FAFC]">

    <!-- SPLASH SCREEN -->
    <div id="splash" class="fixed inset-0 bg-white z-[100] flex flex-col items-center justify-center splash-screen">
        <img src="https://files.oaiusercontent.com/file-6fTz8pXN5pXm5S8Z1J2W3Q?se=2026-03-06T11%3A37%3A18Z&sp=r&sv=2024-08-04&sr=b&rscc=max-age%3D604800%2C%20immutable%2C%20private&rscd=attachment%3B%20filename%3D87767.png&sig=4%2BZK8oG/o9YqX7zX9/Y7U/z4p6w7m9J0X0U1e6U1U/U%3D" 
             class="w-28 mb-12 drop-shadow-xl" alt="BIKAN Logo">
        <div class="loader-bar">
            <div class="loader-progress"></div>
        </div>
        <p class="mt-8 text-[9px] font-black uppercase tracking-[0.5em] text-slate-400">BIKAN Business OS</p>
    </div>

    <!-- MAIN APP CONTENT -->
    <div id="app-content" class="opacity-0 transition-opacity duration-700 pb-32">
        
        <!-- HEADER -->
        <header class="sticky top-0 z-40 bg-white/70 backdrop-blur-xl px-6 py-6 border-b border-slate-100 flex justify-between items-center">
            <div>
                <h1 class="text-xl font-black tracking-tighter text-slate-900">BIKAN BUSINESS</h1>
                <div class="flex items-center gap-2 mt-1">
                    <span class="w-1.5 h-1.5 bg-blue-600 rounded-full animate-pulse"></span>
                    <span class="text-[8px] font-black text-blue-600 uppercase tracking-widest">Ihssan Admin Panel</span>
                </div>
            </div>
            <div class="flex gap-2">
                <button class="w-10 h-10 bg-slate-50 rounded-xl flex items-center justify-center text-slate-400 border border-slate-100">
                    <i data-lucide="bell" class="w-5 h-5"></i>
                </button>
                <div class="w-10 h-10 bg-slate-900 rounded-xl flex items-center justify-center text-white font-black text-xs shadow-lg">
                    I
                </div>
            </div>
        </header>

        <!-- DASHBOARD BODY -->
        <main class="p-6 space-y-8">
            
            <!-- STATS CARD -->
            <div class="bg-slate-900 rounded-[2.5rem] p-8 text-white relative overflow-hidden shadow-2xl shadow-blue-900/10 card-pop">
                <div class="absolute -right-10 -top-10 w-40 h-40 bg-blue-600/20 rounded-full blur-3xl"></div>
                <div class="relative z-10">
                    <p class="text-[9px] font-black text-slate-400 uppercase tracking-widest mb-1">Ventes du jour</p>
                    <h2 class="text-4xl font-black tracking-tighter">258 000 <span class="text-xs text-blue-400 font-bold ml-1">FCFA</span></h2>
                    
                    <div class="mt-8 flex gap-3">
                        <div class="bg-white/10 px-4 py-2 rounded-xl backdrop-blur-md flex items-center gap-2">
                            <i data-lucide="trending-up" class="w-3 h-3 text-emerald-400"></i>
                            <span class="text-[8px] font-black uppercase text-emerald-400">+18.4%</span>
                        </div>
                        <div class="bg-white/10 px-4 py-2 rounded-xl backdrop-blur-md flex items-center gap-2">
                            <i data-lucide="globe" class="w-3 h-3 text-blue-400"></i>
                            <span class="text-[8px] font-black uppercase text-blue-400">International</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- SEARCH -->
            <div class="relative card-pop" style="animation-delay: 0.1s;">
                <i data-lucide="search" class="absolute left-5 top-1/2 -translate-y-1/2 text-slate-300 w-5 h-5"></i>
                <input type="text" placeholder="Rechercher un produit..." 
                       class="w-full bg-white border border-slate-100 py-5 pl-14 pr-6 rounded-2xl shadow-sm outline-none font-bold text-sm focus:ring-4 focus:ring-blue-100/20 transition-all">
            </div>

            <!-- PRODUCT GRID -->
            <div class="space-y-4">
                <div class="flex justify-between items-center px-2">
                    <h3 class="text-xs font-black uppercase tracking-widest text-slate-400">Top Produits</h3>
                    <i data-lucide="more-horizontal" class="w-4 h-4 text-slate-300"></i>
                </div>
                
                <div class="grid grid-cols-2 gap-4">
                    <!-- Produit 1 -->
                    <div class="bg-white p-4 rounded-[2rem] shadow-sm border border-slate-50 active:scale-95 transition-all card-pop" style="animation-delay: 0.2s;">
                        <div class="aspect-square bg-slate-50 rounded-[1.5rem] mb-4 flex items-center justify-center">
                            <i data-lucide="package" class="w-10 h-10 text-slate-200"></i>
                        </div>
                        <h4 class="font-black text-slate-800 text-[10px] uppercase truncate">Stock Bénin</h4>
                        <div class="flex justify-between items-center mt-2">
                            <p class="font-black text-blue-600 text-sm">15 000 <span class="text-[8px]">F</span></p>
                            <button class="bg-slate-900 text-white p-2 rounded-xl"><i data-lucide="plus" class="w-4 h-4"></i></button>
                        </div>
                    </div>
                    <!-- Produit 2 -->
                    <div class="bg-white p-4 rounded-[2rem] shadow-sm border border-slate-50 active:scale-95 transition-all card-pop" style="animation-delay: 0.3s;">
                        <div class="aspect-square bg-slate-50 rounded-[1.5rem] mb-4 flex items-center justify-center">
                            <i data-lucide="package" class="w-10 h-10 text-slate-200"></i>
                        </div>
                        <h4 class="font-black text-slate-800 text-[10px] uppercase truncate">Stock France</h4>
                        <div class="flex justify-between items-center mt-2">
                            <p class="font-black text-blue-600 text-sm">22 000 <span class="text-[8px]">F</span></p>
                            <button class="bg-slate-900 text-white p-2 rounded-xl"><i data-lucide="plus" class="w-4 h-4"></i></button>
                        </div>
                    </div>
                </div>
            </div>
        </main>

        <!-- BOTTOM NAVIGATION -->
        <nav class="fixed bottom-0 inset-x-0 nav-blur border-t border-slate-50 px-8 pt-4 pb-10 flex justify-between items-center z-50">
            <button class="flex flex-col items-center gap-1.5 text-blue-600">
                <div class="relative">
                    <i data-lucide="layout-grid" class="w-6 h-6"></i>
                    <div class="absolute -top-1 -right-1 w-1.5 h-1.5 bg-blue-600 rounded-full"></div>
                </div>
                <span class="text-[8px] font-black uppercase tracking-widest">Boutique</span>
            </button>
            <button class="flex flex-col items-center gap-1.5 text-slate-300">
                <i data-lucide="bar-chart-3" class="w-6 h-6"></i>
                <span class="text-[8px] font-black uppercase tracking-widest">Analyses</span>
            </button>
            <button class="flex flex-col items-center gap-1.5 text-slate-300">
                <i data-lucide="users" class="w-6 h-6"></i>
                <span class="text-[8px] font-black uppercase tracking-widest">Équipe</span>
            </button>
            <button class="flex flex-col items-center gap-1.5 text-slate-300">
                <i data-lucide="settings" class="w-6 h-6"></i>
                <span class="text-[8px] font-black uppercase tracking-widest">Profil</span>
            </button>
        </nav>
    </div>

    <script>
        // Initialisation des icônes
        lucide.createIcons();

        // Gestion de l'écran de démarrage
        window.addEventListener('load', () => {
            setTimeout(() => {
                const splash = document.getElementById('splash');
                const appContent = document.getElementById('app-content');
                
                splash.style.opacity = '0';
                appContent.classList.remove('opacity-0');
                
                setTimeout(() => {
                    splash.style.visibility = 'hidden';
                }, 600);
            }, 1800);
        });

        // Vibration au clic pour effet "App" sur Android/iPhone compatibles
        document.querySelectorAll('button').forEach(btn => {
            btn.addEventListener('click', () => {
                if (window.navigator.vibrate) window.navigator.vibrate(10);
            });
        });
    </script>
</body>
</html>

