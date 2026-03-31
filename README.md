<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Makvana Smitraj — Developer Profile</title>
<script src="https://cdn.tailwindcss.com"></script>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@400;500&family=Outfit:wght@300;400;500&display=swap" rel="stylesheet">
<script>
tailwind.config = {
  theme: {
    extend: {
      fontFamily: {
        display: ['Syne', 'sans-serif'],
        body: ['Outfit', 'sans-serif'],
        mono: ['DM Mono', 'monospace'],
      },
      colors: {
        bg:       '#08090d',
        surface:  '#0f1117',
        surface2: '#161922',
        surface3: '#1c2030',
        accent:   '#4f8ef7',
        purple:   '#7c5cfc',
        teal:     '#2dd4bf',
        amber:    '#f59e0b',
        rose:     '#f43f5e',
      },
      animation: {
        'fade-up':    'fadeUp 0.7s ease both',
        'fade-in':    'fadeIn 0.6s ease both',
        'float':      'float 6s ease-in-out infinite',
        'float2':     'float 8s ease-in-out 1s infinite',
        'float3':     'float 7s ease-in-out 2s infinite',
        'spin-slow':  'spin 20s linear infinite',
        'pulse-slow': 'pulse 4s cubic-bezier(0.4,0,0.6,1) infinite',
        'shimmer':    'shimmer 2.5s linear infinite',
        'typing':     'typing 3.5s steps(30,end) both, blink .75s step-end infinite',
        'slide-right':'slideRight 0.5s ease both',
        'glow-pulse': 'glowPulse 3s ease-in-out infinite',
        'bounce-in':  'bounceIn 0.6s cubic-bezier(0.34,1.56,0.64,1) both',
        'draw-line':  'drawLine 1.2s ease both',
        'count-up':   'countUp 0.8s ease both',
      },
      keyframes: {
        fadeUp:     { from: { opacity: '0', transform: 'translateY(28px)' }, to: { opacity: '1', transform: 'translateY(0)' } },
        fadeIn:     { from: { opacity: '0' }, to: { opacity: '1' } },
        float:      { '0%,100%': { transform: 'translateY(0px)' }, '50%': { transform: 'translateY(-18px)' } },
        shimmer:    { from: { backgroundPosition: '-200% center' }, to: { backgroundPosition: '200% center' } },
        glowPulse:  { '0%,100%': { opacity: '0.4', transform: 'scale(1)' }, '50%': { opacity: '0.8', transform: 'scale(1.08)' } },
        bounceIn:   { from: { opacity: '0', transform: 'scale(0.7)' }, to: { opacity: '1', transform: 'scale(1)' } },
        drawLine:   { from: { strokeDashoffset: '500' }, to: { strokeDashoffset: '0' } },
        slideRight: { from: { opacity: '0', transform: 'translateX(-20px)' }, to: { opacity: '1', transform: 'translateX(0)' } },
      }
    }
  }
}
</script>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: #08090d;
    font-family: 'Outfit', sans-serif;
    color: #e2e4ed;
    overflow-x: hidden;
  }

  /* ── ANIMATED BG ── */
  .bg-grid {
    position: fixed; inset: 0; z-index: 0; pointer-events: none;
    background-image:
      linear-gradient(rgba(79,142,247,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(79,142,247,0.04) 1px, transparent 1px);
    background-size: 48px 48px;
    mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 30%, transparent 100%);
  }

  .orb {
    position: fixed; border-radius: 50%; pointer-events: none; z-index: 0;
    filter: blur(70px); animation: glowPulse 4s ease-in-out infinite;
  }

  /* ── SHIMMER TEXT ── */
  .shimmer-text {
    background: linear-gradient(90deg, #a8b4d8 0%, #ffffff 25%, #4f8ef7 50%, #7c5cfc 75%, #a8b4d8 100%);
    background-size: 200% auto;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: shimmer 4s linear infinite;
  }

  /* ── TYPING CURSOR ── */
  .typing-line::after {
    content: '|';
    color: #4f8ef7;
    animation: blink 0.75s step-end infinite;
  }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* ── SECTION REVEAL ── */
  .reveal { opacity: 0; transform: translateY(32px); transition: opacity 0.7s ease, transform 0.7s ease; }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* ── STAGGER ── */
  .stagger > * { opacity: 0; transform: translateY(20px); transition: opacity 0.5s ease, transform 0.5s ease; }
  .stagger.visible > *:nth-child(1)  { opacity:1; transform:none; transition-delay:.05s }
  .stagger.visible > *:nth-child(2)  { opacity:1; transform:none; transition-delay:.1s }
  .stagger.visible > *:nth-child(3)  { opacity:1; transform:none; transition-delay:.15s }
  .stagger.visible > *:nth-child(4)  { opacity:1; transform:none; transition-delay:.2s }
  .stagger.visible > *:nth-child(5)  { opacity:1; transform:none; transition-delay:.25s }
  .stagger.visible > *:nth-child(6)  { opacity:1; transform:none; transition-delay:.3s }
  .stagger.visible > *:nth-child(7)  { opacity:1; transform:none; transition-delay:.35s }
  .stagger.visible > *:nth-child(8)  { opacity:1; transform:none; transition-delay:.4s }
  .stagger.visible > *:nth-child(9)  { opacity:1; transform:none; transition-delay:.45s }
  .stagger.visible > *:nth-child(10) { opacity:1; transform:none; transition-delay:.5s }

  /* ── SKILL BAR ── */
  .skill-bar-fill { width: 0; transition: width 1.2s cubic-bezier(0.25, 1, 0.5, 1); }
  .skill-bar-fill.animate { width: var(--w); }

  /* ── CARD HOVER ── */
  .card-hover {
    transition: transform 0.25s ease, border-color 0.25s ease, background 0.25s ease;
  }
  .card-hover:hover {
    transform: translateY(-4px);
    border-color: rgba(79,142,247,0.35) !important;
    background: #161922 !important;
  }

  /* ── PILL HOVER ── */
  .pill-hover {
    transition: transform 0.2s ease, border-color 0.2s ease, background 0.2s ease, box-shadow 0.2s ease;
  }
  .pill-hover:hover {
    transform: translateY(-3px) scale(1.04);
    border-color: rgba(79,142,247,0.4);
    box-shadow: 0 0 16px rgba(79,142,247,0.2);
  }

  /* ── MAGNETIC BUTTON ── */
  .btn-mag {
    transition: transform 0.2s ease, box-shadow 0.2s ease, background 0.2s ease;
  }
  .btn-mag:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 30px rgba(79,142,247,0.35);
  }
  .btn-mag:active { transform: scale(0.97); }

  /* ── CURSOR DOT ── */
  #cursor {
    position: fixed; width: 10px; height: 10px;
    background: #4f8ef7; border-radius: 50%;
    pointer-events: none; z-index: 9999;
    transform: translate(-50%, -50%);
    transition: transform 0.1s ease, width 0.2s ease, height 0.2s ease, opacity 0.2s ease;
    mix-blend-mode: screen;
  }
  #cursor-ring {
    position: fixed; width: 36px; height: 36px;
    border: 1px solid rgba(79,142,247,0.5); border-radius: 50%;
    pointer-events: none; z-index: 9998;
    transform: translate(-50%, -50%);
    transition: transform 0.12s ease, width 0.2s ease, height 0.2s ease, opacity 0.3s ease;
  }

  /* ── GRADIENT BORDER ── */
  .grad-border {
    position: relative;
    background: #0f1117;
    border-radius: 14px;
  }
  .grad-border::before {
    content: '';
    position: absolute; inset: -1px;
    border-radius: 15px;
    background: linear-gradient(135deg, rgba(79,142,247,0.4), rgba(124,92,252,0.3), rgba(45,212,191,0.2));
    z-index: -1;
    opacity: 0;
    transition: opacity 0.3s ease;
  }
  .grad-border:hover::before { opacity: 1; }

  /* ── SECTION LABEL ── */
  .section-label {
    display: flex; align-items: center; gap: 12px;
    font-family: 'DM Mono', monospace;
    font-size: 11px; color: #3d4258;
    letter-spacing: 0.12em; text-transform: uppercase;
    margin-bottom: 28px;
  }
  .section-label::after {
    content: ''; flex: 1; height: 1px;
    background: linear-gradient(to right, rgba(79,142,247,0.2), transparent);
  }

  /* ── PROGRESS RING ── */
  .progress-circle { transform: rotate(-90deg); }
  .progress-circle circle { transition: stroke-dashoffset 1.4s cubic-bezier(0.25,1,0.5,1); }

  /* ── FLOATING PARTICLES ── */
  .particle {
    position: absolute; border-radius: 50%;
    background: rgba(79,142,247,0.5);
    animation: float var(--dur, 6s) ease-in-out infinite;
    animation-delay: var(--delay, 0s);
  }

  /* ── SCROLL INDICATOR ── */
  #scroll-progress {
    position: fixed; top: 0; left: 0; height: 2px; z-index: 1000;
    background: linear-gradient(to right, #4f8ef7, #7c5cfc);
    transition: width 0.1s linear;
  }

  /* ── NOISE ── */
  .noise-overlay {
    position: fixed; inset: 0; pointer-events: none; z-index: 1;
    opacity: 0.03;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  }
</style>
</head>
<body>

<!-- Cursor -->
<div id="cursor"></div>
<div id="cursor-ring"></div>

<!-- Scroll progress -->
<div id="scroll-progress" style="width:0%"></div>

<!-- BG layers -->
<div class="bg-grid"></div>
<div class="noise-overlay"></div>
<div class="orb" style="width:600px;height:600px;background:radial-gradient(circle,rgba(79,142,247,0.1) 0%,transparent 70%);top:-150px;right:-150px;animation-delay:0s"></div>
<div class="orb" style="width:450px;height:450px;background:radial-gradient(circle,rgba(124,92,252,0.09) 0%,transparent 70%);bottom:10%;left:-100px;animation-delay:1.5s"></div>
<div class="orb" style="width:320px;height:320px;background:radial-gradient(circle,rgba(45,212,191,0.07) 0%,transparent 70%);top:55%;right:5%;animation-delay:3s"></div>

<div class="relative z-10 max-w-4xl mx-auto px-6 py-16">

  <!-- ══════════════════ HERO ══════════════════ -->
  <header class="text-center pt-12 pb-20 relative">

    <!-- floating particles -->
    <div class="absolute inset-0 pointer-events-none overflow-hidden" aria-hidden="true">
      <div class="particle" style="width:4px;height:4px;top:20%;left:15%;--dur:7s;--delay:0s"></div>
      <div class="particle" style="width:3px;height:3px;top:60%;left:8%;--dur:9s;--delay:1s;background:rgba(124,92,252,0.6)"></div>
      <div class="particle" style="width:5px;height:5px;top:30%;right:12%;--dur:6s;--delay:2s;background:rgba(45,212,191,0.5)"></div>
      <div class="particle" style="width:3px;height:3px;top:75%;right:20%;--dur:8s;--delay:0.5s"></div>
      <div class="particle" style="width:6px;height:6px;top:10%;left:45%;--dur:10s;--delay:1.5s;background:rgba(245,158,11,0.4)"></div>
    </div>

    <!-- Badge -->
    <div class="animate-fade-up" style="animation-delay:0.1s">
      <span class="inline-flex items-center gap-2 bg-surface border border-white/[0.07] rounded-full px-4 py-2 text-xs font-mono text-gray-500 mb-8 tracking-widest uppercase">
        <span class="w-1.5 h-1.5 rounded-full bg-teal animate-pulse"></span>
        Available for collaboration
      </span>
    </div>

    <!-- Namaste -->
    <div class="animate-fade-up mb-2" style="animation-delay:0.2s">
      <span class="text-3xl">🙏</span>
    </div>

    <!-- Name -->
    <h1 class="font-display font-extrabold leading-none tracking-tighter mb-5 animate-fade-up"
        style="font-size:clamp(48px,9vw,88px);animation-delay:0.3s">
      <span class="shimmer-text">Makvana Smitraj</span>
    </h1>

    <!-- Animated role line -->
    <div class="animate-fade-up mb-8" style="animation-delay:0.4s">
      <p id="role-text" class="text-gray-400 text-lg font-light typing-line" style="font-family:'DM Mono',monospace;min-height:28px"></p>
    </div>

    <!-- Tags -->
    <div class="flex flex-wrap justify-center gap-2.5 mb-10 stagger animate-fade-up" id="hero-tags" style="animation-delay:0.5s">
      <span class="inline-flex items-center gap-2 bg-surface border border-white/[0.06] rounded-full px-3.5 py-1.5 text-xs font-mono text-gray-400 pill-hover cursor-default">
        <span class="w-1.5 h-1.5 rounded-full bg-accent"></span>Full-Stack Dev
      </span>
      <span class="inline-flex items-center gap-2 bg-surface border border-white/[0.06] rounded-full px-3.5 py-1.5 text-xs font-mono text-gray-400 pill-hover cursor-default">
        <span class="w-1.5 h-1.5 rounded-full bg-purple"></span>MERN Stack
      </span>
      <span class="inline-flex items-center gap-2 bg-surface border border-white/[0.06] rounded-full px-3.5 py-1.5 text-xs font-mono text-gray-400 pill-hover cursor-default">
        <span class="w-1.5 h-1.5 rounded-full bg-teal"></span>AI Learner
      </span>
      <span class="inline-flex items-center gap-2 bg-surface border border-white/[0.06] rounded-full px-3.5 py-1.5 text-xs font-mono text-gray-400 pill-hover cursor-default">
        <span class="w-1.5 h-1.5 rounded-full bg-amber"></span>Open to Collaborate
      </span>
      <span class="inline-flex items-center gap-2 bg-surface border border-white/[0.06] rounded-full px-3.5 py-1.5 text-xs font-mono text-gray-400 pill-hover cursor-default">
        <span class="w-1.5 h-1.5 rounded-full bg-rose"></span>Surat, India
      </span>
    </div>

    <!-- CTAs -->
    <div class="flex flex-wrap items-center justify-center gap-3 animate-fade-up" style="animation-delay:0.65s">
      <a href="https://www.linkedin.com/in/smitrajmakvana" target="_blank"
         class="btn-mag inline-flex items-center gap-2 bg-accent text-white text-sm font-medium rounded-full px-6 py-2.5 no-underline">
        LinkedIn ↗
      </a>
      <a href="mailto:smitrajsinhmakvana@gmail.com"
         class="btn-mag inline-flex items-center gap-2 border border-white/10 text-gray-400 hover:text-white text-sm font-medium rounded-full px-6 py-2.5 no-underline"
         style="transition:color .2s,border-color .2s">
        smitrajsinhmakvana@gmail.com
      </a>
    </div>

    <!-- Scroll cue -->
    <div class="mt-16 flex justify-center animate-bounce">
      <div class="w-5 h-8 border border-white/10 rounded-full flex items-start justify-center pt-1.5">
        <div class="w-1 h-2 bg-accent/60 rounded-full animate-bounce" style="animation-delay:.3s"></div>
      </div>
    </div>
  </header>

  <!-- ══════════════════ ABOUT ══════════════════ -->
  <section class="mb-20 reveal" id="about">
    <div class="section-label">// about me</div>
    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 stagger">

      <div class="grad-border card-hover p-5 flex items-start gap-4 bg-surface border border-white/[0.06] rounded-2xl cursor-default">
        <div class="w-10 h-10 rounded-xl bg-accent/10 flex items-center justify-center text-lg flex-shrink-0">💼</div>
        <div>
          <p class="text-xs font-mono text-gray-600 uppercase tracking-widest mb-1">Current Role</p>
          <p class="text-sm text-gray-300 leading-relaxed">Full-Stack Developer Intern<br><span class="text-accent">Krishang Technolab</span></p>
        </div>
      </div>

      <div class="grad-border card-hover p-5 flex items-start gap-4 bg-surface border border-white/[0.06] rounded-2xl cursor-default">
        <div class="w-10 h-10 rounded-xl bg-purple/10 flex items-center justify-center text-lg flex-shrink-0">🔭</div>
        <div>
          <p class="text-xs font-mono text-gray-600 uppercase tracking-widest mb-1">Building Now</p>
          <p class="text-sm text-gray-300 leading-relaxed">Super Admin Panel — RBAC System with Analytics Dashboard</p>
        </div>
      </div>

      <div class="grad-border card-hover p-5 flex items-start gap-4 bg-surface border border-white/[0.06] rounded-2xl cursor-default">
        <div class="w-10 h-10 rounded-xl bg-teal/10 flex items-center justify-center text-lg flex-shrink-0">🌱</div>
        <div>
          <p class="text-xs font-mono text-gray-600 uppercase tracking-widest mb-1">Learning</p>
          <p class="text-sm text-gray-300 leading-relaxed">Next.js · Advanced Backend · AI &amp; RAG Systems</p>
        </div>
      </div>

      <div class="grad-border card-hover p-5 flex items-start gap-4 bg-surface border border-white/[0.06] rounded-2xl cursor-default">
        <div class="w-10 h-10 rounded-xl bg-amber/10 flex items-center justify-center text-lg flex-shrink-0">👯</div>
        <div>
          <p class="text-xs font-mono text-gray-600 uppercase tracking-widest mb-1">Open to Collaborate</p>
          <p class="text-sm text-gray-300 leading-relaxed">MERN + AI Projects · Open Source · Real-world Apps</p>
        </div>
      </div>

      <div class="grad-border card-hover p-5 flex items-start gap-4 bg-surface border border-white/[0.06] rounded-2xl sm:col-span-2 cursor-default">
        <div class="w-10 h-10 rounded-xl bg-accent/10 flex items-center justify-center text-lg flex-shrink-0">🧠</div>
        <div>
          <p class="text-xs font-mono text-gray-600 uppercase tracking-widest mb-1">Core Strengths</p>
          <p class="text-sm text-gray-300 leading-relaxed">APIs &amp; Authentication · Role-Based Access Control · REST Architecture · Secure Data Handling · Deployment (Render / Vercel)</p>
        </div>
      </div>

    </div>
  </section>

  <!-- ══════════════════ TECH STACK ══════════════════ -->
  <section class="mb-20 reveal" id="stack">
    <div class="section-label">// tech stack</div>

    <div class="space-y-8">

      <!-- Languages -->
      <div>
        <p class="text-xs font-mono text-gray-600 uppercase tracking-widest mb-4">Languages</p>
        <div class="flex flex-wrap gap-2.5 stagger">
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#A8B9CC"></span>C</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#F89820"></span>Java</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#F7DF1E"></span>JavaScript</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#3178C6"></span>TypeScript</span>
        </div>
      </div>

      <!-- Skill bars -->
      <div class="grad-border bg-surface border border-white/[0.06] rounded-2xl p-6 skill-bars-block">
        <p class="text-xs font-mono text-gray-600 uppercase tracking-widest mb-6">Proficiency</p>
        <div class="space-y-4">
          <div><div class="flex justify-between mb-1.5"><span class="text-sm text-gray-400">JavaScript / TypeScript</span><span class="text-xs font-mono text-accent">88%</span></div><div class="h-1.5 bg-white/[0.05] rounded-full overflow-hidden"><div class="skill-bar-fill h-full bg-gradient-to-r from-accent to-purple rounded-full" style="--w:88%"></div></div></div>
          <div><div class="flex justify-between mb-1.5"><span class="text-sm text-gray-400">React / Next.js</span><span class="text-xs font-mono text-accent">82%</span></div><div class="h-1.5 bg-white/[0.05] rounded-full overflow-hidden"><div class="skill-bar-fill h-full bg-gradient-to-r from-accent to-teal rounded-full" style="--w:82%"></div></div></div>
          <div><div class="flex justify-between mb-1.5"><span class="text-sm text-gray-400">Node.js / Express</span><span class="text-xs font-mono text-accent">80%</span></div><div class="h-1.5 bg-white/[0.05] rounded-full overflow-hidden"><div class="skill-bar-fill h-full bg-gradient-to-r from-purple to-rose rounded-full" style="--w:80%"></div></div></div>
          <div><div class="flex justify-between mb-1.5"><span class="text-sm text-gray-400">MongoDB / MySQL</span><span class="text-xs font-mono text-accent">75%</span></div><div class="h-1.5 bg-white/[0.05] rounded-full overflow-hidden"><div class="skill-bar-fill h-full bg-gradient-to-r from-teal to-accent rounded-full" style="--w:75%"></div></div></div>
          <div><div class="flex justify-between mb-1.5"><span class="text-sm text-gray-400">REST APIs / Auth</span><span class="text-xs font-mono text-accent">85%</span></div><div class="h-1.5 bg-white/[0.05] rounded-full overflow-hidden"><div class="skill-bar-fill h-full bg-gradient-to-r from-amber to-rose rounded-full" style="--w:85%"></div></div></div>
        </div>
      </div>

      <!-- Frontend -->
      <div>
        <p class="text-xs font-mono text-gray-600 uppercase tracking-widest mb-4">Frontend</p>
        <div class="flex flex-wrap gap-2.5 stagger">
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#61DAFB"></span>React</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#e2e8f0"></span>Next.js</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#646CFF"></span>Vite</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#7952B3"></span>Bootstrap</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#38BDF8"></span>Tailwind</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#8B5CF6"></span>Radix UI</span>
        </div>
      </div>

      <!-- Backend -->
      <div>
        <p class="text-xs font-mono text-gray-600 uppercase tracking-widest mb-4">Backend</p>
        <div class="flex flex-wrap gap-2.5 stagger">
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#339933"></span>Node.js</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#e2e8f0"></span>Express.js</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#4f8ef7"></span>JWT</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#2dd4bf"></span>REST APIs</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#f59e0b"></span>EJS</span>
        </div>
      </div>

      <!-- DB -->
      <div>
        <p class="text-xs font-mono text-gray-600 uppercase tracking-widest mb-4">Database</p>
        <div class="flex flex-wrap gap-2.5 stagger">
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#47A248"></span>MongoDB</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#4479A1"></span>MySQL</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#3ECF8E"></span>Supabase</span>
        </div>
      </div>

      <!-- Tools -->
      <div>
        <p class="text-xs font-mono text-gray-600 uppercase tracking-widest mb-4">Tools &amp; Platforms</p>
        <div class="flex flex-wrap gap-2.5 stagger">
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#F05032"></span>Git</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#e2e8f0"></span>GitHub</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#e2e8f0"></span>Vercel</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#46E3B7"></span>Render</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#CB3837"></span>npm</span>
          <span class="pill-hover inline-flex items-center gap-2 bg-surface2 border border-white/[0.07] rounded-lg px-3.5 py-2 text-sm font-mono text-gray-300 cursor-default"><span class="w-2 h-2 rounded-sm" style="background:#FF6C37"></span>Postman</span>
        </div>
      </div>

    </div>
  </section>

  <!-- ══════════════════ EXPERIENCE ══════════════════ -->
  <section class="mb-20 reveal" id="exp">
    <div class="section-label">// experience</div>
    <div class="relative bg-surface border border-white/[0.07] rounded-2xl p-7 overflow-hidden grad-border">
      <!-- Animated gradient accent line -->
      <div class="absolute left-0 top-0 bottom-0 w-0.5 rounded-full" style="background:linear-gradient(to bottom,#4f8ef7,#7c5cfc,#2dd4bf)"></div>

      <!-- Animated scan line -->
      <div class="absolute left-0 right-0 h-px pointer-events-none" id="scanline"
           style="background:linear-gradient(to right,transparent,rgba(79,142,247,0.3),transparent);animation:scan 3s ease-in-out infinite">
      </div>
      <style>@keyframes scan{0%{top:0;opacity:0}10%{opacity:1}90%{opacity:1}100%{top:100%;opacity:0}}</style>

      <div class="flex flex-wrap items-start justify-between gap-3 mb-6 pl-4">
        <div>
          <h3 class="font-display font-bold text-xl text-gray-100 mb-1">Full-Stack Developer Intern</h3>
          <p class="text-sm font-mono" style="color:#4f8ef7">Krishang Technolab</p>
        </div>
        <span class="inline-flex items-center gap-1.5 text-xs font-mono px-3 py-1.5 rounded-full border"
              style="background:rgba(79,142,247,0.08);border-color:rgba(79,142,247,0.2);color:#4f8ef7">
          <span class="w-1.5 h-1.5 rounded-full bg-teal animate-pulse"></span> Active Internship
        </span>
      </div>

      <ul class="space-y-0 pl-4 stagger">
        <li class="flex items-start gap-3 py-3 border-b border-white/[0.04]">
          <span class="text-accent mt-0.5 flex-shrink-0">›</span>
          <span class="text-sm text-gray-400 leading-relaxed">Developed scalable, production-grade MERN stack applications from design to deployment</span>
        </li>
        <li class="flex items-start gap-3 py-3 border-b border-white/[0.04]">
          <span class="text-accent mt-0.5 flex-shrink-0">›</span>
          <span class="text-sm text-gray-400 leading-relaxed">Built and integrated RESTful APIs following clean architecture principles</span>
        </li>
        <li class="flex items-start gap-3 py-3 border-b border-white/[0.04]">
          <span class="text-accent mt-0.5 flex-shrink-0">›</span>
          <span class="text-sm text-gray-400 leading-relaxed">Implemented secure authentication &amp; authorization systems using JWT and RBAC</span>
        </li>
        <li class="flex items-start gap-3 py-3 border-b border-white/[0.04]">
          <span class="text-accent mt-0.5 flex-shrink-0">›</span>
          <span class="text-sm text-gray-400 leading-relaxed">Deployed applications on cloud platforms including Render and Vercel</span>
        </li>
        <li class="flex items-start gap-3 py-3">
          <span class="text-accent mt-0.5 flex-shrink-0">›</span>
          <span class="text-sm text-gray-400 leading-relaxed">Built Super Admin Panel featuring multi-role dashboards and real-time analytics</span>
        </li>
      </ul>
    </div>
  </section>

  <!-- ══════════════════ PROJECTS ══════════════════ -->
  <section class="mb-20 reveal" id="projects">
    <div class="section-label">// featured projects</div>
    <div class="space-y-4 stagger">

      <a href="https://github.com/Smitraj24/Super_Admin_Panel" target="_blank"
         class="grad-border card-hover block bg-surface border border-white/[0.07] rounded-2xl p-6 no-underline group">
        <div class="flex items-start gap-5">
          <span class="font-mono text-xs text-gray-700 mt-1 w-6 flex-shrink-0">01</span>
          <div class="flex-1">
            <div class="flex items-center justify-between gap-3 mb-3">
              <h3 class="font-display font-bold text-lg text-gray-100 group-hover:text-accent" style="transition:color .2s">Super Admin Panel</h3>
              <span class="text-gray-600 group-hover:text-accent group-hover:translate-x-0.5 group-hover:-translate-y-0.5" style="transition:all .2s">↗</span>
            </div>
            <p class="text-sm text-gray-500 leading-relaxed mb-4">A full-featured RBAC system with secure auth and real-time analytics dashboard. Built for scalable multi-role enterprise management.</p>
            <div class="flex flex-wrap gap-2">
              <span class="text-xs font-mono px-2.5 py-1 rounded-md bg-surface3 border border-white/[0.05] text-gray-500">RBAC</span>
              <span class="text-xs font-mono px-2.5 py-1 rounded-md bg-surface3 border border-white/[0.05] text-gray-500">JWT Auth</span>
              <span class="text-xs font-mono px-2.5 py-1 rounded-md bg-surface3 border border-white/[0.05] text-gray-500">Analytics</span>
              <span class="text-xs font-mono px-2.5 py-1 rounded-md bg-surface3 border border-white/[0.05] text-gray-500">MERN</span>
            </div>
          </div>
        </div>
      </a>

      <a href="https://github.com/Smitraj24" target="_blank"
         class="grad-border card-hover block bg-surface border border-white/[0.07] rounded-2xl p-6 no-underline group">
        <div class="flex items-start gap-5">
          <span class="font-mono text-xs text-gray-700 mt-1 w-6 flex-shrink-0">02</span>
          <div class="flex-1">
            <div class="flex items-center justify-between gap-3 mb-3">
              <h3 class="font-display font-bold text-lg text-gray-100 group-hover:text-accent" style="transition:color .2s">Inventory Management System</h3>
              <span class="text-gray-600 group-hover:text-accent group-hover:translate-x-0.5 group-hover:-translate-y-0.5" style="transition:all .2s">↗</span>
            </div>
            <p class="text-sm text-gray-500 leading-relaxed mb-4">End-to-end inventory solution with product &amp; order management, user dashboards, and real-world business logic with full CRUD operations.</p>
            <div class="flex flex-wrap gap-2">
              <span class="text-xs font-mono px-2.5 py-1 rounded-md bg-surface3 border border-white/[0.05] text-gray-500">Product Mgmt</span>
              <span class="text-xs font-mono px-2.5 py-1 rounded-md bg-surface3 border border-white/[0.05] text-gray-500">Order Tracking</span>
              <span class="text-xs font-mono px-2.5 py-1 rounded-md bg-surface3 border border-white/[0.05] text-gray-500">CRUD</span>
              <span class="text-xs font-mono px-2.5 py-1 rounded-md bg-surface3 border border-white/[0.05] text-gray-500">MongoDB</span>
            </div>
          </div>
        </div>
      </a>

      <a href="https://github.com/Smitraj24" target="_blank"
         class="grad-border card-hover block bg-surface border border-white/[0.07] rounded-2xl p-6 no-underline group">
        <div class="flex items-start gap-5">
          <span class="font-mono text-xs text-gray-700 mt-1 w-6 flex-shrink-0">03</span>
          <div class="flex-1">
            <div class="flex items-center justify-between gap-3 mb-3">
              <h3 class="font-display font-bold text-lg text-gray-100 group-hover:text-accent" style="transition:color .2s">Wanderlust</h3>
              <span class="text-gray-600 group-hover:text-accent group-hover:translate-x-0.5 group-hover:-translate-y-0.5" style="transition:all .2s">↗</span>
            </div>
            <p class="text-sm text-gray-500 leading-relaxed mb-4">A full-stack travel listing platform with Passport.js auth, bcrypt password hashing, and complete CRUD for listing management.</p>
            <div class="flex flex-wrap gap-2">
              <span class="text-xs font-mono px-2.5 py-1 rounded-md bg-surface3 border border-white/[0.05] text-gray-500">Passport.js</span>
              <span class="text-xs font-mono px-2.5 py-1 rounded-md bg-surface3 border border-white/[0.05] text-gray-500">bcrypt</span>
              <span class="text-xs font-mono px-2.5 py-1 rounded-md bg-surface3 border border-white/[0.05] text-gray-500">Full CRUD</span>
              <span class="text-xs font-mono px-2.5 py-1 rounded-md bg-surface3 border border-white/[0.05] text-gray-500">Node.js</span>
            </div>
          </div>
        </div>
      </a>

    </div>
  </section>

  <!-- ══════════════════ CURRENTLY LEARNING ══════════════════ -->
  <section class="mb-20 reveal" id="learning">
    <div class="section-label">// currently learning</div>
    <div class="grid grid-cols-2 sm:grid-cols-3 gap-3 stagger">
      <div class="card-hover bg-surface border border-white/[0.06] rounded-2xl p-5 cursor-default">
        <div class="text-2xl mb-3">⚡</div>
        <div class="text-sm font-medium text-gray-200 mb-1">Next.js 14</div>
        <div class="text-xs font-mono text-gray-600">App Router · RSC</div>
      </div>
      <div class="card-hover bg-surface border border-white/[0.06] rounded-2xl p-5 cursor-default">
        <div class="text-2xl mb-3">🤖</div>
        <div class="text-sm font-medium text-gray-200 mb-1">RAG Systems</div>
        <div class="text-xs font-mono text-gray-600">LangChain · Embeddings</div>
      </div>
      <div class="card-hover bg-surface border border-white/[0.06] rounded-2xl p-5 cursor-default">
        <div class="text-2xl mb-3">🗄️</div>
        <div class="text-sm font-medium text-gray-200 mb-1">Advanced Backend</div>
        <div class="text-xs font-mono text-gray-600">Queues · Caching</div>
      </div>
      <div class="card-hover bg-surface border border-white/[0.06] rounded-2xl p-5 cursor-default">
        <div class="text-2xl mb-3">🔐</div>
        <div class="text-sm font-medium text-gray-200 mb-1">Auth Patterns</div>
        <div class="text-xs font-mono text-gray-600">OAuth · RBAC · Refresh</div>
      </div>
      <div class="card-hover bg-surface border border-white/[0.06] rounded-2xl p-5 cursor-default">
        <div class="text-2xl mb-3">🚀</div>
        <div class="text-sm font-medium text-gray-200 mb-1">DevOps Basics</div>
        <div class="text-xs font-mono text-gray-600">CI/CD · Docker</div>
      </div>
      <div class="card-hover bg-surface border border-white/[0.06] rounded-2xl p-5 cursor-default">
        <div class="text-2xl mb-3">📊</div>
        <div class="text-sm font-medium text-gray-200 mb-1">System Design</div>
        <div class="text-xs font-mono text-gray-600">Scalability · APIs</div>
      </div>
    </div>
  </section>

  <!-- ══════════════════ FUN FACT ══════════════════ -->
  <section class="mb-20 reveal" id="fun">
    <div class="section-label">// fun fact</div>
    <div class="relative rounded-2xl p-7 overflow-hidden border"
         style="background:linear-gradient(135deg,rgba(124,92,252,0.07) 0%,rgba(79,142,247,0.07) 100%);border-color:rgba(124,92,252,0.2)">
      <div class="absolute inset-0 pointer-events-none" aria-hidden="true">
        <div class="particle" style="width:60px;height:60px;top:10%;right:5%;opacity:0.04;--dur:8s"></div>
        <div class="particle" style="width:40px;height:40px;bottom:10%;left:5%;opacity:0.04;--dur:10s;--delay:2s;background:rgba(124,92,252,0.5)"></div>
      </div>
      <div class="flex items-start gap-5">
        <span class="text-4xl flex-shrink-0 animate-bounce" style="animation-duration:2s">🕵️</span>
        <p class="text-base text-gray-400 italic leading-relaxed" style="font-family:'Outfit',sans-serif">
          Debugging is like being a detective in a crime movie where you are also the criminal.
          The best engineers are the ones who learned to love the mystery. 💻
        </p>
      </div>
    </div>
  </section>

  <!-- ══════════════════ FOOTER ══════════════════ -->
  <footer class="text-center pt-10 pb-6 border-t border-white/[0.05]">
    <p class="font-display font-extrabold text-2xl mb-2 shimmer-text tracking-tight">Smitraj24</p>
    <p class="text-xs font-mono text-gray-700">
      ⭐ From <a href="https://github.com/Smitraj24" target="_blank" class="text-accent hover:underline">github.com/Smitraj24</a>
    </p>
  </footer>

</div>

<script>
// ── Custom cursor ──
const cursor = document.getElementById('cursor');
const ring   = document.getElementById('cursor-ring');
let mx = 0, my = 0, rx = 0, ry = 0;
document.addEventListener('mousemove', e => { mx = e.clientX; my = e.clientY; });
(function lerp() {
  rx += (mx - rx) * 0.12;
  ry += (my - ry) * 0.12;
  cursor.style.left = mx + 'px'; cursor.style.top = my + 'px';
  ring.style.left   = rx + 'px'; ring.style.top   = ry + 'px';
  requestAnimationFrame(lerp);
})();
document.querySelectorAll('a,button,[class*="card-hover"],[class*="pill-hover"]').forEach(el => {
  el.addEventListener('mouseenter', () => { cursor.style.transform = 'translate(-50%,-50%) scale(2.5)'; ring.style.transform = 'translate(-50%,-50%) scale(1.5)'; });
  el.addEventListener('mouseleave', () => { cursor.style.transform = 'translate(-50%,-50%) scale(1)';   ring.style.transform = 'translate(-50%,-50%) scale(1)';   });
});

// ── Scroll progress ──
const bar = document.getElementById('scroll-progress');
window.addEventListener('scroll', () => {
  const p = window.scrollY / (document.body.scrollHeight - window.innerHeight);
  bar.style.width = (p * 100) + '%';
});

// ── Intersection Observer for reveals ──
const io = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.classList.add('visible');

      // Skill bars
      if (e.target.classList.contains('reveal')) {
        e.target.querySelectorAll('.skill-bar-fill').forEach(b => b.classList.add('animate'));
      }

      // Stagger children
      if (e.target.classList.contains('stagger')) {
        e.target.querySelectorAll(':scope > *').forEach((child, i) => {
          child.style.transitionDelay = (i * 0.07) + 's';
          child.style.opacity = '1';
          child.style.transform = 'none';
        });
      }
    }
  });
}, { threshold: 0.12 });

document.querySelectorAll('.reveal, .stagger').forEach(el => io.observe(el));

// Also trigger stagger inside reveal
const io2 = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.querySelectorAll('.stagger').forEach(s => {
        s.querySelectorAll(':scope > *').forEach((child, i) => {
          child.style.transitionDelay = (0.1 + i * 0.07) + 's';
          child.style.opacity = '1';
          child.style.transform = 'none';
        });
      });
    }
  });
}, { threshold: 0.1 });
document.querySelectorAll('.reveal').forEach(el => io2.observe(el));

// ── Typing animation ──
const roles = [
  'Full-Stack Developer',
  'MERN Stack Engineer',
  'AI & Backend Learner',
  'Building Real-World Apps',
];
let ri = 0, ci = 0, deleting = false;
const el = document.getElementById('role-text');
function typeLoop() {
  const word = roles[ri];
  if (!deleting) {
    el.textContent = word.slice(0, ++ci);
    if (ci === word.length) { deleting = true; setTimeout(typeLoop, 2200); return; }
    setTimeout(typeLoop, 75);
  } else {
    el.textContent = word.slice(0, --ci);
    if (ci === 0) { deleting = false; ri = (ri + 1) % roles.length; setTimeout(typeLoop, 400); return; }
    setTimeout(typeLoop, 40);
  }
}
typeLoop();

// ── Particle mouse parallax ──
document.addEventListener('mousemove', e => {
  const cx = e.clientX / window.innerWidth  - 0.5;
  const cy = e.clientY / window.innerHeight - 0.5;
  document.querySelectorAll('.particle').forEach((p, i) => {
    const s = (i % 3 + 1) * 8;
    p.style.transform = `translate(${cx * s}px, ${cy * s}px)`;
  });
});

// ── Count up for skill % labels ──
function countUp(el) {
  const target = parseInt(el.textContent);
  let n = 0;
  const step = () => {
    n = Math.min(n + Math.ceil(target / 30), target);
    el.textContent = n + '%';
    if (n < target) requestAnimationFrame(step);
  };
  requestAnimationFrame(step);
}
const barObserver = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.querySelectorAll('.text-accent.text-xs').forEach(countUp);
      barObserver.unobserve(e.target);
    }
  });
}, { threshold: 0.3 });
document.querySelectorAll('.skill-bars-block').forEach(b => barObserver.observe(b));
</script>
</body>
</html>
