---
title: 12 Days Editing Page
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>12 Days of Subscriptions | Recurly Navigate</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    colors: {
                        recurly: {
                            purple: '#4a2c82', // Approximated Recurly deep purple
                            light: '#f8f9fc',
                            accent: '#8b5cf6'
                        },
                        festive: {
                            gold: '#fbbf24',
                            silver: '#e2e8f0',
                            glow: '#fef3c7'
                        }
                    },
                    animation: {
                        'float': 'float 6s ease-in-out infinite',
                        'pulse-slow': 'pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                    },
                    keyframes: {
                        float: {
                            '0%, 100%': { transform: 'translateY(0)' },
                            '50%': { transform: 'translateY(-10px)' },
                        }
                    }
                }
            }
        }
    </script>
    <style>
        /* Subtle snow/sparkle background for the hero */
        .festive-bg {
            background-color: #311b5e; /* Deep purple */
            background-image: 
                radial-gradient(circle at 15% 50%, rgba(251, 191, 36, 0.15) 0%, transparent 25%),
                radial-gradient(circle at 85% 30%, rgba(139, 92, 246, 0.2) 0%, transparent 25%);
        }
        
        .snow-overlay {
            position: absolute;
            top: 0; left: 0; right: 0; bottom: 0;
            background-image: url("data:image/svg+xml,%3Csvg width='400' height='400' xmlns='http://www.w3.org/2000/svg'%3E%3Ccircle cx='50' cy='50' r='2' fill='white' fill-opacity='0.1'/%3E%3Ccircle cx='200' cy='150' r='1.5' fill='white' fill-opacity='0.2'/%3E%3Ccircle cx='350' cy='50' r='1' fill='white' fill-opacity='0.1'/%3E%3Ccircle cx='100' cy='300' r='2' fill='white' fill-opacity='0.15'/%3E%3Ccircle cx='250' cy='350' r='1' fill='white' fill-opacity='0.1'/%3E%3C/svg%3E");
            opacity: 0.6;
            pointer-events: none;
        }

        /* Advent Door styling */
        .advent-door {
            transition: all 0.3s ease;
            transform-style: preserve-3d;
        }
        .advent-door:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
            border-color: #fbbf24; /* Festive Gold */
        }
        
        .door-unlocked {
            background: linear-gradient(135deg, #ffffff 0%, #f8f9fc 100%);
            border: 2px solid #e2e8f0;
        }
        
        .door-current {
            background: linear-gradient(135deg, #ffffff 0%, #fef3c7 100%);
            border: 2px solid #fbbf24;
            box-shadow: 0 0 15px rgba(251, 191, 36, 0.3);
        }
        
        .door-locked {
            background: #f1f5f9;
            border: 2px dashed #cbd5e1;
            opacity: 0.8;
            cursor: not-allowed;
        }
        .door-locked:hover {
            transform: none;
            box-shadow: none;
            border-color: #cbd5e1;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 antialiased selection:bg-recurly-accent selection:text-white">

    <!-- Navigation Bar (Mocking Readme/Navigate feel) -->
    <nav class="bg-white border-b border-slate-200 sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-16 items-center">
                <div class="flex items-center gap-2">
                    <!-- Placeholder Recurly Logo -->
                    <div class="w-8 h-8 bg-recurly-purple rounded flex items-center justify-center text-white font-bold text-xl">R</div>
                    <span class="font-semibold text-lg text-slate-900 tracking-tight">Navigate</span>
                    <span class="ml-2 px-2 py-0.5 rounded text-xs font-medium bg-indigo-100 text-indigo-800">Campaign</span>
                </div>
                <div class="hidden md:flex space-x-8 text-sm font-medium text-slate-600">
                    <a href="#" class="hover:text-recurly-purple transition-colors">Launch</a>
                    <a href="#" class="hover:text-recurly-purple transition-colors">Acquire</a>
                    <a href="#" class="hover:text-recurly-purple transition-colors">Retain</a>
                    <a href="#" class="hover:text-recurly-purple transition-colors">Scale</a>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <header class="relative festive-bg text-white overflow-hidden py-20 lg:py-28">
        <div class="snow-overlay"></div>
        
        <!-- Decorative background elements -->
        <div class="absolute top-10 left-10 w-24 h-24 bg-festive-gold rounded-full mix-blend-multiply filter blur-2xl opacity-30 animate-float"></div>
        <div class="absolute bottom-10 right-10 w-32 h-32 bg-purple-400 rounded-full mix-blend-multiply filter blur-2xl opacity-30 animate-float" style="animation-delay: 2s;"></div>

        <div class="relative max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 text-center z-10">
            <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/10 border border-white/20 backdrop-blur-sm text-sm font-medium text-festive-glow mb-6">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m22 2-7 20-4-9-9-4Z"/><path d="M22 2 11 13"/></svg>
                Leading up to the Q1 2027 Strategy Webinar
            </div>
            
            <h1 class="text-5xl md:text-6xl font-extrabold tracking-tight mb-6 drop-shadow-md">
                12 Days of <span class="text-transparent bg-clip-text bg-gradient-to-r from-festive-gold to-yellow-200">Subscriptions</span>
            </h1>
            
            <p class="text-lg md:text-xl text-indigo-100 max-w-3xl mx-auto mb-10 leading-relaxed">
                Unwrap a new strategy, tip, or mini-quiz every day. Master your subscription foundation and earn exclusive prizes as we gear up for our biggest webinar event of the year.
            </p>

            <button class="bg-festive-gold text-slate-900 px-8 py-3.5 rounded-lg font-semibold text-lg hover:bg-yellow-300 transition-colors shadow-lg shadow-yellow-500/20">
                Start Today's Activity
            </button>
        </div>
    </header>

    <!-- Prizes & Motivation Banner -->
    <section class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 -mt-8 relative z-20">
        <div class="bg-white rounded-2xl shadow-xl border border-slate-100 p-1">
            <div class="bg-gradient-to-r from-slate-50 to-indigo-50/50 rounded-xl p-6 md:p-8 flex flex-col md:flex-row items-center justify-between gap-6 border border-white">
                <div class="flex items-start gap-4">
                    <div class="w-12 h-12 bg-indigo-100 text-indigo-600 rounded-full flex items-center justify-center shrink-0">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M6 9H4.5a2.5 2.5 0 0 1 0-5H6"/><path d="M18 9h1.5a2.5 2.5 0 0 0 0-5H18"/><path d="M4 22h16"/><path d="M10 14.66V17c0 .55-.47.98-.97 1.21C7.85 18.75 7 20.24 7 22"/><path d="M14 14.66V17c0 .55.47.98.97 1.21C16.15 18.75 17 20.24 17 22"/><path d="M18 2H6v7a6 6 0 0 0 12 0V2Z"/></svg>
                    </div>
                    <div>
                        <h3 class="text-xl font-bold text-slate-900 mb-1">Participate & Win Big!</h3>
                        <p class="text-slate-600">The most active participants who complete daily tasks will be entered to win exclusive Recurly swag and tech prizes during the Q1 2027 Webinar.</p>
                    </div>
                </div>
                <div class="shrink-0 w-full md:w-auto">
                    <a href="#tracking-form" class="block w-full md:w-auto text-center px-6 py-2.5 bg-white border-2 border-indigo-100 text-indigo-700 font-medium rounded-lg hover:bg-indigo-50 hover:border-indigo-200 transition-colors">
                        Log Your Progress ↓
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- Advent Calendar Grid -->
    <main class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <div class="text-center mb-12">
            <h2 class="text-3xl font-bold text-slate-900 mb-4">Your Daily Subscription Gifts</h2>
            <p class="text-slate-600 max-w-2xl mx-auto">Click a door to unlock today's activity. Catch up on past days, but no peeking at the future!</p>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 md:gap-6">
            
            <!-- Day 1: Completed / Unlocked -->
            <a href="#" class="advent-door door-unlocked rounded-xl p-6 relative group flex flex-col h-full min-h-[160px]">
                <div class="absolute top-4 right-4 text-green-500">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                </div>
                <span class="text-4xl font-black text-slate-200 group-hover:text-indigo-100 transition-colors absolute bottom-2 right-4 z-0">1</span>
                <div class="relative z-10 flex flex-col h-full">
                    <div class="text-xs font-bold uppercase tracking-wider text-indigo-600 mb-2 flex items-center gap-1.5">
                        <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m22 8-6 4 6 4V8Z"/><rect x="2" y="6" width="14" height="12" rx="2" ry="2"/></svg>
                        Video
                    </div>
                    <h4 class="font-bold text-slate-800 text-lg leading-tight mb-2">Foundation Launch</h4>
                    <p class="text-sm text-slate-500 mt-auto">Completed</p>
                </div>
            </a>

            <!-- Day 2: Completed / Unlocked -->
            <a href="#" class="advent-door door-unlocked rounded-xl p-6 relative group flex flex-col h-full min-h-[160px]">
                <div class="absolute top-4 right-4 text-green-500">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                </div>
                <span class="text-4xl font-black text-slate-200 group-hover:text-indigo-100 transition-colors absolute bottom-2 right-4 z-0">2</span>
                <div class="relative z-10 flex flex-col h-full">
                    <div class="text-xs font-bold uppercase tracking-wider text-amber-600 mb-2 flex items-center gap-1.5">
                        <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m8 3 4 8 5-5 5 15H2L8 3z"/></svg>
                        Tip
                    </div>
                    <h4 class="font-bold text-slate-800 text-lg leading-tight mb-2">Convert Customers Faster</h4>
                    <p class="text-sm text-slate-500 mt-auto">Completed</p>
                </div>
            </a>

            <!-- Day 3: Completed / Unlocked -->
            <a href="#" class="advent-door door-unlocked rounded-xl p-6 relative group flex flex-col h-full min-h-[160px]">
                 <div class="absolute top-4 right-4 text-green-500">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                </div>
                <span class="text-4xl font-black text-slate-200 group-hover:text-indigo-100 transition-colors absolute bottom-2 right-4 z-0">3</span>
                <div class="relative z-10 flex flex-col h-full">
                    <div class="text-xs font-bold uppercase tracking-wider text-emerald-600 mb-2 flex items-center gap-1.5">
                        <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><path d="M9.09 9a3 3 0 0 1 5.83 1c0 2-3 3-3 3"/><line x1="12" y1="17" x2="12.01" y2="17"/></svg>
                        Quiz
                    </div>
                    <h4 class="font-bold text-slate-800 text-lg leading-tight mb-2">Account Updater Knowledge</h4>
                    <p class="text-sm text-slate-500 mt-auto">Completed</p>
                </div>
            </a>

            <!-- Day 4: Current Day (Action Needed) -->
            <a href="#" class="advent-door door-current rounded-xl p-6 relative group flex flex-col h-full min-h-[160px] cursor-pointer">
                <div class="absolute -top-2 -right-2 bg-red-500 text-white text-xs font-bold px-2 py-1 rounded-full shadow-sm animate-pulse-slow">
                    New!
                </div>
                <span class="text-4xl font-black text-amber-200/50 group-hover:text-amber-200 transition-colors absolute bottom-2 right-4 z-0">4</span>
                <div class="relative z-10 flex flex-col h-full">
                    <div class="text-xs font-bold uppercase tracking-wider text-indigo-600 mb-2 flex items-center gap-1.5">
                        <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m22 8-6 4 6 4V8Z"/><rect x="2" y="6" width="14" height="12" rx="2" ry="2"/></svg>
                        Video
                    </div>
                    <h4 class="font-bold text-slate-900 text-lg leading-tight mb-2">Mastering Dunning & Retries</h4>
                    <p class="text-sm text-amber-700 font-medium mt-auto flex items-center gap-1">
                        Watch Now <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>
                    </p>
                </div>
            </a>

            <!-- Days 5 through 12: Locked -->
            <div class="advent-door door-locked rounded-xl p-6 relative flex flex-col h-full min-h-[160px] justify-center items-center text-center">
                <svg class="text-slate-400 mb-2" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
                <span class="text-3xl font-bold text-slate-300">5</span>
            </div>
            
            <div class="advent-door door-locked rounded-xl p-6 relative flex flex-col h-full min-h-[160px] justify-center items-center text-center">
                <svg class="text-slate-400 mb-2" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
                <span class="text-3xl font-bold text-slate-300">6</span>
            </div>

            <div class="advent-door door-locked rounded-xl p-6 relative flex flex-col h-full min-h-[160px] justify-center items-center text-center">
                <svg class="text-slate-400 mb-2" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
                <span class="text-3xl font-bold text-slate-300">7</span>
            </div>

            <div class="advent-door door-locked rounded-xl p-6 relative flex flex-col h-full min-h-[160px] justify-center items-center text-center">
                <svg class="text-slate-400 mb-2" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
                <span class="text-3xl font-bold text-slate-300">8</span>
            </div>

            <div class="advent-door door-locked rounded-xl p-6 relative flex flex-col h-full min-h-[160px] justify-center items-center text-center">
                <svg class="text-slate-400 mb-2" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
                <span class="text-3xl font-bold text-slate-300">9</span>
            </div>

            <div class="advent-door door-locked rounded-xl p-6 relative flex flex-col h-full min-h-[160px] justify-center items-center text-center">
                <svg class="text-slate-400 mb-2" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
                <span class="text-3xl font-bold text-slate-300">10</span>
            </div>

            <div class="advent-door door-locked rounded-xl p-6 relative flex flex-col h-full min-h-[160px] justify-center items-center text-center">
                <svg class="text-slate-400 mb-2" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
                <span class="text-3xl font-bold text-slate-300">11</span>
            </div>

            <div class="advent-door door-locked rounded-xl p-6 relative flex flex-col h-full min-h-[160px] justify-center items-center text-center">
                <svg class="text-slate-400 mb-2" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
                <span class="text-3xl font-bold text-slate-300">12</span>
            </div>

        </div>
    </main>

    <!-- Activity Tracker / Form Embed Section -->
    <section id="tracking-form" class="bg-white border-t border-slate-200 py-20">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-8">
                <div class="inline-block bg-indigo-50 text-indigo-700 px-3 py-1 rounded-full text-sm font-semibold mb-3">Activity Tracker</div>
                <h2 class="text-3xl font-bold text-slate-900 mb-4">Log Your Progress</h2>
                <p class="text-slate-600">Finished today's video or quiz? Log it below to ensure you get credit towards the grand prizes drawn during the Q1 2027 Webinar.</p>
            </div>

            <!-- Form Placeholder Container -->
            <div class="bg-slate-50 border border-slate-200 rounded-2xl shadow-inner p-4 md:p-8">
                <!-- Visual mock of where the iframe goes -->
                <div class="border-2 border-dashed border-slate-300 rounded-xl bg-white flex flex-col items-center justify-center min-h-[400px] text-slate-400 p-8 text-center relative overflow-hidden">
                    
                    <!-- Faux form UI for visualization purposes -->
                    <div class="absolute inset-0 opacity-20 pointer-events-none flex flex-col gap-4 p-8">
                        <div class="h-8 bg-slate-300 rounded w-1/3 mx-auto mb-4"></div>
                        <div class="h-10 bg-slate-200 rounded w-full"></div>
                        <div class="h-10 bg-slate-200 rounded w-full"></div>
                        <div class="h-24 bg-slate-200 rounded w-full"></div>
                        <div class="h-10 bg-slate-400 rounded w-1/4 mt-4"></div>
                    </div>

                    <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="mb-4 z-10"><path d="M14.5 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V7.5L14.5 2z"/><polyline points="14 2 14 8 20 8"/><path d="M16 13H8"/><path d="M16 17H8"/><path d="M10 9H8"/></svg>
                    <p class="font-medium text-slate-600 z-10">Wrike Form Embed Placeholder</p>
                    <p class="text-sm z-10 mt-2 max-w-xs">Insert your Wrike form iframe code here within the Readme platform editor.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Simple Footer -->
    <footer class="bg-slate-900 text-slate-400 py-12 text-center text-sm">
        <div class="max-w-7xl mx-auto px-4">
            <p class="mb-2">© 2026 Recurly, Inc. All rights reserved.</p>
            <p>12 Days of Subscriptions Campaign · Leading to the Q1 2027 Webinar</p>
        </div>
    </footer>

</body>
</html>
`}</HTMLBlock>
