<!DOCTYPE html>
<html lang="en" class="dark scroll-smooth">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ali Hassan Jamil — Principal Cyber Security Architect & GitHub README Studio</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="https://unpkg.com/lucide@0.460.0/dist/umd/lucide.min.js"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600;700&display=swap" rel="stylesheet">
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
            cyber: {
              bg: '#050811',
              card: '#0b1120',
              border: '#1e293b',
              cyan: '#00f2fe',
              emerald: '#10b981',
              rose: '#f43f5e',
              amber: '#f59e0b'
            }
          }
        }
      }
    };
  </script>
  <style>
    body {
      background-color: #050811;
      color: #e2e8f0;
      background-image: 
        radial-gradient(circle at 15% 15%, rgba(0, 242, 254, 0.07) 0%, transparent 35%),
        radial-gradient(circle at 85% 80%, rgba(16, 185, 129, 0.06) 0%, transparent 35%);
    }
    .cyber-grid {
      background-size: 32px 32px;
      background-image: 
        linear-gradient(to right, rgba(30, 41, 59, 0.25) 1px, transparent 1px),
        linear-gradient(to bottom, rgba(30, 41, 59, 0.25) 1px, transparent 1px);
    }
    .glow-cyan {
      box-shadow: 0 0 25px rgba(0, 242, 254, 0.18);
    }
    .glow-emerald {
      box-shadow: 0 0 25px rgba(16, 185, 129, 0.15);
    }
  </style>
</head>
<body class="min-h-screen font-sans antialiased selection:bg-cyan-500 selection:text-slate-950 cyber-grid">

  <!-- Toast Notification -->
  <div id="toastBanner" class="fixed bottom-5 right-5 z-50 hidden items-center gap-3 rounded-xl border border-cyan-500/40 bg-slate-900/95 px-5 py-3.5 text-sm font-medium text-cyan-300 shadow-2xl backdrop-blur-md">
    <i data-lucide="check-circle-2" class="h-5 w-5 text-emerald-400"></i>
    <span id="toastMessage">Copied to clipboard!</span>
  </div>

  <!-- Architecture / Code Modal -->
  <div id="projectModal" class="fixed inset-0 z-50 hidden items-center justify-center bg-slate-950/80 p-4 backdrop-blur-sm">
    <div class="relative w-full max-w-2xl rounded-2xl border border-cyan-500/30 bg-slate-900 p-6 shadow-2xl">
      <div class="flex items-start justify-between border-b border-slate-800 pb-4">
        <div>
          <span id="modalBadge" class="inline-block rounded-full bg-cyan-500/10 px-3 py-1 font-mono text-xs font-semibold text-cyan-400">MASTER DOMAIN</span>
          <h3 id="modalTitle" class="mt-2 text-xl font-bold text-white">Operation Blueprint</h3>
        </div>
        <button id="closeModalBtn" type="button" class="rounded-lg border border-slate-700 p-2 text-slate-400 hover:border-cyan-500 hover:text-white">
          <i data-lucide="x" class="h-5 w-5"></i>
        </button>
      </div>
      <p id="modalSummary" class="mt-4 text-sm leading-relaxed text-slate-300"></p>
      <div class="mt-4 rounded-xl border border-slate-800 bg-slate-950 p-4">
        <div class="mb-2 flex items-center justify-between">
          <span class="font-mono text-xs text-slate-400">Architecture & Execution Snippet</span>
          <button id="copyModalCodeBtn" type="button" class="flex items-center gap-1.5 rounded bg-slate-800 px-2.5 py-1 font-mono text-xs text-cyan-400 hover:bg-slate-700">
            <i data-lucide="copy" class="h-3.5 w-3.5"></i> Copy Snippet
          </button>
        </div>
        <pre id="modalCode" class="overflow-x-auto font-mono text-xs leading-relaxed text-emerald-400"></pre>
      </div>
    </div>
  </div>

  <!-- Top Sticky Navigation Bar -->
  <header class="sticky top-0 z-40 border-b border-slate-800/80 bg-slate-950/90 backdrop-blur-md">
    <div class="mx-auto flex max-w-7xl flex-wrap items-center justify-between gap-3 px-4 py-3 sm:px-6">
      <div class="flex items-center gap-3">
        <div class="flex h-10 w-10 items-center justify-center rounded-xl border border-cyan-500/40 bg-cyan-500/10 text-cyan-400">
          <i data-lucide="shield-check" class="h-5 w-5"></i>
        </div>
        <div>
          <div class="flex items-center gap-2">
            <span class="font-mono text-sm font-bold tracking-wider text-white">ALI HASSAN JAMIL</span>
            <span class="rounded bg-emerald-500/15 px-2 py-0.5 font-mono text-[10px] font-semibold text-emerald-400 border border-emerald-500/30">MASTER: CYBER SECURITY</span>
          </div>
          <p class="font-mono text-xs text-slate-400">Principal Cyber Security & DFIR Specialist | Python & MERN Engineer</p>
        </div>
      </div>

      <nav class="flex flex-wrap items-center gap-2">
        <a href="#github-readme" class="rounded-lg px-3 py-1.5 font-mono text-xs font-semibold text-cyan-300 hover:bg-slate-800">GitHub README</a>
        <a href="#arsenal" class="rounded-lg px-3 py-1.5 font-mono text-xs text-slate-300 hover:bg-slate-800 hover:text-cyan-400">Skill Options</a>
        <a href="#terminal" class="rounded-lg px-3 py-1.5 font-mono text-xs text-slate-300 hover:bg-slate-800 hover:text-cyan-400">Live Terminal</a>
        <a href="#operations" class="rounded-lg px-3 py-1.5 font-mono text-xs text-slate-300 hover:bg-slate-800 hover:text-cyan-400">Operations</a>
        <button id="topCopyReadmeBtn" type="button" class="flex items-center gap-1.5 rounded-lg bg-gradient-to-r from-cyan-400 to-emerald-400 px-4 py-2 font-mono text-xs font-extrabold text-slate-950 shadow-lg hover:opacity-95 transition">
          <i data-lucide="copy" class="h-4 w-4"></i> Copy GitHub README
        </button>
      </nav>
    </div>
  </header>

  <main class="mx-auto max-w-7xl space-y-10 px-4 py-6 sm:px-6">

    <!-- IMPORTANT FIX EXPLANATION + 1-CLICK COPY BOX RIGHT AT THE TOP -->
    <section id="github-readme" class="rounded-3xl border-2 border-cyan-400/60 bg-slate-900/95 p-6 sm:p-8 glow-cyan">
      <div class="flex flex-col justify-between gap-4 border-b border-slate-800 pb-5 lg:flex-row lg:items-center">
        <div class="space-y-1.5">
          <div class="inline-flex items-center gap-2 rounded-full bg-rose-500/15 border border-rose-500/40 px-3 py-1 font-mono text-xs font-bold text-rose-300">
            <i data-lucide="alert-triangle" class="h-3.5 w-3.5"></i>
            WHY COPY-PASTING FROM THE "CODE" TAB DIDN'T WORK ON GITHUB:
          </div>
          <h2 class="text-xl sm:text-2xl font-extrabold text-white">
            Don't copy the HTML file code — Click the Green Button below!
          </h2>
          <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">
            GitHub's <code class="text-cyan-300 font-mono">README.md</code> blocks HTML <code class="text-rose-300 font-mono">&lt;script&gt;</code> and <code class="text-rose-300 font-mono">&lt;style&gt;</code> tags. I built a **100% GitHub-Native Animated & Clickable Markdown Code** below (with animated SVG header, glowing badges, **clickable expandable skill menus**, and dark telemetry cards) that works inside GitHub <code class="text-cyan-300 font-mono">README.md</code>!
          </p>
        </div>

        <button id="bottomCopyReadmeBtn" type="button" class="shrink-0 inline-flex items-center justify-center gap-2.5 rounded-2xl bg-gradient-to-r from-emerald-400 to-cyan-400 px-6 py-4 font-mono text-sm font-extrabold text-slate-950 shadow-2xl hover:scale-[1.02] transition">
          <i data-lucide="copy" class="h-5 w-5"></i> Copy Raw Markdown for GitHub
        </button>
      </div>

      <!-- Exact Preview of What GitHub Renders (Animated SVG + Clickable <details> Menus) -->
      <div class="mt-6 grid gap-6 lg:grid-cols-12">
        <div class="lg:col-span-7 space-y-4">
          <span class="font-mono text-xs font-bold uppercase tracking-wider text-emerald-400">
            1. Live Preview of How Your GitHub README Will Look & Work on GitHub:
          </span>
          <div class="rounded-2xl border border-slate-800 bg-[#0d1117] p-4 space-y-4">
            <img src="https://capsule-render.vercel.app/api?type=waving&color=0:050811,50:0b1d2e,100:00f2fe&height=170&section=header&text=ALI%20HASSAN%20JAMIL&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=MASTER%20OF%20CYBER%20SECURITY%20%26%20DFIR%20%7C%20PYTHON%20%26%20MERN%20ENGINEER&descAlignY=58&descSize=14" class="w-full rounded-xl" alt="GitHub Banner Preview" />
            <div class="flex justify-center">
              <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=16&duration=2600&pause=700&color=00F2FE&center=true&vCenter=true&width=700&lines=%5BMASTER+PROFESSION%5D+%E2%86%92+Cyber+Security+%26+Digital+Forensics+Architect;%5BOFFENSIVE+%26+DEFENSIVE%5D+%E2%86%92+DFIR+%7C+Wireshark+DPI+%7C+Burp+Suite+PenTesting;%5BDEVELOPMENT+SKILLS%5D+%E2%86%92+Python+Cryptography+%7C+MERN+Stack+%7C+MS+SQL" alt="Typing Preview" class="max-w-full h-auto" />
            </div>

            <p class="font-mono text-xs text-slate-400">
              👇 On GitHub, visitors can click any of these 5 Skill Options right inside your README to expand/collapse them:
            </p>

            <!-- Real Native HTML <details> Accordions (Identical to GitHub README rendering) -->
            <div class="space-y-2 text-xs">
              <details open class="rounded-xl border border-cyan-500/30 bg-slate-900/90 p-3">
                <summary class="cursor-pointer font-mono font-bold text-cyan-300">
                  🕵️‍♂️ OPTION 1 — MASTER PROFESSION: Digital Forensics &amp; Incident Response (DFIR)
                </summary>
                <div class="mt-2 border-t border-slate-800 pt-2 text-slate-300 space-y-1">
                  <p>• <b>Autopsy &amp; Registry Forensics:</b> SAM, SYSTEM, NTUSER.DAT hive reconstruction &amp; user activity timelines.</p>
                  <p>• <b>Disk &amp; Memory Acquisition:</b> Bit-stream imaging (E01/dd) with FTK Imager, PALADIN OS, DumpIt &amp; Bulk Extractor.</p>
                </div>
              </details>

              <details class="rounded-xl border border-cyan-500/30 bg-slate-900/90 p-3">
                <summary class="cursor-pointer font-mono font-bold text-cyan-300">
                  🌐 OPTION 2 — MASTER PROFESSION: Network Security, SOC &amp; Deep Packet Inspection
                </summary>
                <div class="mt-2 border-t border-slate-800 pt-2 text-slate-300 space-y-1">
                  <p>• <b>Wireshark &amp; tcpdump DPI:</b> Live traffic dissection, SYN scan detection &amp; anomalous DNS/HTTP hunting.</p>
                  <p>• <b>Network Defense &amp; Auditing:</b> Nmap enumeration, Suricata IDS rules, Aircrack-ng &amp; VLAN segmentation.</p>
                </div>
              </details>

              <details class="rounded-xl border border-cyan-500/30 bg-slate-900/90 p-3">
                <summary class="cursor-pointer font-mono font-bold text-cyan-300">
                  🎯 OPTION 3 — MASTER PROFESSION: Offensive Penetration Testing &amp; Web Security
                </summary>
                <div class="mt-2 border-t border-slate-800 pt-2 text-slate-300 space-y-1">
                  <p>• <b>OWASP Top 10 Auditing:</b> Burp Suite request interception, IDOR / Broken Access Control &amp; SQL/NoSQL Injection testing.</p>
                  <p>• <b>Session &amp; Token Exploitation:</b> JWT signature auditing, HttpOnly/Secure cookie hardening &amp; Kali Linux OSINT.</p>
                </div>
              </details>

              <details class="rounded-xl border border-emerald-500/30 bg-slate-900/90 p-3">
                <summary class="cursor-pointer font-mono font-bold text-emerald-300">
                  🐍 OPTION 4 — CORE ENGINEERING SKILL: Python Cryptography &amp; Socket Servers
                </summary>
                <div class="mt-2 border-t border-slate-800 pt-2 text-slate-300 space-y-1">
                  <p>• <b>Cryptographic Protocols:</b> Python 3.11, ECDSA digital signatures (SECP256k1), SHA-256 hash chains &amp; custom ciphers.</p>
                  <p>• <b>Network Automation:</b> Multi-threaded TCP socket servers (GoofyCoin engine), security scanners &amp; OpenCV.</p>
                </div>
              </details>

              <details class="rounded-xl border border-amber-500/30 bg-slate-900/90 p-3">
                <summary class="cursor-pointer font-mono font-bold text-amber-300">
                  💻 OPTION 5 — SUPPORTING SKILL: Full-Stack MERN, Enterprise SQL &amp; x86 Assembly
                </summary>
                <div class="mt-2 border-t border-slate-800 pt-2 text-slate-300 space-y-1">
                  <p>• <b>Secure MERN Stack:</b> Node.js, Express.js, React.js &amp; MongoDB Atlas with JWT &amp; Role-Based Access Control (RBAC).</p>
                  <p>• <b>Enterprise SQL &amp; Systems:</b> 10-table normalized MS SQL Server (T-SQL) databases &amp; 16-bit 8086 Assembly (EMU8086).</p>
                </div>
              </details>
            </div>
          </div>
        </div>

        <!-- Right: Raw Markdown Box to Copy -->
        <div class="lg:col-span-5 flex flex-col justify-between space-y-3">
          <div class="flex items-center justify-between">
            <span class="font-mono text-xs font-bold uppercase tracking-wider text-cyan-400">
              2. Raw GitHub Markdown Code (Paste into README.md):
            </span>
          </div>
          <pre id="readmeCodeBlock" class="h-[420px] overflow-y-auto rounded-2xl border border-slate-800 bg-slate-950 p-4 font-mono text-[11px] leading-relaxed text-emerald-300 select-all"></pre>
        </div>
      </div>
    </section>

    <!-- HERO EXECUTIVE COMMAND SECTION -->
    <section class="relative overflow-hidden rounded-3xl border border-slate-800 bg-slate-900/75 p-6 sm:p-10">
      <div class="grid gap-8 lg:grid-cols-12 lg:items-center">
        <div class="lg:col-span-7 space-y-5">
          <div class="inline-flex items-center gap-2 rounded-full border border-cyan-500/30 bg-cyan-500/10 px-3.5 py-1 font-mono text-xs text-cyan-300">
            <span class="h-2 w-2 rounded-full bg-cyan-400 animate-pulse"></span>
            EXECUTIVE CYBER DEFENSE &amp; DIGITAL FORENSICS COMMAND
          </div>

          <h1 class="text-3xl font-extrabold tracking-tight text-white sm:text-5xl leading-tight">
            Master of <span class="bg-gradient-to-r from-cyan-400 to-emerald-400 bg-clip-text text-transparent">Cyber Security &amp; DFIR</span>. Engineered with Python &amp; MERN.
          </h1>

          <p class="text-sm sm:text-base leading-relaxed text-slate-300">
            My master profession is **Offensive/Defensive Cyber Security, Deep Packet Inspection, and Digital Forensics Incident Response (DFIR)**—backed by supporting engineering mastery in **Python Cryptography, Enterprise SQL Databases, and Secure Full-Stack MERN Development**.
          </p>

          <div class="flex flex-wrap items-center gap-3 pt-2">
            <a href="https://www.linkedin.com/in/alihassanjamil-cyber" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-2 rounded-xl bg-blue-600 px-4 py-2.5 text-xs font-semibold text-white hover:bg-blue-500 transition">
              <i data-lucide="linkedin" class="h-4 w-4"></i> LinkedIn Profile
            </a>
            <a href="https://github.com/alihassanjamil" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-2 rounded-xl border border-slate-700 bg-slate-800 px-4 py-2.5 text-xs font-semibold text-white hover:border-cyan-400 transition">
              <i data-lucide="github" class="h-4 w-4"></i> github.com/alihassanjamil
            </a>
          </div>
        </div>

        <div class="lg:col-span-5">
          <div class="rounded-2xl border border-slate-800 bg-slate-950 p-4 shadow-2xl">
            <div class="flex items-center justify-between border-b border-slate-800 pb-3">
              <span class="font-mono text-xs text-slate-400">root@alihassanjamil:~# python3 master_profile.py</span>
              <span class="rounded bg-cyan-500/10 px-2 py-0.5 font-mono text-[10px] text-cyan-400">PYTHON 3.11</span>
            </div>
            <pre class="mt-3 overflow-x-auto font-mono text-xs leading-relaxed text-slate-200"><span class="text-rose-400">class</span> <span class="text-cyan-400 font-bold">CyberSecurityMaster</span>:
    <span class="text-rose-400">def</span> <span class="text-emerald-400">__init__</span>(self):
        self.operator = <span class="text-amber-300">"Ali Hassan Jamil"</span>
        self.master_profession = <span class="text-amber-300">"Cyber Security &amp; Digital Forensics"</span>
        self.supporting_skills = [<span class="text-amber-300">"Python Crypto"</span>, <span class="text-amber-300">"MERN Stack"</span>, <span class="text-amber-300">"MS SQL"</span>]</pre>
          </div>
        </div>
      </div>
    </section>

    <!-- INTERACTIVE MULTI-OPTION SKILL MATRIX -->
    <section id="arsenal" class="space-y-6">
      <div class="flex flex-col justify-between gap-4 border-b border-slate-800 pb-4 md:flex-row md:items-end">
        <div>
          <span class="font-mono text-xs font-semibold uppercase tracking-widest text-cyan-400">Interactive Skill Selector</span>
          <h2 class="mt-1 text-2xl font-bold text-white sm:text-3xl">Master Profession vs. Supporting Technical Skills</h2>
        </div>
        <div class="flex items-center gap-2">
          <div class="relative">
            <i data-lucide="search" class="absolute left-3 top-2.5 h-4 w-4 text-slate-500"></i>
            <input id="skillSearchInput" type="text" placeholder="Filter tool (e.g. Wireshark, Python, MERN)..." class="w-64 rounded-xl border border-slate-800 bg-slate-900 pl-9 pr-3 py-2 text-xs text-white placeholder-slate-500 focus:border-cyan-400 focus:outline-none" />
          </div>
        </div>
      </div>

      <div id="skillCategoryTabs" class="flex flex-wrap gap-2">
        <button type="button" data-cat="all" class="skill-tab rounded-xl border border-cyan-400 bg-cyan-500/20 px-4 py-2 font-mono text-xs font-bold text-cyan-300 transition">
          All Arsenal (18)
        </button>
        <button type="button" data-cat="dfir" class="skill-tab rounded-xl border border-slate-800 bg-slate-900 px-4 py-2 font-mono text-xs font-semibold text-slate-300 hover:border-cyan-500/50 transition">
          🕵️‍♂️ Master: Digital Forensics (DFIR)
        </button>
        <button type="button" data-cat="netsec" class="skill-tab rounded-xl border border-slate-800 bg-slate-900 px-4 py-2 font-mono text-xs font-semibold text-slate-300 hover:border-cyan-500/50 transition">
          🌐 Master: Network &amp; Packet Defense
        </button>
        <button type="button" data-cat="pentest" class="skill-tab rounded-xl border border-slate-800 bg-slate-900 px-4 py-2 font-mono text-xs font-semibold text-slate-300 hover:border-cyan-500/50 transition">
          🎯 Master: Web &amp; API PenTesting
        </button>
        <button type="button" data-cat="python" class="skill-tab rounded-xl border border-slate-800 bg-slate-900 px-4 py-2 font-mono text-xs font-semibold text-emerald-300 hover:border-emerald-500/50 transition">
          🐍 Skill: Python &amp; Cryptography
        </button>
        <button type="button" data-cat="mern" class="skill-tab rounded-xl border border-slate-800 bg-slate-900 px-4 py-2 font-mono text-xs font-semibold text-amber-300 hover:border-amber-500/50 transition">
          💻 Skill: MERN Stack &amp; Enterprise SQL
        </button>
      </div>

      <div id="skillsGrid" class="grid gap-4 sm:grid-cols-2 lg:grid-cols-3"></div>
    </section>

    <!-- INTERACTIVE CYBER COMMAND TERMINAL -->
    <section id="terminal" class="space-y-4">
      <div>
        <span class="font-mono text-xs font-semibold uppercase tracking-widest text-emerald-400">Live Command Simulator</span>
        <h2 class="mt-1 text-2xl font-bold text-white">Interactive Cyber Operations Console</h2>
      </div>

      <div class="rounded-2xl border border-slate-800 bg-slate-950 p-4 sm:p-6 shadow-2xl glow-emerald">
        <div class="mb-4 flex flex-wrap gap-2 border-b border-slate-800 pb-4">
          <button type="button" data-cmd="clearance" class="term-btn rounded-lg border border-cyan-500/40 bg-cyan-500/10 px-3 py-1.5 font-mono text-xs text-cyan-300 hover:bg-cyan-500/20">
            $ ./verify_master_profession.sh
          </button>
          <button type="button" data-cmd="dfir" class="term-btn rounded-lg border border-slate-700 bg-slate-900 px-3 py-1.5 font-mono text-xs text-slate-300 hover:border-cyan-400">
            $ autopsy --investigate Mantooth.E01
          </button>
          <button type="button" data-cmd="wireshark" class="term-btn rounded-lg border border-slate-700 bg-slate-900 px-3 py-1.5 font-mono text-xs text-slate-300 hover:border-cyan-400">
            $ tshark -i eth0 --detect-threat
          </button>
          <button type="button" data-cmd="python" class="term-btn rounded-lg border border-slate-700 bg-slate-900 px-3 py-1.5 font-mono text-xs text-emerald-300 hover:border-emerald-400">
            $ python3 goofycoin_ecdsa_server.py
          </button>
          <button type="button" data-cmd="mern" class="term-btn rounded-lg border border-slate-700 bg-slate-900 px-3 py-1.5 font-mono text-xs text-amber-300 hover:border-amber-400">
            $ node audit_mern_rbac_security.js
          </button>
        </div>

        <div id="terminalOutput" class="min-h-[170px] font-mono text-xs leading-relaxed text-emerald-400 whitespace-pre-wrap"></div>
      </div>
    </section>

    <!-- FLAGSHIP CYBER OPERATIONS & ENGINEERING REPOSITORIES -->
    <section id="operations" class="space-y-6">
      <div>
        <span class="font-mono text-xs font-semibold uppercase tracking-widest text-cyan-400">Verified Portfolio</span>
        <h2 class="mt-1 text-2xl font-bold text-white sm:text-3xl">Flagship Security Operations &amp; Engineering Systems</h2>
      </div>

      <div id="projectsGrid" class="grid gap-5 md:grid-cols-2 lg:grid-cols-3"></div>
    </section>

  </main>

  <footer class="mt-12 border-t border-slate-800/80 bg-slate-950 py-6 text-center font-mono text-xs text-slate-500">
    ALI HASSAN JAMIL • MASTER OF CYBER SECURITY &amp; DIGITAL FORENSICS • PYTHON &amp; MERN STACK ENGINEER • LAHORE, PAKISTAN
  </footer>

  <script>
    const SKILLS_DATA = [
      {
        id: 's1',
        name: 'Autopsy & Windows Registry Forensics',
        category: 'dfir',
        tier: 'MASTER PROFESSION',
        level: 100,
        badgeColor: 'cyan',
        tools: 'Autopsy • SAM / SYSTEM / NTUSER.DAT • MRU Lists',
        desc: 'Deep forensic reconstruction of user profiles, SAM password hives, network interfaces, USB mount histories, and timeline artifacts from compromised disk images.'
      },
      {
        id: 's2',
        name: 'Bit-Stream Disk Imaging & Evidence Carving',
        category: 'dfir',
        tier: 'MASTER PROFESSION',
        level: 100,
        badgeColor: 'cyan',
        tools: 'FTK Imager • PALADIN OS • E01 / dd / AFF Formats',
        desc: 'Write-blocked physical disk acquisition, cryptographic hash verification (MD5/SHA-256), unallocated slack-space inspection, and deleted file recovery.'
      },
      {
        id: 's3',
        name: 'Volatile RAM & Process Memory Forensics',
        category: 'dfir',
        tier: 'MASTER PROFESSION',
        level: 98,
        badgeColor: 'cyan',
        tools: 'DumpIt • Bulk Extractor • ListDLLs',
        desc: 'Live memory capture and string/artifact extraction to uncover injected DLLs, hidden processes, cleartext credentials, and active command-and-control sockets.'
      },
      {
        id: 's4',
        name: 'Wireshark Deep Packet Inspection (DPI)',
        category: 'netsec',
        tier: 'MASTER PROFESSION',
        level: 100,
        badgeColor: 'cyan',
        tools: 'Wireshark • tcpdump • TCP/IP • DNS / HTTP Streams',
        desc: 'Packet-level traffic dissection across Linux and Windows networks—isolating SYN floods, rogue port scans, ARP spoofing, and unauthorized data exfiltration.'
      },
      {
        id: 's5',
        name: 'Network Reconnaissance & Wireless Auditing',
        category: 'netsec',
        tier: 'MASTER PROFESSION',
        level: 96,
        badgeColor: 'cyan',
        tools: 'Nmap • Aircrack-ng • Kali Linux',
        desc: 'Active/passive network enumeration, OS/service fingerprinting, firewall evasion analysis, and wireless handshake auditing.'
      },
      {
        id: 's6',
        name: 'Intrusion Detection & Campus LAN/WAN Security',
        category: 'netsec',
        tier: 'MASTER PROFESSION',
        level: 95,
        badgeColor: 'cyan',
        tools: 'Suricata IDS • Cisco Packet Tracer • VLANs / DHCP / DNS',
        desc: 'Designing segmented enterprise network topologies with security redundancy, VLAN isolation, router/switch hardening, and real-time IDS alerting.'
      },
      {
        id: 's7',
        name: 'OWASP Top 10 & Web Vulnerability Auditing',
        category: 'pentest',
        tier: 'MASTER PROFESSION',
        level: 96,
        badgeColor: 'cyan',
        tools: 'Burp Suite • IDOR • SQL/NoSQL Injection • XSS',
        desc: 'Intercepting and mutating HTTP/HTTPS requests to expose Broken Access Control (IDOR), authentication bypasses, and injection flaws in modern web apps.'
      },
      {
        id: 's8',
        name: 'Session, Cookie & JWT Security Exploitation',
        category: 'pentest',
        tier: 'MASTER PROFESSION',
        level: 95,
        badgeColor: 'cyan',
        tools: 'JWT Auditing • HttpOnly / Secure Flags • Base64 / Hashes',
        desc: 'Auditing token expiration, signature verification flaws, insecure session storage, and privilege escalation vectors across REST APIs.'
      },
      {
        id: 's9',
        name: 'OSINT & Attack Surface Reconnaissance',
        category: 'pentest',
        tier: 'MASTER PROFESSION',
        level: 95,
        badgeColor: 'cyan',
        tools: 'Google Dorking • Metadata Analysis • Kali Toolchain',
        desc: 'Advanced search operator reconnaissance to locate exposed directories, leaked configuration files, and vulnerable subdomains before adversaries do.'
      },
      {
        id: 's10',
        name: 'Python Cryptographic & Blockchain Engines',
        category: 'python',
        tier: 'CORE DEV SKILL',
        level: 96,
        badgeColor: 'emerald',
        tools: 'Python 3.11 • ecdsa • hashlib • SHA-256',
        desc: 'Engineering elliptic-curve digital signature (ECDSA) validators, custom Unicode cipher suites, immutable transaction chains, and double-spend detection.'
      },
      {
        id: 's11',
        name: 'Python Multi-Threaded TCP Socket Servers',
        category: 'python',
        tier: 'CORE DEV SKILL',
        level: 94,
        badgeColor: 'emerald',
        tools: 'Python socket • Client/Server Protocol • OpenCV',
        desc: 'Building custom networked socket servers for secure real-time message verification, automated security scripts, and computer vision pipelines.'
      },
      {
        id: 's12',
        name: 'Secure Full-Stack MERN Architecture',
        category: 'mern',
        tier: 'SUPPORTING SKILL',
        level: 92,
        badgeColor: 'amber',
        tools: 'Node.js • Express.js • React.js • MongoDB Atlas',
        desc: 'Developing production full-stack web platforms fortified with Role-Based Access Control (RBAC), JWT middleware, rate limiting, and sanitized schemas.'
      },
      {
        id: 's13',
        name: 'Enterprise SQL Server & Database Security',
        category: 'mern',
        tier: 'SUPPORTING SKILL',
        level: 92,
        badgeColor: 'amber',
        tools: 'MS SQL Server (SSMS) • T-SQL • Stored Procedures • Triggers',
        desc: 'Architecting 10-table normalized relational databases with strict foreign-key constraints, automated audit triggers, and parameterized queries.'
      },
      {
        id: 's14',
        name: 'x86 16-Bit Real-Mode Microprocessor Assembly',
        category: 'mern',
        tier: 'SYSTEMS SKILL',
        level: 88,
        badgeColor: 'amber',
        tools: 'Intel 8086 • EMU8086 • 0B800h Video Memory • BIOS Interrupts',
        desc: 'Writing hardware-level assembly programs utilizing direct video RAM rendering, custom timer interrupt loops (INT 10h / INT 16h), and memory registers.'
      }
    ];

    const PROJECTS_DATA = [
      {
        id: 'p1',
        title: 'Mantooth Memory & Registry Forensics (DFIR)',
        domain: 'MASTER: DIGITAL FORENSICS',
        stack: 'Autopsy • FTK Imager • PALADIN OS • Windows Registry',
        summary: 'Comprehensive digital forensics investigation tracing Windows Registry artifacts across SAM hives, user profiles, network interfaces, and MRU lists to reconstruct incident timelines.',
        code: `# Forensic Verification Workflow (DFIR Lab)
[1] Acquire bit-stream image -> Mantooth.E01 (Write-Blocked via PALADIN)
[2] Verify integrity         -> SHA256: 9f86d081884c7d659a2feaa0c55ad015...
[3] Parse Registry Hives     -> C:\\Windows\\System32\\config\\SAM & SYSTEM
[4] Extract Volatile Strings -> bulk_extractor -o output_dir memory_dump.raw
[STATUS] 100% Artifact Chain Preserved for Court-Admissible Report`
      },
      {
        id: 'p2',
        title: 'GoofyCoin Cryptographic Socket Server',
        domain: 'PYTHON CRYPTOGRAPHY',
        stack: 'Python 3.11 • ECDSA • hashlib • TCP Sockets',
        summary: 'Custom cryptocurrency socket server implementing ECDSA key generation, digital signature validation, transaction chain verification, and automated double-spend catching.',
        code: `import ecdsa, hashlib, socket

def verify_transaction_signature(public_key_hex: str, payload: bytes, sig_hex: str) -> bool:
    vk = ecdsa.VerifyingKey.from_string(bytes.fromhex(public_key_hex), curve=ecdsa.SECP256k1)
    digest = hashlib.sha256(payload).digest()
    return vk.verify_digest(bytes.fromhex(sig_hex), digest)
# Rejects unauthorized coin transfers & logs tamper attempt`
      },
      {
        id: 'p3',
        title: 'Wireshark Network Packet & IDS Playbooks',
        domain: 'MASTER: NETWORK SECURITY',
        stack: 'Wireshark • Nmap • Suricata • Kali Linux',
        summary: '30-day enterprise packet analysis and network troubleshooting suite isolating rogue SYN scans, DNS anomalies, cleartext credential leaks, and LAN/WAN bottlenecks.',
        code: `# Wireshark & Nmap Defensive Filter Rules
# 1. Detect SYN Port Sweep without completed handshake:
tcp.flags.syn == 1 and tcp.flags.ack == 0

# 2. Isolate suspicious HTTP POST credential submissions:
http.request.method == "POST" && frame contains "password"

# 3. Verify open service attack surface:
nmap -sV -sC -O --script vuln 192.168.1.0/24`
      },
      {
        id: 'p4',
        title: 'LGU ONE — Zero-Trust Campus LMS Blueprint',
        domain: 'SECURITY ARCHITECTURE',
        stack: 'System Design • RBAC • REST API Security • MERN',
        summary: 'Master architectural blueprint for a next-generation connected university ecosystem engineered with strict Role-Based Access Control (RBAC) and segmented privilege tiers.',
        code: `// Zero-Trust Role-Based Access Control (RBAC) Guard
const authorizeRole = (...allowedRoles) => (req, res, next) => {
  if (!req.user || !allowedRoles.includes(req.user.securityRole)) {
    return res.status(403).json({
      alert: "SECURITY_VIOLATION: Unauthorized privilege escalation blocked."
    });
  }
  next();
};`
      },
      {
        id: 'p5',
        title: 'Hardened Multi-Vendor MERN Delivery Platform',
        domain: 'SUPPORTING SKILL: MERN STACK',
        stack: 'Node.js • Express • React • MongoDB Atlas • JWT',
        summary: 'Full-stack multi-vendor restaurant and food delivery platform featuring JWT authentication, isolated vendor cart state, input sanitization, and MongoDB analytics pipelines.',
        code: `// Hardened JWT Authentication & MongoDB Aggregation Pipeline
const token = jwt.sign(
  { userId: user._id, role: user.role },
  process.env.JWT_SECRET_KEY,
  { expiresIn: '2h', algorithm: 'HS256' }
);
res.cookie('session_token', token, { httpOnly: true, secure: true, sameSite: 'Strict' });`
      },
      {
        id: 'p6',
        title: 'DHA Enterprise Real Estate DBMS (v2.0)',
        domain: 'DATABASE SECURITY (T-SQL)',
        stack: 'MS SQL Server • T-SQL • Stored Procedures • Triggers',
        summary: '10-table normalized relational database architecture modeling DHA property phases, client transfers, automated tax calculations, and unpaid installment tracking.',
        code: `-- Parameterized T-SQL Audit Query (SQL-Injection Resistant)
CREATE PROCEDURE sp_VerifyUnpaidInstallments
    @PhaseNumber INT
AS
BEGIN
    SET NOCOUNT ON;
    SELECT c.ClientName, p.PlotNumber, i.DueDate, i.AmountDue
    FROM Installments i
    INNER JOIN Properties p ON i.PropertyID = p.PropertyID
    INNER JOIN Clients c ON i.ClientID = c.ClientID
    WHERE i.PaymentStatus = 'Unpaid' AND p.PhaseNo = @PhaseNumber;
END;`
      }
    ];

    const TERMINAL_LOGS = {
      clearance: `[root@cyber-command]# ./verify_master_profession.sh --operator "Ali Hassan Jamil"
--------------------------------------------------------------------------------
[+] OPERATOR IDENTIFIED : Ali Hassan Jamil
[+] MASTER PROFESSION   : Cyber Security & Digital Forensics (DFIR) Specialist
[+] CORE DOMAINS        : Disk/Memory Forensics | Deep Packet Inspection | PenTesting
[+] SUPPORTING SKILLS   : Python Cryptography | Full-Stack MERN | MS SQL | x86 ASM
[+] CERTIFICATIONS      : Google Cybersecurity (Foundations, Network Security, Linux & SQL, Risk Mgmt)
[STATUS] CLEARANCE VERIFIED — READY FOR ENTERPRISE SECURITY OPERATIONS.`,
      dfir: `[root@cyber-command]# autopsy --investigate Mantooth.E01 --verify-hash
--------------------------------------------------------------------------------
[*] Mounting Forensic Image : Mantooth.E01 (Read-Only Write-Blocked Mode)
[*] Extracting Registry     : SAM, SYSTEM, SECURITY, NTUSER.DAT
[+] Recovered Deleted Files : 42 carved artifacts via FTK Imager & Bulk Extractor
[+] Memory Dump Analysis    : Inspected active processes & DLLs via DumpIt / ListDLLs
[STATUS] Forensic Chain of Custody Intact — Zero Tampering Detected.`,
      wireshark: `[root@cyber-command]# tshark -i eth0 -Y "tcp.flags.syn==1 && tcp.flags.ack==0"
--------------------------------------------------------------------------------
[*] Capturing Live Traffic on Interface eth0 (Kali Linux Security Node)...
[!] ALERT: Anomalous SYN Burst detected from 192.168.10.45 -> Ports 22, 80, 443, 3306
[+] Correlating with Suricata IDS Signature #2010935 (Reconnaissance Nmap Scan)
[+] Action Taken: Isolated rogue host at VLAN switch port & logged PCAP evidence.`,
      python: `[root@cyber-command]# python3 goofycoin_ecdsa_server.py --port 5050
--------------------------------------------------------------------------------
[*] Initializing GoofyCoin Cryptographic Socket Server on TCP Port 5050...
[+] Curve Loaded        : SECP256k1 (Elliptic Curve Digital Signature Algorithm)
[+] Block #01 Verified  : SHA-256 Hash 0000a8f49c1e... (Valid Signature)
[!] Attack Blocked      : Caught unauthorized double-spend attempt from client socket!`,
      mern: `[root@cyber-command]# node audit_mern_rbac_security.js --env production
--------------------------------------------------------------------------------
[*] Auditing Express.js & MongoDB Atlas API Endpoints...
[✓] JWT Auth Guard      : HttpOnly + SameSite=Strict cookies enforced
[✓] Access Control      : RBAC verified across Admin, Vendor, and Customer routes
[✓] Injection Defense   : Mongoose schema sanitization & parameterized queries active.`
    };

    const CLEAN_GITHUB_README = `<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:050811,50:0b1d2e,100:00f2fe&height=210&section=header&text=ALI%20HASSAN%20JAMIL&fontSize=46&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=MASTER%20OF%20CYBER%20SECURITY%20%26%20DFIR%20%7C%20PYTHON%20%26%20MERN%20ENGINEER&descAlignY=58&descSize=15" width="100%" />

  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=19&duration=2600&pause=700&color=00F2FE&center=true&vCenter=true&width=880&lines=%5BMASTER+PROFESSION%5D+%E2%86%92+Cyber+Security+%26+Digital+Forensics+Architect;%5BOFFENSIVE+%26+DEFENSIVE%5D+%E2%86%92+DFIR+%7C+Wireshark+DPI+%7C+Burp+Suite+PenTesting;%5BDEVELOPMENT+SKILLS%5D+%E2%86%92+Python+Cryptography+%7C+MERN+Stack+%7C+Enterprise+SQL" alt="Typing SVG" />
  </a>

  <p align="center">
    <a href="https://www.linkedin.com/in/alihassanjamil-cyber"><img src="https://img.shields.io/badge/LINKEDIN-ALI_HASSAN_JAMIL-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
    <a href="mailto:alipowerhassan@gmail.com"><img src="https://img.shields.io/badge/EMAIL-ALIPOWERHASSAN%40GMAIL.COM-EA4335?style=for-the-badge&logo=gmail&logoColor=white" /></a>
    <a href="https://github.com/alihassanjamil"><img src="https://img.shields.io/badge/MASTER_DOMAIN-CYBER_SECURITY_%26_DFIR-00F2FE?style=for-the-badge&logo=kalilinux&logoColor=black" /></a>
  </p>
</div>

---

## 🛡️ Executive Security Profile

I am a **Cyber Security & Digital Forensics (DFIR) Specialist** focused on enterprise network defense, deep packet inspection, memory/disk incident forensics, and offensive web vulnerability auditing.

My **Master Profession is Cyber Security & Digital Forensics**, reinforced by advanced software engineering skills in **Python Cryptographic Socket Servers, Enterprise Microsoft SQL Server (T-SQL), Full-Stack MERN Architecture, and x86 Assembly**.

\`\`\`text
MASTER PROFESSION — CYBER SECURITY & DIGITAL FORENSICS
├── Digital Forensics & Incident Response (DFIR)  ████████████████████  100%  [Master Domain]
├── Network Security & Deep Packet Inspection     ████████████████████  100%  [Master Domain]
├── Web & API Penetration Testing (OWASP Top 10)  ███████████████████░   96%  [Master Domain]
└── Threat Intelligence & Cryptographic Defense   ███████████████████░   95%  [Master Domain]

SUPPORTING ENGINEERING SKILLS — CODE, AUTOMATION & DATABASES
├── Python Security Scripting & ECDSA Sockets     ███████████████████░   96%  [Core Dev Skill]
├── Enterprise Database Security (MS SQL / T-SQL) ██████████████████░░   92%  [Database Skill]
├── Secure Full-Stack Web Dev (MERN Stack)        ██████████████████░░   92%  [Supporting Skill]
└── x86 16-Bit Real-Mode Assembly (EMU8086)       █████████████████░░░   88%  [Systems Skill]
\`\`\`

---

## 🎛️ Interactive Skill Options (Click Any Domain Below to Expand)

<details open>
<summary><b>🕵️‍♂️ OPTION 1 — MASTER PROFESSION: Digital Forensics & Incident Response (DFIR)</b></summary>
<br/>

- **Bit-Stream Disk Imaging & Carving:** Write-blocked physical disk acquisition (\`E01\`, \`AFF\`, \`dd\`), hash verification, and deleted artifact recovery using **FTK Imager** and **PALADIN OS**.
- **Volatile Memory Forensics:** Live RAM acquisition and process/DLL analysis via **DumpIt**, **Bulk Extractor**, and **ListDLLs** to expose injected code and active C2 connections.
- **Registry & OS Reconstruction:** Deep forensic investigation in **Autopsy** across Windows Registry hives (\`SAM\`, \`SYSTEM\`, \`NTUSER.DAT\`), MRU lists, and user timelines.
</details>

<details>
<summary><b>🌐 OPTION 2 — MASTER PROFESSION: Network Security, SOC & Deep Packet Inspection</b></summary>
<br/>

- **Deep Packet Inspection (DPI):** Live traffic capture, TCP handshake analysis, and protocol anomaly hunting via **Wireshark** and **tcpdump**.
- **Network Reconnaissance & Wireless Auditing:** Host discovery, port/service enumeration, OS fingerprinting, and wireless auditing with **Nmap** and **Aircrack-ng**.
- **Intrusion Detection & Perimeter Defense:** **Suricata IDS** rule monitoring, enterprise LAN/WAN segmentation, VLAN hardening, and **Cisco Packet Tracer** architectures.
</details>

<details>
<summary><b>🎯 OPTION 3 — MASTER PROFESSION: Offensive Web Penetration Testing (OWASP)</b></summary>
<br/>

- **Web & API Vulnerability Auditing:** Intercepting and mutating HTTP/HTTPS traffic in **Burp Suite** to uncover **Broken Access Control (IDOR)**, **SQL/NoSQL Injection**, and **XSS**.
- **Session & Token Exploitation:** Auditing **JWT** implementations, cookie flags (\`HttpOnly\`, \`Secure\`, \`SameSite\`), and authentication bypasses in **Kali Linux**.
</details>

<details>
<summary><b>🐍 OPTION 4 — CORE DEV SKILL: Python Cryptographic & Socket Engineering</b></summary>
<br/>

- **Cryptographic Protocols:** Engineering **ECDSA** digital signature validators (\`ecdsa\`), **SHA-256** hash chains (\`hashlib\`), custom cipher algorithms, and double-spend detection.
- **Network Socket Servers:** Multi-threaded TCP/UDP client-server engines (\`socket\`), automated security scanners, and **OpenCV** vision pipelines.
</details>

<details>
<summary><b>💻 OPTION 5 — SUPPORTING SKILL: Secure MERN Stack, Enterprise SQL & x86 Assembly</b></summary>
<br/>

- **Full-Stack MERN (Supporting Skill):** Building hardened **Node.js, Express.js, React.js & MongoDB Atlas** platforms with strict **RBAC** middleware, JWT guards, and input sanitization.
- **Enterprise Relational Databases:** 10-table normalized **MS SQL Server (T-SQL)** databases with stored procedures, triggers, and foreign-key constraints.
- **Low-Level Microprocessor Systems:** 16-bit real-mode **Intel 8086 Assembly (\`EMU8086\`)** utilizing direct \`0B800h\` video memory and BIOS interrupts.
</details>

<br/>

<div align="center">
  <img src="https://skillicons.dev/icons?i=kali,linux,bash,py,mysql,nodejs,express,react,mongodb,js,git,github,vscode,postman&perline=7" />
</div>

---

## 🔬 Command-Line Security Blueprint (\`cyber_architect.py\`)

\`\`\`python
#!/usr/bin/env python3
class PrincipalCyberSecurityArchitect:
    def __init__(self):
        self.operator = "Ali Hassan Jamil"
        self.master_profession = "Cyber Security & Digital Forensics (DFIR)"
        self.supporting_skills = ["Python Cryptography", "MERN Stack", "MS SQL Server", "x86 Assembly"]

    def execute_defense_matrix(self) -> dict:
        return {
            "DFIR_Forensics" : ["Autopsy", "FTK Imager", "PALADIN OS", "DumpIt", "Bulk Extractor"],
            "Network_Defense": ["Wireshark DPI", "Nmap", "Suricata IDS", "tcpdump", "Kali Linux"],
            "Web_PenTesting" : ["Burp Suite", "OWASP Top 10", "IDOR/SQLi", "JWT Security"],
            "Python_And_Dev" : ["ECDSA Socket Servers", "Node/Express/React/MongoDB", "T-SQL"]
        }
\`\`\`

---

## 📂 Flagship Security Operations & Engineering Repositories

| Operation / Repository | Classification | Technical Architecture & Security Impact |
| :--- | :--- | :--- |
| 🕵️‍♂️ **\`DFIR-Memory-And-Registry-Forensics\`** | **Master: Digital Forensics** | Bit-stream disk imaging (\`E01\`), volatile RAM string carving, and Windows Registry/SAM reconstruction in **Autopsy & FTK Imager**. |
| 🌐 **\`Wireshark-Enterprise-Packet-Forensics\`** | **Master: Network Security** | Deep packet inspection playbooks isolating SYN port sweeps, DNS anomalies, and unauthorized exfiltration across Linux & Windows. |
| 🔐 **\`GoofyCoin-ECDSA-Crypto-Server\`** | **Skill: Python Cryptography** | Custom Python TCP socket server enforcing **ECDSA** digital signatures, SHA-256 transaction chains, and double-spend detection. |
| 🛡️ **\`LGU-ONE-ZeroTrust-Campus-LMS\`** | **Master: Security Architecture** | Connected campus ecosystem blueprint engineered with strict Role-Based Access Control (RBAC) and segmented API gateways. |
| 🏢 **\`DHA-Enterprise-SQL-Database-System\`** | **Skill: Database Security** | 10-table normalized **MS SQL Server (T-SQL)** database featuring stored procedures, triggers, and financial audit queries. |
| 💻 **\`Hardened-MultiVendor-MERN-Platform\`** | **Skill: Full-Stack MERN** | **Node.js, Express, React & MongoDB** platform built with strict JWT session validation, RBAC route guards, and sanitized schemas. |
| ⚙️ **\`x86-RealMode-8086-Assembly-Engine\`** | **Skill: Low-Level Systems** | 16-bit **Intel 8086 Assembly** engine utilizing direct \`0B800h\` video memory addressing and hardware timer interrupts. |

---

## 📜 Verified Security Certifications

- **Google Cybersecurity Specialization** — *Foundations of Cybersecurity*
- **Google Cybersecurity Specialization** — *Connect and Protect: Networks and Network Security*
- **Google Cybersecurity Specialization** — *Tools of the Trade: Linux and SQL*
- **Google Cybersecurity Specialization** — *Play It Safe: Manage Security Risks*

---

## 📊 Live GitHub Telemetry

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=alihassanjamil&show_icons=true&theme=tokyonight&hide_border=true&bg_color=050811&title_color=00f2fe&icon_color=00f2fe&text_color=e2e8f0" height="165" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=alihassanjamil&layout=compact&theme=tokyonight&hide_border=true&bg_color=050811&title_color=00f2fe&text_color=e2e8f0" height="165" />
</div>

<div align="center">
  <img src="https://streak-stats.demolab.com?user=alihassanjamil&theme=tokyonight&hide_border=true&background=050811&ring=00f2fe&fire=00f2fe&currStreakLabel=00f2fe" height="165" />
</div>
`;

    let activeCategory = 'all';
    let searchQuery = '';
    let currentModalCode = '';

    function showToast(msg) {
      const toast = document.getElementById('toastBanner');
      const text = document.getElementById('toastMessage');
      text.textContent = msg;
      toast.classList.remove('hidden');
      toast.classList.add('flex');
      setTimeout(() => {
        toast.classList.add('hidden');
        toast.classList.remove('flex');
      }, 3000);
    }

    function copyTextToClipboard(text, successMsg) {
      if (navigator.clipboard && navigator.clipboard.writeText) {
        navigator.clipboard.writeText(text).then(() => {
          showToast(successMsg);
        }).catch(() => {
          fallbackCopy(text, successMsg);
        });
      } else {
        fallbackCopy(text, successMsg);
      }
    }

    function fallbackCopy(text, successMsg) {
      const ta = document.createElement('textarea');
      ta.value = text;
      ta.style.position = 'fixed';
      ta.style.opacity = '0';
      document.body.appendChild(ta);
      ta.select();
      try {
        document.execCommand('copy');
        showToast(successMsg);
      } catch (err) {
        showToast('Press Ctrl+C to copy the selected text.');
      }
      document.body.removeChild(ta);
    }

    function renderSkills() {
      const grid = document.getElementById('skillsGrid');
      const filtered = SKILLS_DATA.filter(item => {
        const matchesCat = activeCategory === 'all' || item.category === activeCategory;
        const q = searchQuery.trim().toLowerCase();
        const matchesSearch = !q || item.name.toLowerCase().includes(q) || item.tools.toLowerCase().includes(q) || item.desc.toLowerCase().includes(q);
        return matchesCat && matchesSearch;
      });

      if (filtered.length === 0) {
        grid.innerHTML = `<div class="col-span-full rounded-2xl border border-slate-800 bg-slate-900/50 p-8 text-center font-mono text-sm text-slate-400">No matching skills found for "${searchQuery}". Try clearing the search filter.</div>`;
        return;
      }

      grid.innerHTML = filtered.map(skill => {
        const isMaster = skill.tier === 'MASTER PROFESSION';
        const badgeStyle = isMaster
          ? 'bg-cyan-500/15 text-cyan-300 border-cyan-500/40'
          : (skill.badgeColor === 'emerald' ? 'bg-emerald-500/15 text-emerald-300 border-emerald-500/40' : 'bg-amber-500/15 text-amber-300 border-amber-500/40');
        const barColor = isMaster
          ? 'from-cyan-400 to-blue-500'
          : (skill.badgeColor === 'emerald' ? 'from-emerald-400 to-teal-500' : 'from-amber-400 to-orange-500');

        return `
          <div class="flex flex-col justify-between rounded-2xl border border-slate-800 bg-slate-900/80 p-5 hover:border-cyan-500/50 transition">
            <div>
              <div class="flex items-center justify-between gap-2">
                <span class="rounded-md border px-2.5 py-0.5 font-mono text-[10px] font-bold ${badgeStyle}">${skill.tier}</span>
                <span class="font-mono text-xs font-bold text-white">${skill.level}%</span>
              </div>
              <h3 class="mt-3 text-base font-bold text-white">${skill.name}</h3>
              <p class="mt-1 font-mono text-xs text-cyan-400">${skill.tools}</p>
              <p class="mt-2.5 text-xs leading-relaxed text-slate-300">${skill.desc}</p>
            </div>
            <div class="mt-4 pt-2">
              <div class="h-2 w-full overflow-hidden rounded-full bg-slate-800">
                <div class="h-full rounded-full bg-gradient-to-r ${barColor}" style="width: ${skill.level}%"></div>
              </div>
            </div>
          </div>
        `;
      }).join('');
    }

    function renderProjects() {
      const grid = document.getElementById('projectsGrid');
      grid.innerHTML = PROJECTS_DATA.map(proj => `
        <div class="flex flex-col justify-between rounded-2xl border border-slate-800 bg-slate-900/75 p-5 hover:border-cyan-500/50 transition">
          <div>
            <span class="inline-block rounded bg-cyan-500/10 px-2.5 py-1 font-mono text-[10px] font-bold text-cyan-400 border border-cyan-500/20">${proj.domain}</span>
            <h3 class="mt-3 text-lg font-bold text-white">${proj.title}</h3>
            <p class="mt-1 font-mono text-xs text-emerald-400">${proj.stack}</p>
            <p class="mt-3 text-xs leading-relaxed text-slate-300">${proj.summary}</p>
          </div>
          <div class="mt-5 pt-3 border-t border-slate-800/80 flex items-center justify-between">
            <span class="font-mono text-[11px] text-slate-400">Verified Architecture</span>
            <button type="button" data-proj-id="${proj.id}" class="inspect-proj-btn inline-flex items-center gap-1.5 rounded-lg bg-slate-800 px-3 py-1.5 font-mono text-xs font-semibold text-cyan-300 hover:bg-cyan-500 hover:text-slate-950 transition">
              Inspect Code
            </button>
          </div>
        </div>
      `).join('');

      document.querySelectorAll('.inspect-proj-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          const projId = btn.getAttribute('data-proj-id');
          const proj = PROJECTS_DATA.find(p => p.id === projId);
          if (!proj) return;
          document.getElementById('modalBadge').textContent = proj.domain;
          document.getElementById('modalTitle').textContent = proj.title;
          document.getElementById('modalSummary').textContent = proj.summary;
          document.getElementById('modalCode').textContent = proj.code;
          currentModalCode = proj.code;
          const modal = document.getElementById('projectModal');
          modal.classList.remove('hidden');
          modal.classList.add('flex');
        });
      });
    }

    function initApp() {
      renderSkills();
      renderProjects();

      document.getElementById('terminalOutput').textContent = TERMINAL_LOGS.clearance;
      document.getElementById('readmeCodeBlock').textContent = CLEAN_GITHUB_README;

      // Category tabs
      document.querySelectorAll('.skill-tab').forEach(tab => {
        tab.addEventListener('click', () => {
          activeCategory = tab.getAttribute('data-cat') || 'all';
          document.querySelectorAll('.skill-tab').forEach(t => {
            t.classList.remove('border-cyan-400', 'bg-cyan-500/20', 'text-cyan-300');
            t.classList.add('border-slate-800', 'bg-slate-900');
          });
          tab.classList.remove('border-slate-800', 'bg-slate-900');
          tab.classList.add('border-cyan-400', 'bg-cyan-500/20', 'text-cyan-300');
          renderSkills();
        });
      });

      // Search filter
      document.getElementById('skillSearchInput').addEventListener('input', (e) => {
        searchQuery = e.target.value || '';
        renderSkills();
      });

      // Terminal buttons
      document.querySelectorAll('.term-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          const cmd = btn.getAttribute('data-cmd');
          document.getElementById('terminalOutput').textContent = TERMINAL_LOGS[cmd] || TERMINAL_LOGS.clearance;
        });
      });

      // Modal close & copy
      document.getElementById('closeModalBtn').addEventListener('click', () => {
        const modal = document.getElementById('projectModal');
        modal.classList.add('hidden');
        modal.classList.remove('flex');
      });

      document.getElementById('copyModalCodeBtn').addEventListener('click', () => {
        copyTextToClipboard(currentModalCode, 'Architecture snippet copied!');
      });

      // Copy GitHub README buttons
      document.getElementById('topCopyReadmeBtn').addEventListener('click', () => {
        copyTextToClipboard(CLEAN_GITHUB_README, 'GitHub README.md copied! Paste directly into GitHub.');
      });
      document.getElementById('bottomCopyReadmeBtn').addEventListener('click', () => {
        copyTextToClipboard(CLEAN_GITHUB_README, 'GitHub README.md copied! Paste directly into GitHub.');
      });

      if (window.lucide) {
        window.lucide.createIcons();
      }
    }

    window.addEventListener('DOMContentLoaded', initApp);
  </script>
</body>
</html>
