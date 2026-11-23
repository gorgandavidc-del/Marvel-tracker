# Marvel-tracker
My Marvel Doomsday Watchlist
<!DOCTYPE html>
<html lang="ro" class="dark">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Maraton Avengers: Doomsday — Tracker Marvel</title>

  <!-- Google Fonts: Inter -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet" />

  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Configurare Tailwind pentru paleta Doctor Doom / Avengers: Doomsday -->
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'system-ui', '-apple-system', 'sans-serif'],
          },
          colors: {
            doom: {
              bg: '#0a0d0c',
              surface: '#111715',
              card: '#141c19',
              border: '#22302b',
              emerald: '#10b981',
              emeraldDark: '#059669',
              gold: '#d4af37',
              silver: '#cbd5e1',
            },
          },
          boxShadow: {
            'doom-glow': '0 0 28px -6px rgba(16, 185, 129, 0.35)',
            'gold-glow': '0 0 24px -6px rgba(212, 175, 55, 0.35)',
          },
          keyframes: {
            checkPop: {
              '0%': { transform: 'scale(0.6)', opacity: '0' },
              '60%': { transform: 'scale(1.18)', opacity: '1' },
              '100%': { transform: 'scale(1)', opacity: '1' },
            },
            fadeSlide: {
              '0%': { opacity: '0', transform: 'translateY(-6px)' },
              '100%': { opacity: '1', transform: 'translateY(0)' },
            },
          },
          animation: {
            'check-pop': 'checkPop 0.28s cubic-bezier(0.22, 1, 0.36, 1) forwards',
            'fade-slide': 'fadeSlide 0.35s ease-out forwards',
          },
        },
      },
    };
  </script>
</head>
<body class="bg-doom-bg text-slate-100 font-sans antialiased selection:bg-emerald-500/30 selection:text-emerald-200 min-h-screen overflow-x-hidden">

  <!-- Efecte ambientale discrete în fundal (smarald și auriu subtil) -->
  <div class="fixed inset-0 pointer-events-none overflow-hidden -z-10" aria-hidden="true">
    <div class="absolute -top-32 left-1/2 -translate-x-1/2 w-[36rem] sm:w-[54rem] h-72 rounded-full bg-emerald-500/10 blur-3xl"></div>
    <div class="absolute top-1/3 -right-32 w-80 h-80 rounded-full bg-emerald-600/5 blur-3xl"></div>
    <div class="absolute bottom-0 -left-32 w-80 h-80 rounded-full bg-amber-500/5 blur-3xl"></div>
  </div>

  <!-- Container principal -->
  <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 py-6 sm:py-10">

    <!-- ==================== HEADER & COUNTDOWN ==================== -->
    <header class="relative rounded-3xl bg-gradient-to-b from-doom-surface/95 to-doom-card/90 border border-doom-border/90 p-5 sm:p-8 shadow-2xl overflow-hidden mb-6 sm:mb-8">
      <!-- Linie metalică superioară inspirată de masca lui Doctor Doom -->
      <div class="absolute inset-x-0 top-0 h-1 bg-gradient-to-r from-transparent via-emerald-500 to-transparent opacity-80"></div>

      <div class="flex flex-col lg:flex-row lg:items-center lg:justify-between gap-6">
        <!-- Titlu și badge -->
        <div class="space-y-3">
          <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-emerald-500/10 border border-emerald-500/30 text-emerald-300 text-xs font-semibold tracking-wider uppercase">
            <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
            Checklist Oficial &amp; Puntea 2026
          </div>

          <div class="flex items-center gap-3.5">
            <!-- Emblemă SVG geometrică Doctor Doom -->
            <div class="shrink-0 w-12 h-12 sm:w-14 sm:h-14 rounded-2xl bg-gradient-to-br from-slate-700/80 via-doom-card to-emerald-950/90 border border-slate-400/30 flex items-center justify-center shadow-doom-glow">
              <svg class="w-7 h-7 sm:w-8 sm:h-8 text-emerald-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
                <path d="M12 2L4 6v5c0 5.5 3.4 9.7 8 11 4.6-1.3 8-5.5 8-11V6l-8-4z" class="stroke-slate-300" />
                <path d="M7.5 10.5l3 1-3 1.2M16.5 10.5l-3 1 3 1.2" class="stroke-emerald-400" stroke-width="2" />
                <path d="M9 16.5h6" class="stroke-amber-400/80" />
              </svg>
            </div>
            <div>
              <h1 class="text-2xl sm:text-4xl font-black tracking-tight bg-gradient-to-r from-slate-100 via-emerald-200 to-slate-300 bg-clip-text text-transparent">
                Maraton Avengers: Doomsday
              </h1>
              <p class="text-xs sm:text-sm text-slate-400 mt-1">
                Premiera în cinematografe: <span class="text-amber-300/90 font-semibold">18 decembrie 2026</span>
              </p>
            </div>
          </div>
        </div>

        <!-- Countdown Live -->
        <div class="bg-doom-bg/80 border border-doom-border rounded-2xl p-3.5 sm:p-4 shrink-0">
          <p class="text-[11px] uppercase tracking-widest text-slate-400 font-semibold text-center mb-2.5" id="countdown-label">
            Timp rămas până la premieră
          </p>
          <div id="countdown-grid" class="grid grid-cols-4 gap-2 sm:gap-2.5 text-center">
            <div class="bg-doom-card border border-slate-700/50 rounded-xl px-2.5 py-2 min-w-[3.8rem] sm:min-w-[4.4rem]">
              <div id="cd-days" class="text-lg sm:text-2xl font-extrabold text-emerald-400 tabular-nums leading-none">--</div>
              <div class="text-[10px] uppercase tracking-wider text-slate-400 mt-1">Zile</div>
            </div>
            <div class="bg-doom-card border border-slate-700/50 rounded-xl px-2.5 py-2 min-w-[3.8rem] sm:min-w-[4.4rem]">
              <div id="cd-hours" class="text-lg sm:text-2xl font-extrabold text-slate-100 tabular-nums leading-none">--</div>
              <div class="text-[10px] uppercase tracking-wider text-slate-400 mt-1">Ore</div>
            </div>
            <div class="bg-doom-card border border-slate-700/50 rounded-xl px-2.5 py-2 min-w-[3.8rem] sm:min-w-[4.4rem]">
              <div id="cd-minutes" class="text-lg sm:text-2xl font-extrabold text-slate-100 tabular-nums leading-none">--</div>
              <div class="text-[10px] uppercase tracking-wider text-slate-400 mt-1">Min</div>
            </div>
            <div class="bg-doom-card border border-slate-700/50 rounded-xl px-2.5 py-2 min-w-[3.8rem] sm:min-w-[4.4rem]">
              <div id="cd-seconds" class="text-lg sm:text-2xl font-extrabold text-amber-300/90 tabular-nums leading-none">--</div>
              <div class="text-[10px] uppercase tracking-wider text-slate-400 mt-1">Sec</div>
            </div>
          </div>
        </div>
      </div>

      <!-- ==================== BARA DE PROGRES GENERAL ==================== -->
      <div class="mt-6 pt-6 border-t border-doom-border/80">
        <div class="flex flex-col sm:flex-row sm:items-end justify-between gap-3 mb-3">
          <div>
            <div class="flex items-baseline gap-2.5">
              <span id="progress-percent" class="text-3xl sm:text-4xl font-black text-emerald-400 tabular-nums">0%</span>
              <span id="progress-fraction" class="text-sm sm:text-base font-semibold text-slate-300 tabular-nums">0 / 20 văzute</span>
            </div>
            <p id="progress-subtitle" class="text-xs text-slate-400 mt-0.5">
              Include cele 18 titluri esențiale și 2 titluri bonus
            </p>
          </div>

          <!-- Toggle: Include Bonus în calculul procentului -->
          <label class="inline-flex items-center gap-3 cursor-pointer select-none bg-doom-bg/70 hover:bg-doom-bg border border-doom-border rounded-2xl px-3.5 py-2.5 transition-colors self-start sm:self-auto">
            <span class="text-xs sm:text-sm font-medium text-slate-300">
              Include Bonus în calculul procentului
            </span>
            <span class="relative inline-flex items-center">
              <input type="checkbox" id="toggle-bonus" class="sr-only peer" checked />
              <div class="w-11 h-6 bg-slate-700 peer-focus:outline-none peer-focus:ring-2 peer-focus:ring-emerald-500/50 rounded-full peer peer-checked:bg-emerald-600 transition-colors after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:after:translate-x-5"></div>
            </span>
          </label>
        </div>

        <!-- Bară de progres vizuală -->
        <div class="w-full h-4 sm:h-4.5 rounded-full bg-doom-bg border border-doom-border p-0.5 overflow-hidden">
          <div
            id="progress-bar-fill"
            class="h-full rounded-full bg-gradient-to-r from-emerald-600 via-emerald-400 to-amber-300 transition-all duration-500 ease-out shadow-doom-glow"
            style="width: 0%"
            role="progressbar"
            aria-valuenow="0"
            aria-valuemin="0"
            aria-valuemax="100"
          ></div>
        </div>

        <!-- Mesaj festiv discret la 100% progres -->
        <div
          id="complete-banner"
          class="hidden mt-4 rounded-2xl bg-gradient-to-r from-emerald-950/90 via-doom-card to-amber-950/40 border border-amber-400/40 px-4 py-3.5 shadow-gold-glow animate-fade-slide"
        >
          <div class="flex items-center gap-3">
            <div class="w-9 h-9 rounded-xl bg-amber-400/15 border border-amber-400/40 flex items-center justify-center shrink-0 text-amber-300">
              <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
                <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z" />
              </svg>
            </div>
            <div>
              <p class="text-sm sm:text-base font-bold text-amber-200">
                Ești pregătit pentru Avengers: Doomsday!
              </p>
              <p class="text-xs text-emerald-300/80">
                Ai completat 100% din lista selectată. Multiversul te așteaptă pe 18 decembrie 2026.
              </p>
            </div>
          </div>
        </div>
      </div>
    </header>

    <!-- ==================== FILTRE, CĂUTARE & ACȚIUNI ==================== -->
    <section class="rounded-2xl bg-doom-surface/90 border border-doom-border p-4 sm:p-5 mb-6 sm:mb-8 space-y-4">
      <div class="flex flex-col md:flex-row md:items-center justify-between gap-3">
        <!-- Bară de căutare -->
        <div class="relative flex-1">
          <svg class="w-4 h-4 text-slate-400 absolute left-3.5 top-1/2 -translate-y-1/2 pointer-events-none" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
            <circle cx="11" cy="11" r="8"></circle>
            <path d="M21 21l-4.35-4.35"></path>
          </svg>
          <input
            type="text"
            id="search-input"
            placeholder="Caută după titlu, an sau personaj (ex: Loki, 2025, Doom)..."
            class="w-full pl-10 pr-10 py-2.5 rounded-xl bg-doom-bg border border-doom-border text-sm text-slate-100 placeholder:text-slate-500 focus:outline-none focus:border-emerald-500/70 focus:ring-2 focus:ring-emerald-500/20 transition-all"
          />
          <button
            type="button"
            id="clear-search"
            class="hidden absolute right-2.5 top-1/2 -translate-y-1/2 p-1.5 rounded-lg text-slate-400 hover:text-slate-100 hover:bg-slate-800 transition-colors"
            aria-label="Șterge căutarea"
          >
            <svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M18 6L6 18M6 6l12 12"></path>
            </svg>
          </button>
        </div>

        <!-- Butoane discrete pentru acțiuni în masă -->
        <div class="flex items-center gap-2 self-end md:self-auto">
          <button
            type="button"
            id="btn-check-all"
            class="px-3.5 py-2.5 rounded-xl text-xs font-semibold text-emerald-300 bg-emerald-500/10 hover:bg-emerald-500/20 border border-emerald-500/25 transition-colors cursor-pointer"
          >
            Bifează tot
          </button>
          <button
            type="button"
            id="btn-reset-all"
            class="px-3.5 py-2.5 rounded-xl text-xs font-semibold text-slate-300 hover:text-rose-300 bg-doom-bg hover:bg-rose-500/10 border border-doom-border hover:border-rose-500/30 transition-colors cursor-pointer"
          >
            Resetează progresul
          </button>
        </div>
      </div>

      <!-- Filtre rapide (Pills) -->
      <div id="filter-bar" class="flex flex-wrap items-center gap-2" role="tablist" aria-label="Filtre listă">
        <!-- Generate dinamic din JS pentru a include și contoarele live -->
      </div>
    </section>

    <!-- ==================== LISTA DE CATEGORII & CARDURI ==================== -->
    <main id="categories-container" class="space-y-5 sm:space-y-6">
      <!-- Randat dinamic din JavaScript -->
    </main>

    <!-- Stare goală când filtrarea/căutarea nu returnează nimic -->
    <div id="empty-state" class="hidden rounded-2xl bg-doom-surface/80 border border-doom-border p-10 text-center">
      <div class="w-12 h-12 mx-auto rounded-2xl bg-doom-bg border border-doom-border flex items-center justify-center text-slate-400 mb-3">
        <svg class="w-6 h-6" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
          <circle cx="11" cy="11" r="8"></circle>
          <path d="M21 21l-4.35-4.35"></path>
        </svg>
      </div>
      <h3 class="text-base font-bold text-slate-200">Niciun titlu găsit</h3>
      <p class="text-sm text-slate-400 mt-1">Încearcă un alt filtru sau șterge termenul de căutare.</p>
      <button
        type="button"
        id="btn-clear-filters"
        class="mt-4 px-4 py-2 rounded-xl text-xs font-semibold bg-emerald-500/15 text-emerald-300 border border-emerald-500/30 hover:bg-emerald-500/25 transition-colors cursor-pointer"
      >
        Afișează toate titlurile
      </button>
    </div>

    <!-- Footer discret -->
    <footer class="mt-10 pb-6 text-center text-xs text-slate-500">
      Progresul tău este salvat automat local în browser. • <span class="text-emerald-500/80">Avengers: Doomsday</span> (18 decembrie 2026)
    </footer>
  </div>

  <!-- ==================== MODAL DE CONFIRMARE PERSONALIZAT ==================== -->
  <div
    id="confirm-modal"
    class="hidden fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/75 backdrop-blur-sm"
    role="dialog"
    aria-modal="true"
    aria-labelledby="modal-title"
  >
    <div class="w-full max-w-md rounded-2xl bg-doom-surface border border-doom-border p-6 shadow-2xl animate-fade-slide">
      <div class="flex items-start gap-3.5">
        <div id="modal-icon-wrap" class="w-10 h-10 rounded-xl flex items-center justify-center shrink-0 border">
          <!-- Icon injectat din JS -->
        </div>
        <div class="flex-1">
          <h2 id="modal-title" class="text-base font-bold text-slate-100">Confirmare</h2>
          <p id="modal-message" class="text-sm text-slate-400 mt-1.5 leading-relaxed"></p>
        </div>
      </div>

      <div class="flex items-center justify-end gap-2.5 mt-6">
        <button
          type="button"
          id="modal-cancel"
          class="px-4 py-2.5 rounded-xl text-xs sm:text-sm font-semibold text-slate-300 bg-doom-bg hover:bg-slate-800 border border-doom-border transition-colors cursor-pointer"
        >
          Anulează
        </button>
        <button
          type="button"
          id="modal-confirm"
          class="px-4 py-2.5 rounded-xl text-xs sm:text-sm font-semibold text-white transition-colors cursor-pointer"
        >
          Confirmă
        </button>
      </div>
    </div>
  </div>

  <!-- ==================== LOGICA APLICAȚIEI (JAVASCRIPT) ==================== -->
  <script>
    /**
     * Datele oficiale pentru maratonul Avengers: Doomsday
     * 6 categorii, 20 de titluri (18 esențiale + 2 bonus)
     */
    const CATEGORIES = [
      {
        id: 'cat-1',
        number: 1,
        title: 'Fundamentul X-Men (Universul Fox)',
        isBonus: false,
        items: [
          {
            id: 'x-men-2000',
            title: 'X-Men',
            year: 2000,
            type: 'Film',
            description: 'Introduce versiunile originale ale lui Professor X, Magneto, Cyclops și Mystique, toți confirmați în Doomsday.',
          },
          {
            id: 'x2-2003',
            title: 'X2: X-Men United',
            year: 2003,
            type: 'Film',
            description: 'Dezvoltă echipa și dinamica mutanților care revin în crossover.',
          },
        ],
      },
      {
        id: 'cat-2',
        number: 2,
        title: 'Esențialul din Infinity Saga',
        isBonus: false,
        items: [
          {
            id: 'cap-first-avenger',
            title: 'Captain America: The First Avenger',
            year: 2011,
            type: 'Film',
            description: 'Originea lui Steve Rogers și fundația primilor Răzbunători.',
          },
          {
            id: 'the-avengers-2012',
            title: 'The Avengers',
            year: 2012,
            type: 'Film',
            description: 'Formarea echipei originale și prima mare amenințare comună.',
          },
          {
            id: 'infinity-war-2018',
            title: 'Avengers: Infinity War',
            year: 2018,
            type: 'Film',
            description: 'Contextul luptei cu Thanos și relațiile dintre eroii principali.',
          },
          {
            id: 'endgame-2019',
            title: 'Avengers: Endgame',
            year: 2019,
            type: 'Film',
            description: 'Punctul zero al călătoriilor în timp, finalul lui Steve Rogers și sacrificiul lui Tony Stark (esențial având în vedere revenirea lui Robert Downey Jr. ca Doctor Doom).',
          },
        ],
      },
      {
        id: 'cat-3',
        number: 3,
        title: 'Regulile Multiversului',
        isBonus: false,
        items: [
          {
            id: 'loki-s1',
            title: 'Loki – Sezonul 1',
            year: 2021,
            type: 'Serial',
            description: 'Explică TVA, variantele și cum se ramifică liniile temporale.',
          },
          {
            id: 'spider-man-nwh',
            title: 'Spider-Man: No Way Home',
            year: 2021,
            type: 'Film',
            description: 'Prima fractură majoră a multiversului în MCU.',
          },
          {
            id: 'doctor-strange-mom',
            title: 'Doctor Strange in the Multiverse of Madness',
            year: 2022,
            type: 'Film',
            description: 'Introduce conceptul de incursiuni (coliziuni între universuri), central pentru Doomsday.',
          },
          {
            id: 'loki-s2',
            title: 'Loki – Sezonul 2',
            year: 2023,
            type: 'Serial',
            description: 'Cel mai important serial din listă; stabilește statutul actual al multiversului și rolul lui Loki.',
          },
          {
            id: 'deadpool-wolverine',
            title: 'Deadpool & Wolverine',
            year: 2024,
            type: 'Film',
            description: 'Puntea dintre universul Fox/X-Men, TVA și MCU; îl introduce și pe Gambit (Channing Tatum).',
          },
        ],
      },
      {
        id: 'cat-4',
        number: 4,
        title: 'Noii eroi și echipele din Earth-616',
        isBonus: false,
        items: [
          {
            id: 'shang-chi',
            title: 'Shang-Chi and the Legend of the Ten Rings',
            year: 2021,
            type: 'Film',
            description: 'Introduce personajul și misterul celor Zece Inele.',
          },
          {
            id: 'wakanda-forever',
            title: 'Black Panther: Wakanda Forever',
            year: 2022,
            type: 'Film',
            description: 'O stabilește pe Shuri drept noul Black Panther și îi introduce pe Namor și regatul Talokan.',
          },
          {
            id: 'cap-brave-new-world',
            title: 'Captain America: Brave New World',
            year: 2025,
            type: 'Film',
            description: 'Primul film al lui Sam Wilson ca Captain America și încercarea de a reconstrui Avengers.',
          },
          {
            id: 'thunderbolts',
            title: 'Thunderbolts*',
            year: 2025,
            type: 'Film',
            description: 'Formează echipa New Avengers și are un final care leagă direct povestea de Doomsday.',
          },
        ],
      },
      {
        id: 'cat-5',
        number: 5,
        title: 'Puntea directă către Doomsday (2025–2026)',
        isBonus: false,
        items: [
          {
            id: 'fantastic-four-first-steps',
            title: 'The Fantastic Four: First Steps',
            year: 2025,
            type: 'Film',
            description: 'Introduce Cei Patru Fantastici din universul lor alternativ și pregătește terenul pentru sosirea lui Doctor Doom.',
          },
          {
            id: 'spider-man-brand-new-day',
            title: 'Spider-Man: Brand New Day',
            year: 2026,
            type: 'Film',
            description: 'Ultimul film MCU înainte de Doomsday, cu o scenă post-credits care face trimitere directă la evenimentele următoare.',
          },
          {
            id: 'visionquest',
            title: 'VisionQuest',
            year: 2026,
            type: 'Serial',
            description: 'Oferă una dintre cele mai directe legături cu Doctor Doom înainte de premiera filmului.',
          },
        ],
      },
      {
        id: 'cat-6',
        number: 6,
        title: 'Bonus (Opționale, dar utile pentru context)',
        isBonus: true,
        items: [
          {
            id: 'wandavision',
            title: 'WandaVision',
            year: 2021,
            type: 'Serial',
            description: 'Context util înainte de Multiverse of Madness și VisionQuest.',
          },
          {
            id: 'falcon-winter-soldier',
            title: 'The Falcon and the Winter Soldier',
            year: 2021,
            type: 'Serial',
            description: 'Aprofundează evoluția lui Sam Wilson, Bucky și U.S. Agent înainte de Brave New World și Thunderbolts*.',
          },
        ],
      },
    ];

    // Listă plată cu toate titlurile pentru calcule rapide
    const ALL_ITEMS = CATEGORIES.flatMap((cat) =>
      cat.items.map((item) => ({ ...item, categoryId: cat.id, isBonus: cat.isBonus }))
    );

    // Chei pentru salvarea în localStorage
    const STORAGE_KEYS = {
      WATCHED: 'doomsday_tracker_watched_v1',
      INCLUDE_BONUS: 'doomsday_tracker_include_bonus_v1',
      COLLAPSED: 'doomsday_tracker_collapsed_v1',
    };

    // Starea aplicației
    const state = {
      watched: new Set(),
      includeBonus: true,
      collapsed: new Set(),
      activeFilter: 'all', // 'all' | 'unwatched' | 'watched' | 'Film' | 'Serial'
      searchQuery: '',
      pendingModalAction: null,
    };

    // Referințe DOM
    const dom = {
      progressPercent: document.getElementById('progress-percent'),
      progressFraction: document.getElementById('progress-fraction'),
      progressSubtitle: document.getElementById('progress-subtitle'),
      progressBarFill: document.getElementById('progress-bar-fill'),
      completeBanner: document.getElementById('complete-banner'),
      toggleBonus: document.getElementById('toggle-bonus'),
      filterBar: document.getElementById('filter-bar'),
      searchInput: document.getElementById('search-input'),
      clearSearch: document.getElementById('clear-search'),
      categoriesContainer: document.getElementById('categories-container'),
      emptyState: document.getElementById('empty-state'),
      btnClearFilters: document.getElementById('btn-clear-filters'),
      btnCheckAll: document.getElementById('btn-check-all'),
      btnResetAll: document.getElementById('btn-reset-all'),
      modal: document.getElementById('confirm-modal'),
      modalTitle: document.getElementById('modal-title'),
      modalMessage: document.getElementById('modal-message'),
      modalIconWrap: document.getElementById('modal-icon-wrap'),
      modalCancel: document.getElementById('modal-cancel'),
      modalConfirm: document.getElementById('modal-confirm'),
      cdDays: document.getElementById('cd-days'),
      cdHours: document.getElementById('cd-hours'),
      cdMinutes: document.getElementById('cd-minutes'),
      cdSeconds: document.getElementById('cd-seconds'),
      cdLabel: document.getElementById('countdown-label'),
    };

    /**
     * Încărcare sigură din localStorage cu tratare de erori
     */
    function loadState() {
      try {
        const savedWatched = localStorage.getItem(STORAGE_KEYS.WATCHED);
        if (savedWatched) {
          const parsed = JSON.parse(savedWatched);
          if (Array.isArray(parsed)) {
            state.watched = new Set(parsed);
          }
        }

        const savedBonus = localStorage.getItem(STORAGE_KEYS.INCLUDE_BONUS);
        if (savedBonus !== null) {
          state.includeBonus = savedBonus === 'true';
        }

        const savedCollapsed = localStorage.getItem(STORAGE_KEYS.COLLAPSED);
        if (savedCollapsed) {
          const parsedCollapsed = JSON.parse(savedCollapsed);
          if (Array.isArray(parsedCollapsed)) {
            state.collapsed = new Set(parsedCollapsed);
          }
        }
      } catch (err) {
        console.warn('Nu s-a putut citi starea din localStorage:', err);
      }

      dom.toggleBonus.checked = state.includeBonus;
    }

    /**
     * Salvare sigură în localStorage
     */
    function saveState() {
      try {
        localStorage.setItem(STORAGE_KEYS.WATCHED, JSON.stringify([...state.watched]));
        localStorage.setItem(STORAGE_KEYS.INCLUDE_BONUS, String(state.includeBonus));
        localStorage.setItem(STORAGE_KEYS.COLLAPSED, JSON.stringify([...state.collapsed]));
      } catch (err) {
        console.warn('Nu s-a putut salva starea în localStorage:', err);
      }
    }

    /**
     * Actualizează numărătoarea inversă până pe 18 decembrie 2026
     */
    function updateCountdown() {
      const targetDate = new Date('2026-12-18T00:00:00').getTime();
      const now = Date.now();
      const diff = targetDate - now;

      if (diff <= 0) {
        dom.cdDays.textContent = '00';
        dom.cdHours.textContent = '00';
        dom.cdMinutes.textContent = '00';
        dom.cdSeconds.textContent = '00';
        dom.cdLabel.textContent = 'Avengers: Doomsday este în cinematografe!';
        return;
      }

      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((diff / (1000 * 60)) % 60);
      const seconds = Math.floor((diff / 1000) % 60);

      dom.cdDays.textContent = String(days).padStart(2, '0');
      dom.cdHours.textContent = String(hours).padStart(2, '0');
      dom.cdMinutes.textContent = String(minutes).padStart(2, '0');
      dom.cdSeconds.textContent = String(seconds).padStart(2, '0');
    }

    /**
     * Calculează și actualizează bara de progres și bannerul de 100%
     */
    function updateProgressUI() {
      const scopedItems = state.includeBonus
        ? ALL_ITEMS
        : ALL_ITEMS.filter((item) => !item.isBonus);

      const totalCount = scopedItems.length;
      const watchedCount = scopedItems.filter((item) => state.watched.has(item.id)).length;
      const percentage = totalCount > 0 ? Math.round((watchedCount / totalCount) * 100) : 0;

      dom.progressPercent.textContent = `${percentage}%`;
      dom.progressFraction.textContent = `${watchedCount} / ${totalCount} văzute`;
      dom.progressSubtitle.textContent = state.includeBonus
        ? 'Include cele 18 titluri esențiale și 2 titluri bonus'
        : 'Calculat doar pentru cele 18 titluri esențiale (fără bonus)';

      dom.progressBarFill.style.width = `${percentage}%`;
      dom.progressBarFill.setAttribute('aria-valuenow', String(percentage));

      if (percentage === 100 && totalCount > 0) {
        dom.completeBanner.classList.remove('hidden');
      } else {
        dom.completeBanner.classList.add('hidden');
      }
    }

    /**
     * Randează butoanele de filtrare rapidă cu contoare live
     */
    function renderFilters() {
      const counts = {
        all: ALL_ITEMS.length,
        unwatched: ALL_ITEMS.filter((i) => !state.watched.has(i.id)).length,
        watched: ALL_ITEMS.filter((i) => state.watched.has(i.id)).length,
        Film: ALL_ITEMS.filter((i) => i.type === 'Film').length,
        Serial: ALL_ITEMS.filter((i) => i.type === 'Serial').length,
      };

      const filters = [
        { key: 'all', label: 'Toate', count: counts.all },
        { key: 'unwatched', label: 'Nevăzute', count: counts.unwatched },
        { key: 'watched', label: 'Văzute', count: counts.watched },
        { key: 'Film', label: 'Filme', count: counts.Film },
        { key: 'Serial', label: 'Seriale', count: counts.Serial },
      ];

      dom.filterBar.innerHTML = filters
        .map((f) => {
          const isActive = state.activeFilter === f.key;
          const activeClasses = isActive
            ? 'bg-emerald-500/20 text-emerald-300 border-emerald-500/50 shadow-sm'
            : 'bg-doom-bg text-slate-400 border-doom-border hover:text-slate-200 hover:border-slate-600';

          return `
            <button
              type="button"
              data-filter="${f.key}"
              role="tab"
              aria-selected="${isActive}"
              class="inline-flex items-center gap-2 px-3.5 py-2 rounded-xl text-xs sm:text-sm font-semibold border transition-all cursor-pointer ${activeClasses}"
            >
              <span>${f.label}</span>
              <span class="px-1.5 py-0.5 rounded-md text-[11px] tabular-nums ${
                isActive ? 'bg-emerald-500/25 text-emerald-200' : 'bg-slate-800 text-slate-400'
              }">${f.count}</span>
            </button>
          `;
        })
        .join('');
    }

    /**
     * Verifică dacă un titlu trece de filtrul activ și de căutare
     */
    function matchesFilters(item) {
      const isWatched = state.watched.has(item.id);

      if (state.activeFilter === 'watched' && !isWatched) return false;
      if (state.activeFilter === 'unwatched' && isWatched) return false;
      if (state.activeFilter === 'Film' && item.type !== 'Film') return false;
      if (state.activeFilter === 'Serial' && item.type !== 'Serial') return false;

      if (state.searchQuery.trim() !== '') {
        const q = state.searchQuery.trim().toLowerCase();
        const haystack = `${item.title} ${item.year} ${item.type} ${item.description}`.toLowerCase();
        if (!haystack.includes(q)) return false;
      }

      return true;
    }

    /**
     * Escape simplu pentru text dinamic în HTML
     */
    function escapeHTML(str) {
      return String(str)
        .replace(/&/g, '&amp;')
        .replace(/</g, '&lt;')
        .replace(/>/g, '&gt;')
        .replace(/"/g, '&quot;')
        .replace(/'/g, '&#39;');
    }

    /**
     * Randează toate categoriile și cardurile aferente
     */
    function renderCategories() {
      let totalVisibleItems = 0;
      const htmlParts = [];

      for (const category of CATEGORIES) {
        const visibleItems = category.items.filter(matchesFilters);
        if (visibleItems.length === 0) continue;

        totalVisibleItems += visibleItems.length;

        const catTotal = category.items.length;
        const catWatched = category.items.filter((i) => state.watched.has(i.id)).length;
        const catPercent = Math.round((catWatched / catTotal) * 100);
        const isCatComplete = catWatched === catTotal;
        const isCollapsed = state.collapsed.has(category.id) && state.searchQuery.trim() === '';

        const cardsHTML = visibleItems
          .map((item) => {
            const checked = state.watched.has(item.id);
            const isSerial = item.type === 'Serial';

            const cardClasses = checked
              ? 'bg-emerald-950/25 border-emerald-500/45 shadow-[0_0_20px_-10px_rgba(16,185,129,0.5)]'
              : 'bg-doom-card/90 border-doom-border hover:border-slate-500/60 hover:bg-doom-card';

            const checkboxClasses = checked
              ? 'bg-emerald-500 border-emerald-400 text-doom-bg shadow-doom-glow'
              : 'bg-doom-bg border-slate-600 group-hover:border-emerald-400/70';

            const typeBadgeClasses = isSerial
              ? 'bg-amber-500/10 text-amber-300 border-amber-500/30'
              : 'bg-slate-400/10 text-slate-300 border-slate-500/30';

            return `
              <article
                data-item-id="${item.id}"
                role="checkbox"
                aria-checked="${checked}"
                tabindex="0"
                class="group relative rounded-2xl border p-4 sm:p-4.5 transition-all duration-200 cursor-pointer select-none focus:outline-none focus:ring-2 focus:ring-emerald-500/60 ${cardClasses}"
              >
                <div class="flex items-start gap-3.5">
                  <!-- Căsuță de bifare animată -->
                  <div class="mt-0.5 w-6 h-6 rounded-lg border-2 flex items-center justify-center shrink-0 transition-all duration-200 ${checkboxClasses}">
                    ${
                      checked
                        ? `<svg class="w-4 h-4 animate-check-pop" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
                             <polyline points="20 6 9 17 4 12"></polyline>
                           </svg>`
                        : ''
                    }
                  </div>

                  <!-- Conținut card -->
                  <div class="flex-1 min-w-0">
                    <div class="flex flex-wrap items-center gap-2 mb-1.5">
                      <span class="inline-flex items-center px-2 py-0.5 rounded-md text-[11px] font-semibold border ${typeBadgeClasses}">
                        ${escapeHTML(item.type)}
                      </span>
                      <span class="inline-flex items-center px-2 py-0.5 rounded-md text-[11px] font-semibold bg-doom-bg text-slate-400 border border-doom-border tabular-nums">
                        ${item.year}
                      </span>
                      ${
                        category.isBonus
                          ? `<span class="inline-flex items-center px-2 py-0.5 rounded-md text-[11px] font-semibold bg-emerald-500/10 text-emerald-300/90 border border-emerald-500/25">Bonus</span>`
                          : ''
                      }
                      ${
                        checked
                          ? `<span class="ml-auto inline-flex items-center gap-1 text-[11px] font-semibold text-emerald-400">
                               Văzut
                             </span>`
                          : ''
                      }
                    </div>

                    <h3 class="text-sm sm:text-base font-bold leading-snug transition-colors ${
                      checked ? 'text-slate-400 line-through decoration-emerald-500/60' : 'text-slate-100 group-hover:text-emerald-200'
                    }">
                      ${escapeHTML(item.title)}
                    </h3>

                    <p class="text-xs sm:text-[13px] leading-relaxed mt-1.5 transition-colors ${
                      checked ? 'text-slate-500' : 'text-slate-400'
                    }">
                      ${escapeHTML(item.description)}
                    </p>
                  </div>
                </div>
              </article>
            `;
          })
          .join('');

        htmlParts.push(`
          <section class="rounded-3xl bg-doom-surface/85 border ${
            isCatComplete ? 'border-emerald-500/40' : 'border-doom-border'
          } overflow-hidden transition-colors">
            <!-- Header secțiune colapsabilă -->
            <button
              type="button"
              data-toggle-cat="${category.id}"
              aria-expanded="${!isCollapsed}"
              class="w-full flex flex-col sm:flex-row sm:items-center justify-between gap-3 p-4 sm:p-5 text-left hover:bg-doom-card/50 transition-colors cursor-pointer"
            >
              <div class="flex items-center gap-3 min-w-0">
                <span class="w-8 h-8 rounded-xl flex items-center justify-center text-xs font-extrabold shrink-0 border ${
                  isCatComplete
                    ? 'bg-emerald-500/20 text-emerald-300 border-emerald-500/40'
                    : 'bg-doom-bg text-slate-300 border-doom-border'
                }">
                  ${category.number}
                </span>
                <div class="min-w-0">
                  <h2 class="text-sm sm:text-lg font-extrabold text-slate-100 truncate">
                    ${escapeHTML(category.title)}
                  </h2>
                </div>
              </div>

              <div class="flex items-center justify-between sm:justify-end gap-3 pl-11 sm:pl-0 shrink-0">
                <!-- Mini indicator progres categorie -->
                <div class="flex items-center gap-2.5">
                  <div class="w-20 sm:w-24 h-2 rounded-full bg-doom-bg border border-doom-border overflow-hidden">
                    <div
                      class="h-full rounded-full transition-all duration-300 ${
                        isCatComplete ? 'bg-emerald-400' : 'bg-emerald-600'
                      }"
                      style="width: ${catPercent}%"
                    ></div>
                  </div>
                  <span class="text-xs font-bold tabular-nums px-2 py-0.5 rounded-lg border ${
                    isCatComplete
                      ? 'bg-emerald-500/15 text-emerald-300 border-emerald-500/35'
                      : 'bg-doom-bg text-slate-300 border-doom-border'
                  }">
                    ${catWatched}/${catTotal}
                  </span>
                </div>

                <!-- Icon săgeată colapsare -->
                <svg
                  class="w-5 h-5 text-slate-400 transition-transform duration-200 ${isCollapsed ? '-rotate-90' : 'rotate-0'}"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  aria-hidden="true"
                >
                  <polyline points="6 9 12 15 18 9"></polyline>
                </svg>
              </div>
            </button>

            <!-- Grid de carduri -->
            <div class="${isCollapsed ? 'hidden' : 'block'} px-4 sm:px-5 pb-4 sm:pb-5 pt-1 border-t border-doom-border/50">
              <div class="grid grid-cols-1 md:grid-cols-2 gap-3 sm:gap-3.5 mt-3">
                ${cardsHTML}
              </div>
            </div>
          </section>
        `);
      }

      dom.categoriesContainer.innerHTML = htmlParts.join('');

      if (totalVisibleItems === 0) {
        dom.emptyState.classList.remove('hidden');
      } else {
        dom.emptyState.classList.add('hidden');
      }
    }

    /**
     * Rerandează întreaga interfață sincronizată cu starea curentă
     */
    function renderAll() {
      updateProgressUI();
      renderFilters();
      renderCategories();
    }

    /**
     * Comută starea de văzut/nevăzut pentru un titlu
     */
    function toggleItem(itemId) {
      if (state.watched.has(itemId)) {
        state.watched.delete(itemId);
      } else {
        state.watched.add(itemId);
      }
      saveState();
      renderAll();
    }

    /**
     * Deschide modalul personalizat de confirmare
     */
    function openConfirmModal({ title, message, confirmText, variant, onConfirm }) {
      dom.modalTitle.textContent = title;
      dom.modalMessage.textContent = message;
      dom.modalConfirm.textContent = confirmText;
      state.pendingModalAction = onConfirm;

      if (variant === 'danger') {
        dom.modalIconWrap.className = 'w-10 h-10 rounded-xl flex items-center justify-center shrink-0 border bg-rose-500/10 border-rose-500/30 text-rose-400';
        dom.modalIconWrap.innerHTML = `
          <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M3 6h18M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"></path>
          </svg>`;
        dom.modalConfirm.className = 'px-4 py-2.5 rounded-xl text-xs sm:text-sm font-semibold text-white bg-rose-600 hover:bg-rose-500 transition-colors cursor-pointer';
      } else {
        dom.modalIconWrap.className = 'w-10 h-10 rounded-xl flex items-center justify-center shrink-0 border bg-emerald-500/10 border-emerald-500/30 text-emerald-400';
        dom.modalIconWrap.innerHTML = `
          <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
            <polyline points="20 6 9 17 4 12"></polyline>
          </svg>`;
        dom.modalConfirm.className = 'px-4 py-2.5 rounded-xl text-xs sm:text-sm font-semibold text-doom-bg bg-emerald-400 hover:bg-emerald-300 transition-colors cursor-pointer';
      }

      dom.modal.classList.remove('hidden');
      dom.modalConfirm.focus();
    }

    function closeConfirmModal() {
      dom.modal.classList.add('hidden');
      state.pendingModalAction = null;
    }

    /**
     * Inițializează toți ascultătorii de evenimente
     */
    function bindEvents() {
      // Toggle bonus în calculul procentului
      dom.toggleBonus.addEventListener('change', (e) => {
        state.includeBonus = e.target.checked;
        saveState();
        updateProgressUI();
      });

      // Filtrare rapidă (delegare de evenimente)
      dom.filterBar.addEventListener('click', (e) => {
        const btn = e.target.closest('[data-filter]');
        if (!btn) return;
        state.activeFilter = btn.dataset.filter;
        renderFilters();
        renderCategories();
      });

      // Căutare live
      dom.searchInput.addEventListener('input', (e) => {
        state.searchQuery = e.target.value;
        dom.clearSearch.classList.toggle('hidden', state.searchQuery.length === 0);
        renderCategories();
      });

      dom.clearSearch.addEventListener('click', () => {
        state.searchQuery = '';
        dom.searchInput.value = '';
        dom.clearSearch.classList.add('hidden');
        renderCategories();
        dom.searchInput.focus();
      });

      // Resetare filtre din starea goală
      dom.btnClearFilters.addEventListener('click', () => {
        state.activeFilter = 'all';
        state.searchQuery = '';
        dom.searchInput.value = '';
        dom.clearSearch.classList.add('hidden');
        renderAll();
      });

      // Click pe card (bifează/debifează) sau pe header categorie (colapsează/extinde)
      dom.categoriesContainer.addEventListener('click', (e) => {
        const card = e.target.closest('[data-item-id]');
        if (card) {
          toggleItem(card.dataset.itemId);
          return;
        }

        const catToggle = e.target.closest('[data-toggle-cat]');
        if (catToggle) {
          const catId = catToggle.dataset.toggleCat;
          if (state.collapsed.has(catId)) {
            state.collapsed.delete(catId);
          } else {
            state.collapsed.add(catId);
          }
          saveState();
          renderCategories();
        }
      });

      // Suport tastatură (Enter / Space) pe carduri pentru accesibilitate
      dom.categoriesContainer.addEventListener('keydown', (e) => {
        if (e.key !== 'Enter' && e.key !== ' ') return;
        const card = e.target.closest('[data-item-id]');
        if (!card) return;
        e.preventDefault();
        toggleItem(card.dataset.itemId);
      });

      // Buton: Bifează tot
      dom.btnCheckAll.addEventListener('click', () => {
        openConfirmModal({
          title: 'Bifează toate titlurile?',
          message: 'Toate cele 20 de filme și seriale din lista de maraton vor fi marcate ca văzute.',
          confirmText: 'Da, bifează tot',
          variant: 'success',
          onConfirm: () => {
            ALL_ITEMS.forEach((item) => state.watched.add(item.id));
            saveState();
            renderAll();
          },
        });
      });

      // Buton: Resetează progresul
      dom.btnResetAll.addEventListener('click', () => {
        openConfirmModal({
          title: 'Resetezi progresul?',
          message: 'Toate bifările salvate vor fi șterse și progresul va reveni la 0%. Această acțiune nu poate fi anulată.',
          confirmText: 'Da, resetează',
          variant: 'danger',
          onConfirm: () => {
            state.watched.clear();
            saveState();
            renderAll();
          },
        });
      });

      // Evenimente modal
      dom.modalCancel.addEventListener('click', closeConfirmModal);
      dom.modalConfirm.addEventListener('click', () => {
        if (typeof state.pendingModalAction === 'function') {
          state.pendingModalAction();
        }
        closeConfirmModal();
      });
      dom.modal.addEventListener('click', (e) => {
        if (e.target === dom.modal) closeConfirmModal();
      });
      document.addEventListener('keydown', (e) => {
        if (e.key === 'Escape' && !dom.modal.classList.contains('hidden')) {
          closeConfirmModal();
        }
      });
    }

    // Pornire aplicație
    window.addEventListener('DOMContentLoaded', () => {
      loadState();
      bindEvents();
      renderAll();
      updateCountdown();
      setInterval(updateCountdown, 1000);
    });
  </script>
</body>
</html>
