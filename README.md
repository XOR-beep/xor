="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nexus BY AHSAN</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Rubik:wght@400;500;700&display=swap');
        
        :root {
            --primary: #6c5ce7;
            --secondary: #a29bfe;
            --accent: #fd79a8;
            --dark: #2d3436;
            --light: #f5f6fa;
        }
        
        body {
            font-family: 'Rubik', sans-serif;
            background-color: #0f0f13;
            color: var(--light);
            overflow-x: hidden;
        }
        
        .pixel-font {
            font-family: 'Press Start 2P', cursive;
        }
        
        .game-card {
            transition: all 0.3s ease;
            transform-style: preserve-3d;
            perspective: 1000px;
        }
        
        .game-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 25px -5px rgba(124, 58, 237, 0.3), 0 10px 10px -5px rgba(124, 58, 237, 0.1);
        }
        
        .glow-effect {
            position: relative;
        }
        
        .glow-effect::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at center, rgba(124, 58, 237, 0.4) 0%, transparent 70%);
            z-index: -1;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        
        .glow-effect:hover::after {
            opacity: 1;
        }
        
        .neon-text {
            text-shadow: 0 0 5px #fff, 0 0 10px #fff, 0 0 15px #a29bfe, 0 0 20px #a29bfe;
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% {
                box-shadow: 0 0 0 0 rgba(124, 58, 237, 0.7);
            }
            70% {
                box-shadow: 0 0 0 10px rgba(124, 58, 237, 0);
            }
            100% {
                box-shadow: 0 0 0 0 rgba(124, 58, 237, 0);
            }
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, #6c5ce7 0%, #a29bfe 50%, #fd79a8 100%);
        }
        
        .typewriter {
            overflow: hidden;
            border-right: .15em solid var(--accent);
            white-space: nowrap;
            letter-spacing: .15em;
            animation: typing 3.5s steps(40, end), blink-caret .75s step-end infinite;
        }
        
        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }
        
        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: var(--accent) }
        }
    </style>
</head>
<body class="min-h-screen">
    <!-- Navigation -->
    <nav class="bg-gray-900 bg-opacity-90 backdrop-blur-md fixed w-full z-50 border-b border-purple-900">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center">
                    <div class="flex-shrink-0">
                        <span class="text-2xl font-bold text-purple-400 pixel-font">NEXUS BY AHSAN</span>
                    </div>
                    <div class="hidden md:block">
                        <div class="ml-10 flex items-baseline space-x-4">
                            <a href="#" class="text-purple-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium transition-all">Home</a>
                            <a href="#" class="text-gray-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium transition-all">Games</a>
                            <a href="#" class="text-gray-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium transition-all">News</a>
                            <a href="#" class="text-gray-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium transition-all">Forums</a>
                            <a href="#" class="text-gray-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium transition-all">Store</a>
                        </div>
                    </div>
                </div>
                <div class="hidden md:block">
                    <div class="ml-4 flex items-center md:ml-6">
                        <button class="bg-purple-600 hover:bg-purple-700 text-white px-4 py-2 rounded-md text-sm font-medium flex items-center transition-all">
                            <i class="fas fa-gamepad mr-2"></i> Play Now
                        </button>
                    </div>
                </div>
                <div class="-mr-2 flex md:hidden">
                    <button type="button" id="mobile-menu-button" class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none">
                        <span class="sr-only">Open main menu</span>
                        <i class="fas fa-bars"></i>
                    </button>
                </div>
            </div>
        </div>
        
        <!-- Mobile menu -->
        <div class="hidden md:hidden" id="mobile-menu">
            <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
                <a href="#" class="text-purple-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium">Home</a>
                <a href="#" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium">Games</a>
                <a href="#" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium">News</a>
                <a href="#" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium">Forums</a>
                <a href="#" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium">Store</a>
                <a href="#" class="bg-purple-600 hover:bg-purple-700 text-white block px-3 py-2 rounded-md text-base font-medium">Play Now</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="relative pt-32 pb-20 md:pt-40 md:pb-28 overflow-hidden">
        <div class="absolute inset-0 z-0">
            <div class="absolute inset-0 bg-gradient-to-b from-purple-900 to-black opacity-90"></div>
            <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1542751375-ad40-3ab599f702a7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80')] bg-cover bg-center opacity-20"></div>
        </div>
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="md:grid md:grid-cols-2 md:gap-12 items-center">
                <div class="text-center md:text-left mb-10 md:mb-0">
                    <h1 class="text-4xl md:text-6xl font-bold mb-6 text-white neon-text">
                        <span class="typewriter">Gaming HUB</span>
                    </h1>
                    <p class="text-lg md:text-xl text-gray-300 mb-8 max-w-lg mx-auto md:mx-0">
                        MY FIRST GAMING SITE I M FROM PAKISTAN 
                        HOPE YOU ENJOY
                    </p>
                    <div class="flex flex-col sm:flex-row gap-4 justify-center md:justify-start">
                        <button class="bg-purple-600 hover:bg-purple-700 text-white px-8 py-3 rounded-lg font-medium text-lg flex items-center justify-center transition-all glow-effect">
                            <i class="fas fa-play mr-2"></i> Play Free
                        </button>
                        <button class="bg-gray-800 hover:bg-gray-700 text-white px-8 py-3 rounded-lg font-medium text-lg flex items-center justify-center transition-all border border-purple-500">
                            <i class="fas fa-info-circle mr-2"></i> Learn More
                        </button>
                    </div>
                    <div class="mt-8 flex justify-center md:justify-start space-x-6">
                        <div class="flex items-center">
                            <i class="fas fa-users text-purple-400 mr-2"></i>
                            <span class="text-gray-300">ONLY PRO PLAYERS</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-trophy text-yellow-400 mr-2"></i>
                            <span class="text-gray-300">TOURNAMENTS SOON..</span>
                        </div>
                    </div>
                </div>
                <div class="relative">
                    <div class="relative max-w-md mx-auto">
                        <div class="absolute -top-6 -left-6 w-full h-full rounded-xl border-2 border-purple-400"></div>
                        <img src="https://images.unsplash.com/photo-1598550476439-6847785fcea6?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="Gaming" class="rounded-xl relative z-10 shadow-2xl">
                        <div class="absolute -bottom-4 -right-4 bg-purple-600 text-white px-4 py-2 rounded-lg font-bold flex items-center">
                            <i class="fas fa-star mr-2"></i> New Update!
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Games -->
    <section class="py-16 bg-gray-900">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">Featured Games</h2>
                <div class="w-20 h-1 bg-purple-500 mx-auto mb-4"></div>
                <p class="text-gray-400 max-w-2xl mx-auto">Discover the hottest games in our collection. Updated weekly with new titles.</p>
            </div>
            
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Game Card 1 -->
                <div class="game-card bg-gray-800 rounded-xl overflow-hidden shadow-lg hover:shadow-purple-500/20 transition-all duration-300">
                    <div class="relative">
                        <img src="https://images.unsplash.com/photo-1542751375-ad40-3ab599f702a7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="Game 1" class="w-full h-48 object-cover">
                        <div class="absolute top-4 right-4 bg-purple-600 text-white text-xs font-bold px-2 py-1 rounded">
                            -20%
                        </div>
                    </div>
                    <div class="p-6">
                        <div class="flex justify-between items-start mb-2">
                            <h3 class="text-xl font-bold text-white">Cyberverse Legends</h3>
                            <div class="flex items-center">
                                <i class="fas fa-star text-yellow-400 mr-1"></i>
                                <span class="text-gray-300">4.8</span>
                            </div>
                        </div>
                        <p class="text-gray-400 text-sm mb-4">Open-world RPG with stunning visuals and immersive gameplay.</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <span class="text-purple-400 font-bold">$39.99</span>
                                <span class="text-gray-500 line-through text-sm ml-2">$49.99</span>
                            </div>
                            <button class="bg-purple-600 hover:bg-purple-700 text-white px-4 py-2 rounded text-sm font-medium transition-all">
                                Add to Cart
                            </button>
                        </div>
                    </div>
                </div>
                
                <!-- Game Card 2 -->
                <div class="game-card bg-gray-800 rounded-xl overflow-hidden shadow-lg hover:shadow-purple-500/20 transition-all duration-300">
                    <div class="relative">
                        <img src="https://images.unsplash.com/photo-1551103782-8ab07afd45c1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="Game 2" class="w-full h-48 object-cover">
                        <div class="absolute top-4 right-4 bg-green-600 text-white text-xs font-bold px-2 py-1 rounded">
                            Free
                        </div>
                    </div>
                    <div class="p-6">
                        <div class="flex justify-between items-start mb-2">
                            <h3 class="text-xl font-bold text-white">Battle Royale X</h3>
                            <div class="flex items-center">
                                <i class="fas fa-star text-yellow-400 mr-1"></i>
                                <span class="text-gray-300">4.5</span>
                            </div>
                        </div>
                        <p class="text-gray-400 text-sm mb-4">The ultimate battle royale experience with 100 players.</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <span class="text-green-400 font-bold">FREE</span>
                            </div>
                            <button class="bg-purple-600 hover:bg-purple-700 text-white px-4 py-2 rounded text-sm font-medium transition-all">
                                Download
                            </button>
                        </div>
                    </div>
                </div>
                
                <!-- Game Card 3 -->
                <div class="game-card bg-gray-800 rounded-xl overflow-hidden shadow-lg hover:shadow-purple-500/20 transition-all duration-300">
                    <div class="relative">
                        <img src="https://images.unsplash.com/photo-1542281286-9e0a16bb7366?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="Game 3" class="w-full h-48 object-cover">
                        <div class="absolute top-4 right-4 bg-red-600 text-white text-xs font-bold px-2 py-1 rounded">
                            New
                        </div>
                    </div>
                    <div class="p-6">
                        <div class="flex justify-between items-start mb-2">
                            <h3 class="text-xl font-bold text-white">Space Odyssey</h3>
                            <div class="flex items-center">
                                <i class="fas fa-star text-yellow-400 mr-1"></i>
                                <span class="text-gray-300">4.9</span>
                            </div>
                        </div>
                        <p class="text-gray-400 text-sm mb-4">Explore the universe in this epic space adventure.</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <span class="text-purple-400 font-bold">$59.99</span>
                            </div>
                            <button class="bg-purple-600 hover:bg-purple-700 text-white px-4 py-2 rounded text-sm font-medium transition-all">
                                Pre-order
                            </button>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="text-center mt-12">
                <button class="border-2 border-purple-500 text-purple-400 hover:bg-purple-500 hover:text-white px-8 py-3 rounded-lg font-medium transition-all">
                    View All Games
                </button>
            </div>
        </div>
    </section>

    <!-- Game Stats -->
    <section class="py-16 bg-gradient-to-b from-gray-900 to-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8 text-center">
                <div class="bg-gray-800 bg-opacity-50 rounded-xl p-8 border border-purple-900 hover:border-purple-500 transition-all">
                    <div class="text-5xl font-bold text-purple-400 mb-2">0</div>
                    <div class="text-gray-300">Active Players</div>
                    <div class="mt-4">
                        <i class="fas fa-users text-3xl text-purple-400 opacity-70"></i>
                    </div>
                </div>
                <div class="bg-gray-800 bg-opacity-50 rounded-xl p-8 border border-purple-900 hover:border-purple-500 transition-all">
                    <div class="text-5xl font-bold text-purple-400 mb-2"> SOON</div>
                    <div class="text-gray-300">Tournaments</div>
                    <div class="mt-4">
                        <i class="fas fa-trophy text-3xl text-purple-400 opacity-70"></i>
                    </div>
                </div>
                <div class="bg-gray-800 bg-opacity-50 rounded-xl p-8 border border-purple-900 hover:border-purple-500 transition-all">
                    <div class="text-5xl font-bold text-purple-400 mb-2">24/7</div>
                    <div class="text-gray-300">Support</div>
                    <div class="mt-4">
                        <i class="fas fa-headset text-3xl text-purple-400 opacity-70"></i>
                    </div>
                </div>
                <div class="bg-gray-800 bg-opacity-50 rounded-xl p-8 border border-purple-900 hover:border-purple-500 transition-all">
                    <div class="text-5xl font-bold text-purple-400 mb-2">100+</div>
                    <div class="text-gray-300">Games Available</div>
                    <div class="mt-4">
                        <i class="fas fa-gamepad text-3xl text-purple-400 opacity-70"></i>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Upcoming Events -->
    <section class="py-16 bg-gray-900">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">Upcoming Events</h2>
                <div class="w-20 h-1 bg-purple-500 mx-auto mb-4"></div>
                <p class="text-gray-400 max-w-2xl mx-auto">Join our exciting tournaments and events with amazing prizes.</p>
            </div>
            
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                <!-- Event 1 -->
                <div class="game-card bg-gray-800 rounded-xl overflow-hidden shadow-lg hover:shadow-purple-500/20 transition-all duration-300 flex flex-col md:flex-row">
                    <div class="md:w-1/3 relative">
                        <img src="https://images.unsplash.com/photo-1543489822-c49534f4ad5a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="Event 1" class="w-full h-full object-cover">
                        <div class="absolute bottom-0 left-0 right-0 bg-gradient-to-t from-black to-transparent p-4">
                            <div class="text-white font-bold">June 15, 2026</div>
                        </div>
                    </div>
                    <div class="md:w-2/3 p-6">
                        <div class="flex justify-between items-start mb-2">
                            <h3 class="text-xl font-bold text-white">Global Championship</h3>
                            <div class="bg-purple-600 text-white text-xs font-bold px-2 py-1 rounded">
                                $50K Prize
                            </div>
                        </div>
                        <p class="text-gray-400 text-sm mb-4">The biggest tournament of the year with players from all over the world competing for the championship title.</p>
                        <div class="flex flex-wrap gap-2 mb-4">
                            <span class="bg-gray-700 text-gray-300 text-xs px-2 py-1 rounded">PC</span>
                            <span class="bg-gray-700 text-gray-300 text-xs px-2 py-1 rounded">PS5</span>
                            <span class="bg-gray-700 text-gray-300 text-xs px-2 py-1 rounded">XBOX</span>
                        </div>
                        <div class="flex justify-between items-center">
                            <div class="flex items-center">
                                <i class="fas fa-users text-purple-400 mr-2"></i>
                                <span class="text-gray-300 text-sm">128 teams registered</span>
                            </div>
                            <button class="bg-purple-600 hover:bg-purple-700 text-white px-4 py-2 rounded text-sm font-medium transition-all">
                                Register Now
                            </button>
                        </div>
                    </div>
                </div>
                
                <!-- Event 2 -->
                <div class="game-card bg-gray-800 rounded-xl overflow-hidden shadow-lg hover:shadow-purple-500/20 transition-all duration-300 flex flex-col md:flex-row">
                    <div class="md:w-1/3 relative">
                        <img src="https://images.unsplash.com/photo-1511512578047-dba367496ab6?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="Event 2" class="w-full h-full object-cover">
                        <div class="absolute bottom-0 left-0 right-0 bg-gradient-to-t from-black to-transparent p-4">
                            <div class="text-white font-bold">July 8, 2026</div>
                        </div>
                    </div>
                    <div class="md:w-2/3 p-6">
                        <div class="flex justify-between items-start mb-2">
                            <h3 class="text-xl font-bold text-white">Summer Showdown</h3>
                            <div class="bg-yellow-600 text-white text-xs font-bold px-2 py-1 rounded">
                                $25K Prize
                            </div>
                        </div>
                        <p class="text-gray-400 text-sm mb-4">A special summer edition of our popular tournament series with new maps and gameplay modes.</p>
                        <div class="flex flex-wrap gap-2 mb-4">
                            <span class="bg-gray-700 text-gray-300 text-xs px-2 py-1 rounded">PC</span>
                            <span class="bg-gray-700 text-gray-300 text-xs px-2 py-1 rounded">Mobile</span>
                        </div>
                        <div class="flex justify-between items-center">
                            <div class="flex items-center">
                                <i class="fas fa-users text-purple-400 mr-2"></i>
                                <span class="text-gray-300 text-sm">64 teams registered</span>
                            </div>
                            <button class="bg-purple-600 hover:bg-purple-700 text-white px-4 py-2 rounded text-sm font-medium transition-all">
                                Register Now
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter -->
    <section class="py-16 gradient-bg">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <h2 class="text-3xl md:text-4xl font-bold text-white mb-6">Stay Updated</h2>
            <p class="text-purple-100 mb-8">Sign up for the latest game releases, updates, and exclusive offers.</p>
            
            <div class="max-w-md mx-auto flex">
                <input type="email" placeholder="Your email address" class="flex-grow px-4 py-3 rounded-l-lg focus:outline-none focus:ring-2 focus:ring-purple-300 text-gray-900">
                <button class="bg-purple-900 hover:bg-purple-800 text-white px-6 py-3 rounded-r-lg font-medium transition-all">
                    SIGN UP 
                </button>
            </div>
            
            <div class="mt-6 flex justify-center space-x-6">
                <a href="#" class="text-white hover:text-purple-200 transition-all">
                    <i class="fab fa-twitter text-2xl"></i>
                </a>
                <a href="#" class="text-white hover:text-purple-200 transition-all">
                    <i class="fab fa-discord text-2xl"></i>
                </a>
                <a href="#" class="text-white hover:text-purple-200 transition-all">
                    <i class="fab fa-instagram text-2xl"></i>
                </a>
                <a href="#" class="text-white hover:text-purple-200 transition-all">
                    <i class="fab fa-youtube text-2xl"></i>
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 pt-16 pb-8">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8 mb-12">
                <div>
                    <h3 class="text-xl font-bold text-white mb-4">Nexus Gaming</h3>
                    <p class="text-gray-400 mb-4">The ultimate gaming platform for competitive and casual players alike.</p>
                    <div class="flex space-x-4">
                        <a href="#" class="text-gray-400 hover:text-white transition-all">
                            <i class="fab fa-facebook-f"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-all">
                            <i class="fab fa-twitter"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-all">
                            <i class="fab fa-instagram"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-all">
                            <i class="fab fa-discord"></i>
                        </a>
                    </div>
                </div>
                <div>
                    <h4 class="text-lg font-semibold text-white mb-4">Quick Links</h4>
                    <ul class="space-y-2">
                        <li><a href="#" class="text-gray-400 hover:text-white transition-all">Home</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-all">Games</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-all">Tournaments</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-all">News</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-all">Support</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-lg font-semibold text-white mb-4">Legal</h4>
                    <ul class="space-y-2">
                        <li><a href="#" class="text-gray-400 hover:text-white transition-all">Terms of Service</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-all">Privacy Policy</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-all">Cookie Policy</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-all">Refund Policy</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-lg font-semibold text-white mb-4">Contact Us</h4>
                    <ul class="space-y-2">
                        <li class="flex items-center text-gray-400">
 <i class="fas fa-envelope mr-2"></i> ahsan.waqas026@gmail.com
                        </li>
                        <li class="flex items-center text-gray-400">
         <i class="fas fa-phone-alt mr-2"></i> 03334476880
          </li>
                        <li class="flex items-center text-gray-400">
   <i class="fas fa-map-marker-alt mr-2"></i> joisha road sandha street#4 house#4
                        </li>
                    </ul>
                </div>
            </div>
            <div class="border-t border-gray-800 pt-8">
                <p class="text-gray-400 text-center">© 2022 Nexus Gaming. All rights reserved to AHSANN .</p>
            </div>
        </div>
    </footer>

    <script>
        // Mobile menu toggle
        document.getElementById('mobile-menu-button').addEventListener('click', function() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        });

        // Game card hover effect
        const gameCards = document.querySelectorAll('.game-card');
        gameCards.forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.classList.add('shadow-lg');
            });
            card.addEventListener('mouseleave', function() {
                this.classList.remove('shadow-lg');
            });
        });

        // Countdown timer for events (example)
        function updateCountdown() {
            const now = new Date();
            const eventDate = new Date('2023-06-15T00:00:00');
            const diff = eventDate - now;
            
            const days = Math.floor(diff / (1000 * 60 * 60 * 24));
            const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((diff % (1000 * 60)) / 1000);
            
            // You would display this in your countdown element
            console.log(`${days}d ${hours}h ${minutes}m ${seconds}s`);
        }
        
        setInterval(updateCountdown, 1000);
    </script>
</body>
</html>
