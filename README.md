<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Bhuvan Parashar • Software Engineer (Java & Spring Boot)</title>
  <meta name="description" content="Software Engineer with 4+ years of backend experience in Java, Spring Boot, microservices, and scalable payment systems." />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">
  <!-- Tailwind (CDN) -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: { sans: ['Inter', 'ui-sans-serif', 'system-ui'] },
          colors: {
            base: '#0b1020',
            base2: '#0f172a',
            ink: '#e5e7eb',
            accent: '#22d3ee', /* cyan-400 */
            accent2: '#a78bfa', /* violet-400 */
          },
          boxShadow: {
            glow: '0 0 0 2px rgba(34,211,238,0.2), 0 0 40px rgba(167,139,250,0.15)',
          },
          keyframes: {
            floaty: { '0%,100%': { transform: 'translateY(0)' }, '50%': { transform: 'translateY(-6px)' } },
            fadeInUp: { '0%': { opacity: 0, transform: 'translateY(12px)' }, '100%': { opacity: 1, transform: 'translateY(0)' } },
            shimmer: { '0%': { transform: 'translateX(-100%)' }, '100%': { transform: 'translateX(100%)' } },
          },
          animation: {
            floaty: 'floaty 6s ease-in-out infinite',
            fadeInUp: 'fadeInUp .8s ease forwards',
            shimmer: 'shimmer 2s linear infinite',
          }
        }
      },
      darkMode: 'class'
    }
  </script>
  <style>
    /* Smooth scrolling & reveal on scroll */
    html { scroll-behavior: smooth; }
    .reveal { opacity: 0; transform: translateY(16px); transition: all .7s ease; }
    .reveal.visible { opacity: 1; transform: translateY(0); }
    /* Pretty scrollbar (desktop) */
    ::-webkit-scrollbar { width: 10px; }
    ::-webkit-scrollbar-track { background: #0f172a; }
    ::-webkit-scrollbar-thumb { background: #334155; border-radius: 8px; }
    ::-webkit-scrollbar-thumb:hover { background: #475569; }
    /* Glass card */
    .glass { background: linear-gradient(180deg, rgba(15,23,42,.8), rgba(2,6,23,.6)); backdrop-filter: blur(8px); border: 1px solid rgba(148,163,184,.15); }
    /* Focus ring */
    .focus-ring:focus { outline: none; box-shadow: 0 0 0 3px rgba(34,211,238,.4); }
  </style>
</head>

<body class="bg-base text-ink font-sans selection:bg-accent/30 selection:text-white">
  <!-- Nav -->
  <header class="sticky top-0 z-40 bg-base/80 backdrop-blur border-b border-slate-800">
    <div class="mx-auto max-w-7xl px-4 py-3 flex items-center justify-between">
      <a href="#top" class="text-lg font-extrabold tracking-tight hover:text-accent transition">BP.</a>
      <nav class="hidden md:flex items-center gap-6 text-sm">
        <a href="#skills" class="hover:text-accent transition">Skills</a>
        <a href="#experience" class="hover:text-accent transition">Experience</a>
        <a href="#contact" class="hover:text-accent transition">Contact</a>
      </nav>
      <a href="#contact" class="px-4 py-2 rounded-lg bg-accent/20 hover:bg-accent/30 border border-accent/40 text-accent transition focus-ring">Get in touch</a>
    </div>
  </header>

  <!-- Hero -->
  <section id="top" class="relative overflow-hidden">
    <div class="absolute inset-0 pointer-events-none opacity-40">
      <div class="absolute -top-24 -right-16 h-80 w-80 rounded-full blur-3xl" style="background: radial-gradient(600px 200px at 50% 50%, rgba(34,211,238,.35), transparent 60%);"></div>
      <div class="absolute -bottom-24 -left-16 h-96 w-96 rounded-full blur-3xl" style="background: radial-gradient(600px 200px at 50% 50%, rgba(167,139,250,.25), transparent 60%);"></div>
    </div>

    <div class="mx-auto max-w-7xl px-4 py-20 lg:py-28 grid lg:grid-cols-2 gap-10 items-center">
      <div class="reveal">
        <h1 class="text-4xl lg:text-6xl font-extrabold leading-tight">
          Bhuvan Parashar
        </h1>
        <p class="mt-2 text-xl text-slate-300">Software Engineer | Java &amp; Spring Boot Specialist</p>
        <p class="mt-6 text-slate-300/90 leading-relaxed">
          Software Engineer with 4+ years of backend development experience in Java, Spring Boot, and scalable payment systems. Proven expertise in designing secure, high-performance applications, modernizing legacy monoliths into microservices, and delivering banking &amp; fintech integrations across 10+ financial institutions. Skilled in REST/SOAP APIs, credit card lifecycle, wallet services, VAN-based systems, UPI, and BNPL platforms. Adept at SQL tuning, exception handling, JUnit testing, and secure transaction workflows. Recognized for improving performance by 30%, leading 10+ projects end-to-end, and mentoring junior developers. Currently expanding expertise in microservices, containerization, and distributed systems, with long-term aspirations to explore AI/ML-driven backend solutions.
        </p>
        <div class="mt-8 flex flex-wrap gap-3">
          <a href="#experience" class="px-5 py-3 rounded-lg bg-accent text-slate-900 font-semibold hover:shadow-glow transition focus-ring">View Experience</a>
          <a href="#skills" class="px-5 py-3 rounded-lg border border-slate-700 hover:border-accent/60 hover:text-accent transition focus-ring">Explore Skills</a>
        </div>
        <p class="mt-4 text-xs text-slate-400">Source: Resume</p>
      </div>

      <!-- Video Panel -->
      <div class="reveal">
        <div class="glass rounded-2xl p-4 lg:p-6 shadow-glow">
          <div class="relative aspect-video rounded-xl overflow-hidden border border-slate-700">
            <!-- Placeholder for AI video -->
            <video id="introVideo" class="w-full h-full object-cover" controls poster="" preload="none">
              <!-- Replace the src below with your generated video URL/file -->
              <source src="intro.mp4" type="video/mp4" />
              Your browser does not support the video tag.
            </video>
            <div id="loadingShimmer" class="absolute inset-0 pointer-events-none">
              <div class="absolute inset-x-0 top-0 h-1 overflow-hidden">
                <div class="h-full w-1/3 bg-gradient-to-r from-transparent via-white/60 to-transparent animate-shimmer"></div>
              </div>
            </div>
          </div>
          <div class="mt-4 flex items-center gap-3">
            <button id="playBtn" class="px-4 py-2 rounded-lg bg-accent text-slate-900 font-semibold hover:shadow-glow transition focus-ring">Play Intro</button>
            <a href="#video-instructions" class="text-sm underline hover:text-accent transition">How this video was made</a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Skills -->
  <section id="skills" class="py-16 border-t border-slate-800">
    <div class="mx-auto max-w-7xl px-4">
      <h2 class="text-3xl font-bold mb-6 reveal">Key Skills</h2>

      <!-- Categories -->
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        <!-- Languages & Frameworks -->
        <div class="glass rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent">Languages &amp; Frameworks</h3>
          <div class="flex flex-wrap gap-2">
            <!-- From resume -->
            <span class="px-3 py-1 rounded-lg bg-accent/15 border border-accent/30 hover:border-accent transition">Core Java (JSE)</span>
            <span class="px-3 py-1 rounded-lg bg-accent/15 border border-accent/30 hover:border-accent transition">Advanced Java (JEE)</span>
            <span class="px-3 py-1 rounded-lg bg-accent/15 border border-accent/30 hover:border-accent transition">Spring Boot</span>
            <span class="px-3 py-1 rounded-lg bg-accent/15 border border-accent/30 hover:border-accent transition">Spring MVC</span>
            <span class="px-3 py-1 rounded-lg bg-accent/15 border border-accent/30 hover:border-accent transition">Hibernate</span>
            <span class="px-3 py-1 rounded-lg bg-accent/15 border border-accent/30 hover:border-accent transition">JPA</span>
            <span class="px-3 py-1 rounded-lg bg-accent/15 border border-accent/30 hover:border-accent transition">REST</span>
            <span class="px-3 py-1 rounded-lg bg-accent/15 border border-accent/30 hover:border-accent transition">SOAP</span>
          </div>
        </div>

        <!-- Architecture & Design -->
        <div class="glass rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent">Architecture &amp; Design</h3>
          <div class="flex flex-wrap gap-2">
            <span class="tag">Monolith → Microservices Transition</span>
            <span class="tag">Proxy Design Pattern</span>
            <span class="tag">Security Interceptors</span>
            <span class="tag">API Lifecycle</span>
          </div>
        </div>

        <!-- Fintech & Payments -->
        <div class="glass rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent">Fintech &amp; Payments</h3>
          <div class="flex flex-wrap gap-2">
            <span class="tag">Credit Card Lifecycle</span>
            <span class="tag">Wallet Services</span>
            <span class="tag">Loyalty Programs</span>
            <span class="tag">VAN Systems</span>
            <span class="tag">UPI</span>
            <span class="tag">Net Banking</span>
            <span class="tag">BNPL</span>
          </div>
        </div>

        <!-- Performance & Security -->
        <div class="glass rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent">Performance &amp; Security</h3>
          <div class="flex flex-wrap gap-2">
            <span class="tag">SQL Optimization</span>
            <span class="tag">Encryption/Decryption</span>
            <span class="tag">Checksum Validation</span>
            <span class="tag">API Fallback</span>
            <span class="tag">Scheduling Jobs</span>
          </div>
        </div>

        <!-- Databases & Testing -->
        <div class="glass rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent">Databases &amp; Testing</h3>
          <div class="flex flex-wrap gap-2">
            <span class="tag">MySQL</span>
            <span class="tag">Oracle DB</span>
            <span class="tag">JUnit</span>
            <span class="tag">JSON/XML Handling</span>
          </div>
        </div>

        <!-- DevOps & Tools -->
        <div class="glass rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent">DevOps &amp; Tools</h3>
          <div class="flex flex-wrap gap-2">
            <span class="tag">Maven</span>
            <span class="tag">Git</span>
            <span class="tag">CI/CD</span>
            <span class="tag">Docker</span>
            <span class="tag">Kubernetes</span>
            <span class="tag">Kafka</span>
            <span class="tag">Tomcat</span>
            <span class="tag">Oracle WebLogic</span>
            <span class="tag">Linux Scripting</span>
            <span class="tag">Postman</span>
            <span class="tag">GCloud VCS</span>
          </div>
        </div>

        <!-- Professional Skills -->
        <div class="glass rounded-xl p-5 reveal">
          <h3 class="font-semibold mb-3 text-accent">Professional Skills</h3>
          <div class="flex flex-wrap gap-2">
            <span class="tag">Agile (Scrum, Jira)</span>
            <span class="tag">Stakeholder Communication</span>
            <span class="tag">Mentorship</span>
            <span class="tag">Task Prioritization</span>
            <span class="tag">Problem-Solving</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Experience -->
  <section id="experience" class="py-16 border-t border-slate-800">
    <div class="mx-auto max-w-7xl px-4">
      <h2 class="text-3xl font-bold mb-8 reveal">Professional Experience</h2>

      <!-- Obopay -->
      <article class="glass rounded-2xl p-6 mb-6 reveal">
        <div class="flex flex-col lg:flex-row lg:items-start lg:justify-between gap-2">
          <div>
            <h3 class="text-xl font-semibold">Software Engineer — Obopay Mobile Technologies Pvt Ltd</h3>
            <p class="text-sm text-slate-400">Aug 2025 – Present</p>
          </div>
          <span class="px-3 py-1 text-xs rounded-lg border border-accent/40 text-accent self-start lg:self-auto">Wallets • Cards • Loyalty</span>
        </div>
        <ul class="mt-4 space-y-2 list-disc list-inside text-slate-300/90">
          <li>Developed Loyalty Program APIs to convert customer transactions into reward points, coupons, and redemption workflows.</li>
          <li>Gained deep domain expertise in credit card issuance, linking, transactions, and reversals within the wallet ecosystem.</li>
          <li>Enhanced monolithic SOAP systems using Proxy Design Pattern and Security Interceptors for modularity &amp; security.</li>
          <li>Improved performance &amp; reliability through SQL tuning, JUnit test coverage, exception handling, tokenization, and Linux scripting.</li>
          <li>Managed deployments on Tomcat (Dev) and Oracle WebLogic (Prod), with version control on GCloud VCS.</li>
          <li>Actively involved in monolith-to-microservices modernization initiatives, aligning with future career goals.</li>
        </ul>
      </article>

      <!-- SabPaisa Developer -->
      <article class="glass rounded-2xl p-6 mb-6 reveal">
        <div class="flex flex-col lg:flex-row lg:items-start lg:justify-between gap-2">
          <div>
            <h3 class="text-xl font-semibold">Software Developer — SabPaisa (SRS Live Technologies Pvt. Ltd.)</h3>
            <p class="text-sm text-slate-400">Feb 2022 – Jan 2025</p>
          </div>
          <span class="px-3 py-1 text-xs rounded-lg border border-accent/40 text-accent self-start lg:self-auto">UPI • VAN • Microservices</span>
        </div>
        <ul class="mt-4 space-y-2 list-disc list-inside text-slate-300/90">
          <li>Challan Project: Refactored a legacy monolith into two microservices, reducing coupling and improving maintainability.</li>
          <li>VAN Generate Service: Enhanced offline payment support (Cash, NEFT, RTGS, IMPS), improving efficiency &amp; maintainability.</li>
          <li>VAN Merchant Service: Designed APIs enabling clients to collect multiple payments against a single VAN, with payer-level permissions.</li>
          <li>VAN Bank Service: Built secure APIs for real-time VAN/challan verification &amp; status updates with multiple banks.</li>
          <li>UPI QR Application: Delivered dynamic QR &amp; Intent UPI integration with a single endpoint for instant payment string generation.</li>
          <li>Executed 10+ successful bank integrations (UPI, Net Banking, BNPL, Wallets), implementing checksum validation, encryption, webhook APIs, and fallback mechanisms.</li>
          <li>Impact: Increased system performance by 30%, reduced turnaround time by 20%, and maintained 95%+ client satisfaction.</li>
        </ul>
      </article>

      <!-- SabPaisa Intern -->
      <article class="glass rounded-2xl p-6 reveal">
        <div class="flex flex-col lg:flex-row lg:items-start lg:justify-between gap-2">
          <div>
            <h3 class="text-xl font-semibold">Java Intern — SabPaisa</h3>
            <p class="text-sm text-slate-400">Aug 2021 – Jan 2022</p>
          </div>
          <span class="px-3 py-1 text-xs rounded-lg border border-accent/40 text-accent self-start lg:self-auto">Payment Gateway</span>
        </div>
        <ul class="mt-4 space-y-2 list-disc list-inside text-slate-300/90">
          <li>Built and maintained REST APIs for the Payment Gateway, covering CRUD and transaction logging.</li>
          <li>Practiced Agile methodologies (Scrum, Daily Standups, Sprint Planning), contributing to rapid iteration cycles.</li>
        </ul>
      </article>

      <!-- Key Projects -->
      <div class="mt-10 reveal">
        <h3 class="text-lg font-semibold mb-4">Key Projects</h3>
        <div class="grid md:grid-cols-2 gap-4">
          <div class="glass rounded-xl p-5">
            <p class="font-medium">Loyalty Program API</p>
            <p class="text-sm text-slate-400">Rewarded customer spending with points, coupons, and redemption flows.</p>
          </div>
          <div class="glass rounded-xl p-5">
            <p class="font-medium">VAN Merchant Service</p>
            <p class="text-sm text-slate-400">Enabled multi-collection capability on a single Virtual Account Number.</p>
          </div>
          <div class="glass rounded-xl p-5">
            <p class="font-medium">UPI QR Application</p>
            <p class="text-sm text-slate-400">Unified integration for Intent UPI &amp; dynamic QR transactions.</p>
          </div>
          <div class="glass rounded-xl p-5">
            <p class="font-medium">Challan Project</p>
            <p class="text-sm text-slate-400">Transformed monolithic app → microservices for scalability and maintainability.</p>
          </div>
        </div>
      </div>

      <!-- Achievements & Certifications -->
      <div class="mt-10 reveal">
        <h3 class="text-lg font-semibold mb-4">Achievements &amp; Certifications</h3>
        <ul class="space-y-2 text-slate-300/90 list-disc list-inside">
          <li>Rising Star Award (2023–24) – SabPaisa</li>
          <li>Quick Resolver Award (2022–23) – SabPaisa</li>
          <li>Certifications: Java &amp; Problem-Solving (HackerRank), Advanced Java (Programming Hub), Oracle Java Explorer Badge, Time Management Mastery (Udemy)</li>
        </ul>
      </div>

      <!-- Education -->
      <div class="mt-10 reveal">
        <h3 class="text-lg font-semibold mb-4">Education</h3>
        <p>MCA (2020–2022) – Maharishi Dayanand University, Rohtak</p>
        <p>BCA (2016–2019) – Maharishi Dayanand University, Rohtak</p>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="py-16 border-t border-slate-800">
    <div class="mx-auto max-w-7xl px-4">
      <h2 class="text-3xl font-bold mb-6 reveal">Contact</h2>
      <div class="grid md:grid-cols-2 gap-6">
        <div class="glass rounded-xl p-6 reveal">
          <p class="text-slate-300/90">I’m currently focused on Java microservices, distributed systems, and scalable API design—open to collaborating on backend and fintech integrations.</p>
          <div class="mt-5 space-y-2">
            <p><span class="text-slate-400">Phone:</span> +91-9716052290</p>
            <p><span class="text-slate-400">Email:</span> <a class="underline hover:text-accent" href="mailto:bhuvan.parashar24@gmail.com">bhuvan.parashar24@gmail.com</a></p>
            <p><span class="text-slate-400">LinkedIn:</span> <a class="underline hover:text-accent" href="https://linkedin.com/in/bhuvan-parashar" target="_blank" rel="noreferrer">linkedin.com/in/bhuvan-parashar</a></p>
          </div>
        </div>
        <div class="glass rounded-xl p-6 reveal" id="video-instructions">
          <h3 class="font-semibold text-accent mb-2">Intro Video Notes</h3>
          <ol class="list-decimal list-inside text-slate-300/90 space-y-2">
            <li>Use the separate “AI Video Introduction Script” (below) with your favorite AI presenter/voice tool.</li>
            <li>Export an MP4 named <code>intro.mp4</code> and place it alongside this <code>index.html</code>.</li>
            <li>The “Play Intro” button will load and play your video.</li>
          </ol>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-10 border-t border-slate-800">
    <div class="mx-auto max-w-7xl px-4 text-sm text-slate-500 flex flex-col md:flex-row items-center justify-between gap-3">
      <p>&copy; <span id="year"></span> Bhuvan Parashar</p>
      <p>Short-term: Specialize in Java Microservices, distributed systems, observability, and scalable API design. Long-term: Integrate AI/ML in backend platforms to build intelligent, self-optimizing enterprise systems.</p>
    </div>
  </footer>

  <!-- Utilities / small components -->
  <template id="chip">
    <span class="tag px-3 py-1 rounded-lg bg-accent/10 border border-slate-700 hover:border-accent/60 hover:text-accent transition"></span>
  </template>

  <!-- Scripts -->
  <script>
    // Intersection Observer to reveal sections
    const io = new IntersectionObserver((entries) => {
      entries.forEach(e => {
        if (e.isIntersecting) e.target.classList.add('visible');
      });
    }, { threshold: 0.12 });

    document.querySelectorAll('.reveal').forEach(el => io.observe(el));

    // Play intro video
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

    // Year
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
# index.html
