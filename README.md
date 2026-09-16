<!DOCTYPE html>
<html lang="es" class="dark">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cristian Lamas | Full Stack Architect & Digital Health Profile</title>
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Google Fonts Inter & JetBrains Mono -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600;700&display=swap" rel="stylesheet">
  
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
            mono: ['JetBrains Mono', 'monospace'],
          },
          colors: {
            albiceleste: {
              50: '#f0f7fe',
              100: '#dbeafe',
              200: '#b9dbfd',
              300: '#93c5fd',
              400: '#60a5fa',
              500: '#74ACDF',
              600: '#2563eb',
              700: '#1d4ed8',
              800: '#1e40af',
              900: '#0A192F',
            }
          }
        }
      }
    }
  </script>
  <style>
    /* Custom scrollbar */
    ::-webkit-scrollbar {
      width: 8px;
      height: 8px;
    }
    ::-webkit-scrollbar-track {
      background: rgba(15, 23, 42, 0.6);
    }
    ::-webkit-scrollbar-thumb {
      background: #334155;
      border-radius: 4px;
    }
    ::-webkit-scrollbar-thumb:hover {
      background: #74ACDF;
    }
    
    .typing-cursor::after {
      content: '|';
      animation: blink 1s infinite;
      color: #74ACDF;
    }
    @keyframes blink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0; }
    }
    
    .glow-cyan {
      box-shadow: 0 0 25px -5px rgba(116, 172, 223, 0.3);
    }
    .glow-cyan-sm {
      box-shadow: 0 0 12px -2px rgba(116, 172, 223, 0.25);
    }
  </style>
</head>
<body class="bg-slate-950 text-slate-100 font-sans min-h-screen selection:bg-sky-500 selection:text-white flex flex-col">

  <!-- Top Navigation & View Mode Switcher -->
  <header class="sticky top-0 z-50 bg-slate-900/90 backdrop-blur-md border-b border-slate-800">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
      <div class="flex items-center space-x-3">
        <div class="w-9 h-9 rounded-xl bg-gradient-to-br from-blue-600 via-sky-500 to-cyan-300 flex items-center justify-center font-mono font-bold text-white shadow-lg shadow-sky-500/20">
          CL
        </div>
        <div>
          <div class="flex items-center space-x-2">
            <h1 class="text-sm font-bold tracking-tight text-white">Cristian Lamas</h1>
            <span class="inline-flex items-center px-2 py-0.5 rounded text-[10px] font-semibold bg-sky-500/10 text-sky-400 border border-sky-500/20">
              Salud Digital & Arch
            </span>
          </div>
          <p class="text-xs text-slate-400">HIGA Gral. San Martín • UNLP Informática</p>
        </div>
      </div>

      <!-- Controls & View Selectors -->
      <div class="flex items-center space-x-2 sm:space-x-3">
        <!-- View Toggle Pills -->
        <div class="bg-slate-950 p-1 rounded-lg border border-slate-800 flex items-center text-xs">
          <button id="btnViewGithub" onclick="switchView('github')" class="px-3 py-1.5 rounded-md font-medium transition-all bg-sky-600 text-white shadow-sm flex items-center space-x-1.5">
            <svg class="w-3.5 h-3.5" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>
            <span class="hidden sm:inline">Vista README</span>
          </button>
          <button id="btnViewSaluz" onclick="switchView('saluz')" class="px-3 py-1.5 rounded-md font-medium text-slate-400 hover:text-slate-200 transition-all flex items-center space-x-1.5">
            <svg class="w-3.5 h-3.5 text-sky-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"/></svg>
            <span>Arquitectura SALUZ</span>
          </button>
          <button id="btnViewCode" onclick="switchView('code')" class="px-3 py-1.5 rounded-md font-medium text-slate-400 hover:text-slate-200 transition-all flex items-center space-x-1.5">
            <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"/></svg>
            <span class="hidden sm:inline">Código Markdown</span>
          </button>
        </div>

        <!-- Copy Markdown Button -->
        <button onclick="copyMarkdownContent()" class="bg-gradient-to-r from-sky-600 to-blue-600 hover:from-sky-500 hover:to-blue-500 text-white text-xs font-semibold px-3 py-2 rounded-lg transition-all shadow-md shadow-sky-500/20 flex items-center space-x-1.5 active:scale-95">
          <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 5H6a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2v-1M8 5a2 2 0 002 2h2a2 2 0 002-2M8 5a2 2 0 012-2h2a2 2 0 012 2m0 0h2a2 2 0 012 2v3m2 4H10m0 0l3-3m-3 3l3 3"/></svg>
          <span id="copyBtnText">Copiar README</span>
        </button>
      </div>
    </div>
  </header>

  <main class="flex-1 max-w-5xl w-full mx-auto p-4 sm:p-6 lg:p-8">

    <!-- TAB 1: GITHUB LIVE VIEW -->
    <div id="viewGithub" class="space-y-6">
      
      <!-- GitHub Container Simulation Box -->
      <div class="bg-slate-900 border border-slate-800 rounded-2xl p-4 sm:p-8 shadow-2xl relative overflow-hidden">
        
        <!-- Subtle Argentina Gradient Accent bar -->
        <div class="absolute top-0 left-0 right-0 h-1 bg-gradient-to-r from-sky-500 via-white to-sky-500 opacity-75"></div>
        
        <!-- GitHub Header Capsule Render Mock -->
        <div class="rounded-xl overflow-hidden mb-6 border border-slate-800/80 shadow-lg relative bg-[#0A192F]">
          <svg viewBox="0 0 800 200" class="w-full h-auto block select-none">
            <defs>
              <linearGradient id="argHeader" x1="0%" y1="0%" x2="100%" y2="100%">
                <stop offset="0%" stop-color="#0A192F" />
                <stop offset="45%" stop-color="#1E3A8A" />
                <stop offset="75%" stop-color="#2563EB" />
                <stop offset="100%" stop-color="#74ACDF" />
              </linearGradient>
            </defs>
            <path d="M0,0 L800,0 L800,160 Q600,210 400,160 Q200,110 0,160 Z" fill="url(#argHeader)" opacity="0.95" />
            <text x="50%" y="42%" dominant-baseline="middle" text-anchor="middle" font-family="Inter, sans-serif" font-weight="800" font-size="34" fill="#FFFFFF" letter-spacing="1">CRISTIAN LAMAS</text>
            <text x="50%" y="62%" dominant-baseline="middle" text-anchor="middle" font-family="Inter, sans-serif" font-weight="500" font-size="14" fill="#E2E8F0" letter-spacing="0.5">Full Stack Architect | Digital Health Systems</text>
            <!-- Sun of May stylized accent in SVG -->
            <circle cx="730" cy="50" r="18" fill="#FBBF24" opacity="0.2" />
            <circle cx="730" cy="50" r="8" fill="#FBBF24" opacity="0.6" />
          </svg>
        </div>

        <!-- Live Typing Simulator -->
        <div class="text-center mb-6 py-2">
          <div class="inline-block px-4 py-2 rounded-lg bg-slate-950/70 border border-slate-800 font-mono text-xs sm:text-sm font-semibold text-sky-400">
            <span id="typingOutput"></span><span class="typing-cursor"></span>
          </div>
        </div>

        <!-- Contact Badges Simulation -->
        <div class="flex flex-wrap items-center justify-center gap-2 mb-8">
          <a href="https://www.linkedin.com/in/crslamas/" target="_blank" class="inline-flex items-center px-3 py-1 rounded bg-[#0A66C2] text-white text-xs font-semibold hover:opacity-90 transition">
            <svg class="w-3.5 h-3.5 mr-1.5 fill-current" viewBox="0 0 24 24"><path d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h14m-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.28 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93h2.75M6.46 10.9v8.37H9.25V10.9H6.46M7.86 6.55a1.64 1.64 0 0 0-1.66 1.64 1.65 1.65 0 0 0 1.66 1.65 1.65 1.65 0 0 0 1.65-1.65 1.65 1.65 0 0 0-1.65-1.64Z"/></svg>
            LinkedIn Connect
          </a>
          <a href="mailto:crslamas@gmail.com" class="inline-flex items-center px-3 py-1 rounded bg-[#D14836] text-white text-xs font-semibold hover:opacity-90 transition">
            <svg class="w-3.5 h-3.5 mr-1.5 fill-current" viewBox="0 0 24 24"><path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
            crslamas@gmail.com
          </a>
          <span class="inline-flex items-center px-3 py-1 rounded bg-[#2A4365] text-[#74ACDF] border border-sky-500/30 text-xs font-semibold">
            📍 Argentina
          </span>
          <span class="inline-flex items-center px-3 py-1 rounded bg-emerald-950/80 text-emerald-300 border border-emerald-500/30 text-xs font-semibold">
            🎯 Salud Pública Hospitalaria
          </span>
        </div>

        <div class="h-px bg-slate-800 my-8"></div>

        <!-- Perfil & Salud Digital -->
        <section class="space-y-4 text-slate-300 text-sm leading-relaxed">
          <h2 class="text-xl font-bold text-white flex items-center space-x-2">
            <span>👨‍💻</span>
            <span>Perfil &amp; Salud Digital</span>
          </h2>
          <p>
            Desarrollador Full Stack con <strong class="text-white">más de 4 años de experiencia activa en el ámbito de la salud pública</strong> (<span class="text-sky-300 font-medium">HIGA Gral. San Martín</span>) y especialización formal en <strong class="text-white">Salud Digital</strong>. Diseño e implemento arquitecturas desacopladas orientadas al dominio sanitario, transformando flujos hospitalarios críticos en plataformas modulares, seguras, auditables y sin fricción técnica para equipos médicos y administrativos.
          </p>

          <div class="grid grid-cols-1 md:grid-cols-3 gap-3 pt-2">
            <div class="p-3.5 rounded-xl bg-slate-950/60 border border-slate-800 flex items-start space-x-3">
              <div class="p-2 rounded-lg bg-sky-500/10 text-sky-400 font-bold">🏛️</div>
              <div>
                <p class="text-xs text-slate-400 font-medium">Formación Base</p>
                <p class="text-xs font-bold text-slate-200">Facultad de Informática (UNLP)</p>
                <p class="text-[11px] text-slate-400">Lic. en Sistemas • APU • Analista TIC</p>
              </div>
            </div>

            <div class="p-3.5 rounded-xl bg-slate-950/60 border border-slate-800 flex items-start space-x-3">
              <div class="p-2 rounded-lg bg-emerald-500/10 text-emerald-400 font-bold">📜</div>
              <div>
                <p class="text-xs text-slate-400 font-medium">Especialización</p>
                <p class="text-xs font-bold text-slate-200">Salud Digital (UNPAZ)</p>
                <p class="text-[11px] text-slate-400">Diplomatura Sanitaria &amp; Gobernanza</p>
              </div>
            </div>

            <div class="p-3.5 rounded-xl bg-slate-950/60 border border-slate-800 flex items-start space-x-3">
              <div class="p-2 rounded-lg bg-indigo-500/10 text-indigo-400 font-bold">🛡️</div>
              <div>
                <p class="text-xs text-slate-400 font-medium">Foco de Dominio</p>
                <p class="text-xs font-bold text-slate-200">Arquitectura Hospitalaria</p>
                <p class="text-[11px] text-slate-400">PKI eSign, SISA &amp; Modular Core</p>
              </div>
            </div>
          </div>
        </section>

        <div class="h-px bg-slate-800 my-8"></div>

        <!-- Proyecto Central: SALUZ -->
        <section class="space-y-4">
          <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-2">
            <h2 class="text-xl font-bold text-white flex items-center space-x-2">
              <span>🏥</span>
              <span>Proyecto Central: <span class="text-sky-400">SALUZ</span></span>
            </h2>
            <span class="inline-flex items-center px-2.5 py-1 rounded-full text-xs font-semibold bg-sky-500/10 text-sky-300 border border-sky-500/30">
              Ecosistema Modular Hospitalario
            </span>
          </div>

          <p class="text-sm text-slate-300 leading-relaxed">
            Plataforma integral y modular diseñada para centralizar la gestión de <strong>Workforce Sanitario</strong>, trazabilidad patrimonial de equipamiento médico, arquitectura física de sedes/salas/camas y procesos de auditoría inmutable con validación criptográfica de firmas.
          </p>

          <!-- ASCII System Topology Block -->
          <div class="bg-slate-950 rounded-xl p-4 border border-slate-800 font-mono text-[11px] sm:text-xs text-sky-300 overflow-x-auto leading-tight shadow-inner">
<pre>┌────────────────────────────────────────────────────────────────────────┐
│                        SALUZ SYSTEM TOPOLOGY                           │
│                                                                        │
│   [ Livewire 3 + Volt ] ─────── [ Flux UI ] ─────── [ PowerGrid ]      │
│            │                          │                      │         │
│   ┌────────┴──────────────────────────┴──────────────────────┴─────┐   │
│   │                        MODULAR DOMAIN ENGINE                   │   │
│   │   • Workforce    (Legajos, Guardias, Licencias, SISA)          │   │
│   │   • Architecture (Sedes, Áreas, Ubicaciones Físicas &amp; Campos)  │   │
│   │   • Patrimony    (Bienes, Movimientos, Trazabilidad de Stock)  │   │
│   │   • System       (Auditoría, Roles/Permisos, Licencias Offline)│   │
│   └────────┬──────────────────────────┬──────────────────────┬─────┘   │
│            │                          │                      │         │
│   [ Public eSign / PDF/A ]    [ Spatie Health ]    [ Laravel Reverb ]  │
│     (OpenSSL / PKI Keys)     (Monitoreo Activo)    (WebSockets Realtime)│
└────────────────────────────────────────────────────────────────────────┘</pre>
          </div>

          <!-- Interactive Details Accordion for SALUZ modules -->
          <div class="border border-slate-800 rounded-xl overflow-hidden bg-slate-950/40">
            <button onclick="toggleSaluzDetails()" class="w-full px-4 py-3 bg-slate-950/80 hover:bg-slate-800/50 flex items-center justify-between text-xs sm:text-sm font-semibold text-slate-200 transition">
              <span class="flex items-center space-x-2">
                <span>🔍</span>
                <span>Desglose Técnico de Módulos (Inspección del Repositorio)</span>
              </span>
              <span id="accordionIcon" class="text-sky-400 font-mono text-sm">▼</span>
            </button>
            <div id="accordionContent" class="p-4 border-t border-slate-800 space-y-3 text-xs">
              <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
                <div class="p-3 rounded-lg bg-slate-900 border border-slate-800">
                  <div class="flex items-center justify-between mb-1.5">
                    <span class="font-bold text-sky-400">Módulo Workforce</span>
                    <span class="text-[10px] bg-slate-800 px-2 py-0.5 rounded text-slate-300">SISA + Guardia</span>
                  </div>
                  <p class="text-slate-300 text-[11px] leading-relaxed">
                    Administración integral de agentes de salud: legajo digital, régimen estatutario, rotación de guardias, balances de licencias y homologación con catálogos federales SISA (profesiones y especialidades).
                  </p>
                </div>

                <div class="p-3 rounded-lg bg-slate-900 border border-slate-800">
                  <div class="flex items-center justify-between mb-1.5">
                    <span class="font-bold text-sky-400">Módulo Architecture</span>
                    <span class="text-[10px] bg-slate-800 px-2 py-0.5 rounded text-slate-300">Infraestructura</span>
                  </div>
                  <p class="text-slate-300 text-[11px] leading-relaxed">
                    Modelado de la topología física hospitalaria: sedes, pabellones, salas, camas y soporte de campos dinámicos EAV (Custom Location Fields).
                  </p>
                </div>

                <div class="p-3 rounded-lg bg-slate-900 border border-slate-800">
                  <div class="flex items-center justify-between mb-1.5">
                    <span class="font-bold text-sky-400">Módulo Patrimony</span>
                    <span class="text-[10px] bg-slate-800 px-2 py-0.5 rounded text-slate-300">PowerGrid Tables</span>
                  </div>
                  <p class="text-slate-300 text-[11px] leading-relaxed">
                    Inventario de bienes, control de ciclo de vida del equipamiento médico, estados de conservación y trazabilidad forense de movimientos internos.
                  </p>
                </div>

                <div class="p-3 rounded-lg bg-slate-900 border border-slate-800">
                  <div class="flex items-center justify-between mb-1.5">
                    <span class="font-bold text-sky-400">Módulo System &amp; eSign</span>
                    <span class="text-[10px] bg-slate-800 px-2 py-0.5 rounded text-slate-300">OpenSSL + PKI</span>
                  </div>
                  <p class="text-slate-300 text-[11px] leading-relaxed">
                    Roles RBAC Spatie, registro de actividad inmutable, servicio de licencias offline para contingencia y firma criptográfica de PDF/A con verificación pública.
                  </p>
                </div>
              </div>
            </div>
          </div>
        </section>

        <div class="h-px bg-slate-800 my-8"></div>

        <!-- Stack Tecnológico -->
        <section class="space-y-4">
          <h2 class="text-xl font-bold text-white flex items-center space-x-2">
            <span>🛠️</span>
            <span>Stack Tecnológico</span>
          </h2>

          <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-3">
            <div class="p-3 rounded-xl bg-slate-950/70 border border-slate-800 flex items-center space-x-3">
              <img src="https://skillicons.dev/icons?i=php,laravel&theme=dark" alt="Backend" class="h-10">
              <div>
                <p class="text-xs font-bold text-slate-200">Backend &amp; Core</p>
                <p class="text-[11px] text-slate-400">PHP 8.x, Laravel 11/12, Modules</p>
              </div>
            </div>

            <div class="p-3 rounded-xl bg-slate-950/70 border border-slate-800 flex items-center space-x-3">
              <img src="https://skillicons.dev/icons?i=livewire,tailwind,js&theme=dark" alt="Frontend" class="h-10">
              <div>
                <p class="text-xs font-bold text-slate-200">Frontend Reactivo</p>
                <p class="text-[11px] text-slate-400">Livewire 3, Flux UI, PowerGrid</p>
              </div>
            </div>

            <div class="p-3 rounded-xl bg-slate-950/70 border border-slate-800 flex items-center space-x-3">
              <img src="https://skillicons.dev/icons?i=mysql,redis&theme=dark" alt="Databases" class="h-10">
              <div>
                <p class="text-xs font-bold text-slate-200">Datos &amp; Caché</p>
                <p class="text-[11px] text-slate-400">MySQL 8.0, Redis Memory Store</p>
              </div>
            </div>

            <div class="p-3 rounded-xl bg-slate-950/70 border border-slate-800 flex items-center space-x-3">
              <img src="https://skillicons.dev/icons?i=docker,nginx,linux&theme=dark" alt="Infra" class="h-10">
              <div>
                <p class="text-xs font-bold text-slate-200">Infraestructura</p>
                <p class="text-[11px] text-slate-400">Docker, WSL2, Linux, Nginx</p>
              </div>
            </div>

            <div class="p-3 rounded-xl bg-slate-950/70 border border-slate-800 flex items-center space-x-3">
              <img src="https://skillicons.dev/icons?i=git,github,vscode&theme=dark" alt="Herramientas" class="h-10">
              <div>
                <p class="text-xs font-bold text-slate-200">Entorno &amp; Control</p>
                <p class="text-[11px] text-slate-400">Git Flow, GitHub, Pest PHP</p>
              </div>
            </div>

            <div class="p-3 rounded-xl bg-slate-950/70 border border-slate-800 flex items-center space-x-3">
              <div class="w-10 h-10 rounded-lg bg-sky-500/10 border border-sky-500/30 flex items-center justify-center text-sky-400 font-mono font-bold text-sm">
                S3
              </div>
              <div>
                <p class="text-xs font-bold text-slate-200">Documental &amp; PKI</p>
                <p class="text-[11px] text-slate-400">MinIO, OpenSSL, PDF/A</p>
              </div>
            </div>
          </div>
        </section>

        <div class="h-px bg-slate-800 my-8"></div>

        <!-- Métricas & Actividad Global -->
        <section class="space-y-4">
          <div class="flex items-center justify-between">
            <h2 class="text-xl font-bold text-white flex items-center space-x-2">
              <span>📊</span>
              <span>Métricas &amp; Actividad Global</span>
            </h2>
            <span class="text-xs text-sky-400 bg-sky-500/10 px-2 py-0.5 rounded border border-sky-500/20">
              Privados &amp; Públicos Habilitados
            </span>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-4 pt-2">
            <!-- Github Stats Card Mock with fallback handling -->
            <div class="rounded-xl overflow-hidden bg-slate-950 border border-slate-800 p-2 flex justify-center items-center shadow-lg">
              <img 
                src="https://github-readme-stats.vercel.app/api?username=crslamas&show_icons=true&theme=tokyonight&count_private=true&include_all_commits=true&hide_border=true&bg_color=0B0F17&title_color=74ACDF&icon_color=74ACDF&text_color=E2E8F0" 
                alt="GitHub Stats de Cristian Lamas"
                class="w-full h-auto max-w-sm rounded"
                onerror="this.parentElement.innerHTML='<div class=\'p-6 text-center text-xs text-slate-400\'><p class=\'font-semibold text-slate-300\'>GitHub Stats (crslamas)</p><p class=\'mt-1 text-sky-400\'>Commits privados contabilizados</p></div>'"
              />
            </div>

            <!-- Top Languages Card Mock -->
            <div class="rounded-xl overflow-hidden bg-slate-950 border border-slate-800 p-2 flex justify-center items-center shadow-lg">
              <img 
                src="https://github-readme-stats.vercel.app/api/top-langs/?username=crslamas&layout=compact&theme=tokyonight&count_private=true&hide_border=true&bg_color=0B0F17&title_color=74ACDF&text_color=E2E8F0" 
                alt="Top Languages"
                class="w-full h-auto max-w-sm rounded"
                onerror="this.parentElement.innerHTML='<div class=\'p-6 text-center text-xs text-slate-400\'><p class=\'font-semibold text-slate-300\'>Top Lenguajes</p><p class=\'mt-1 text-sky-400\'>PHP, Blade, JS, Docker</p></div>'"
              />
            </div>
          </div>

          <!-- Streak Card Mock -->
          <div class="rounded-xl overflow-hidden bg-slate-950 border border-slate-800 p-2 flex justify-center items-center shadow-lg mt-3">
            <img 
              src="https://github-readme-streak-stats.herokuapp.com/?user=crslamas&theme=tokyonight&hide_border=true&background=0B0F17&ring=74ACDF&fire=74ACDF&currStreakLabel=74ACDF" 
              alt="GitHub Streak"
              class="w-full h-auto max-w-md rounded"
              onerror="this.parentElement.innerHTML='<div class=\'p-4 text-center text-xs text-slate-400\'>Racha de contribuciones activas contabilizadas</div>'"
            />
          </div>
        </section>

        <div class="h-px bg-slate-800 my-8"></div>

        <!-- Desarrollos Asistenciales & Experiencia de Campo -->
        <section class="space-y-4">
          <h2 class="text-xl font-bold text-white flex items-center space-x-2">
            <span>📁</span>
            <span>Desarrollos Asistenciales &amp; Experiencia de Campo</span>
          </h2>
          <p class="text-xs sm:text-sm text-slate-400">
            Sistemas reales diseñados e implementados en el ámbito hospitalario público con alta demanda operativa:
          </p>

          <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 text-xs">
            <div class="p-3.5 rounded-xl bg-slate-950/60 border border-slate-800 hover:border-slate-700 transition">
              <div class="flex items-center space-x-2 font-bold text-slate-200 mb-1">
                <span>🛏️</span>
                <span>SiGeCa (Gestión de Camas)</span>
                <span class="ml-auto text-[10px] text-emerald-400 bg-emerald-500/10 px-1.5 py-0.5 rounded">Producción</span>
              </div>
              <p class="text-slate-400 leading-relaxed text-[11px]">
                Plataforma continua para control en tiempo real de ingresos, altas, traslados internos y porcentaje de ocupación censal.
              </p>
            </div>

            <div class="p-3.5 rounded-xl bg-slate-950/60 border border-slate-800 hover:border-slate-700 transition">
              <div class="flex items-center space-x-2 font-bold text-slate-200 mb-1">
                <span>🚑</span>
                <span>Derivaciones Hospitalarias</span>
                <span class="ml-auto text-[10px] text-sky-400 bg-sky-500/10 px-1.5 py-0.5 rounded">Red Sanitaria</span>
              </div>
              <p class="text-slate-400 leading-relaxed text-[11px]">
                Gestión y seguimiento operativo del traslado coordinado de pacientes de complejidad entre nodos asistenciales.
              </p>
            </div>

            <div class="p-3.5 rounded-xl bg-slate-950/60 border border-slate-800 hover:border-slate-700 transition">
              <div class="flex items-center space-x-2 font-bold text-slate-200 mb-1">
                <span>🦴</span>
                <span>Banco de Prótesis</span>
                <span class="ml-auto text-[10px] text-emerald-400 bg-emerald-500/10 px-1.5 py-0.5 rounded">Producción</span>
              </div>
              <p class="text-slate-400 leading-relaxed text-[11px]">
                Trazabilidad integral, auditoría de expedientes y administración de inventario de implantes y prótesis ortopédicas.
              </p>
            </div>

            <div class="p-3.5 rounded-xl bg-slate-950/60 border border-slate-800 hover:border-slate-700 transition">
              <div class="flex items-center space-x-2 font-bold text-slate-200 mb-1">
                <span>🏷️</span>
                <span>CIE-10 Coder (IA Asistida)</span>
                <span class="ml-auto text-[10px] text-indigo-400 bg-indigo-500/10 px-1.5 py-0.5 rounded">IA Health</span>
              </div>
              <p class="text-slate-400 leading-relaxed text-[11px]">
                Asistente inteligente para la agilización y normalización de diagnósticos médicos según clasificaciones internacionales.
              </p>
            </div>
          </div>
        </section>

        <!-- Footer Wave Simulation -->
        <div class="mt-10 rounded-xl overflow-hidden border border-slate-800/80">
          <svg viewBox="0 0 800 60" class="w-full h-auto block select-none">
            <defs>
              <linearGradient id="argFooter" x1="0%" y1="0%" x2="100%" y2="0%">
                <stop offset="0%" stop-color="#74ACDF" />
                <stop offset="50%" stop-color="#2563EB" />
                <stop offset="100%" stop-color="#0A192F" />
              </linearGradient>
            </defs>
            <path d="M0,30 Q200,60 400,30 Q600,0 800,30 L800,60 L0,60 Z" fill="url(#argFooter)" opacity="0.9" />
          </svg>
        </div>

      </div>
    </div>

    <!-- TAB 2: SALUZ ARCHITECTURE EXPLORER -->
    <div id="viewSaluz" class="hidden space-y-6">
      <div class="bg-slate-900 border border-slate-800 rounded-2xl p-6 shadow-xl">
        <div class="flex flex-col sm:flex-row sm:items-center justify-between pb-4 border-b border-slate-800 gap-2">
          <div>
            <h2 class="text-lg font-bold text-white flex items-center space-x-2">
              <span class="w-3 h-3 rounded-full bg-emerald-400 animate-pulse"></span>
              <span>Explorador de Arquitectura: Ecosistema SALUZ</span>
            </h2>
            <p class="text-xs text-slate-400 mt-0.5">Basado en la estructura interna real de tus módulos de Laravel 11/12</p>
          </div>
          <div class="flex items-center space-x-2">
            <span class="text-xs text-slate-400">Seleccioná un módulo:</span>
          </div>
        </div>

        <!-- Module Selector Buttons -->
        <div class="grid grid-cols-2 sm:grid-cols-4 gap-2 pt-4">
          <button onclick="selectSaluzTab('workforce')" id="tabBtnWorkforce" class="saluz-nav-btn p-3 rounded-xl border border-sky-500/40 bg-sky-500/10 text-sky-300 font-semibold text-xs flex flex-col items-center justify-center text-center transition">
            <span class="text-base mb-1">👥</span>
            <span>Workforce</span>
            <span class="text-[10px] text-slate-400 font-normal">Legajos &amp; SISA</span>
          </button>
          
          <button onclick="selectSaluzTab('architecture')" id="tabBtnArchitecture" class="saluz-nav-btn p-3 rounded-xl border border-slate-800 bg-slate-950/60 text-slate-400 hover:text-slate-200 font-semibold text-xs flex flex-col items-center justify-center text-center transition">
            <span class="text-base mb-1">🏢</span>
            <span>Architecture</span>
            <span class="text-[10px] text-slate-400 font-normal">Sedes &amp; Camas</span>
          </button>

          <button onclick="selectSaluzTab('patrimony')" id="tabBtnPatrimony" class="saluz-nav-btn p-3 rounded-xl border border-slate-800 bg-slate-950/60 text-slate-400 hover:text-slate-200 font-semibold text-xs flex flex-col items-center justify-center text-center transition">
            <span class="text-base mb-1">🩺</span>
            <span>Patrimony</span>
            <span class="text-[10px] text-slate-400 font-normal">Bienes &amp; Trazabilidad</span>
          </button>

          <button onclick="selectSaluzTab('system')" id="tabBtnSystem" class="saluz-nav-btn p-3 rounded-xl border border-slate-800 bg-slate-950/60 text-slate-400 hover:text-slate-200 font-semibold text-xs flex flex-col items-center justify-center text-center transition">
            <span class="text-base mb-1">🔐</span>
            <span>System &amp; eSign</span>
            <span class="text-[10px] text-slate-400 font-normal">PKI &amp; Auditoría</span>
          </button>
        </div>

        <!-- Dynamic Module Details Display -->
        <div class="mt-6 p-5 rounded-xl bg-slate-950 border border-slate-800 space-y-4">
          
          <!-- WORKFORCE CONTENT -->
          <div id="moduleContentWorkforce" class="saluz-content space-y-4">
            <div class="flex items-center justify-between">
              <h3 class="font-bold text-white text-sm sm:text-base flex items-center space-x-2">
                <span>📁 Modules/Workforce</span>
                <span class="text-xs px-2 py-0.5 rounded bg-sky-500/20 text-sky-300 font-normal">Recurso Humano Sanitario</span>
              </h3>
              <span class="text-xs text-slate-400 font-mono">19+ Enums • 15+ Modelos</span>
            </div>

            <p class="text-xs text-slate-300 leading-relaxed">
              El núcleo operativo de capital humano hospitalario. Implementa la gestión integral de agentes con vinculación estatutaria, balances de licencias anuales/extraordinarias, cronograma de guardias y sincronización con nomencladores nacionales <strong>SISA (profesiones y especialidades médicas)</strong>.
            </p>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 text-xs">
              <div class="p-3 rounded-lg bg-slate-900 border border-slate-800">
                <span class="text-sky-400 font-semibold">Componentes Livewire Activos:</span>
                <ul class="mt-1.5 space-y-1 text-slate-300 font-mono text-[11px]">
                  <li>• AgentProfile (Personal, Studies, Family)</li>
                  <li>• ShiftsIndex &amp; GuardAssignments</li>
                  <li>• AgentLeaves &amp; LeaveBalances</li>
                  <li>• DesignationManager &amp; OrganicUnits</li>
                </ul>
              </div>
              <div class="p-3 rounded-lg bg-slate-900 border border-slate-800">
                <span class="text-sky-400 font-semibold">Catálogos &amp; Regímenes Enums:</span>
                <ul class="mt-1.5 space-y-1 text-slate-300 font-mono text-[11px]">
                  <li>• SISA Especialidades &amp; Profesiones</li>
                  <li>• StatutoryRegime &amp; WorkingHoursRegime</li>
                  <li>• GuardModality &amp; AttendanceStatus</li>
                  <li>• LeaveStatus &amp; DisabilityType</li>
                </ul>
              </div>
            </div>
          </div>

          <!-- ARCHITECTURE CONTENT -->
          <div id="moduleContentArchitecture" class="saluz-content hidden space-y-4">
            <div class="flex items-center justify-between">
              <h3 class="font-bold text-white text-sm sm:text-base flex items-center space-x-2">
                <span>📁 Modules/Architecture</span>
                <span class="text-xs px-2 py-0.5 rounded bg-sky-500/20 text-sky-300 font-normal">Estructura Hospitalaria</span>
              </h3>
              <span class="text-xs text-slate-400 font-mono">Locations &amp; Dynamic Fields</span>
            </div>

            <p class="text-xs text-slate-300 leading-relaxed">
              Modela la infraestructura espacial y funcional del centro de salud: desde sedes principales hasta sectores, servicios, salas y camas. Permite configurar campos personalizados dinámicos para cada ubicación sin alterar esquemas fijos de base de datos.
            </p>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 text-xs">
              <div class="p-3 rounded-lg bg-slate-900 border border-slate-800">
                <span class="text-sky-400 font-semibold">Modelos &amp; Servicios:</span>
                <ul class="mt-1.5 space-y-1 text-slate-300 font-mono text-[11px]">
                  <li>• Location &amp; CustomLocationField</li>
                  <li>• LocationValidationService</li>
                  <li>• ArchitectureServiceProvider</li>
                  <li>• Migrations 2026_locations_table</li>
                </ul>
              </div>
              <div class="p-3 rounded-lg bg-slate-900 border border-slate-800">
                <span class="text-sky-400 font-semibold">Vistas Reactivas:</span>
                <ul class="mt-1.5 space-y-1 text-slate-300 font-mono text-[11px]">
                  <li>• LocationsManager.php (Livewire)</li>
                  <li>• CustomFieldsManager.php</li>
                  <li>• Hierarchical Tree Selector</li>
                </ul>
              </div>
            </div>
          </div>

          <!-- PATRIMONY CONTENT -->
          <div id="moduleContentPatrimony" class="saluz-content hidden space-y-4">
            <div class="flex items-center justify-between">
              <h3 class="font-bold text-white text-sm sm:text-base flex items-center space-x-2">
                <span>📁 Modules/Patrimony</span>
                <span class="text-xs px-2 py-0.5 rounded bg-sky-500/20 text-sky-300 font-normal">Inventario &amp; Bienes</span>
              </h3>
              <span class="text-xs text-slate-400 font-mono">PowerGrid + Movements</span>
            </div>

            <p class="text-xs text-slate-300 leading-relaxed">
              Control exhaustivo del inventario de bienes hospitalarios (equipamiento de diagnóstico, mobiliario y recursos clínicos). Incluye trazabilidad de transferencias internas de sala a sala y registro de estado de conservación.
            </p>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 text-xs">
              <div class="p-3 rounded-lg bg-slate-900 border border-slate-800">
                <span class="text-sky-400 font-semibold">Trazabilidad de Movimientos:</span>
                <ul class="mt-1.5 space-y-1 text-slate-300 font-mono text-[11px]">
                  <li>• Asset, AssetMovement</li>
                  <li>• Enums: AssetStatus, AssetType</li>
                  <li>• CustomAssetField (Atributos dinámicos)</li>
                </ul>
              </div>
              <div class="p-3 rounded-lg bg-slate-900 border border-slate-800">
                <span class="text-sky-400 font-semibold">Tablas de Alto Rendimiento:</span>
                <ul class="mt-1.5 space-y-1 text-slate-300 font-mono text-[11px]">
                  <li>• AssetTable (Livewire PowerGrid)</li>
                  <li>• AssetForm &amp; AssetManager</li>
                  <li>• ExportJob (Procesamiento en cola)</li>
                </ul>
              </div>
            </div>
          </div>

          <!-- SYSTEM CONTENT -->
          <div id="moduleContentSystem" class="saluz-content hidden space-y-4">
            <div class="flex items-center justify-between">
              <h3 class="font-bold text-white text-sm sm:text-base flex items-center space-x-2">
                <span>📁 Modules/System &amp; Public eSign</span>
                <span class="text-xs px-2 py-0.5 rounded bg-sky-500/20 text-sky-300 font-normal">Seguridad &amp; Criptografía</span>
              </h3>
              <span class="text-xs text-slate-400 font-mono">OpenSSL + Offline Licenses</span>
            </div>

            <p class="text-xs text-slate-300 leading-relaxed">
              Capa de gobernanza del sistema: auditoría forense inmutable de todas las mutaciones de datos, roles Spatie, validación de licencias para operar en modo offline sin conexión a internet y un subsistema de firma digital con verificación pública mediante códigos QR.
            </p>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 text-xs">
              <div class="p-3 rounded-lg bg-slate-900 border border-slate-800">
                <span class="text-sky-400 font-semibold">Criptografía &amp; Documentos:</span>
                <ul class="mt-1.5 space-y-1 text-slate-300 font-mono text-[11px]">
                  <li>• SignService (OpenSSL PKI Keys)</li>
                  <li>• PublicEsignController (Verificación QR)</li>
                  <li>• Plantillas PDF/A para resoluciones oficiales</li>
                  <li>• HandlesEsign Trait</li>
                </ul>
              </div>
              <div class="p-3 rounded-lg bg-slate-900 border border-slate-800">
                <span class="text-sky-400 font-semibold">Auditoría &amp; Resiliencia:</span>
                <ul class="mt-1.5 space-y-1 text-slate-300 font-mono text-[11px]">
                  <li>• OfflineLicenseService (Garantía operativa)</li>
                  <li>• Spatie Health &amp; ActivityLog integrados</li>
                  <li>• UserCrud &amp; RoleCrud con permisos granulares</li>
                </ul>
              </div>
            </div>
          </div>

        </div>
      </div>
    </div>

    <!-- TAB 3: RAW MARKDOWN CODE -->
    <div id="viewCode" class="hidden space-y-4">
      <div class="bg-slate-900 border border-slate-800 rounded-2xl p-4 sm:p-6 shadow-xl">
        <div class="flex items-center justify-between pb-4 border-b border-slate-800">
          <div>
            <h2 class="text-sm sm:text-base font-bold text-white font-mono">README.md (Código Fuente)</h2>
            <p class="text-xs text-slate-400">Listo para copiar y pegar directamente en tu repositorio de GitHub</p>
          </div>
          <button onclick="copyMarkdownContent()" class="bg-sky-600 hover:bg-sky-500 text-white text-xs font-semibold px-3 py-1.5 rounded-lg transition">
            Copiar Todo
          </button>
        </div>

        <div class="relative mt-4">
          <textarea id="rawMarkdownTextarea" readonly class="w-full h-[550px] bg-slate-950 text-slate-300 font-mono text-xs p-4 rounded-xl border border-slate-800 focus:outline-none focus:border-sky-500 resize-none select-all leading-relaxed"></textarea>
        </div>
      </div>
    </div>

  </main>

  <!-- Toast Notification Message -->
  <div id="toastNotification" class="fixed bottom-6 right-6 z-50 transform translate-y-20 opacity-0 transition-all duration-300 bg-emerald-600 text-white px-4 py-3 rounded-xl shadow-2xl flex items-center space-x-3 pointer-events-none">
    <svg class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg>
    <div>
      <p class="text-xs font-bold">¡Copiado con éxito!</p>
      <p class="text-[11px] text-emerald-100">El código Markdown ya está en tu portapapeles.</p>
    </div>
  </div>

  <script>
    // Exact Markdown Content definition
    const markdownContent = `<div align="center">

  <!-- Header Dinámico con Identidad Visual Albiceleste & Tech Blue -->
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0A192F,50:2A4365,100:74ACDF&height=210&section=header&text=Cristian%20Lamas&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Full%20Stack%20Architect%20%7C%20Digital%20Health%20Systems&descSize=18&descAlignY=58&descColor=E2E8F0" width="100%" />

  <!-- Typing SVG Animado -->
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&weight=600&size=19&pause=1200&color=74ACDF&center=true&vCenter=true&width=620&lines=Arquitectura+Hospitalaria+Modular;Salud+Digital+%26+Gobernanza+de+Datos;Laravel+%2B+Livewire+%2B+Flux+UI;UNLP+Facultad+de+Inform%C3%A1tica" alt="Typing SVG" />
  </a>

  <br/>

  <!-- Enlaces de Contacto y Estado -->
  <a href="https://www.linkedin.com/in/crslamas/" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white" />
  </a>
  <a href="mailto:crslamas@gmail.com">
    <img src="https://img.shields.io/badge/Email-crslamas@gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white" />
  </a>
  <img src="https://img.shields.io/badge/Ubicaci%C3%B3n-Argentina-74ACDF?style=flat-square&logo=google-maps&logoColor=white" />
  <img src="https://img.shields.io/badge/Enfoque-Salud_P%C3%BAblica-2E7D32?style=flat-square&logo=target&logoColor=white" />

</div>

---

### 👨‍💻 Perfil & Salud Digital

Desarrollador Full Stack con **más de 4 años de experiencia en el ámbito de la salud pública** (HIGA Gral. San Martín) y especialización en **Salud Digital**. Especializado en la arquitectura e implementación de soluciones orientadas al dominio sanitario, transformando flujos operativos complejos en plataformas modulares, seguras y con mínima fricción para los equipos médicos y administrativos.

* 🏛️ **Formación:** Estudiante en la **Facultad de Informática (UNLP)** — Licenciatura en Sistemas / Analista Programador Universitario (APU) / Analista TIC.
* 📜 **Especialización:** Diplomado en Salud Digital (UNPAZ).
* 🎯 **Foco actual:** Arquitecturas modulares limpias, infraestructura de firma electrónica/digital y digitalización integral del capital humano hospitalario.

---

### 🏥 Proyecto Central: SALUZ

> **Ecosistema Modular de Gestión y Operaciones Hospitalarias Críticas.**  
> Diseñado bajo una arquitectura modular desacoplada para centralizar el capital humano, la trazabilidad patrimonial, la infraestructura física y los procesos institucionales con altos estándares de auditoría.

\`\`\`
┌────────────────────────────────────────────────────────────────────────┐
│                        SALUZ SYSTEM TOPOLOGY                           │
│                                                                        │
│   [ Livewire 3 + Volt ] ─────── [ Flux UI ] ─────── [ PowerGrid ]      │
│            │                          │                      │         │
│   ┌────────┴──────────────────────────┴──────────────────────┴─────┐   │
│   │                        MODULAR DOMAIN ENGINE                   │   │
│   │   • Workforce    (Legajos, Guardias, Licencias, SISA)          │   │
│   │   • Architecture (Sedes, Áreas, Ubicaciones Físicas & Campos)  │   │
│   │   • Patrimony    (Bienes, Movimientos, Trazabilidad de Stock)  │   │
│   │   • System       (Auditoría, Roles/Permisos, Licencias Offline)│   │
│   └────────┬──────────────────────────┬──────────────────────┬─────┘   │
│            │                          │                      │         │
│   [ Public eSign / PDF/A ]    [ Spatie Health ]    [ Laravel Reverb ]  │
│     (OpenSSL / PKI Keys)     (Monitoreo Activo)    (WebSockets Realtime)│
└────────────────────────────────────────────────────────────────────────┘
\`\`\`

<details>
<summary>🔍 <strong>Ver Desglose Técnico de Módulos</strong></summary>
<br/>

| Capa / Subsistema | Tecnologías & Paquetes | Responsabilidad e Implementación |
| :--- | :--- | :--- |
| **Módulo Workforce** | \`Laravel Modules\` + \`SISA Catalogs\` | Gestión integral del recurso humano sanitario: legajos digitales, régimen estatutario, rotación de guardias, balances de licencias y homologación con catálogos federales de salud (SISA). |
| **Módulo Architecture** | \`Livewire\` + \`EAV Custom Fields\` | Modelado jerárquico de la infraestructura física del hospital: sedes, pabellones, salas, camas y campos dinámicos configurables. |
| **Módulo Patrimony** | \`Livewire PowerGrid\` + \`Enums\` | Inventario hospitalario, control de altas/bajas de equipamiento médico y auditoría de transferencias internas. |
| **Módulo System** | \`Spatie Permission\` + \`ActivityLog\` | Control de acceso basado en roles (RBAC), registro de auditoría forense inmutable y validación de licencias de nodo offline. |
| **Firma Digital (eSign)** | \`OpenSSL\` + \`PKI\` + \`Public eSign Verify\` | Emisión, firma criptográfica y validación pública vía código QR/Token de documentos hospitalarios oficiales en PDF/A. |
| **Frontend & UX** | \`Flux UI\` + \`Livewire 3\` + \`Tiptap\` + \`TailwindCSS\` | Experiencia reactiva sin recarga de página, con formularios fluidos, tablas de alto rendimiento y editor de texto enriquecido. |
| **Infraestructura & QA** | \`Docker Compose\` + \`Pest PHP\` + \`Larastan\` | Entornos autocontenidos en contenedores PHP 8.x, suites de pruebas automatizadas y análisis estático estricto. |

</details>

---

### 🛠️ Stack Tecnológico

<div align="center">

| Área | Tecnologías |
| :--- | :--- |
| **Backend & Core** | <img src="https://skillicons.dev/icons?i=php,laravel&theme=dark" height="38" /> |
| **Frontend & UI** | <img src="https://skillicons.dev/icons?i=livewire,tailwind,js,html,css,vue,bootstrap&theme=dark" height="38" /> |
| **Bases de Datos & Caché** | <img src="https://skillicons.dev/icons?i=mysql,redis&theme=dark" height="38" /> |
| **Infraestructura & Servidores** | <img src="https://skillicons.dev/icons?i=docker,nginx,linux,bash&theme=dark" height="38" /> |
| **Entorno & Herramientas** | <img src="https://skillicons.dev/icons?i=git,github,vscode&theme=dark" height="38" /> |

</div>

---

### 📊 Métricas & Actividad Global

<div align="center">
  <!-- Tarjetas Estadísticas con commits públicos y privados habilitados -->
  <img src="https://github-readme-stats.vercel.app/api?username=crslamas&show_icons=true&theme=tokyonight&count_private=true&include_all_commits=true&hide_border=true&bg_color=0D1117&title_color=74ACDF&icon_color=74ACDF&text_color=E2E8F0" height="165" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=crslamas&layout=compact&theme=tokyonight&count_private=true&hide_border=true&bg_color=0D1117&title_color=74ACDF&text_color=E2E8F0" height="165" />
</div>

<div align="center">
  <!-- Racha de Actividad -->
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=crslamas&theme=tokyonight&hide_border=true&background=0D1117&ring=74ACDF&fire=74ACDF&currStreakLabel=74ACDF" height="165" />
</div>

---

### 📁 Desarrollos Asistenciales & Experiencia de Campo

Sistemas diseñados e implementados en entornos hospitalarios de alta exigencia:

* 🛏️ **SiGeCa (Gestión de Camas):** Sistema en producción continua para la administración de ingresos, transferencias y monitoreo en tiempo real de la tasa de ocupación hospitalaria.
* 🚑 **Derivaciones:** Herramienta para la gestión y seguimiento operativo del traslado en red de pacientes de complejidad.
* 🦴 **Banco de Prótesis:** Sistema de trazabilidad, control de stock y auditoría de expedientes de implantes y prótesis ortopédicas.
* 🏷️ **CIE-10 Coder:** Herramienta asistida por modelos de lenguaje orientada a acelerar la clasificación y codificación de diagnósticos médicos.
* 📦 **Irinka:** Sistema de facturación, gestión comercial y control de stock multidepósito.

---

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:74ACDF,50:2A4365,100:0A192F&height=100&section=footer" width="100%" />
</div>`;

    // Initialize textarea
    document.addEventListener('DOMContentLoaded', () => {
      document.getElementById('rawMarkdownTextarea').value = markdownContent;
      startTypingAnimation();
    });

    // Typing simulation
    const phrases = [
      "Arquitectura Hospitalaria Modular",
      "Salud Digital & Gobernanza de Datos",
      "Laravel + Livewire + Flux UI",
      "UNLP Facultad de Informática",
      "Ecosistema SALUZ en Producción"
    ];
    let phraseIndex = 0;
    let charIndex = 0;
    let isDeleting = false;

    function startTypingAnimation() {
      const output = document.getElementById('typingOutput');
      if (!output) return;

      const currentPhrase = phrases[phraseIndex];

      if (isDeleting) {
        output.textContent = currentPhrase.substring(0, charIndex - 1);
        charIndex--;
      } else {
        output.textContent = currentPhrase.substring(0, charIndex + 1);
        charIndex++;
      }

      let speed = isDeleting ? 35 : 70;

      if (!isDeleting && charIndex === currentPhrase.length) {
        speed = 1800; // Pause at end
        isDeleting = true;
      } else if (isDeleting && charIndex === 0) {
        isDeleting = false;
        phraseIndex = (phraseIndex + 1) % phrases.length;
        speed = 400;
      }

      setTimeout(startTypingAnimation, speed);
    }

    // View Switching
    function switchView(viewName) {
      document.getElementById('viewGithub').classList.add('hidden');
      document.getElementById('viewSaluz').classList.add('hidden');
      document.getElementById('viewCode').classList.add('hidden');

      // Reset Button Styles
      const btnGit = document.getElementById('btnViewGithub');
      const btnSaluz = document.getElementById('btnViewSaluz');
      const btnCode = document.getElementById('btnViewCode');

      [btnGit, btnSaluz, btnCode].forEach(btn => {
        btn.className = "px-3 py-1.5 rounded-md font-medium text-slate-400 hover:text-slate-200 transition-all flex items-center space-x-1.5";
      });

      if (viewName === 'github') {
        document.getElementById('viewGithub').classList.remove('hidden');
        btnGit.className = "px-3 py-1.5 rounded-md font-medium transition-all bg-sky-600 text-white shadow-sm flex items-center space-x-1.5";
      } else if (viewName === 'saluz') {
        document.getElementById('viewSaluz').classList.remove('hidden');
        btnSaluz.className = "px-3 py-1.5 rounded-md font-medium transition-all bg-sky-600 text-white shadow-sm flex items-center space-x-1.5";
      } else if (viewName === 'code') {
        document.getElementById('viewCode').classList.remove('hidden');
        btnCode.className = "px-3 py-1.5 rounded-md font-medium transition-all bg-sky-600 text-white shadow-sm flex items-center space-x-1.5";
      }
    }

    // Accordion Toggle
    function toggleSaluzDetails() {
      const content = document.getElementById('accordionContent');
      const icon = document.getElementById('accordionIcon');
      if (content.classList.contains('hidden')) {
        content.classList.remove('hidden');
        icon.textContent = '▲';
      } else {
        content.classList.add('hidden');
        icon.textContent = '▼';
      }
    }

    // Module Subtab Selector inside Saluz Explorer
    function selectSaluzTab(tabId) {
      document.querySelectorAll('.saluz-content').forEach(el => el.classList.add('hidden'));
      document.querySelectorAll('.saluz-nav-btn').forEach(btn => {
        btn.className = "saluz-nav-btn p-3 rounded-xl border border-slate-800 bg-slate-950/60 text-slate-400 hover:text-slate-200 font-semibold text-xs flex flex-col items-center justify-center text-center transition";
      });

      const targetContent = document.getElementById('moduleContent' + tabId.charAt(0).toUpperCase() + tabId.slice(1));
      const targetBtn = document.getElementById('tabBtn' + tabId.charAt(0).toUpperCase() + tabId.slice(1));

      if (targetContent) targetContent.classList.remove('hidden');
      if (targetBtn) {
        targetBtn.className = "saluz-nav-btn p-3 rounded-xl border border-sky-500/40 bg-sky-500/10 text-sky-300 font-semibold text-xs flex flex-col items-center justify-center text-center transition";
      }
    }

    // Robust Clipboard Copying Function
    function copyMarkdownContent() {
      const textarea = document.getElementById('rawMarkdownTextarea');
      textarea.select();
      textarea.setSelectionRange(0, 99999);

      let successful = false;
      try {
        successful = document.execCommand('copy');
      } catch (err) {
        successful = false;
      }

      if (successful) {
        showToast();
      }
    }

    function showToast() {
      const toast = document.getElementById('toastNotification');
      toast.classList.remove('translate-y-20', 'opacity-0');
      toast.classList.add('translate-y-0', 'opacity-100');

      setTimeout(() => {
        toast.classList.remove('translate-y-0', 'opacity-100');
        toast.classList.add('translate-y-20', 'opacity-0');
      }, 2600);
    }
  </script>
</body>
</html>
