<!DOCTYPE html>
<html lang="en">
<head>
  <!--
    IMPLEMENTATION NOTES (read once, then scroll):
    1) Put these files next to this index.html:
       - intro.mp4                  (your AI video export)
       - intro.en.vtt               (optional captions; see steps below)
       - poster.jpg                 (optional thumbnail)
    2) Test locally via a local server (e.g., VS Code Live Server or `python -m http.server`).
  -->
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Bhuvan Parashar • Software Engineer (Java & Spring Boot)</title>
  <meta name="description" content="Software Engineer with 4+ years of backend experience in Java, Spring Boot, microservices, and scalable payment systems." />

  <!-- Fonts & Tailwind -->
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Icons (Lucide) -->
  <script src="https://unpkg.com/lucide@latest"></script>

  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          fontFamily: { sans: ['Inter', 'ui-sans-serif', 'system-ui'] },
          colors: {
            base: '#060913',
            base2: '#0b1020',
            ink: '#e5e7eb',
            accent: '#22d3ee',  /* cyan-400 */
            accent2: '#a78bfa', /* violet-400 */
            mint: '#10b981',
          },
          boxShadow: {
            glow: '0 0 0 2px rgba(34,211,238,0.15), 0 10px 40px -10px rgba(167,139,250,0.25)',
          },
          keyframes: {
            floaty: { '0%,100%': { transform: 'translateY(0)' }, '50%': { transform: 'translateY(-6px)' } },
            fadeInUp: { '0%': { opacity: 0, transform: 'translateY(12px)' }, '100%': { opacity: 1, transform: 'translateY(0)' } },
            sheen: { '0%': { transform: 'translateX(-120%)' }, '100%': { transform: 'translateX(120%)' } },
            borderSpin: { '0%': { transform: 'rotate(0deg)' }, '100%': { transform: 'rotate(360deg)' } },
          },
          animation: {
            floaty: 'floaty 6s ease-in-out infinite',
            fadeInUp: 'fadeInUp .8s ease forwards',
            sheen: 'sheen 1.2s linear infinite',
            borderSpin: 'borderSpin 7s linear infinite',
          }
        }
      }
    }
  </script>

  <style>
    :root {
      --ring: rgba(34, 211, 238, .45);
      --card-bg: rgba(10, 15, 30, .6);
      --card-stroke: rgba(148, 163, 184, .18);
    }
    html { scroll-behavior: smooth; }
    body {
      background:
        radial-gradient(1200px 500px at 10% -10%, #0b173a55, transparent 60%),
        radial-gradient(1000px 500px at 110% 10%, #2a0c3a55, transparent 60%),
        #060913;
    }
    .reveal { opacity: 0; transform: translateY(16px); transition: all .7s ease; }
    .reveal.visible { opacity: 1; transform: translateY(0); }

    /* Scrollbar */
    ::-webkit-scrollbar { width: 10px; height: 10px; }
    ::-webkit-scrollbar-track { background: #0b1020; }
    ::-webkit-scrollbar-thumb { background: #2b3a55; border-radius: 10px; }
    ::-webkit-scrollbar-thumb:hover { background: #3a4a6a; }

    /* Glass cards */
    .card {
      position: relative;
      background: linear-gradient(180deg, rgba(15,23,42,.75), rgba(2,6,23,.6));
      border: 1px solid var(--card-stroke);
      backdrop-filter: blur(10px);
      border-radius: 16px;
      transition: transform .25s ease, box-shadow .25s ease, border-color .25s ease;
      box-shadow: 0 30px 60px -30px rgba(0,0,0,.6);
    }
    .card:hover { transform: translateY(-2px); border-color: rgba(167,139,250,.35); box-shadow: 0 0 0 2px rgba(167,139,250,.12), 0 30px 60px -28px rgba(0,0,0,.8); }
    .card--border { overflow: hidden; }
    .card--border::before {
      content: '';
      position: absolute; inset: -120%;
      background: conic-gradient(from 0deg,
        transparent 0deg,
        rgba(34,211,238,.35) 60deg,
        rgba(167,139,250,.35) 120deg,
        rgba(16,185,129,.30) 180deg,
        rgba(34,211,238,.35) 240deg,
        transparent 360deg);
      animation: borderSpin linear infinite 7s;
      filter: blur(18px);
    }
    .card--border::after {
      content: '';
      position: absolute; inset: 1px;
      border-radius: 14px;
      background: var(--card-bg);
      border: 1px solid var(--card-stroke);
      backdrop-filter: blur(8px);
    }
    .card--border > * { position: relative; z-index: 1; }

    /* Buttons */
    .focus-ring:focus { outline: none; box-shadow: 0 0 0 3px var(--ring); }
    .btn-sheen { position: relative; overflow: hidden; }
    .btn-sheen::after {
      content: ''; position: absolute; inset: 0;
      background: linear-gradient(120deg, transparent 0%, rgba(255,255,255,.35) 20%, transparent 40%);
      transform: translateX(-120%);
    }
    .btn-sheen:hover::after { animation: sheen 1.2s linear; }

    /* Code rain canvas */
    #codeCanvas {
      position: fixed; inset: 0; z-index: -1;
      opacity: .28; mix-blend-mode: screen; pointer-events: none;
    }

    /* Tags */
    .tag {
      display: inline-flex; align-items: center; gap: .35rem;
      padding: .35rem .6rem; border-radius: .6rem;
      background: rgba(148,163,184,.08);
      border: 1px solid rgba(148,163,184,.18);
      transition: all .2s ease; font-size: .8rem;
    }
    .tag:hover { border-color: rgba(34,211,238,.35); color: #67e8f9; }
    .badge {
      display: inline-flex; align-items: center; gap: .5rem;
      padding: .4rem .7rem; border-radius: 999px;
      background: rgba(34,211,238,.12);
      border: 1px solid rgba(34,211,238,.35);
      font-size: .75rem; color: #a5f3fc;
    }
  </style>
</head>

<body class="bg-base text-ink font-sans selection:bg-accent/30 selection:text-white">
  <!-- Animated code background -->
  <canvas id="codeCanvas" aria-hidden="true"></canvas>

  <!-- Soft radial accents -->
  <div aria-hidden="true" class="pointer-events-none fixed inset-x-0 -top-24 h-48 opacity-50 blur-3xl" style="background: radial-gradient(600px 200px at 10% 50%, rgba(34,211,238,.45), transparent 60%); z-index:-1;"></div>
  <div aria-hidden="true" class="pointer-events-none fixed inset-x-0 -top-16 h-56 opacity-30 blur-3xl" style="background: radial-gradient(600px 220px at 90% 50%, rgba(167,139,250,.35), transparent 60%); z-index:-1;"></div>

  <!-- Nav -->
  <header class="sticky top-0 z-40 bg-base/70 backdrop-blur border-b border-slate-800/70">
    <div class="mx-auto max-w-7xl px-4 py-3 flex items-center justify-between">
      <a href="#top" class="text-lg font-extrabold tracking-tight hover:text-accent transition flex items-center gap-2" aria-label="Go to top">
        <span class="inline-flex items-center justify-center h-8 w-8 rounded-lg bg-accent/15 border border-accent/40">
          <i data-lucide="code-xml" class="w-4 h-4" aria-hidden="true"></i>
        </span>
        BP.
      </a>
      <nav class="hidden md:flex items-center gap-6 text-sm" aria-label="Primary">
        <a href="#skills" class="hover:text-accent transition flex items-center gap-2"><i data-lucide="sparkles" class="w-4 h-4"></i>Skills</a>
        <a href="#experience" class="hover:text-accent transition flex items-center gap-2"><i data-lucide="briefcase" class="w-4 h-4"></i>Experience</a>
        <a href="#projects" class="hover:text-accent transition flex items-center gap-2"><i data-lucide="box" class="w-4 h-4"></i>Projects</a>
        <a href="#contact" class="hover:text-accent transition flex items-center gap-2"><i data-lucide="send" class="w-4 h-4"></i>Contact</a>
      </nav>
      <a href="#contact" class="px-4 py-2 rounded-lg bg-accent/20 hover:bg-accent/30 border border-accent/40 text-accent transition focus-ring btn-sheen flex items-center gap-2">
        <i data-lucide="message-square" class="w-4 h-4"></i> Get in touch
      </a>
    </div>
  </header>

  <!-- Hero -->
  <section id="top" class="relative overflow-hidden">
    <div class="mx-auto max-w-7xl px-4 py-16 lg:py-24 grid lg:grid-cols-2 gap-10 items-center">
      <div class="reveal">
        <div class="inline-flex items-center gap-2 badge">
          <i data-lucide="zap" class="w-4 h-4"></i> Java • Spring Boot • Fintech Integrations
        </div>
        <h1 class="mt-4 text-4xl lg:text-6xl font-extrabold leading-tight tracking-tight">
          Bhuvan Parashar
        </h1>
        <p class="mt-2 text-xl text-slate-300">Software Engineer • Java &amp; Spring Boot Specialist</p>
        <p class="mt-6 text-slate-300/90 leading-relaxed">
          Backend engineer with 4+ years building secure, high-performance fintech systems: Java, Spring Boot, microservices, UPI, VAN, wallets, BNPL. Led 10+ integrations across banks, modernized monoliths, and tuned SQL for measurable performance wins.
        </p>
        <div class="mt-8 flex flex-wrap gap-3">
          <a href="#experience" class="px-5 py-3 rounded-lg bg-accent text-slate-900 font-semibold hover:shadow-glow transition focus-ring btn-sheen flex items-center gap-2">
            <i data-lucide="timeline" class="w-4 h-4"></i> View Experience
          </a>
          <a href="#skills" class="px-5 py-3 rounded-lg border border-slate-700 hover:border-accent/60 hover:text-accent transition focus-ring flex items-center gap-2">
            <i data-lucide="grid" class="w-4 h-4"></i> Explore Skills
          </a>
        </div>
        <p class="mt-4 text-xs text-slate-400">Resume-backed profile</p>
      </div>

      <!-- Video Panel (Fully wired) -->
      <div class="reveal">
        <div class="card card--border rounded-2xl p-5 lg:p-6 shadow-glow">
          <div class="relative aspect-video rounded-xl overflow-hidden border border-slate-700">
            <!--
              HOW TO USE:
              - Place "intro.mp4" beside this HTML.
              - Optional captions: place "intro.en.vtt" beside it.
              - Optional poster: place "poster.jpg" beside it.
            -->
            <video
              id="introVideo"
              class="w-full h-full object-cover"
              controls
              preload="none"
              playsinline
              poster="poster.jpg"
              controlslist="nodownload"
              disablepictureinpicture
              aria-label="Intro video: Bhuvan Parashar - Java & Spring Boot Engineer"
            >
              <source src="intro.mp4" type="video/mp4" />
              <!-- Captions track (optional but recommended) -->
              <track label="English" kind="subtitles" srclang="en" src="intro.en.vtt" default />
              Your browser does not support the video tag.
            </video>

            <!-- Loading shimmer -->
            <div id="loadingShimmer" class="absolute inset-0 pointer-events-none">
              <div class="absolute inset-x-0 top-0 h-1 overflow-hidden">
                <div class="h-full w-1/3 bg-gradient-to-r from-transparent via-white/60 to-transparent animate-sheen"></div>
              </div>
            </div>

            <!-- Top-right chips -->
            <div class="absolute top-3 right-3 flex gap-2">
              <span class="tag"><i data-lucide="shield-check" class="w-4 h-4"></i>Secure</span>
              <span class="tag"><i data-lucide="rocket" class="w-4 h-4"></i>Scalable</span>
            </div>
          </div>

          <!-- Play button (works with JS below) -->
          <div class="mt-4 flex items-center gap-3">
            <button id="playBtn" class="px-4 py-2 rounded-lg bg-accent text-slate-900 font-semibold hover:shadow-glow transition focus-ring btn-sheen flex items-center gap-2">
              <i data-lucide="play" class="w-4 h-4"></i> Play Intro
            </button>
            <a href="#video-instructions" class="text-sm underline hover:text-accent transition flex items-center gap-1">
              <i data-lucide="wand-2" class="w-4 h-4"></i> How this video was made
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Skills -->
  <section id="skills" class="py-16 border-t border-slate-800/70">
    <div class="mx-auto max-w-7xl px-4">
      <h2 class="text-3xl font-bold mb-8 reveal flex items-center gap-3">
        <i data-lucide="sparkle" class="w-7 h-7"></i> Key Skills
      </h2>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        <!-- Cards replicated from your data -->
        <div class="card rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent flex items-center gap-2">
            <i data-lucide="braces" class="w-5 h-5"></i> Languages & Frameworks
          </h3>
          <div class="flex flex-wrap gap-2">
            <span class="tag">Core Java (JSE)</span><span class="tag">Advanced Java (JEE)</span>
            <span class="tag">Spring Boot</span><span class="tag">Spring MVC</span>
            <span class="tag">Hibernate</span><span class="tag">JPA</span>
            <span class="tag">REST</span><span class="tag">SOAP</span>
          </div>
        </div>

        <div class="card rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent flex items-center gap-2">
            <i data-lucide="sitemap" class="w-5 h-5"></i> Architecture & Design
          </h3>
          <div class="flex flex-wrap gap-2">
            <span class="tag">Monolith → Microservices</span><span class="tag">Proxy Pattern</span>
            <span class="tag">Security Interceptors</span><span class="tag">API Lifecycle</span>
          </div>
        </div>

        <div class="card rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent flex items-center gap-2">
            <i data-lucide="contactless-payment" class="w-5 h-5"></i> Fintech & Payments
          </h3>
          <div class="flex flex-wrap gap-2">
            <span class="tag">Credit Card Lifecycle</span><span class="tag">Wallet Services</span>
            <span class="tag">Loyalty Programs</span><span class="tag">VAN Systems</span>
            <span class="tag">UPI</span><span class="tag">Net Banking</span><span class="tag">BNPL</span>
          </div>
        </div>

        <div class="card rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent flex items-center gap-2">
            <i data-lucide="gauge" class="w-5 h-5"></i> Performance & Security
          </h3>
          <div class="flex flex-wrap gap-2">
            <span class="tag">SQL Optimization</span><span class="tag">Encryption/Decryption</span>
            <span class="tag">Checksum Validation</span><span class="tag">API Fallback</span>
            <span class="tag">Schedulers</span>
          </div>
        </div>

        <div class="card rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent flex items-center gap-2">
            <i data-lucide="database" class="w-5 h-5"></i> Databases & Testing
          </h3>
          <div class="flex flex-wrap gap-2">
            <span class="tag">MySQL</span><span class="tag">Oracle DB</span><span class="tag">JUnit</span><span class="tag">JSON/XML</span>
          </div>
        </div>

        <div class="card rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent flex items-center gap-2">
            <i data-lucide="settings" class="w-5 h-5"></i> DevOps & Tools
          </h3>
          <div class="flex flex-wrap gap-2">
            <span class="tag">Maven</span><span class="tag">Git</span><span class="tag">CI/CD</span><span class="tag">Docker</span>
            <span class="tag">Kubernetes</span><span class="tag">Kafka</span><span class="tag">Tomcat</span>
            <span class="tag">Oracle WebLogic</span><span class="tag">Linux Scripting</span>
            <span class="tag">Postman</span><span class="tag">GCloud VCS</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Experience -->
  <section id="experience" class="py-16 border-t border-slate-800/70">
    <div class="mx-auto max-w-7xl px-4">
      <h2 class="text-3xl font-bold mb-8 reveal flex items-center gap-3">
        <i data-lucide="briefcase" class="w-7 h-7"></i> Professional Experience
      </h2>

      <article class="card card--border rounded-2xl p-6 mb-6 reveal">
        <div class="flex flex-col lg:flex-row lg:items-start lg:justify-between gap-2">
          <div>
            <h3 class="text-xl font-semibold flex items-center gap-2">
              <i data-lucide="wallet" class="w-5 h-5"></i> Software Engineer — Obopay Mobile Technologies Pvt Ltd
            </h3>
            <p class="text-sm text-slate-400">Aug 2025 – Present</p>
          </div>
          <span class="badge"><i data-lucide="gift" class="w-4 h-4"></i> Wallets • Cards • Loyalty</span>
        </div>
        <ul class="mt-4 space-y-2 list-disc list-inside text-slate-300/90">
          <li>Loyalty APIs (points, coupons, redemptions).</li>
          <li>Card issuance, linking, transactions, reversals in wallet ecosystem.</li>
          <li>Hardened SOAP monolith with Proxy & Security Interceptors.</li>
          <li>SQL tuning, JUnit coverage, exception handling, tokenization, Linux scripting.</li>
          <li>Deployments: Tomcat (Dev), Oracle WebLogic (Prod), GCloud VCS.</li>
          <li>Contributing to monolith→microservices modernization.</li>
        </ul>
      </article>

      <article class="card rounded-2xl p-6 mb-6 reveal">
        <div class="flex flex-col lg:flex-row lg:items-start lg:justify-between gap-2">
          <div>
            <h3 class="text-xl font-semibold flex items-center gap-2">
              <i data-lucide="building-2" class="w-5 h-5"></i> Software Developer — SabPaisa (SRS Live Technologies Pvt. Ltd.)
            </h3>
            <p class="text-sm text-slate-400">Feb 2022 – Jan 2025</p>
          </div>
        <span class="badge"><i data-lucide="link-2" class="w-4 h-4"></i> UPI • VAN • Microservices</span>
        </div>
        <ul class="mt-4 space-y-2 list-disc list-inside text-slate-300/90">
          <li>Split legacy monolith into services (Challan) → maintainability↑.</li>
          <li>VAN Generate (Cash/NEFT/RTGS/IMPS) & VAN Merchant (multi-collection).</li>
          <li>VAN Bank: real-time verification & status with multiple banks.</li>
          <li>UPI QR: unified dynamic QR + intent endpoint.</li>
          <li>10+ bank integrations with encryption, checksums, webhooks, fallbacks.</li>
          <li>Impact: performance +30%, TAT −20%, 95%+ client satisfaction.</li>
        </ul>
      </article>

      <article class="card rounded-2xl p-6 reveal">
        <div class="flex flex-col lg:flex-row lg:items-start lg:justify-between gap-2">
          <div>
            <h3 class="text-xl font-semibold flex items-center gap-2">
              <i data-lucide="graduation-cap" class="w-5 h-5"></i> Java Intern — SabPaisa
            </h3>
            <p class="text-sm text-slate-400">Aug 2021 – Jan 2022</p>
          </div>
          <span class="badge"><i data-lucide="credit-card" class="w-4 h-4"></i> Payment Gateway</span>
        </div>
        <ul class="mt-4 space-y-2 list-disc list-inside text-slate-300/90">
          <li>Built REST APIs for payments, CRUD & transaction logs.</li>
          <li>Agile (Scrum, Standups, Sprint Planning).</li>
        </ul>
      </article>

      <!-- Projects -->
      <div id="projects" class="mt-10 reveal">
        <h3 class="text-lg font-semibold mb-4 flex items-center gap-2">
          <i data-lucide="box" class="w-5 h-5"></i> Key Projects
        </h3>
        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-4">
          <div class="card rounded-xl p-5"><div class="flex items-center gap-2 font-medium">
            <i data-lucide="gift" class="w-5 h-5 text-accent"></i> Loyalty Program API</div>
            <p class="text-sm text-slate-400 mt-1">Points, coupons, redemptions with audit trails.</p></div>
          <div class="card rounded-xl p-5"><div class="flex items-center gap-2 font-medium">
            <i data-lucide="columns-3" class="w-5 h-5 text-accent"></i> VAN Merchant Service</div>
            <p class="text-sm text-slate-400 mt-1">Multiple collections per VAN with ACL.</p></div>
          <div class="card rounded-xl p-5"><div class="flex items-center gap-2 font-medium">
            <i data-lucide="scan-line" class="w-5 h-5 text-accent"></i> UPI QR Application</div>
            <p class="text-sm text-slate-400 mt-1">Unified Intent + dynamic QR flows.</p></div>
          <div class="card rounded-xl p-5"><div class="flex items-center gap-2 font-medium">
            <i data-lucide="split" class="w-5 h-5 text-accent"></i> Challan Microservices</div>
            <p class="text-sm text-slate-400 mt-1">Monolith → microservices for scale.</p></div>
        </div>
      </div>

      <!-- Achievements & Education -->
      <div class="mt-10 reveal">
        <h3 class="text-lg font-semibold mb-4 flex items-center gap-2">
          <i data-lucide="trophy" class="w-5 h-5"></i> Achievements & Certifications
        </h3>
        <ul class="space-y-2 text-slate-300/90 list-disc list-inside">
          <li>Rising Star Award (2023–24) – SabPaisa</li>
          <li>Quick Resolver Award (2022–23) – SabPaisa</li>
          <li>Certs: HackerRank (Java & Problem-Solving), Advanced Java (Programming Hub), Oracle Java Explorer, Time Management (Udemy)</li>
        </ul>
      </div>

      <div class="mt-10 reveal">
        <h3 class="text-lg font-semibold mb-4 flex items-center gap-2">
          <i data-lucide="book-open-check" class="w-5 h-5"></i> Education
        </h3>
        <p>MCA (2020–2022) – Maharishi Dayanand University, Rohtak</p>
        <p>BCA (2016–2019) – Maharishi Dayanand University, Rohtak</p>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="py-16 border-t border-slate-800/70">
    <div class="mx-auto max-w-7xl px-4">
      <h2 class="text-3xl font-bold mb-8 reveal flex items-center gap-3">
        <i data-lucide="send" class="w-7 h-7"></i> Contact
      </h2>
      <div class="grid md:grid-cols-2 gap-6">
        <div class="card rounded-xl p-6 reveal">
          <p class="text-slate-300/90">Open to roles in Java microservices, distributed systems, and scalable API design. Let’s build something reliable & fast.</p>
          <div class="mt-5 space-y-3">
            <p class="flex items-center gap-3"><i data-lucide="phone" class="w-5 h-5 text-accent"></i> +91-9716052290</p>
            <p class="flex items-center gap-3"><i data-lucide="mail" class="w-5 h-5 text-accent"></i>
              <a class="underline hover:text-accent" href="mailto:bhuvan.parashar24@gmail.com">bhuvan.parashar24@gmail.com</a></p>
            <p class="flex items-center gap-3"><i data-lucide="linkedin" class="w-5 h-5 text-accent"></i>
              <a class="underline hover:text-accent" href="https://linkedin.com/in/bhuvan-parashar" target="_blank" rel="noreferrer">linkedin.com/in/bhuvan-parashar</a></p>
          </div>
        </div>

        <div class="card rounded-xl p-6 reveal" id="video-instructions">
          <h3 class="font-semibold text-accent mb-3 flex items-center gap-2">
            <i data-lucide="wand-2" class="w-5 h-5"></i> Intro Video Notes
          </h3>
          <ol class="list-decimal list-inside text-slate-300/90 space-y-2">
            <li>Generate your AI video using the script I provided (60s recommended).</li>
            <li>Export as <code>intro.mp4</code>, 1920×1080 (H.264), 24–30fps.</li>
            <li>(Optional) Save captions as <code>intro.en.vtt</code>; add a <code>poster.jpg</code> thumbnail.</li>
            <li>Place the files next to this <code>index.html</code>.</li>
            <li>Use a local server to test (so captions load).</li>
          </ol>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-10 border-t border-slate-800/70">
    <div class="mx-auto max-w-7xl px-4 text-sm text-slate-500 flex flex-col md:flex-row items-center justify-between gap-3">
      <p>&copy; <span id="year"></span> Bhuvan Parashar</p>
      <p>Short-term: Java microservices, distributed systems, observability. Long-term: AI/ML-assisted backends.</p>
    </div>
  </footer>

  <!-- Scripts -->
  <script>
    // Lucide icons
    window.addEventListener('DOMContentLoaded', () => { lucide.createIcons(); });

    // Reveal on scroll
    const io = new IntersectionObserver((entries) => {
      entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
    }, { threshold: 0.12 });
    document.querySelectorAll('.reveal').forEach(el => io.observe(el));

    // Video controls (Play button + shimmer)
    const video = document.getElementById('introVideo');
    const playBtn = document.getElementById('playBtn');
    const shimmer = document.getElementById('loadingShimmer');
    if (playBtn && video) {
      playBtn.addEventListener('click', () => {
        shimmer?.classList.add('opacity-0');
        video.play().catch(console.warn);
      });
      video.addEventListener('play', () => shimmer?.classList.add('hidden'));
      video.addEventListener('loadeddata', () => shimmer?.classList.add('hidden'));
    }

    // Footer year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Code rain background
    const canvas = document.getElementById('codeCanvas');
    const ctx = canvas.getContext('2d');
    const glyphs = '01{}[]()<>=+-/*$#&_~:%^!?ABCDEFGHIJKLMNOPQRSTUVWXYZ';
    let width, height, cols, drops;

    function resizeCanvas() {
      width = canvas.width = window.innerWidth;
      height = canvas.height = window.innerHeight;
      cols = Math.floor(width / 16);
      drops = Array(cols).fill(0).map(() => Math.random() * -height);
    }
    resizeCanvas();
    window.addEventListener('resize', resizeCanvas);

    function draw() {
      ctx.fillStyle = 'rgba(6, 9, 19, 0.08)'; // trail
      ctx.fillRect(0, 0, width, height);

      const grad = ctx.createLinearGradient(0, 0, width, height);
      grad.addColorStop(0, 'rgba(34,211,238,0.9)');
      grad.addColorStop(0.5, 'rgba(167,139,250,0.85)');
      grad.addColorStop(1, 'rgba(16,185,129,0.85)');
      ctx.fillStyle = grad;
      ctx.font = '14px monospace';

      for (let i = 0; i < drops.length; i++) {
        const text = glyphs[Math.floor(Math.random() * glyphs.length)];
        const x = i * 16;
        const y = drops[i] * 16;

        ctx.fillText(text, x, y);

        if (y > height && Math.random() > 0.985) drops[i] = Math.random() * -20;
        drops[i] += 0.9 + Math.random() * 0.6;
      }
      requestAnimationFrame(draw);
    }
    draw();
  </script>
</body>
</html>
