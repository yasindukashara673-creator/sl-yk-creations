# sl-yk-creations[index.html](https://github.com/user-attachments/files/34380425/index.html)
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SL YK Creations - Official Portfolio & Tech Hub</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brand: {
                            red: '#FF0033',
                            cyan: '#00F0FF',
                            purple: '#7000FF',
                            dark: '#0A0A10',
                            card: '#12121E',
                            border: '#1F1F35'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    animation: {
                        'pulse-glow': 'pulseGlow 3s infinite alternate',
                        'float': 'float 4s ease-in-out infinite',
                    },
                    keyframes: {
                        pulseGlow: {
                            '0%': { boxShadow: '0 0 15px rgba(0, 240, 255, 0.2)' },
                            '100%': { boxShadow: '0 0 35px rgba(0, 240, 255, 0.6), 0 0 15px rgba(255, 0, 51, 0.4)' },
                        },
                        float: {
                            '0%, 100%': { transform: 'translateY(0px)' },
                            '50%': { transform: 'translateY(-10px)' },
                        }
                    }
                }
            }
        }
    </script>
    <!-- Google Fonts & FontAwesome -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0A0A10;
            color: #E2E8F0;
            overflow-x: hidden;
        }

        /* Glassmorphism Styles */
        .glass-panel {
            background: rgba(18, 18, 30, 0.75);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }

        .glass-card {
            background: rgba(22, 22, 38, 0.6);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .glass-card:hover {
            border-color: rgba(0, 240, 255, 0.4);
            transform: translateY(-4px);
            box-shadow: 0 12px 30px -10px rgba(0, 240, 255, 0.15);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0A0A10;
        }
        ::-webkit-scrollbar-thumb {
            background: #1F1F35;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #00F0FF;
        }

        /* Canvas Particle Background */
        #bgCanvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
        }

        /* Tech Glow Effect */
        .neon-text-cyan {
            text-shadow: 0 0 10px rgba(0, 240, 255, 0.5), 0 0 20px rgba(0, 240, 255, 0.3);
        }
        .neon-text-red {
            text-shadow: 0 0 10px rgba(255, 0, 51, 0.6), 0 0 20px rgba(255, 0, 51, 0.3);
        }
    </style>
</head>
<body class="relative">

    <!-- Interactive Particle Background Canvas -->
    <canvas id="bgCanvas"></canvas>

    <div class="relative z-10 flex flex-col min-h-screen">
        
        <!-- ================= NAVBAR ================= -->
        <nav class="sticky top-0 z-50 glass-panel border-b border-gray-800/50">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex items-center justify-between h-20">
                    
                    <!-- Logo -->
                    <div class="flex items-center gap-3">
                        <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-brand-red via-brand-purple to-brand-cyan flex items-center justify-center font-bold text-white text-xl shadow-lg">
                            YK
                        </div>
                        <a href="#" class="font-extrabold text-xl tracking-wider text-white">
                            SL YK <span class="text-brand-cyan font-normal">CREATIONS</span>
                        </a>
                    </div>

                    <!-- Desktop Nav Links -->
                    <div class="hidden md:flex items-center space-x-8 text-sm font-medium">
                        <a href="#hero" class="hover:text-brand-cyan transition-colors">Home</a>
                        <a href="#content" class="hover:text-brand-cyan transition-colors">Videos & Projects</a>
                        <a href="#tech-widget" class="hover:text-brand-cyan transition-colors">Arduino / Tech Lab</a>
                        <a href="#about" class="hover:text-brand-cyan transition-colors">About Us</a>
                        <a href="#contact" class="hover:text-brand-cyan transition-colors">Contact</a>
                    </div>

                    <!-- YouTube Subscribe Action Button -->
                    <div class="hidden md:flex items-center">
                        <a href="https://www.youtube.com/channel/UCYtP5jod_AcezSizX4p-Mqg?sub_confirmation=1" 
                           target="_blank" rel="noopener noreferrer" 
                           class="px-5 py-2.5 rounded-full font-semibold text-sm bg-brand-red hover:bg-red-600 text-white flex items-center gap-2 shadow-lg shadow-red-900/40 hover:scale-105 transition-all">
                            <i class="fa-brands fa-youtube text-lg"></i> Subscribe
                        </a>
                    </div>

                    <!-- Mobile Hamburger Button -->
                    <div class="md:hidden flex items-center">
                        <button id="mobile-menu-btn" class="text-gray-300 hover:text-white focus:outline-none p-2">
                            <i class="fa-solid fa-bars text-2xl"></i>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Mobile Menu Dropdown -->
            <div id="mobile-menu" class="hidden md:hidden glass-panel border-t border-gray-800 px-4 pt-2 pb-6 space-y-3">
                <a href="#hero" class="block text-gray-300 hover:text-brand-cyan py-2">Home</a>
                <a href="#content" class="block text-gray-300 hover:text-brand-cyan py-2">Videos & Projects</a>
                <a href="#tech-widget" class="block text-gray-300 hover:text-brand-cyan py-2">Arduino / Tech Lab</a>
                <a href="#about" class="block text-gray-300 hover:text-brand-cyan py-2">About Us</a>
                <a href="#contact" class="block text-gray-300 hover:text-brand-cyan py-2">Contact</a>
                <a href="https://www.youtube.com/channel/UCYtP5jod_AcezSizX4p-Mqg?sub_confirmation=1" 
                   target="_blank" 
                   class="w-full mt-3 px-4 py-3 rounded-xl font-bold bg-brand-red text-white flex items-center justify-center gap-2">
                    <i class="fa-brands fa-youtube"></i> Subscribe on YouTube
                </a>
            </div>
        </nav>

        <!-- ================= HERO SECTION ================= -->
        <section id="hero" class="relative pt-12 pb-20 md:pt-24 md:pb-32 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto flex flex-col items-center text-center">
            
            <!-- Badge -->
            <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full glass-panel border-brand-cyan/30 text-brand-cyan text-xs font-semibold tracking-wider uppercase mb-8">
                <span class="w-2 h-2 rounded-full bg-brand-cyan animate-ping"></span>
                Official Channel Showcase
            </div>

            <!-- Main Heading -->
            <h1 class="text-4xl sm:text-6xl lg:text-7xl font-extrabold text-white tracking-tight leading-tight max-w-4xl">
                Creative Tech, DIY Innovations & <span class="text-transparent bg-clip-text bg-gradient-to-r from-brand-cyan via-purple-400 to-brand-red">Entertainment Hub</span>
            </h1>

            <p class="mt-6 text-lg sm:text-xl text-gray-400 max-w-2xl leading-relaxed">
                Welcome to <strong class="text-white">SL YK creations</strong>! Exploring Arduino robotics, tech tutorials, music, short films, and gaming experiences. Join our community today.
            </p>

            <!-- Buttons -->
            <div class="mt-10 flex flex-col sm:flex-row gap-4 w-full sm:w-auto">
                <a href="https://www.youtube.com/channel/UCYtP5jod_AcezSizX4p-Mqg?sub_confirmation=1" target="_blank" 
                   class="px-8 py-4 rounded-xl font-bold bg-gradient-to-r from-brand-red to-red-600 text-white flex items-center justify-center gap-3 shadow-xl shadow-red-900/30 hover:scale-105 transition-transform">
                    <i class="fa-brands fa-youtube text-xl"></i> Join Channel Community
                </a>
                <a href="#content" class="px-8 py-4 rounded-xl font-bold glass-panel text-white hover:bg-white/10 flex items-center justify-center gap-2 transition-all">
                    Explore Content <i class="fa-solid fa-arrow-down text-sm"></i>
                </a>
            </div>

            <!-- YouTube Channel Stats Bar -->
            <div class="mt-16 grid grid-cols-2 md:grid-cols-4 gap-4 sm:gap-6 w-full max-w-4xl">
                <div class="glass-card p-4 sm:p-6 rounded-2xl">
                    <div class="text-3xl font-extrabold text-brand-cyan neon-text-cyan">Tech & DIY</div>
                    <div class="text-xs text-gray-400 mt-1 uppercase tracking-wider">Arduino & Code</div>
                </div>
                <div class="glass-card p-4 sm:p-6 rounded-2xl">
                    <div class="text-3xl font-extrabold text-brand-red neon-text-red">Short Films</div>
                    <div class="text-xs text-gray-400 mt-1 uppercase tracking-wider">Creative Dramas</div>
                </div>
                <div class="glass-card p-4 sm:p-6 rounded-2xl">
                    <div class="text-3xl font-extrabold text-purple-400">Music & Raps</div>
                    <div class="text-xs text-gray-400 mt-1 uppercase tracking-wider">Original Audio</div>
                </div>
                <div class="glass-card p-4 sm:p-6 rounded-2xl">
                    <div class="text-3xl font-extrabold text-emerald-400">Gaming</div>
                    <div class="text-xs text-gray-400 mt-1 uppercase tracking-wider">Live & Highlights</div>
                </div>
            </div>
        </section>

        <!-- ================= CONTENT SHOWCASE SECTION ================= -->
        <section id="content" class="py-16 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto w-full">
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-10">
                <div>
                    <h2 class="text-3xl sm:text-4xl font-bold text-white">Featured Content & Projects</h2>
                    <p class="text-gray-400 mt-2">Filter through YouTube videos and creations by category.</p>
                </div>

                <!-- Category Filter Buttons -->
                <div class="flex flex-wrap gap-2 mt-6 md:mt-0" id="filter-buttons">
                    <button data-filter="all" class="filter-btn active px-4 py-2 rounded-lg text-sm font-semibold bg-brand-cyan text-gray-900 transition-all">All</button>
                    <button data-filter="tech" class="filter-btn px-4 py-2 rounded-lg text-sm font-semibold glass-panel text-gray-300 hover:text-white transition-all">Tech & Arduino</button>
                    <button data-filter="entertainment" class="filter-btn px-4 py-2 rounded-lg text-sm font-semibold glass-panel text-gray-300 hover:text-white transition-all">Films & Shorts</button>
                    <button data-filter="music" class="filter-btn px-4 py-2 rounded-lg text-sm font-semibold glass-panel text-gray-300 hover:text-white transition-all">Music & Raps</button>
                    <button data-filter="gaming" class="filter-btn px-4 py-2 rounded-lg text-sm font-semibold glass-panel text-gray-300 hover:text-white transition-all">Gaming</button>
                </div>
            </div>

            <!-- Content Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6" id="projects-grid">
                
                <!-- Project 1 (Tech) -->
                <div class="project-card glass-card rounded-2xl overflow-hidden group" data-category="tech">
                    <div class="relative overflow-hidden aspect-video bg-gray-900">
                        <img src="https://placehold.co/600x400/12121E/00F0FF?text=Smart+Arduino+Project" alt="Arduino Project" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-black/50 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center gap-3">
                            <button onclick="openModal('Smart Bluetooth RC Car & Sensor Suite', 'Detailed walkthrough on building a micro-controller powered vehicle using Arduino UNO, L298N Motor Driver, and Bluetooth Module with Android Control App.', 'https://www.youtube.com/embed/dQw4w9WgXcQ')" class="p-3 bg-brand-cyan text-gray-900 rounded-full font-bold shadow-lg hover:scale-110 transition-transform">
                                <i class="fa-solid fa-play"></i>
                            </button>
                        </div>
                        <span class="absolute top-3 left-3 bg-brand-cyan/90 text-gray-900 text-xs font-bold px-2.5 py-1 rounded-md">Tech & Electronics</span>
                    </div>
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white group-hover:text-brand-cyan transition-colors">Arduino IoT Home Automation & Robotics</h3>
                        <p class="text-sm text-gray-400 mt-2 line-clamp-2">Complete step-by-step tutorial on programming microcontrollers, wiring sensors, and building smart hardware devices.</p>
                        <div class="mt-4 flex items-center justify-between text-xs text-gray-500 font-medium">
                            <span><i class="fa-regular fa-clock"></i> 12 mins</span>
                            <span class="text-brand-cyan">SL YK Tech Lab</span>
                        </div>
                    </div>
                </div>

                <!-- Project 2 (Entertainment) -->
                <div class="project-card glass-card rounded-2xl overflow-hidden group" data-category="entertainment">
                    <div class="relative overflow-hidden aspect-video bg-gray-900">
                        <img src="https://placehold.co/600x400/12121E/FF0033?text=Short+Film+Special" alt="Short Film" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-black/50 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center gap-3">
                            <button onclick="openModal('Original Short Film - Life & Choices', 'An engaging Sinhala short movie created by SL YK creations exploring relatable everyday life drama and humor.', 'https://www.youtube.com/embed/dQw4w9WgXcQ')" class="p-3 bg-brand-red text-white rounded-full font-bold shadow-lg hover:scale-110 transition-transform">
                                <i class="fa-solid fa-play"></i>
                            </button>
                        </div>
                        <span class="absolute top-3 left-3 bg-brand-red text-white text-xs font-bold px-2.5 py-1 rounded-md">Short Film</span>
                    </div>
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white group-hover:text-brand-red transition-colors">Creative Comedy Short Drama</h3>
                        <p class="text-sm text-gray-400 mt-2 line-clamp-2">An entertaining short video showcasing storytelling, directing, and creative Sinhala video production.</p>
                        <div class="mt-4 flex items-center justify-between text-xs text-gray-500 font-medium">
                            <span><i class="fa-regular fa-clock"></i> 8 mins</span>
                            <span class="text-brand-red">Entertainment</span>
                        </div>
                    </div>
                </div>

                <!-- Project 3 (Music) -->
                <div class="project-card glass-card rounded-2xl overflow-hidden group" data-category="music">
                    <div class="relative overflow-hidden aspect-video bg-gray-900">
                        <img src="https://placehold.co/600x400/12121E/7000FF?text=Original+Rap+Track" alt="Music Rap Track" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-black/50 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center gap-3">
                            <button onclick="openModal('SL YK Original Rap Track', 'Feel the rhythm! Original music production, lyrics, and rap beats produced directly by the SL YK crew.', 'https://www.youtube.com/embed/dQw4w9WgXcQ')" class="p-3 bg-purple-600 text-white rounded-full font-bold shadow-lg hover:scale-110 transition-transform">
                                <i class="fa-solid fa-play"></i>
                            </button>
                        </div>
                        <span class="absolute top-3 left-3 bg-purple-600 text-white text-xs font-bold px-2.5 py-1 rounded-md">Music & Rap</span>
                    </div>
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white group-hover:text-purple-400 transition-colors">Original Beats & Sinhala Rap Track</h3>
                        <p class="text-sm text-gray-400 mt-2 line-clamp-2">Expressive original audio beat production and rap performance brought to you by SL YK creations.</p>
                        <div class="mt-4 flex items-center justify-between text-xs text-gray-500 font-medium">
                            <span><i class="fa-regular fa-clock"></i> 4 mins</span>
                            <span class="text-purple-400">SL YK Audio Studio</span>
                        </div>
                    </div>
                </div>

                <!-- Project 4 (Gaming) -->
                <div class="project-card glass-card rounded-2xl overflow-hidden group" data-category="gaming">
                    <div class="relative overflow-hidden aspect-video bg-gray-900">
                        <img src="https://placehold.co/600x400/12121E/10B981?text=Gaming+Highlights" alt="Gaming Video" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-black/50 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center gap-3">
                            <button onclick="openModal('Pro Gaming Highlights & Montage', 'Epic gaming moments, funny gameplay edits, and high-energy gameplay streams from our channel.', 'https://www.youtube.com/embed/dQw4w9WgXcQ')" class="p-3 bg-emerald-500 text-gray-900 rounded-full font-bold shadow-lg hover:scale-110 transition-transform">
                                <i class="fa-solid fa-play"></i>
                            </button>
                        </div>
                        <span class="absolute top-3 left-3 bg-emerald-500 text-gray-900 text-xs font-bold px-2.5 py-1 rounded-md">Gaming</span>
                    </div>
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white group-hover:text-emerald-400 transition-colors">Action Gameplay & Live Highlights</h3>
                        <p class="text-sm text-gray-400 mt-2 line-clamp-2">Best clutches, funniest moments, and walkthrough commentary on modern multiplayer games.</p>
                        <div class="mt-4 flex items-center justify-between text-xs text-gray-500 font-medium">
                            <span><i class="fa-regular fa-clock"></i> 15 mins</span>
                            <span class="text-emerald-400">Gaming Realm</span>
                        </div>
                    </div>
                </div>

                <!-- Project 5 (Tech) -->
                <div class="project-card glass-card rounded-2xl overflow-hidden group" data-category="tech">
                    <div class="relative overflow-hidden aspect-video bg-gray-900">
                        <img src="https://placehold.co/600x400/12121E/00F0FF?text=DIY+Electronics+Guide" alt="DIY Electronics" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-black/50 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center gap-3">
                            <button onclick="openModal('DIY Electronics Solder & Repair', 'Learn how to solder electronic components safely and construct custom power supplies.', 'https://www.youtube.com/embed/dQw4w9WgXcQ')" class="p-3 bg-brand-cyan text-gray-900 rounded-full font-bold shadow-lg hover:scale-110 transition-transform">
                                <i class="fa-solid fa-play"></i>
                            </button>
                        </div>
                        <span class="absolute top-3 left-3 bg-brand-cyan/90 text-gray-900 text-xs font-bold px-2.5 py-1 rounded-md">Tech & Electronics</span>
                    </div>
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white group-hover:text-brand-cyan transition-colors">Basic Electronics & Soldering Guide</h3>
                        <p class="text-sm text-gray-400 mt-2 line-clamp-2">Essential electronic concepts explained for beginners starting out with circuit design.</p>
                        <div class="mt-4 flex items-center justify-between text-xs text-gray-500 font-medium">
                            <span><i class="fa-regular fa-clock"></i> 10 mins</span>
                            <span class="text-brand-cyan">Tech Tutorials</span>
                        </div>
                    </div>
                </div>

                <!-- Project 6 (Entertainment) -->
                <div class="project-card glass-card rounded-2xl overflow-hidden group" data-category="entertainment">
                    <div class="relative overflow-hidden aspect-video bg-gray-900">
                        <img src="https://placehold.co/600x400/12121E/FF0033?text=Funny+Vlog+%26+Behind+The+Scenes" alt="Vlog" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-black/50 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center gap-3">
                            <button onclick="openModal('Behind The Scenes Fun & Vlogs', 'Join us behind the camera to see how we film our videos and have fun during shooting days!', 'https://www.youtube.com/embed/dQw4w9WgXcQ')" class="p-3 bg-brand-red text-white rounded-full font-bold shadow-lg hover:scale-110 transition-transform">
                                <i class="fa-solid fa-play"></i>
                            </button>
                        </div>
                        <span class="absolute top-3 left-3 bg-brand-red text-white text-xs font-bold px-2.5 py-1 rounded-md">Vlog / BTS</span>
                    </div>
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white group-hover:text-brand-red transition-colors">Behind The Scenes & Funny Moments</h3>
                        <p class="text-sm text-gray-400 mt-2 line-clamp-2">Exclusive bloopers, shoot setups, and daily vlogs featuring the SL YK team.</p>
                        <div class="mt-4 flex items-center justify-between text-xs text-gray-500 font-medium">
                            <span><i class="fa-regular fa-clock"></i> 6 mins</span>
                            <span class="text-brand-red">Life & Vlogs</span>
                        </div>
                    </div>
                </div>

            </div>
        </section>

        <!-- ================= INTERACTIVE ARDUINO / TECH LAB WIDGET ================= -->
        <section id="tech-widget" class="py-16 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto w-full">
            <div class="glass-panel rounded-3xl p-6 sm:p-10 relative overflow-hidden border border-brand-cyan/20">
                <div class="absolute top-0 right-0 w-96 h-96 bg-brand-cyan/10 rounded-full filter blur-3xl pointer-events-none"></div>

                <div class="flex flex-col lg:flex-row gap-10 items-center">
                    
                    <!-- Left Column: Interactive Simulation -->
                    <div class="w-full lg:w-1/2 space-y-6">
                        <div>
                            <span class="text-xs font-bold uppercase tracking-wider text-brand-cyan bg-brand-cyan/10 px-3 py-1 rounded-full">Interactive Hardware Demo</span>
                            <h2 class="text-3xl font-extrabold text-white mt-3">Virtual Arduino LED & Relay Controller</h2>
                            <p class="text-gray-400 text-sm mt-2">Try out a real-time simulation of hardware logic toggling similar to the projects featured on SL YK creations!</p>
                        </div>

                        <!-- Circuit Interactive Controls -->
                        <div class="glass-card p-6 rounded-2xl border border-gray-800 space-y-4">
                            <div class="flex items-center justify-between border-b border-gray-800 pb-3">
                                <div class="flex items-center gap-3">
                                    <div id="led-indicator" class="w-5 h-5 rounded-full bg-gray-700 shadow-none transition-all duration-300"></div>
                                    <span class="text-sm font-semibold text-gray-200">System LED Output (Pin 13)</span>
                                </div>
                                <button id="led-toggle-btn" class="px-4 py-1.5 rounded-lg text-xs font-bold bg-brand-cyan text-gray-900 hover:bg-cyan-300 transition-all">
                                    Toggle State
                                </button>
                            </div>

                            <div class="flex items-center justify-between border-b border-gray-800 pb-3">
                                <div class="flex items-center gap-3">
                                    <div id="fan-indicator" class="w-5 h-5 rounded-full bg-gray-700 shadow-none transition-all duration-300"></div>
                                    <span class="text-sm font-semibold text-gray-200">Relay Module Power (Pin 8)</span>
                                </div>
                                <button id="fan-toggle-btn" class="px-4 py-1.5 rounded-lg text-xs font-bold bg-purple-600 text-white hover:bg-purple-500 transition-all">
                                    Toggle Relay
                                </button>
                            </div>

                            <div class="pt-2">
                                <label class="text-xs text-gray-400 font-semibold block mb-2">Simulated PWM Signal Intensity</label>
                                <input type="range" id="pwm-slider" min="0" max="255" value="128" class="w-full accent-brand-cyan bg-gray-800 rounded-lg cursor-pointer">
                                <div class="flex justify-between text-xs text-gray-500 mt-1">
                                    <span>0 (OFF)</span>
                                    <span id="pwm-val" class="text-brand-cyan font-bold">PWM: 128</span>
                                    <span>255 (MAX)</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Right Column: Interactive Code Editor View -->
                    <div class="w-full lg:w-1/2">
                        <div class="glass-panel rounded-2xl overflow-hidden border border-gray-800">
                            <!-- Code Header -->
                            <div class="bg-gray-900/80 px-4 py-3 border-b border-gray-800 flex items-center justify-between">
                                <div class="flex items-center gap-2">
                                    <span class="w-3 h-3 rounded-full bg-red-500"></span>
                                    <span class="w-3 h-3 rounded-full bg-yellow-500"></span>
                                    <span class="w-3 h-3 rounded-full bg-green-500"></span>
                                    <span class="text-xs text-gray-400 font-mono ml-2">sl_yk_arduino_demo.ino</span>
                                </div>
                                <button onclick="copyDemoCode()" class="text-xs text-brand-cyan hover:underline flex items-center gap-1">
                                    <i class="fa-regular fa-copy"></i> Copy Code
                                </button>
                            </div>
                            <!-- Code Content -->
                            <pre class="p-4 text-xs font-mono text-gray-300 overflow-x-auto leading-relaxed bg-black/40">
<span class="text-purple-400">#define</span> LED_PIN 13
<span class="text-purple-400">#define</span> RELAY_PIN 8

<span class="text-blue-400">void</span> <span class="text-yellow-400">setup</span>() {
  <span class="text-blue-400">pinMode</span>(LED_PIN, <span class="text-red-400">OUTPUT</span>);
  <span class="text-blue-400">pinMode</span>(RELAY_PIN, <span class="text-red-400">OUTPUT</span>);
  <span class="text-gray-500">// SL YK Creations Custom Hardware Init</span>
  <span class="text-blue-400">Serial</span>.<span class="text-yellow-400">begin</span>(9600);
}

<span class="text-blue-400">void</span> <span class="text-yellow-400">loop</span>() {
  <span class="text-gray-500">// Simulated micro-controller execution</span>
  <span class="text-blue-400">digitalWrite</span>(LED_PIN, <span class="text-brand-cyan font-bold" id="code-led-state">HIGH</span>);
  <span class="text-blue-400">digitalWrite</span>(RELAY_PIN, <span class="text-purple-400 font-bold" id="code-relay-state">LOW</span>);
  <span class="text-blue-400">delay</span>(<span class="text-green-400">1000</span>);
}</pre>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <!-- ================= ABOUT & CREW SECTION ================= -->
        <section id="about" class="py-16 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto w-full">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                
                <!-- Text Content -->
                <div class="space-y-6">
                    <span class="text-xs font-bold uppercase tracking-wider text-brand-red bg-brand-red/10 px-3 py-1 rounded-full">About The Channel</span>
                    <h2 class="text-3xl sm:text-4xl font-extrabold text-white">Behind SL YK Creations</h2>
                    <p class="text-gray-300 leading-relaxed">
                        <strong class="text-white">SL YK creations</strong> is a passionate Sri Lankan YouTube content creation channel dedicated to delivering innovative, educational, and fun content. 
                    </p>
                    <p class="text-gray-400 text-sm leading-relaxed">
                        From designing DIY Arduino electronics to producing engaging short films, original rap tracks, and high-energy gaming highlights—our goal is to inspire creators, tech enthusiasts, and viewers worldwide.
                    </p>

                    <!-- Features List -->
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-2">
                        <div class="flex items-start gap-3">
                            <div class="w-8 h-8 rounded-lg bg-brand-cyan/20 text-brand-cyan flex items-center justify-center shrink-0 mt-1">
                                <i class="fa-solid fa-microchip"></i>
                            </div>
                            <div>
                                <h4 class="text-white font-semibold text-sm">Tech & Electronics</h4>
                                <p class="text-xs text-gray-400">Practical micro-controller projects & tutorials.</p>
                            </div>
                        </div>

                        <div class="flex items-start gap-3">
                            <div class="w-8 h-8 rounded-lg bg-brand-red/20 text-brand-red flex items-center justify-center shrink-0 mt-1">
                                <i class="fa-solid fa-film"></i>
                            </div>
                            <div>
                                <h4 class="text-white font-semibold text-sm">Short Films & Drama</h4>
                                <p class="text-xs text-gray-400">Creative cinema & comedy scripts.</p>
                            </div>
                        </div>

                        <div class="flex items-start gap-3">
                            <div class="w-8 h-8 rounded-lg bg-purple-500/20 text-purple-400 flex items-center justify-center shrink-0 mt-1">
                                <i class="fa-solid fa-music"></i>
                            </div>
                            <div>
                                <h4 class="text-white font-semibold text-sm">Music & Beat Production</h4>
                                <p class="text-xs text-gray-400">Original tracks and music videos.</p>
                            </div>
                        </div>

                        <div class="flex items-start gap-3">
                            <div class="w-8 h-8 rounded-lg bg-emerald-500/20 text-emerald-400 flex items-center justify-center shrink-0 mt-1">
                                <i class="fa-solid fa-gamepad"></i>
                            </div>
                            <div>
                                <h4 class="text-white font-semibold text-sm">Gaming Hub</h4>
                                <p class="text-xs text-gray-400">Interactive streaming and clips.</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Visual Element / Channel Card Banner -->
                <div class="glass-panel p-6 sm:p-8 rounded-3xl border border-gray-800 text-center relative overflow-hidden">
                    <div class="w-24 h-24 rounded-2xl bg-gradient-to-tr from-brand-red via-brand-purple to-brand-cyan mx-auto flex items-center justify-center text-4xl font-black text-white shadow-2xl mb-6">
                        YK
                    </div>
                    <h3 class="text-2xl font-bold text-white">SL YK creations</h3>
                    <p class="text-sm text-brand-cyan font-medium mt-1">YouTube Channel ID: UCYtP5jod_AcezSizX4p-Mqg</p>
                    
                    <div class="mt-6 pt-6 border-t border-gray-800/80 flex justify-center gap-6">
                        <a href="https://www.youtube.com/channel/UCYtP5jod_AcezSizX4p-Mqg" target="_blank" class="w-10 h-10 rounded-full glass-card flex items-center justify-center text-gray-300 hover:text-brand-red hover:border-brand-red transition-colors">
                            <i class="fa-brands fa-youtube text-lg"></i>
                        </a>
                        <a href="#" class="w-10 h-10 rounded-full glass-card flex items-center justify-center text-gray-300 hover:text-blue-500 hover:border-blue-500 transition-colors">
                            <i class="fa-brands fa-facebook-f text-lg"></i>
                        </a>
                        <a href="#" class="w-10 h-10 rounded-full glass-card flex items-center justify-center text-gray-300 hover:text-pink-500 hover:border-pink-500 transition-colors">
                            <i class="fa-brands fa-instagram text-lg"></i>
                        </a>
                    </div>
                </div>

            </div>
        </section>

        <!-- ================= CONTACT SECTION ================= -->
        <section id="contact" class="py-16 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto w-full">
            <div class="max-w-3xl mx-auto glass-panel p-8 sm:p-10 rounded-3xl border border-gray-800">
                <div class="text-center mb-8">
                    <span class="text-xs font-bold uppercase tracking-wider text-brand-cyan bg-brand-cyan/10 px-3 py-1 rounded-full">Get In Touch</span>
                    <h2 class="text-3xl font-extrabold text-white mt-2">Connect With SL YK Creations</h2>
                    <p class="text-gray-400 text-sm mt-1">Have a project idea, business inquiry, or hardware question? Send us a message!</p>
                </div>

                <form id="contact-form" onsubmit="handleFormSubmit(event)" class="space-y-6">
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                        <div>
                            <label class="block text-xs font-medium text-gray-300 mb-2">Your Name</label>
                            <input type="text" required placeholder="John Doe" class="w-full px-4 py-3 rounded-xl glass-card text-white placeholder-gray-500 focus:outline-none focus:border-brand-cyan transition-colors">
                        </div>
                        <div>
                            <label class="block text-xs font-medium text-gray-300 mb-2">Your Email</label>
                            <input type="email" required placeholder="john@example.com" class="w-full px-4 py-3 rounded-xl glass-card text-white placeholder-gray-500 focus:outline-none focus:border-brand-cyan transition-colors">
                        </div>
                    </div>

                    <div>
                        <label class="block text-xs font-medium text-gray-300 mb-2">Subject</label>
                        <input type="text" required placeholder="Video Collaboration / Electronics Project" class="w-full px-4 py-3 rounded-xl glass-card text-white placeholder-gray-500 focus:outline-none focus:border-brand-cyan transition-colors">
                    </div>

                    <div>
                        <label class="block text-xs font-medium text-gray-300 mb-2">Message</label>
                        <textarea rows="4" required placeholder="Write your message here..." class="w-full px-4 py-3 rounded-xl glass-card text-white placeholder-gray-500 focus:outline-none focus:border-brand-cyan transition-colors"></textarea>
                    </div>

                    <button type="submit" class="w-full py-4 rounded-xl font-bold bg-brand-cyan text-gray-900 hover:bg-cyan-300 shadow-lg shadow-cyan-900/30 transition-all flex items-center justify-center gap-2">
                        <i class="fa-solid fa-paper-plane"></i> Send Message
                    </button>
                </form>

                <div id="form-message" class="hidden mt-4 p-4 rounded-xl text-center text-sm font-semibold"></div>
            </div>
        </section>

        <!-- ================= FOOTER ================= -->
        <footer class="mt-auto border-t border-gray-800/80 glass-panel py-8">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col sm:flex-row items-center justify-between gap-4">
                <div class="flex items-center gap-2 text-sm text-gray-400">
                    <div class="w-6 h-6 rounded-md bg-brand-cyan text-gray-900 flex items-center justify-center font-bold text-xs">YK</div>
                    <span>© <span id="year"></span> <strong>SL YK creations</strong>. All rights reserved.</span>
                </div>
                
                <div class="flex gap-6 text-sm text-gray-400">
                    <a href="https://www.youtube.com/channel/UCYtP5jod_AcezSizX4p-Mqg" target="_blank" class="hover:text-brand-red transition-colors">YouTube</a>
                    <a href="#tech-widget" class="hover:text-brand-cyan transition-colors">Arduino Lab</a>
                    <a href="#content" class="hover:text-brand-cyan transition-colors">Projects</a>
                </div>
            </div>
        </footer>

    </div>

    <!-- ================= VIDEO MODAL ================= -->
    <div id="video-modal" class="fixed inset-0 z-50 hidden bg-black/80 backdrop-blur-md flex items-center justify-center p-4">
        <div class="glass-panel border border-gray-700 w-full max-w-3xl rounded-3xl overflow-hidden shadow-2xl relative">
            <button onclick="closeModal()" class="absolute top-4 right-4 w-9 h-9 rounded-full bg-gray-800 hover:bg-red-600 text-white flex items-center justify-center z-10 transition-colors">
                <i class="fa-solid fa-xmark text-lg"></i>
            </button>
            
            <div class="aspect-video w-full bg-black">
                <iframe id="modal-iframe" class="w-full h-full" src="" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>

            <div class="p-6">
                <h3 id="modal-title" class="text-xl font-bold text-white"></h3>
                <p id="modal-description" class="text-sm text-gray-400 mt-2"></p>
                
                <div class="mt-6 flex justify-end">
                    <a href="https://www.youtube.com/channel/UCYtP5jod_AcezSizX4p-Mqg?sub_confirmation=1" target="_blank" class="px-5 py-2.5 rounded-xl text-sm font-bold bg-brand-red text-white hover:bg-red-600 flex items-center gap-2">
                        <i class="fa-brands fa-youtube"></i> Visit Channel
                    </a>
                </div>
            </div>
        </div>
    </div>

    <!-- ================= JAVASCRIPT LOGIC ================= -->
    <script>
        // Set dynamic current year
        document.getElementById('year').textContent = new Date().getFullYear();

        // Canvas Particles Animation Setup
        const canvas = document.getElementById('bgCanvas');
        const ctx = canvas.getContext('2d');
        let particles = [];

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2 + 0.5;
                this.speedX = (Math.random() - 0.5) * 0.5;
                this.speedY = (Math.random() - 0.5) * 0.5;
                this.color = Math.random() > 0.5 ? '#00F0FF' : '#7000FF';
                this.alpha = Math.random() * 0.5 + 0.2;
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;

                if (this.x < 0) this.x = canvas.width;
                if (this.x > canvas.width) this.x = 0;
                if (this.y < 0) this.y = canvas.height;
                if (this.y > canvas.height) this.y = 0;
            }
            draw() {
                ctx.save();
                ctx.globalAlpha = this.alpha;
                ctx.fillStyle = this.color;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        function initParticles() {
            particles = [];
            const count = Math.min(Math.floor(window.innerWidth / 15), 80);
            for (let i = 0; i < count; i++) {
                particles.push(new Particle());
            }
        }
        initParticles();

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => {
                p.update();
                p.draw();
            });
            requestAnimationFrame(animateParticles);
        }
        animateParticles();

        // Mobile Navigation Toggle
        const mobileMenuBtn = document.getElementById('mobile-menu-btn');
        const mobileMenu = document.getElementById('mobile-menu');

        mobileMenuBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        // Category Filtering Logic
        const filterButtons = document.querySelectorAll('.filter-btn');
        const projectCards = document.querySelectorAll('.project-card');

        filterButtons.forEach(btn => {
            btn.addEventListener('click', () => {
                filterButtons.forEach(b => {
                    b.classList.remove('bg-brand-cyan', 'text-gray-900');
                    b.classList.add('glass-panel', 'text-gray-300');
                });
                btn.classList.remove('glass-panel', 'text-gray-300');
                btn.classList.add('bg-brand-cyan', 'text-gray-900');

                const filter = btn.getAttribute('data-filter');
                projectCards.forEach(card => {
                    if (filter === 'all' || card.getAttribute('data-category') === filter) {
                        card.style.display = 'block';
                    } else {
                        card.style.display = 'none';
                    }
                });
            });
        });

        // Interactive Hardware Demo Controls
        let ledState = false;
        let relayState = false;

        const ledBtn = document.getElementById('led-toggle-btn');
        const ledInd = document.getElementById('led-indicator');
        const codeLedState = document.getElementById('code-led-state');

        const fanBtn = document.getElementById('fan-toggle-btn');
        const fanInd = document.getElementById('fan-indicator');
        const codeRelayState = document.getElementById('code-relay-state');

        const pwmSlider = document.getElementById('pwm-slider');
        const pwmVal = document.getElementById('pwm-val');

        ledBtn.addEventListener('click', () => {
            ledState = !ledState;
            if (ledState) {
                ledInd.classList.remove('bg-gray-700');
                ledInd.classList.add('bg-brand-cyan', 'shadow-[0_0_15px_#00F0FF]');
                codeLedState.textContent = 'HIGH';
            } else {
                ledInd.classList.remove('bg-brand-cyan', 'shadow-[0_0_15px_#00F0FF]');
                ledInd.classList.add('bg-gray-700');
                codeLedState.textContent = 'LOW';
            }
        });

        fanBtn.addEventListener('click', () => {
            relayState = !relayState;
            if (relayState) {
                fanInd.classList.remove('bg-gray-700');
                fanInd.classList.add('bg-purple-500', 'shadow-[0_0_15px_#7000FF]');
                codeRelayState.textContent = 'HIGH';
            } else {
                fanInd.classList.remove('bg-purple-500', 'shadow-[0_0_15px_#7000FF]');
                fanInd.classList.add('bg-gray-700');
                codeRelayState.textContent = 'LOW';
            }
        });

        pwmSlider.addEventListener('input', (e) => {
            pwmVal.textContent = `PWM: ${e.target.value}`;
        });

        function copyDemoCode() {
            const code = `#define LED_PIN 13\n#define RELAY_PIN 8\n\nvoid setup() {\n  pinMode(LED_PIN, OUTPUT);\n  pinMode(RELAY_PIN, OUTPUT);\n  Serial.begin(9600);\n}\n\nvoid loop() {\n  digitalWrite(LED_PIN, HIGH);\n  digitalWrite(RELAY_PIN, LOW);\n  delay(1000);\n}`;
            navigator.clipboard.writeText(code).then(() => {
                alert('Arduino demo code copied to clipboard!');
            }).catch(() => {
                document.execCommand('copy');
            });
        }

        // Modal Functionality
        const modal = document.getElementById('video-modal');
        const modalTitle = document.getElementById('modal-title');
        const modalDescription = document.getElementById('modal-description');
        const modalIframe = document.getElementById('modal-iframe');

        function openModal(title, description, embedUrl) {
            modalTitle.textContent = title;
            modalDescription.textContent = description;
            modalIframe.src = embedUrl;
            modal.classList.remove('hidden');
        }

        function closeModal() {
            modal.classList.add('hidden');
            modalIframe.src = '';
        }

        // Contact Form Handling
        function handleFormSubmit(e) {
            e.preventDefault();
            const msgBox = document.getElementById('form-message');
            msgBox.classList.remove('hidden', 'bg-red-900/50', 'text-red-300');
            msgBox.classList.add('bg-brand-cyan/20', 'text-brand-cyan', 'border', 'border-brand-cyan/40');
            msgBox.textContent = 'Thank you! Your message has been sent to SL YK creations.';
            document.getElementById('contact-form').reset();
        }
    </script>
</body>
</html>
