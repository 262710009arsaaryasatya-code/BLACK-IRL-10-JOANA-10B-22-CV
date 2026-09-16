<!DOCTYPE html>
<html lang="id" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Magical Mid-Autumn & Mooncake Festival</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Lucide Icons (pinned, jsdelivr) -->
    <script src="https://cdn.jsdelivr.net/npm/lucide@0.294.0/dist/umd/lucide.js"></script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700;800&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        night: { 900: '#170304', 800: '#2B0808', 700: '#3F0F0F' },
                        gold: { 300: '#FDE047', 400: '#FACC15', 500: '#EAB308', 600: '#CA8A04' },
                    },
                    fontFamily: {
                        header: ['Cinzel', 'serif'],
                        body: ['Plus Jakarta Sans', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        :root {
            --bg: #1A0304;
            --text: #FDF3E7;
        }
        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: var(--bg);
            color: var(--text);
            overflow-x: hidden;
        }

        .moon {
            background: radial-gradient(circle, #FFFBEB 0%, #FDE047 50%, #EAB308 100%);
            box-shadow: 0 0 90px 30px rgba(250, 204, 21, 0.4), 0 0 160px 80px rgba(234, 179, 8, 0.2);
        }

        /* Rich Chinese festival backdrop: deep red-gold glow + stars + auspicious cloud (祥云) motif */
        .stars {
            background-image:
                radial-gradient(circle at 50% -5%, rgba(250,204,21,0.22) 0%, rgba(153,27,27,0.45) 35%, rgba(26,3,4,0.95) 72%, #0d0203 100%),
                radial-gradient(2px 2px at 20px 30px, #fff, rgba(0,0,0,0)),
                radial-gradient(2px 2px at 50px 100px, #ffd700, rgba(0,0,0,0)),
                radial-gradient(1px 1px at 120px 40px, #fff, rgba(0,0,0,0)),
                radial-gradient(2px 2px at 200px 180px, #fff, rgba(0,0,0,0)),
                url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='160' height='160'%3E%3Cg fill='none' stroke='%23EAB308' stroke-width='2' opacity='0.16'%3E%3Cpath d='M20 100 Q8 78 30 72 Q24 50 52 56 Q58 32 80 44 Q98 38 104 60 Q120 66 108 88 Q116 108 88 104 Q82 118 60 108 Q44 118 32 104 Q14 108 20 100 Z'/%3E%3C/g%3E%3C/svg%3E");
            background-repeat: no-repeat, repeat, repeat, repeat, repeat, repeat;
            background-size: cover, 250px 250px, 250px 250px, 250px 250px, 250px 250px, 320px 320px;
        }

        .glass-panel {
            background: linear-gradient(160deg, rgba(69, 10, 10, 0.72), rgba(20, 4, 5, 0.85));
            backdrop-filter: blur(16px);
            border: 1px solid rgba(250, 204, 21, 0.25);
        }

        /* Floating Flying Lantern Animation */
        @keyframes flyUp {
            0% { transform: translateY(100vh) scale(0.6) rotate(-2deg); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 0.9; }
            100% { transform: translateY(-120vh) scale(1.1) rotate(4deg); opacity: 0; }
        }

        .floating-lantern {
            position: fixed;
            z-index: 40;
            cursor: pointer;
            animation: flyUp 18s linear forwards;
            transition: transform 0.2s ease;
        }

        .floating-lantern:hover {
            transform: scale(1.3) !important;
            filter: drop-shadow(0 0 15px #facc15);
        }

        .glow-card {
            box-shadow: 0 4px 20px -2px rgba(234, 179, 8, 0.15);
        }

        .moon-art {
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: radial-gradient(circle at 50% 40%, #1E293B 0%, #070A12 70%);
            position: relative;
            overflow: hidden;
        }
        .moon-art .big-moon {
            width: 55%;
            aspect-ratio: 1/1;
            border-radius: 9999px;
            background: radial-gradient(circle, #FFFBEB 0%, #FDE047 55%, #EAB308 100%);
            box-shadow: 0 0 60px 15px rgba(250, 204, 21, 0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3.5rem;
        }

        /* Responsive wide content safety */
        .overflow-x-auto { overflow-x: auto; }
    </style>
</head>
<body class="stars min-h-screen flex flex-col justify-between">

    <!-- Sky Canvas Container for Flying Lanterns -->
    <div id="sky-container" class="fixed inset-0 pointer-events-none z-40 overflow-hidden"></div>

    <!-- Modal Pop-up Pesan Lentera saat Diklik -->
    <div id="lantern-modal" class="fixed inset-0 bg-black/80 backdrop-blur-md z-50 hidden flex items-center justify-center p-4">
        <div class="glass-panel p-8 rounded-3xl max-w-md w-full text-center relative border-2 border-gold-400">
            <button onclick="closeModal()" class="absolute top-4 right-4 text-gray-400 hover:text-white text-xl font-bold">✕</button>
            <div class="text-6xl mb-4">🐇🏮</div>
            <h3 class="font-header text-2xl font-bold text-gold-300 mb-2">Pesan Lentera Kelinci</h3>
            <p id="modal-message" class="text-lg text-gray-200 italic my-6 bg-night-900/80 p-4 rounded-xl border border-gold-500/30">
                "..."
            </p>
            <p id="modal-author" class="text-xs text-gold-400 tracking-widest uppercase mb-6">- Pengirim Rahasia -</p>
            <button onclick="closeModal()" class="px-6 py-2.5 rounded-xl bg-gold-500 text-night-900 font-bold hover:bg-gold-400 transition">
                Tutup Pesan
            </button>
        </div>
    </div>

    <!-- Header Navigation -->
    <header class="sticky top-0 z-30 glass-panel">
        <div class="max-w-7xl mx-auto px-4 h-20 flex items-center justify-between">
            <div class="flex items-center gap-3">
                <div class="w-10 h-10 rounded-full moon flex items-center justify-center text-night-900 font-bold text-xl">🥮</div>
                <span class="font-header text-xl font-bold bg-gradient-to-r from-gold-300 to-amber-500 bg-clip-text text-transparent">
                    Mooncake Festival
                </span>
            </div>
            <nav class="hidden lg:flex gap-6 text-sm font-medium">
                <a href="#change" class="hover:text-gold-400">Dewi Chang'e</a>
                <a href="#mooncakes" class="hover:text-gold-400">Filosofi Kue Bulan</a>
                <a href="#lanterns-info" class="hover:text-gold-400">Makna Lentera</a>
                <a href="#events" class="hover:text-gold-400">Perlombaan</a>
                <a href="#game" class="hover:text-gold-400">Mini Game</a>
                <a href="#quiz" class="hover:text-gold-400">Kuis</a>
            </nav>
            <a href="#sky-section" class="px-5 py-2.5 rounded-full bg-gradient-to-r from-gold-500 to-amber-600 text-night-900 font-bold hover:shadow-lg transition">
                Terbangkan Lentera
            </a>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="relative py-16 text-center overflow-hidden">
        <div class="absolute top-10 left-1/2 -translate-x-1/2 w-80 h-80 sm:w-96 sm:h-96 rounded-full moon opacity-80 pointer-events-none"></div>
        <div class="relative z-10 max-w-4xl mx-auto px-4 mt-8">
            <span class="px-4 py-1.5 rounded-full glass-panel border border-gold-400/30 text-gold-300 text-sm">🥮 Perayaan Musim Gugur & Keharmonisan</span>
            <h1 class="font-header text-4xl sm:text-6xl font-extrabold text-white my-6 leading-tight">
                Purnama Indah, Pesona <br>
                <span class="bg-gradient-to-r from-gold-300 via-yellow-200 to-amber-500 bg-clip-text text-transparent">Festival Kue Bulan</span>
            </h1>
            <p class="text-gray-300 text-base sm:text-lg max-w-2xl mx-auto mb-8">
                Jelajahi keajaiban dongeng Dewi Chang'e, makna mendalam dibalik kue bulan & lentera, serta terbangkan harapanmu ke langit malam!
            </p>
        </div>
    </section>

    <!-- Karakter & Legenda Chang'e -->
    <section id="change" class="py-16">
        <div class="max-w-6xl mx-auto px-4">
            <div class="glass-panel p-8 sm:p-12 rounded-3xl border border-gold-500/30 relative">
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
                    <div class="lg:col-span-5 flex flex-col items-center text-center">
                        <div class="w-full h-80 rounded-2xl border-2 border-gold-400/50 overflow-hidden relative shadow-2xl">
                            <svg viewBox="0 0 400 520" xmlns="http://www.w3.org/2000/svg" class="w-full h-full">
                                <defs>
                                    <radialGradient id="skyGlow" cx="50%" cy="15%" r="75%">
                                        <stop offset="0%" stop-color="#92400E" stop-opacity="0.55"/>
                                        <stop offset="45%" stop-color="#450a0a" stop-opacity="0.9"/>
                                        <stop offset="100%" stop-color="#0d0203" stop-opacity="1"/>
                                    </radialGradient>
                                    <radialGradient id="moonGlow" cx="50%" cy="50%" r="50%">
                                        <stop offset="0%" stop-color="#FFFBEB"/>
                                        <stop offset="55%" stop-color="#FDE047"/>
                                        <stop offset="100%" stop-color="#EAB308"/>
                                    </radialGradient>
                                    <linearGradient id="robeGrad" x1="0" y1="0" x2="0" y2="1">
                                        <stop offset="0%" stop-color="#F87171"/>
                                        <stop offset="100%" stop-color="#7F1D1D"/>
                                    </linearGradient>
                                </defs>

                                <rect width="400" height="520" fill="url(#skyGlow)"/>

                                <!-- stars -->
                                <circle cx="40" cy="55" r="1.6" fill="#FDE68A"/>
                                <circle cx="345" cy="85" r="1.3" fill="#FDE68A"/>
                                <circle cx="70" cy="150" r="1.1" fill="#FDE68A"/>
                                <circle cx="310" cy="45" r="1.6" fill="#FDE68A"/>
                                <circle cx="365" cy="210" r="1.1" fill="#FDE68A"/>
                                <circle cx="30" cy="230" r="1.1" fill="#FDE68A"/>

                                <!-- moon glow rings -->
                                <circle cx="200" cy="150" r="135" fill="#FDE047" opacity="0.08"/>
                                <circle cx="200" cy="150" r="105" fill="#FDE047" opacity="0.12"/>

                                <!-- moon -->
                                <circle cx="200" cy="150" r="82" fill="url(#moonGlow)"/>
                                <circle cx="175" cy="122" r="8" fill="#EAB308" opacity="0.3"/>
                                <circle cx="228" cy="168" r="12" fill="#EAB308" opacity="0.28"/>
                                <circle cx="190" cy="178" r="5" fill="#EAB308" opacity="0.28"/>

                                <!-- Chang'e -->
                                <g transform="translate(200,185)">
                                    <path d="M-70,45 Q-102,12 -86,-32 Q-70,-8 -54,12 Z" fill="#DC2626" opacity="0.9"/>
                                    <path d="M70,45 Q102,12 86,-32 Q70,-8 54,12 Z" fill="#DC2626" opacity="0.9"/>
                                    <path d="M-45,112 Q-56,42 -25,-8 Q0,-24 25,-8 Q56,42 45,112 Q0,132 -45,112 Z" fill="url(#robeGrad)" stroke="#FDE047" stroke-width="2"/>
                                    <path d="M-25,-8 Q0,-24 25,-8 L20,12 Q0,2 -20,12 Z" fill="#FDE047"/>
                                    <rect x="-30" y="32" width="60" height="8" rx="4" fill="#FDE047" opacity="0.9"/>
                                    <circle cx="0" cy="-35" r="20" fill="#FFE4C4"/>
                                    <circle cx="0" cy="-56" r="10" fill="#1C1917"/>
                                    <path d="M-20,-40 Q0,-66 20,-40 Q15,-51 0,-53 Q-15,-51 -20,-40 Z" fill="#1C1917"/>
                                    <circle cx="10" cy="-59" r="3" fill="#FDE047"/>
                                    <path d="M-25,2 Q-15,26 0,31 Q15,26 25,2" fill="none" stroke="#DC2626" stroke-width="10" stroke-linecap="round"/>
                                    <g transform="translate(0,34)">
                                        <circle r="22" fill="#D97706" stroke="#92400E" stroke-width="2"/>
                                        <circle r="16" fill="none" stroke="#78350F" stroke-width="1" opacity="0.6"/>
                                        <path d="M0,-16 L4,-4 L16,0 L4,4 L0,16 L-4,4 L-16,0 L-4,-4 Z" fill="#FDE047" opacity="0.85"/>
                                    </g>
                                </g>

                                <!-- Jade Rabbit -->
                                <g transform="translate(115,330)">
                                    <ellipse cx="0" cy="10" rx="26" ry="18" fill="#F8FAFC"/>
                                    <circle cx="-14" cy="-8" r="12" fill="#F8FAFC"/>
                                    <ellipse cx="-20" cy="-24" rx="4" ry="14" fill="#F8FAFC" transform="rotate(-15 -20 -24)"/>
                                    <ellipse cx="-8" cy="-24" rx="4" ry="14" fill="#F8FAFC" transform="rotate(10 -8 -24)"/>
                                    <circle cx="-18" cy="-9" r="1.5" fill="#1C1917"/>
                                    <circle cx="-10" cy="-9" r="1.5" fill="#1C1917"/>
                                    <ellipse cx="-14" cy="-4" rx="2" ry="1.2" fill="#F87171"/>
                                </g>

                                <!-- distant clouds -->
                                <path d="M0,470 Q40,440 90,460 Q120,430 170,450 Q210,425 260,450 Q300,430 350,455 Q380,440 400,460 L400,520 L0,520 Z" fill="#450a0a" opacity="0.9"/>
                                <path d="M0,492 Q60,472 130,487 Q190,467 260,487 Q330,472 400,490 L400,520 L0,520 Z" fill="#22040A"/>
                            </svg>
                        </div>
                        <h3 class="font-header text-2xl font-bold text-gold-300 mt-4">Dewi Chang'e & Kelinci Bulan</h3>
                        <p class="text-xs text-gold-400 tracking-wider">DEWI BULAN ABADI</p>
                    </div>

                    <div class="lg:col-span-7">
                        <div class="inline-flex items-center gap-2 text-gold-400 text-sm font-bold mb-2">
                            <i data-lucide="sparkles" class="w-4 h-4"></i> Legenda Utama
                        </div>
                        <h2 class="font-header text-3xl font-bold text-white mb-4">Kisah Pengorbanan Dewi Chang'e</h2>
                        <p class="text-gray-300 mb-4 leading-relaxed">
                            Dahulu kala, 10 matahari terbit bersamaan hingga bumi kekeringan. Pahlawan pemanah <strong>Hou Yi</strong> memanah jatuh 9 matahari dan diberi ramuan keabadian oleh Dewi Barat.
                        </p>
                        <p class="text-gray-300 mb-4 leading-relaxed">
                            Ketika muridnya yang serakah (Peng Meng) mencoba mencuri ramuan tersebut saat Hou Yi berburu, istrinya yang cantik, <strong>Chang'e</strong>, terpaksa meminum ramuan itu demi melindunginya.
                        </p>
                        <p class="text-gray-300 leading-relaxed">
                            Tubuh Chang'e mendadak menjadi ringan dan melayang naik ke langit hingga mendarat di Bulan. Rindu akan istrinya, Hou Yi mempersembahkan kue bulan dan buah-buahan kesukaan Chang'e di bawah sinar purnama. Tradisi ini diteruskan hingga kini sebagai simbol reuni keluarga.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Penjelasan Kue Bulan & Simbolisme -->
    <section id="mooncakes" class="py-16">
        <div class="max-w-6xl mx-auto px-4">
            <div class="text-center mb-12">
                <h2 class="font-header text-3xl sm:text-4xl font-bold text-white mb-3">Mengapa Kue Bulan Jadi Simbol Utama?</h2>
                <p class="text-gray-400 max-w-2xl mx-auto">Kue bulan bukan sekadar hidangan manis, melainkan simbol budaya yang sarat sejarah dan kehangatan.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="glass-panel p-6 rounded-2xl glow-card">
                    <div class="text-4xl mb-4">🌕</div>
                    <h3 class="font-header text-xl font-bold text-gold-300 mb-2">Simbol Kebersamaan (Reuni)</h3>
                    <p class="text-gray-300 text-sm leading-relaxed">
                        Bentuk kue bulan yang bulat sempurna melambangkan <strong>Bulatnya Reuni Keluarga</strong> (团圆 - Tuányuán). Saat purnama paling terang, keluarga berkumpul memotong kue bulan dan membagikannya ke setiap anggota.
                    </p>
                </div>

                <div class="glass-panel p-6 rounded-2xl glow-card">
                    <div class="text-4xl mb-4">📜</div>
                    <h3 class="font-header text-xl font-bold text-gold-300 mb-2">Pesan Rahasia Sejarah</h3>
                    <p class="text-gray-300 text-sm leading-relaxed">
                        Menurut sejarah Dinasti Yuan, kue bulan digunakan oleh pahlawan Liu Bowen untuk menyembunyikan <strong>surat rahasia rencana pemberontakan</strong> yang diselipkan di dalam adonan kue bulan untuk mengoordinasikan gerakan rakyat.
                    </p>
                </div>

                <div class="glass-panel p-6 rounded-2xl glow-card">
                    <div class="text-4xl mb-4">🥮</div>
                    <h3 class="font-header text-xl font-bold text-gold-300 mb-2">Kuning Telur & Rembulan</h3>
                    <p class="text-gray-300 text-sm leading-relaxed">
                        Kuning telur asin utuh di tengah isian kue bulan melambangkan <strong>cahaya bulan purnama</strong> yang bersinar terang di tengah kegelapan malam, memberikan keberkahan dan kedamaian.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Penjelasan Lentera Mooncake Festival -->
    <section id="lanterns-info" class="py-16">
        <div class="max-w-6xl mx-auto px-4">
            <div class="glass-panel p-8 sm:p-12 rounded-3xl border border-gold-500/30">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
                    <div>
                        <div class="text-gold-400 font-bold text-sm mb-2">🏮 Tradisi Cahaya</div>
                        <h2 class="font-header text-3xl font-bold text-white mb-4">Mengapa Lentera Selalu Ada di Festival Kue Bulan?</h2>
                        <ul class="space-y-4 text-gray-300 text-sm">
                            <li class="flex items-start gap-3">
                                <span class="text-gold-400 text-lg">✦</span>
                                <div>
                                    <strong>Penerang Malam & Penunjuk Jalan:</strong> Pada masa lalu, festival ini dirayakan saat malam purnama. Lentera dibawa oleh anak-anak dan keluarga untuk menerangi jalan saat berjalan menikmati keindahan malam.
                                </div>
                            </li>
                            <li class="flex items-start gap-3">
                                <span class="text-gold-400 text-lg">✦</span>
                                <div>
                                    <strong>Menerbangkan Harapan ke Dewa:</strong> Menerbangkan lentera ke langit melambangkan doa dan impian manusia yang dipanjatkan agar membubung tinggi sampai ke kahyangan Dewi Chang'e.
                                </div>
                            </li>
                            <li class="flex items-start gap-3">
                                <span class="text-gold-400 text-lg">✦</span>
                                <div>
                                    <strong>Simbol Kelinci Bulan:</strong> Lentera berbentuk kelinci (Rabbit Lantern) dibuat khusus untuk menghormati Kelinci Bulan yang setia menumbuk ramuan di rembulan.
                                </div>
                            </li>
                        </ul>
                    </div>
                    <div class="flex justify-center">
                        <div class="w-full max-w-xs p-6 glass-panel rounded-2xl border border-gold-400/40 text-center animate-bounce">
                            <svg viewBox="0 0 200 220" xmlns="http://www.w3.org/2000/svg" class="w-28 h-28 mx-auto mb-3">
                                <defs>
                                    <radialGradient id="lanternGlow" cx="50%" cy="45%" r="55%">
                                        <stop offset="0%" stop-color="#FFFBEB"/>
                                        <stop offset="60%" stop-color="#FDE047"/>
                                        <stop offset="100%" stop-color="#CA8A04"/>
                                    </radialGradient>
                                </defs>
                                <circle cx="100" cy="110" r="80" fill="#FDE047" opacity="0.15"/>
                                <line x1="100" y1="0" x2="100" y2="40" stroke="#EAB308" stroke-width="3"/>
                                <ellipse cx="82" cy="18" rx="6" ry="20" fill="url(#lanternGlow)" transform="rotate(-15 82 18)"/>
                                <ellipse cx="118" cy="18" rx="6" ry="20" fill="url(#lanternGlow)" transform="rotate(15 118 18)"/>
                                <ellipse cx="100" cy="110" rx="65" ry="75" fill="url(#lanternGlow)" stroke="#CA8A04" stroke-width="3"/>
                                <path d="M100,35 Q40,110 100,185" fill="none" stroke="#CA8A04" stroke-width="2" opacity="0.5"/>
                                <path d="M100,35 Q160,110 100,185" fill="none" stroke="#CA8A04" stroke-width="2" opacity="0.5"/>
                                <circle cx="78" cy="100" r="6" fill="#1C1917"/>
                                <circle cx="122" cy="100" r="6" fill="#1C1917"/>
                                <ellipse cx="100" cy="118" rx="6" ry="4" fill="#DC2626"/>
                                <line x1="100" y1="185" x2="100" y2="205" stroke="#DC2626" stroke-width="3"/>
                                <path d="M90,205 L110,205 L105,220 L95,220 Z" fill="#DC2626"/>
                            </svg>
                            <h4 class="font-header text-gold-300 font-bold">Lentera Kelinci Harapan</h4>
                            <p class="text-xs text-gray-400 mt-2">Cahaya hangatnya melambangkan kedamaian, kesehatan, dan keberuntungan bagi keluarga.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Interactive Flying Rabbit Lantern Section -->
    <section id="sky-section" class="py-16">
        <div class="max-w-4xl mx-auto px-4 text-center">
            <div class="glass-panel p-8 rounded-3xl border-2 border-gold-400/50">
                <h2 class="font-header text-3xl font-bold text-gold-300 mb-3">🏮 Terbangkan Lentera Kelinci ke Langit!</h2>
                <p class="text-gray-300 text-sm mb-6">
                    Tuliskan harapanmu! Setelah diterbangkan, lentera akan <strong>melayang naik ke langit</strong>. Kamu bisa <strong>mengklik lentera yang terbang</strong> untuk membaca pesannya kembali.
                </p>

                <div class="max-w-md mx-auto space-y-3">
                    <input type="text" id="wish-author" placeholder="Nama Anda / Pengirim..." class="w-full px-4 py-2.5 rounded-xl bg-night-900 border border-gold-500/40 text-white placeholder-gray-500 text-sm focus:outline-none focus:border-gold-400">
                    <textarea id="wish-message" rows="3" placeholder="Tuliskan harapan atau kata-kata indah Anda..." class="w-full px-4 py-2.5 rounded-xl bg-night-900 border border-gold-500/40 text-white placeholder-gray-500 text-sm focus:outline-none focus:border-gold-400"></textarea>
                    
                    <button onclick="launchLantern()" class="w-full py-3 rounded-xl bg-gradient-to-r from-gold-500 to-amber-600 text-night-900 font-bold hover:brightness-110 transition flex items-center justify-center gap-2">
                        <i data-lucide="send" class="w-5 h-5"></i> Terbangkan Lentera Kelinci Sekarang
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Detail Perlombaan Festival -->
    <section id="events" class="py-16">
        <div class="max-w-6xl mx-auto px-4">
            <div class="text-center mb-12">
                <h2 class="font-header text-3xl sm:text-4xl font-bold text-white mb-3">Acara & Perlombaan Festival</h2>
                <p class="text-gray-400 max-w-xl mx-auto">Saksikan keseruan kompetisi kreatif bertema Mooncake Festival dengan total hadiah menarik!</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <!-- Lomba Masak Bento -->
                <div class="glass-panel p-8 rounded-3xl border border-gold-500/30">
                    <div class="w-full h-44 rounded-2xl overflow-hidden mb-5 border border-gold-400/30">
                        <svg viewBox="0 0 400 240" xmlns="http://www.w3.org/2000/svg" class="w-full h-full">
                            <defs>
                                <linearGradient id="bentoBoxGrad" x1="0" y1="0" x2="0" y2="1">
                                    <stop offset="0%" stop-color="#7F1D1D"/>
                                    <stop offset="100%" stop-color="#450a0a"/>
                                </linearGradient>
                            </defs>
                            <rect width="400" height="240" fill="#1A0304"/>
                            <rect x="40" y="40" width="320" height="160" rx="18" fill="url(#bentoBoxGrad)" stroke="#EAB308" stroke-width="3"/>
                            <line x1="200" y1="50" x2="200" y2="190" stroke="#EAB308" stroke-width="2" opacity="0.5"/>
                            <line x1="40" y1="120" x2="200" y2="120" stroke="#EAB308" stroke-width="2" opacity="0.5"/>
                            <g transform="translate(120,85)">
                                <ellipse cx="0" cy="14" rx="34" ry="26" fill="#FFFDF5"/>
                                <ellipse cx="-22" cy="-18" rx="8" ry="24" fill="#FFFDF5" transform="rotate(-18 -22 -18)"/>
                                <ellipse cx="-10" cy="-24" rx="8" ry="26" fill="#FFFDF5" transform="rotate(6 -10 -24)"/>
                                <ellipse cx="-22" cy="-18" rx="4" ry="16" fill="#FCA5A5" transform="rotate(-18 -22 -18)"/>
                                <ellipse cx="-10" cy="-24" rx="4" ry="17" fill="#FCA5A5" transform="rotate(6 -10 -24)"/>
                                <circle cx="-10" cy="6" r="2.4" fill="#1C1917"/>
                                <circle cx="8" cy="6" r="2.4" fill="#1C1917"/>
                                <ellipse cx="-1" cy="14" rx="2.6" ry="1.6" fill="#F87171"/>
                            </g>
                            <g transform="translate(120,158)">
                                <circle r="22" fill="#FFFDF5"/>
                                <path d="M-22,0 A22,22 0 0 0 22,0 Z" fill="#065F46" opacity="0.75"/>
                            </g>
                            <g transform="translate(280,85)">
                                <circle r="26" fill="#D97706" stroke="#78350F" stroke-width="2"/>
                                <circle r="18" fill="none" stroke="#92400E" stroke-width="1" opacity="0.6"/>
                                <path d="M0,-18 L4,-5 L18,0 L4,5 L0,18 L-4,5 L-18,0 L-4,-5 Z" fill="#FDE047" opacity="0.9"/>
                            </g>
                            <g transform="translate(280,160)">
                                <path d="M0,-24 L7,-8 L24,-6 L10,4 L15,22 L0,12 L-15,22 L-10,4 L-24,-6 L-7,-8 Z" fill="#EA580C" stroke="#7C2D12" stroke-width="1.5"/>
                            </g>
                            <g transform="translate(255,175)">
                                <path d="M0,-16 L5,-5 L16,-4 L7,3 L10,15 L0,8 L-10,15 L-7,3 L-16,-4 L-5,-5 Z" fill="#F59E0B" stroke="#7C2D12" stroke-width="1"/>
                            </g>
                            <rect x="55" y="30" width="4" height="150" rx="2" fill="#EAB308" transform="rotate(15 57 105)"/>
                            <rect x="65" y="30" width="4" height="150" rx="2" fill="#EAB308" transform="rotate(15 67 105)"/>
                        </svg>
                    </div>
                    <div class="flex items-center gap-4 mb-4">
                        <div class="w-14 h-14 rounded-2xl bg-amber-500/20 flex items-center justify-center text-3xl border border-gold-400/40">🍱</div>
                        <div>
                            <h3 class="font-header text-2xl font-bold text-gold-300">Lomba Masak Bento Kreatif</h3>
                            <span class="text-xs text-gold-400 font-semibold">TEMA: MOONCAKE & RABBIT BENTO</span>
                        </div>
                    </div>
                    <p class="text-gray-300 text-sm leading-relaxed mb-4">
                        Kompetisi menghias bekal makanan (Bento) unik dengan kreasi nasi berbentuk Kelinci Bulan, kue bulan mini dari telur/roti, dan garnis ornamen dedaunan musim gugur.
                    </p>
                    <div class="space-y-2 text-xs text-gray-300 bg-night-900/60 p-4 rounded-xl border border-gold-500/20">
                        <p><strong>Kriteria Penilaian:</strong> Kreativitas Bentuk (40%), Komposisi Gizi & Rasa (35%), Kebersihan & Presentasi (25%).</p>
                        <p><strong>Waktu Lomba:</strong> Sabtu, 60 Menit Durasi Menghias.</p>
                    </div>
                </div>

                <!-- Lomba Baca Puisi Mandarin -->
                <div class="glass-panel p-8 rounded-3xl border border-gold-500/30">
                    <div class="w-full h-44 rounded-2xl overflow-hidden mb-5 border border-gold-400/30">
                        <svg viewBox="0 0 400 240" xmlns="http://www.w3.org/2000/svg" class="w-full h-full">
                            <rect width="400" height="240" fill="#1A0304"/>
                            <circle cx="50" cy="50" r="26" fill="#FDE047" opacity="0.85"/>
                            <circle cx="42" cy="42" r="8" fill="#EAB308" opacity="0.4"/>
                            <g transform="translate(200,20)">
                                <rect x="-90" y="0" width="180" height="14" rx="7" fill="#92400E"/>
                                <circle cx="-90" cy="7" r="9" fill="#78350F"/>
                                <circle cx="90" cy="7" r="9" fill="#78350F"/>
                            </g>
                            <rect x="110" y="34" width="180" height="170" fill="#FDF3E7" opacity="0.95"/>
                            <rect x="110" y="34" width="180" height="170" fill="none" stroke="#92400E" stroke-width="3"/>
                            <g stroke="#450a0a" stroke-width="4" stroke-linecap="round" opacity="0.85">
                                <line x1="140" y1="55" x2="140" y2="185"/>
                                <line x1="170" y1="55" x2="170" y2="185"/>
                                <line x1="200" y1="55" x2="200" y2="185"/>
                                <line x1="230" y1="55" x2="230" y2="185"/>
                                <line x1="260" y1="55" x2="260" y2="185"/>
                            </g>
                            <g stroke="#7F1D1D" stroke-width="3" stroke-linecap="round" opacity="0.6">
                                <path d="M132,70 Q140,60 148,70" fill="none"/>
                                <path d="M132,100 L148,100" fill="none"/>
                                <path d="M162,80 Q170,65 178,80" fill="none"/>
                            </g>
                            <rect x="248" y="150" width="30" height="30" rx="4" fill="#B91C1C" stroke="#7F1D1D" stroke-width="2"/>
                            <g transform="translate(330,60) rotate(35)">
                                <rect x="-6" y="-70" width="12" height="90" rx="6" fill="#78350F"/>
                                <rect x="-6" y="-70" width="12" height="20" rx="6" fill="#EAB308"/>
                                <path d="M-6,20 Q0,45 6,20 Z" fill="#1C1917"/>
                            </g>
                        </svg>
                    </div>
                    <div class="flex items-center gap-4 mb-4">
                        <div class="w-14 h-14 rounded-2xl bg-red-500/20 flex items-center justify-center text-3xl border border-red-400/40">📜</div>
                        <div>
                            <h3 class="font-header text-2xl font-bold text-gold-300">Lomba Membaca Puisi Mandarin</h3>
                            <span class="text-xs text-gold-400 font-semibold">TEMA: KERINDUAN PURNAMA & KELUARGA</span>
                        </div>
                    </div>
                    <p class="text-gray-300 text-sm leading-relaxed mb-4">
                        Unjuk bakat melantunkan bait-bait puisi klasik Tiongkok terkenal seperti karya Su Shi (<em>Shuǐ Diào Gē Tóu</em>) atau Li Bai (<em>Jìng Yè Sī</em>) dengan penghayatan mendalam.
                    </p>
                    <div class="space-y-2 text-xs text-gray-300 bg-night-900/60 p-4 rounded-xl border border-gold-500/20">
                        <p><strong>Kriteria Penilaian:</strong> Artikulasi/Lafal Mandarin (40%), Penghayatan & Intonasi (40%), Kostum Tradisional (20%).</p>
                        <p><strong>Kategori:</strong> Anak-anak & Dewasa.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Interactive Mini Game: Mooncake Catcher -->
    <section id="game" class="py-16">
        <div class="max-w-3xl mx-auto px-4">
            <div class="glass-panel p-8 rounded-3xl text-center border-2 border-gold-400/40 relative">
                <h2 class="font-header text-3xl font-bold text-gold-300 mb-2">🎮 Game: Mooncake Catcher</h2>
                <p class="text-gray-300 text-sm mb-4">Gerakkan keranjang kelinci (kiri/kanan) untuk menangkap Kue Bulan 🥮 yang jatuh dari langit!</p>
                
                <div class="flex justify-between items-center max-w-md mx-auto mb-4 font-bold text-sm">
                    <span class="text-gold-400">Skor: <span id="game-score">0</span></span>
                    <button onclick="startGame()" class="px-4 py-1.5 rounded-lg bg-gold-500 text-night-900 hover:bg-gold-400">Mulai Game</button>
                </div>

                <!-- Game Canvas Box -->
                <div id="game-box" class="relative w-full h-64 bg-night-900/90 rounded-2xl border border-gold-500/30 overflow-hidden cursor-pointer">
                    <div id="basket" class="absolute bottom-2 left-1/2 -translate-x-1/2 text-4xl transition-all duration-75 select-none">🧺🐇</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Quiz Interaktif Lengkap -->
    <section id="quiz" class="py-16">
        <div class="max-w-3xl mx-auto px-4">
            <div class="glass-panel p-8 sm:p-10 rounded-3xl border border-gold-500/30">
                <div class="flex justify-between items-center mb-6 border-b border-gray-700 pb-4">
                    <div>
                        <span class="text-xs font-bold text-gold-400 uppercase tracking-wider">Uji Pengetahuan Wawasan</span>
                        <h2 class="font-header text-2xl sm:text-3xl font-bold text-white">Kuis Mooncake Festival</h2>
                    </div>
                    <span id="quiz-progress" class="text-sm font-semibold text-gray-400">Soal 1 dari 8</span>
                </div>

                <div id="quiz-container">
                    <h3 id="quiz-question" class="text-lg font-semibold text-gold-200 mb-6"></h3>
                    <div id="quiz-options" class="space-y-3 mb-6"></div>
                    <div id="quiz-feedback" class="hidden p-4 rounded-xl mb-6 text-sm font-medium"></div>
                    <button id="next-btn" onclick="nextQuestion()" class="hidden px-6 py-2.5 rounded-xl bg-gold-500 text-night-900 font-bold hover:bg-gold-400 transition ml-auto">
                        Soal Berikutnya →
                    </button>
                </div>

                <div id="quiz-result" class="hidden text-center py-8">
                    <div class="text-6xl mb-4">🏆</div>
                    <h3 class="font-header text-3xl font-bold text-gold-300 mb-2">Kuis Selesai!</h3>
                    <p class="text-gray-300 mb-4">Selamat! Anda telah mempelajari banyak wawasan seputar Mooncake Festival.</p>
                    <div class="text-3xl font-bold text-white mb-6">
                        Skor Anda: <span id="final-score" class="text-gold-400">0</span> / <span id="total-score">8</span>
                    </div>
                    <button onclick="restartQuiz()" class="px-8 py-3 rounded-xl bg-gold-500 text-night-900 font-bold hover:bg-gold-400 transition">
                        Ulangi Kuis
                    </button>
                </div>
            </div>
        </div>
    </section>

    <footer class="glass-panel border-t border-gold-500/20 py-8 text-center text-sm text-gray-400">
        <p>&copy; 2026 Celebration of Mooncake Festival. Dibuat dengan penuh kehangatan & pesona tradisi.</p>
    </footer>

    <!-- JavaScript Script Code -->
    <script>
        try { lucide.createIcons(); } catch(e) { console.warn('icons unavailable', e); }

        // 1. Interactive Sky Flying Lantern System
        const initialLanterns = [
            { author: "Chang'e Fan", message: "Semoga semua keluarga hidup rukun dan damai!" },
            { author: "Budi", message: "Semoga lulus ujian tahun ini dengan nilai yang memuaskan!" },
            { author: "Dewi", message: "Kesehatan dan kebahagiaan untuk kedua orang tua tercinta." }
        ];

        function createFloatingLantern(author, msg) {
            const container = document.getElementById('sky-container');
            const lantern = document.createElement('div');
            lantern.className = 'floating-lantern flex flex-col items-center pointer-events-auto';
            
            const randomX = Math.random() * 85 + 5;
            lantern.style.left = randomX + 'vw';
            
            const duration = Math.random() * 8 + 14;
            lantern.style.animationDuration = duration + 's';

            lantern.innerHTML = `
                <div class="text-4xl filter drop-shadow-[0_0_10px_#facc15]">🐇🏮</div>
                <span class="text-[10px] bg-night-900/90 text-gold-300 px-2 py-0.5 rounded-full border border-gold-400/40 mt-1 whitespace-nowrap">${author}</span>
            `;

            lantern.onclick = () => {
                document.getElementById('modal-message').textContent = `"${msg}"`;
                document.getElementById('modal-author').textContent = `- Dari: ${author} -`;
                document.getElementById('lantern-modal').classList.remove('hidden');
            };

            container.appendChild(lantern);

            setTimeout(() => {
                lantern.remove();
            }, duration * 1000);
        }

        function launchLantern() {
            const authorInput = document.getElementById('wish-author');
            const msgInput = document.getElementById('wish-message');

            const author = authorInput.value.trim() || 'Pengirim Rahasia';
            const msg = msgInput.value.trim() || 'Semoga terang bulan membawa keberkahan dan kedamaian.';

            createFloatingLantern(author, msg);

            authorInput.value = '';
            msgInput.value = '';
        }

        setInterval(() => {
            const item = initialLanterns[Math.floor(Math.random() * initialLanterns.length)];
            createFloatingLantern(item.author, item.message);
        }, 5000);

        function closeModal() {
            document.getElementById('lantern-modal').classList.add('hidden');
        }

        // 2. Mini Game: Mooncake Catcher
        let gameInterval, cakeInterval;
        let scoreCount = 0;
        let basketPos = 50;

        const gameBox = document.getElementById('game-box');
        const basket = document.getElementById('basket');

        gameBox.addEventListener('mousemove', (e) => {
            const rect = gameBox.getBoundingClientRect();
            let x = e.clientX - rect.left;
            basketPos = (x / rect.width) * 100;
            basket.style.left = `${Math.max(5, Math.min(95, basketPos))}%`;
        });

        function startGame() {
            scoreCount = 0;
            document.getElementById('game-score').textContent = scoreCount;
            
            document.querySelectorAll('.falling-cake').forEach(el => el.remove());

            clearInterval(cakeInterval);
            cakeInterval = setInterval(spawnCake, 1000);
        }

        function spawnCake() {
            const cake = document.createElement('div');
            cake.className = 'falling-cake absolute text-2xl select-none';
            cake.textContent = '🥮';
            
            let posX = Math.random() * 90 + 5;
            let posY = 0;
            cake.style.left = posX + '%';
            cake.style.top = '0px';

            gameBox.appendChild(cake);

            let drop = setInterval(() => {
                posY += 4;
                cake.style.top = posY + 'px';

                if (posY > 210 && posY < 240 && Math.abs(posX - basketPos) < 10) {
                    scoreCount += 10;
                    document.getElementById('game-score').textContent = scoreCount;
                    clearInterval(drop);
                    cake.remove();
                }

                if (posY > 250) {
                    clearInterval(drop);
                    cake.remove();
                }
            }, 30);
        }

        // 3. Quiz Data (8 Pertanyaan Lengkap)
        const quizData = [
            { question: "Siapakah tokoh dalam legenda yang meminum ramuan abadi dan melayang ke Bulan?", options: ["Hou Yi", "Chang'e", "Li Bai", "Peng Meng"], answer: 1 },
            { question: "Hewan apakah yang setia mendampingi Dewi Chang'e menumbuk obat di Bulan?", options: ["Naga Emas", "Kelinci Bulan", "Burung Phoenix", "Kura-kura"], answer: 1 },
            { question: "Bentuk bulat sempurna kue bulan melambangkan apa?", options: ["Reuni dan Kebersamaan Keluarga", "Kekayaan Melimpah", "Kecepatan Pemanah", "Matahari Terik"], answer: 0 },
            { question: "Menurut sejarah Dinasti Yuan, apa yang disembunyikan di dalam kue bulan?", options: ["Emas Murni", "Pesan Rahasia Pemberontakan", "Kelinci Kecil", "Cincin Kerajaan"], answer: 1 },
            { question: "Apa fungsi utama menerbangkan lentera pada malam perayaan Mooncake Festival?", options: ["Mengirim Harapan ke Kahyangan", "Menakuti Burung", "Memanggil Hujan", "Penanda Perlombaan"], answer: 0 },
            { question: "Bento berbentuk apa yang dilombakan pada acara kreasi kuliner festival?", options: ["Bentuk Kelinci Bulan & Ornaments Musim Gugur", "Bentuk Naga", "Bentuk Perahu Naga", "Bentuk Pohon Cendana"], answer: 0 },
            { question: "Puisi karya Su Shi yang sering dibacakan saat lomba puisi bertema apa?", options: ["Perang Kerajaan", "Kerindu Kerinduan Pada Rembulan & Keluarga", "Pertanian Padi", "Kisah Pelaut"], answer: 1 },
            { question: "Apa yang disimbolkan oleh kuning telur asin di tengah-tengah kue bulan?", options: ["Cahaya Bulan Purnama", "Batu Permata", "Bintang Kejora", "Matahari Pagi"], answer: 0 }
        ];

        let currentQuestion = 0, quizScore = 0, selectedOption = null;

        function loadQuiz() {
            selectedOption = null;
            const q = quizData[currentQuestion];
            document.getElementById('quiz-progress').textContent = `Soal ${currentQuestion + 1} dari ${quizData.length}`;
            document.getElementById('quiz-question').textContent = `${currentQuestion + 1}. ${q.question}`;
            
            const optionsContainer = document.getElementById('quiz-options');
            optionsContainer.innerHTML = '';
            document.getElementById('quiz-feedback').classList.add('hidden');
            document.getElementById('next-btn').classList.add('hidden');

            q.options.forEach((opt, idx) => {
                const btn = document.createElement('button');
                btn.className = "w-full text-left p-4 rounded-xl border border-gray-700 bg-night-800 hover:border-gold-400 transition flex items-center justify-between";
                btn.onclick = () => selectOption(idx);
                btn.innerHTML = `<span>${opt}</span><span class="text-xs border px-2 py-0.5 rounded border-gray-600">${String.fromCharCode(65 + idx)}</span>`;
                optionsContainer.appendChild(btn);
            });
        }

        function selectOption(idx) {
            if (selectedOption !== null) return;
            selectedOption = idx;

            const q = quizData[currentQuestion];
            const options = document.getElementById('quiz-options').children;
            const feedback = document.getElementById('quiz-feedback');

            if (idx === q.answer) {
                quizScore++;
                options[idx].classList.add('border-green-500', 'bg-green-900/40');
                feedback.className = "p-4 rounded-xl mb-6 text-sm bg-green-900/40 border border-green-500 text-green-300";
                feedback.textContent = "✨ Benar sekali! Jawaban Anda sangat tepat.";
            } else {
                options[idx].classList.add('border-red-500', 'bg-red-900/40');
                options[q.answer].classList.add('border-green-500', 'bg-green-900/40');
                feedback.className = "p-4 rounded-xl mb-6 text-sm bg-red-900/40 border border-red-500 text-red-300";
                feedback.textContent = `❌ Jawaban kurang tepat. Jawaban benar: ${q.options[q.answer]}`;
            }

            feedback.classList.remove('hidden');
            document.getElementById('next-btn').classList.remove('hidden');
        }

        function nextQuestion() {
            currentQuestion++;
            if (currentQuestion < quizData.length) loadQuiz();
            else {
                document.getElementById('quiz-container').classList.add('hidden');
                document.getElementById('quiz-result').classList.remove('hidden');
                document.getElementById('final-score').textContent = quizScore;
                document.getElementById('total-score').textContent = quizData.length;
            }
        }

        function restartQuiz() {
            currentQuestion = 0;
            quizScore = 0;
            document.getElementById('quiz-result').classList.add('hidden');
            document.getElementById('quiz-container').classList.remove('hidden');
            loadQuiz();
        }

        window.onload = loadQuiz;
    </script>
</body>
</html>
