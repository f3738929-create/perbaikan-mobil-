
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aplikasi Perbaiki Mobil</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome untuk ikon -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts: Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style> body { font-family: 'Inter', sans-serif; } </style>
</head>
<body class="bg-slate-100 text-slate-800 flex h-screen overflow-hidden">

    <!-- SIDEBAR -->
    <aside class="w-64 bg-slate-900 text-slate-300 flex flex-col justify-between hidden md:flex">
        <div>
            <div class="p-5 border-b border-slate-800 flex items-center space-x-3">
                <i class="fa-solid fa-car-wrench text-blue-500 text-2xl"></i>
                <span class="text-lg font-bold text-white tracking-wide">Perbaiki Mobil</span>
            </div>
            <nav class="p-4 space-y-1">
                <button onclick="switchTab('dashboard')" id="nav-dashboard" class="w-full flex items-center space-x-3 px-4 py-3 rounded-lg text-sm font-medium transition bg-blue-600 text-white">
                    <i class="fa-solid fa-chart-pie w-5"></i><span>Dashboard</span>
                </button>
                <button onclick="switchTab('input')" id="nav-input" class="w-full flex items-center space-x-3 px-4 py-3 rounded-lg text-sm font-medium transition hover:bg-slate-800 hover:text-white">
                    <i class="fa-solid fa-user-plus w-5"></i><span>Input Data & Keluhan</span>
                </button>
                <button onclick="switchTab('perbaikan')" id="nav-perbaikan" class="w-full flex items-center space-x-3 px-4 py-3 rounded-lg text-sm font-medium transition hover:bg-slate-800 hover:text-white">
                    <i class="fa-solid fa-screwdriver-wrench w-5"></i><span>Proses Perbaikan</span>
                </button>
            </nav>
        </div>
        <div class="p-4 border-t border-slate-800 text-xs text-slate-500 text-center">
            &copy; 2026 Perbaiki Mobil App
        </div>
    </aside>

    <!-- MAIN CONTENT CONTAINER -->
    <div class="flex-1 flex flex-col h-screen overflow-hidden">
        
        <!-- HEADER -->
        <header class="bg-white shadow-sm h-16 flex items-center justify-between px-6 z-10">
            <div class="flex items-center space-x-3 md:hidden">
                <i class="fa-solid fa-car-wrench text-blue-600 text-xl"></i>
                <span class="font-bold text-gray-800">Perbaiki Mobil</span>
            </div>
            <h1 id="page-title" class="text-xl font-bold text-gray-800 hidden md:block">Dashboard</h1>
            <div class="flex items-center space-x-3">
                <span class="text-sm font-medium text-gray-600">Admin Bengkel</span>
                <div class="w-9 h-9 bg-blue-600 text-white rounded-full flex items-center justify-center font-bold">A</div>
            </div>
        </header>

        <!-- MOBILE NAVIGATION (BOTTOM) -->
        <div class="bg-white border-t border-gray-200 flex md:hidden justify-around p-2 z-10">
            <button onclick="switchTab('dashboard')" id="mob-dashboard" class="flex flex-col items-center text-blue-600 text-xs font-medium">
                <i class="fa-solid fa-chart-pie text-lg mb-1"></i><span>Dashboard</span>
            </button>
            <button onclick="switchTab('input')" id="mob-input" class="flex flex-col items-center text-gray-500 text-xs font-medium">
                <i class="fa-solid fa-user-plus text-lg mb-1"></i><span>Input Pelanggan</span>
            </button>
            <button onclick="switchTab('perbaikan')" id="mob-perbaikan" class="flex flex-col items-center text-gray-500 text-xs font-medium">
                <i class="fa-solid fa-screwdriver-wrench text-lg mb-1"></i><span>Perbaikan</span>
            </button>
        </div>

        <!-- CONTENT BODY -->
        <main class="flex-1 overflow-y-auto p-6 bg-slate-50">

            <!-- TAB 1: DASHBOARD -->
            <section id="tab-dashboard" class="space-y-6">
                <!-- Stat Cards -->
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
                    <div class="bg-white p-5 rounded-xl shadow-sm border border-gray-100 flex items-center justify-between">
                        <div>
                            <p class="text-xs font-medium text-gray-500 uppercase tracking-wider">Total Mobil Masuk</p>
                            <h3 id="stat-total" class="text-2xl font-bold text-gray-800 mt-1">0</h3>
                        </div>
                        <div class="w-12 h-12 bg-blue-50 text-blue-600 rounded-xl flex items-center justify-center text-xl">
                            <i class="fa-solid fa-car"></i>
                        </div>
                    </div>
                    <div class="bg-white p-5 rounded-xl shadow-sm border border-gray-100 flex items-center justify-between">
                        <div>
                            <p class="text-xs font-medium text-gray-500 uppercase tracking-wider">Dalam Perbaikan</p>
                            <h3
