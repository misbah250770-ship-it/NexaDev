<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>NexaDev — Software Development Team</title>
<meta name="description" content="NexaDev adalah software development team yang berfokus menciptakan solusi digital modern, fungsional, dan berdampak." />
<meta name="theme-color" content="#04070d" />

<!-- Open Graph -->
<meta property="og:title" content="NexaDev — Software Development Team" />
<meta property="og:description" content="We Create Digital Solutions. NexaDev is a collaborative software development team focused on creating modern and useful digital solutions." />
<meta property="og:type" content="website" />
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="NexaDev — Software Development Team" />
<meta name="twitter:description" content="We Create Digital Solutions." />

<!-- Favicon (SVG inline) -->
<link rel="icon" type="image/svg+xml" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32'%3E%3Cdefs%3E%3ClinearGradient id='g' x1='0' y1='0' x2='1' y2='1'%3E%3Cstop offset='0' stop-color='%233b82f6'/%3E%3Cstop offset='.5' stop-color='%2322d3ee'/%3E%3Cstop offset='1' stop-color='%2334d399'/%3E%3C/linearGradient%3E%3C/defs%3E%3Crect width='32' height='32' rx='8' fill='url(%23g)'/%3E%3Cpath d='M9 23V9l14 14V9' stroke='%2304121a' stroke-width='2.8' stroke-linecap='round' stroke-linejoin='round' fill='none'/%3E%3C/svg%3E" />

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&family=Space+Grotesk:wght@500;600;700&display=swap" rel="stylesheet" />
<style>
/* =========================================================
   NEXADEV — SINGLE FILE WEBSITE
   1. Tokens & Reset
   2. Scroll Progress + Background Decor
   3. Navbar
   4. Hero
   5. About
   6. Team
   7. Process (How We Work)
   8. Projects
   9. Contact + Form
   10. Footer
   11. Back to Top + Toast
   12. Utilities & Responsive
   ========================================================= */

/* ============ 1. TOKENS & RESET ============ */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root{
  --bg:            #04070d;
  --bg-soft:       #080d16;
  --surface:       rgba(255,255,255,.032);
  --surface-2:     rgba(255,255,255,.06);
  --border:        rgba(255,255,255,.08);
  --border-strong: rgba(255,255,255,.16);

  --text:  #e8eef8;
  --muted: #9aa8bd;

  --blue:  #3b82f6;
  --cyan:  #22d3ee;
  --green: #34d399;

  --grad: linear-gradient(115deg, #3b82f6 0%, #22d3ee 52%, #34d399 100%);

  --radius:   20px;
  --radius-sm:14px;
  --max:      1160px;
  --nav-h:    74px;

  --ease: cubic-bezier(.22, 1, .36, 1);
}

html{
  scroll-behavior: smooth;
  -webkit-text-size-adjust: 100%;
}

body{
  background: var(--bg);
  color: var(--text);
  font-family: 'Plus Jakarta Sans', system-ui, -apple-system, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
  font-size: 16px;
  line-height: 1.65;
  overflow-x: hidden;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

img, svg{ display: block; max-width: 100%; }
a{ color: inherit; text-decoration: none; }
button{ font: inherit; color: inherit; background: none; border: none; cursor: pointer; }
ul{ list-style: none; }

::selection{ background: rgba(34,211,238,.28); color: #fff; }

::-webkit-scrollbar{ width: 10px; }
::-webkit-scrollbar-track{ background: #04070d; }
::-webkit-scrollbar-thumb{
  background: linear-gradient(180deg, #1e4a7a, #155e63);
  border-radius: 99px;
  border: 2px solid #04070d;
}
::-webkit-scrollbar-thumb:hover{ background: linear-gradient(180deg, #22d3ee, #34d399); }

/* ============ 2. SCROLL PROGRESS + BG DECOR ============ */
.scroll-progress{
  position: fixed;
  top: 0; left: 0; right: 0;
  height: 3px;
  z-index: 101;
  background: rgba(255,255,255,.03);
  pointer-events: none;
}
.scroll-progress span{
  display: block;
  height: 100%;
  width: 0%;
  background: var(--grad);
  box-shadow: 0 0 14px rgba(34,211,238,.7);
  transition: width .08s linear;
}

.bg-decor{
  position: fixed;
  inset: 0;
  z-index: 0;
  overflow: hidden;
  pointer-events: none;
}
.orb{
  position: absolute;
  border-radius: 50%;
  filter: blur(110px);
  opacity: .45;
}
.orb-1{
  width: 520px; height: 520px;
  top: -180px; left: -140px;
  background: radial-gradient(circle, rgba(59,130,246,.55), transparent 70%);
}
.orb-2{
  width: 480px; height: 480px;
  top: 26%; right: -180px;
  background: radial-gradient(circle, rgba(34,211,238,.42), transparent 70%);
}
.orb-3{
  width: 520px; height: 520px;
  bottom: -220px; left: 32%;
  background: radial-gradient(circle, rgba(52,211,153,.30), transparent 70%);
}
.grid-overlay{
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(255,255,255,.028) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,.028) 1px, transparent 1px);
  background-size: 64px 64px;
  -webkit-mask-image: radial-gradient(ellipse 90% 62% at 50% 0%, #000 15%, transparent 78%);
  mask-image: radial-gradient(ellipse 90% 62% at 50% 0%, #000 15%, transparent 78%);
}

header, main, footer, .mobile-menu{ position: relative; z-index: 1; }

/* ============ 3. NAVBAR ============ */
.nav{
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  padding: 18px 0;
  transition: padding .35s var(--ease), background .35s ease, border-color .35s ease, backdrop-filter .35s ease;
  border-bottom: 1px solid transparent;
}
.nav.scrolled{
  padding: 10px 0;
  background: rgba(4,7,13,.72);
  -webkit-backdrop-filter: blur(18px);
  backdrop-filter: blur(18px);
  border-bottom-color: var(--border);
}

.nav-inner{
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
}

.logo{
  display: inline-flex;
  align-items: center;
  gap: 10px;
  font-family: 'Space Grotesk', sans-serif;
  font-weight: 700;
  font-size: 1.16rem;
  letter-spacing: -.02em;
  white-space: nowrap;
}
.logo-mark{
  width: 34px; height: 34px;
  display: grid;
  place-items: center;
  border-radius: 10px;
  background: var(--grad);
  color: #04070d;
  box-shadow: 0 6px 22px -6px rgba(34,211,238,.7);
  flex: none;
}
.logo-accent{
  background: var(--grad);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  -webkit-text-fill-color: transparent;
}

.nav-links{
  display: flex;
  align-items: center;
  gap: 32px;
}
.nav-links a{
  position: relative;
  font-size: .92rem;
  font-weight: 500;
  color: var(--muted);
  padding: 6px 0;
  transition: color .25s ease;
}
.nav-links a::after{
  content: '';
  position: absolute;
  left: 0; right: 0; bottom: 0;
  height: 1.5px;
  border-radius: 2px;
  background: var(--grad);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform .35s var(--ease);
}
.nav-links a:hover,
.nav-links a.active{ color: var(--text); }
.nav-links a:hover::after,
.nav-links a.active::after{ transform: scaleX(1); }

.nav-cta{ display: inline-flex; }

.hamburger{
  display: none;
  width: 44px; height: 44px;
  border-radius: 12px;
  border: 1px solid var(--border-strong);
  background: rgba(255,255,255,.03);
  position: relative;
  flex: none;
}
.hamburger span{
  position: absolute;
  left: 12px;
  width: 20px; height: 2px;
  border-radius: 2px;
  background: var(--text);
  transition: transform .35s var(--ease), opacity .25s ease, top .35s var(--ease);
}
.hamburger span:nth-child(1){ top: 15px; }
.hamburger span:nth-child(2){ top: 21px; }
.hamburger span:nth-child(3){ top: 27px; }
.hamburger.open span:nth-child(1){ top: 21px; transform: rotate(45deg); }
.hamburger.open span:nth-child(2){ opacity: 0; transform: scaleX(.4); }
.hamburger.open span:nth-child(3){ top: 21px; transform: rotate(-45deg); }

.mobile-menu{
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 99;
  display: none;
  flex-direction: column;
  gap: 4px;
  padding: calc(var(--nav-h) + 22px) 22px 28px;
  background: rgba(5,8,14,.97);
  -webkit-backdrop-filter: blur(22px);
  backdrop-filter: blur(22px);
  border-bottom: 1px solid var(--border);
  transform: translateY(-108%);
  visibility: hidden;
  transition: transform .45s var(--ease), visibility .45s ease;
}
.mobile-menu.open{ transform: translateY(0); visibility: visible; }
.mobile-menu a{
  padding: 14px 14px;
  border-radius: 12px;
  font-size: 1rem;
  font-weight: 600;
  color: var(--muted);
  transition: background .25s ease, color .25s ease, padding-left .25s ease;
}
.mobile-menu a:hover,
.mobile-menu a.active{
  color: var(--text);
  background: rgba(34,211,238,.07);
  padding-left: 20px;
}
.mobile-menu .btn{ margin-top: 14px; justify-content: center; }

/* ============ 4. HERO ============ */
.hero{
  padding: calc(var(--nav-h) + 76px) 0 96px;
  position: relative;
}

.hero-grid{
  display: grid;
  grid-template-columns: 1.05fr .95fr;
  gap: 64px;
  align-items: center;
}

.badge{
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 8px 18px 8px 13px;
  border-radius: 999px;
  border: 1px solid var(--border-strong);
  background: rgba(255,255,255,.03);
  font-size: .78rem;
  font-weight: 600;
  letter-spacing: .04em;
  text-transform: uppercase;
  color: #c3d1e4;
  margin-bottom: 26px;
}

.pulse-dot{
  width: 8px; height: 8px;
  border-radius: 50%;
  background: var(--green);
  flex: none;
  animation: pulse 2.2s infinite;
}
@keyframes pulse{
  0%   { box-shadow: 0 0 0 0 rgba(52,211,153,.65); }
  70%  { box-shadow: 0 0 0 9px rgba(52,211,153,0); }
  100% { box-shadow: 0 0 0 0 rgba(52,211,153,0); }
}

h1{
  font-family: 'Space Grotesk', sans-serif;
  font-size: clamp(2.25rem, 5.6vw, 4rem);
  line-height: 1.06;
  letter-spacing: -.035em;
  font-weight: 700;
  margin-bottom: 22px;
}

.grad-text{
  background: var(--grad);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  -webkit-text-fill-color: transparent;
}

.lead{
  font-size: 1.03rem;
  color: var(--muted);
  max-width: 540px;
  margin-bottom: 34px;
}

.hero-actions{
  display: flex;
  flex-wrap: wrap;
  gap: 14px;
  margin-bottom: 48px;
}

.btn{
  position: relative;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 14px 28px;
  min-height: 50px;
  border-radius: 999px;
  border: 1px solid transparent;
  font-size: .94rem;
  font-weight: 700;
  letter-spacing: .01em;
  white-space: nowrap;
  overflow: hidden;
  cursor: pointer;
  transition: transform .3s var(--ease), box-shadow .3s ease, background .3s ease, border-color .3s ease, color .3s ease;
}
.btn svg{ transition: transform .3s var(--ease); }
.btn:hover svg{ transform: translateX(4px); }

.btn-primary{
  background: var(--grad);
  color: #04121a;
  box-shadow: 0 10px 32px -10px rgba(34,211,238,.75);
}
.btn-primary:hover{
  transform: translateY(-3px);
  box-shadow: 0 18px 44px -10px rgba(34,211,238,.9);
}

.btn-ghost{
  background: rgba(255,255,255,.025);
  border-color: var(--border-strong);
  color: var(--text);
}
.btn-ghost:hover{
  transform: translateY(-3px);
  border-color: rgba(34,211,238,.55);
  background: rgba(34,211,238,.07);
  box-shadow: 0 14px 34px -16px rgba(34,211,238,.7);
}

.ripple{
  position: absolute;
  border-radius: 50%;
  background: rgba(255,255,255,.45);
  transform: scale(0);
  pointer-events: none;
  animation: rippleAnim .65s ease-out forwards;
}
@keyframes rippleAnim{
  to{ transform: scale(2.4); opacity: 0; }
}

.hero-stats{
  display: flex;
  flex-wrap: wrap;
  gap: 14px 42px;
  padding-top: 30px;
  border-top: 1px solid var(--border);
}
.stat{ display: flex; flex-direction: column; }
.stat-num{
  font-family: 'Space Grotesk', sans-serif;
  font-size: 1.65rem;
  font-weight: 700;
  line-height: 1.2;
  letter-spacing: -.02em;
  background: var(--grad);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  -webkit-text-fill-color: transparent;
  display: inline-block;
  min-width: 1.6em;
}
.stat-label{
  font-size: .8rem;
  color: var(--muted);
  letter-spacing: .04em;
}

.hero-visual{
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 380px;
}
.hero-visual::before{
  content: '';
  position: absolute;
  width: 440px; height: 440px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(34,211,238,.26), transparent 68%);
  filter: blur(52px);
  z-index: 0;
}

.mockup{
  position: relative;
  z-index: 1;
  width: 100%;
  max-width: 520px;
  border-radius: 22px;
  border: 1px solid var(--border-strong);
  background: linear-gradient(160deg, rgba(19,26,40,.96), rgba(7,11,19,.97));
  box-shadow:
    0 44px 90px -34px rgba(0,0,0,.95),
    0 0 0 1px rgba(34,211,238,.06) inset;
  overflow: hidden;
  animation: floatSlow 7s ease-in-out infinite;
}
@keyframes floatSlow{
  0%, 100%{ transform: translateY(0); }
  50%     { transform: translateY(-12px); }
}

.mock-top{
  display: flex;
  align-items: center;
  gap: 7px;
  padding: 14px 16px;
  border-bottom: 1px solid var(--border);
  background: rgba(255,255,255,.022);
}
.dot{
  width: 9px; height: 9px;
  border-radius: 50%;
  background: rgba(255,255,255,.13);
  flex: none;
}
.mock-url{
  flex: 1;
  height: 10px;
  margin-left: 10px;
  border-radius: 99px;
  background: rgba(255,255,255,.055);
  overflow: hidden;
}
.mock-url span{
  display: block;
  width: 42%; height: 100%;
  border-radius: 99px;
  background: var(--grad);
  opacity: .65;
}

.mock-body{
  display: grid;
  grid-template-columns: 52px 1fr;
  gap: 16px;
  padding: 18px;
}
.mock-side{
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.side-item{
  height: 10px;
  border-radius: 99px;
  background: rgba(255,255,255,.07);
}
.side-item:nth-child(2){ width: 74%; }
.side-item:nth-child(3){ width: 88%; }
.side-item:nth-child(4){ width: 60%; }
.side-item.active{ background: linear-gradient(90deg, #22d3ee, #34d399); opacity: .85; }

.mock-main{
  display: flex;
  flex-direction: column;
  gap: 16px;
  min-width: 0;
}
.mock-head{
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 14px;
}
.mock-title{
  height: 12px;
  width: 46%;
  border-radius: 99px;
  background: rgba(255,255,255,.1);
}
.mock-pill{
  height: 22px;
  width: 68px;
  border-radius: 99px;
  border: 1px solid rgba(34,211,238,.4);
  background: rgba(34,211,238,.09);
  flex: none;
}

.chart{
  display: flex;
  align-items: flex-end;
  gap: 9px;
  height: 132px;
  padding: 12px;
  border-radius: 14px;
  border: 1px solid var(--border);
  background: rgba(255,255,255,.018);
}
.chart span{
  flex: 1;
  height: var(--h, 50%);
  border-radius: 6px 6px 3px 3px;
  background: linear-gradient(180deg, rgba(34,211,238,.9), rgba(59,130,246,.18));
  transform-origin: bottom;
  animation: barGrow 1s var(--ease) backwards;
}
.chart span:nth-child(1){ animation-delay: .15s; }
.chart span:nth-child(2){ animation-delay: .25s; background: linear-gradient(180deg, rgba(59,130,246,.9), rgba(59,130,246,.18)); }
.chart span:nth-child(3){ animation-delay: .35s; }
.chart span:nth-child(4){ animation-delay: .45s; background: linear-gradient(180deg, rgba(52,211,153,.9), rgba(52,211,153,.18)); }
.chart span:nth-child(5){ animation-delay: .55s; }
.chart span:nth-child(6){ animation-delay: .65s; background: linear-gradient(180deg, rgba(34,211,238,.9), rgba(34,211,238,.18)); }
.chart span:nth-child(7){ animation-delay: .75s; }
@keyframes barGrow{
  from{ transform: scaleY(.12); opacity: 0; }
  to  { transform: scaleY(1);   opacity: 1; }
}

.mock-tiles{
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}
.tile{
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 12px;
  border-radius: 13px;
  border: 1px solid var(--border);
  background: rgba(255,255,255,.02);
  min-width: 0;
}
.tile i{
  width: 26px; height: 26px;
  border-radius: 8px;
  background: linear-gradient(135deg, #3b82f6, #22d3ee);
  flex: none;
}
.tile:nth-child(2) i{ background: linear-gradient(135deg, #22d3ee, #34d399); }
.tile b{
  display: block;
  flex: 1;
  height: 8px;
  border-radius: 99px;
  background: rgba(255,255,255,.075);
}

.float-card{
  position: absolute;
  z-index: 2;
  display: inline-flex;
  align-items: center;
  gap: 9px;
  padding: 10px 17px;
  border-radius: 999px;
  border: 1px solid var(--border-strong);
  background: rgba(9,14,23,.88);
  -webkit-backdrop-filter: blur(12px);
  backdrop-filter: blur(12px);
  font-size: .78rem;
  font-weight: 700;
  letter-spacing: .02em;
  white-space: nowrap;
  box-shadow: 0 20px 44px -22px rgba(0,0,0,.95);
}
.fc-1{ top: 6%; left: -5%; animation: floatChip 6s ease-in-out infinite; }
.fc-2{ bottom: 9%; right: -4%; animation: floatChip 6s ease-in-out infinite .9s; }
.fc-num{
  font-family: 'Space Grotesk', sans-serif;
  font-size: 1rem;
  background: var(--grad);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  -webkit-text-fill-color: transparent;
}
@keyframes floatChip{
  0%, 100%{ transform: translateY(0); }
  50%     { transform: translateY(-11px); }
}

/* ============ SECTION BASE ============ */
section{ scroll-margin-top: 84px; }
.section{ padding: clamp(74px, 9vw, 122px) 0; }

.container{
  width: 100%;
  max-width: var(--max);
  margin: 0 auto;
  padding: 0 24px;
}

.eyebrow{
  display: inline-flex;
  align-items: center;
  gap: 9px;
  font-size: .75rem;
  font-weight: 800;
  letter-spacing: .2em;
  text-transform: uppercase;
  color: var(--cyan);
  margin-bottom: 16px;
}
.eyebrow::before{
  content: '';
  width: 24px;
  height: 2px;
  border-radius: 2px;
  background: var(--grad);
}

h2{
  font-family: 'Space Grotesk', sans-serif;
  font-size: clamp(1.75rem, 4vw, 2.65rem);
  line-height: 1.14;
  letter-spacing: -.03em;
  font-weight: 700;
}

.section-sub{
  color: var(--muted);
  font-size: 1rem;
  max-width: 620px;
}

/* ============ 5. ABOUT ============ */
.about-head{
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  align-items: end;
  margin-bottom: 56px;
}
.about-head .section-sub{ padding-bottom: 6px; }

.grid-3{
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 22px;
}

.card{
  position: relative;
  padding: 32px 28px;
  border-radius: var(--radius);
  border: 1px solid var(--border);
  background: linear-gradient(165deg, rgba(255,255,255,.045), rgba(255,255,255,.012));
  overflow: hidden;
  transition: transform .4s var(--ease), border-color .4s ease, box-shadow .4s ease, background .4s ease;
}
.card::before{
  content: '';
  position: absolute;
  inset: 0;
  border-radius: inherit;
  background: radial-gradient(420px circle at var(--mx, 50%) var(--my, 0%), rgba(34,211,238,.14), transparent 65%);
  opacity: 0;
  transition: opacity .45s ease;
  pointer-events: none;
}
.card:hover{
  transform: translateY(-7px);
  border-color: rgba(34,211,238,.4);
  box-shadow: 0 28px 60px -30px rgba(34,211,238,.55);
}
.card:hover::before{ opacity: 1; }

.card-icon{
  width: 52px; height: 52px;
  display: grid;
  place-items: center;
  border-radius: 15px;
  margin-bottom: 22px;
  color: var(--cyan);
  background: rgba(34,211,238,.09);
  border: 1px solid rgba(34,211,238,.22);
  transition: transform .4s var(--ease), color .35s ease, background .35s ease;
}
.card:hover .card-icon{
  transform: translateY(-4px) scale(1.05);
  color: #04121a;
  background: var(--grad);
  border-color: transparent;
}

.card h3{
  font-family: 'Space Grotesk', sans-serif;
  font-size: 1.16rem;
  font-weight: 700;
  letter-spacing: -.015em;
  margin-bottom: 10px;
}
.card p{
  font-size: .93rem;
  color: var(--muted);
  line-height: 1.7;
}

/* ============ 6. TEAM ============ */
.team-head{
  text-align: center;
  max-width: 640px;
  margin: 0 auto 56px;
}
.team-head .eyebrow{ justify-content: center; }
.team-head .eyebrow::before{ display: none; }
.team-head .section-sub{ margin: 14px auto 0; }

.team-card{
  text-align: center;
  padding: 38px 26px 32px;
}
.avatar{
  width: 92px; height: 92px;
  margin: 0 auto 20px;
  display: grid;
  place-items: center;
  border-radius: 50%;
  font-family: 'Space Grotesk', sans-serif;
  font-size: 1.6rem;
  font-weight: 700;
  letter-spacing: .02em;
  color: var(--text);
  background: linear-gradient(150deg, rgba(59,130,246,.2), rgba(34,211,238,.12), rgba(52,211,153,.14));
  border: 1px solid var(--border-strong);
  position: relative;
  transition: transform .45s var(--ease), box-shadow .45s ease, border-color .45s ease;
}
.avatar::after{
  content: '';
  position: absolute;
  inset: -6px;
  border-radius: 50%;
  background: var(--grad);
  opacity: 0;
  filter: blur(14px);
  z-index: -1;
  transition: opacity .45s ease;
}
.team-card:hover .avatar{
  transform: translateY(-5px) scale(1.04);
  border-color: rgba(34,211,238,.5);
  box-shadow: 0 20px 44px -20px rgba(34,211,238,.8);
}
.team-card:hover .avatar::after{ opacity: .45; }

.team-card h3{
  font-family: 'Space Grotesk', sans-serif;
  font-size: 1.1rem;
  font-weight: 700;
  letter-spacing: -.015em;
  margin-bottom: 6px;
}
.team-role{
  font-size: .82rem;
  font-weight: 600;
  letter-spacing: .06em;
  text-transform: uppercase;
  color: var(--cyan);
}
.team-card p.bio{
  margin-top: 14px;
  font-size: .9rem;
  color: var(--muted);
}
.team-line{
  width: 46px;
  height: 3px;
  margin: 18px auto 0;
  border-radius: 99px;
  background: var(--grad);
  opacity: .55;
  transition: width .45s var(--ease), opacity .4s ease;
}
.team-card:hover .team-line{ width: 84px; opacity: 1; }

/* ============ 7. PROCESS (HOW WE WORK) ============ */
.process-head{
  text-align: center;
  max-width: 640px;
  margin: 0 auto 62px;
}
.process-head .eyebrow{ justify-content: center; }
.process-head .eyebrow::before{ display: none; }
.process-head .section-sub{ margin: 14px auto 0; }

.process-grid{
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 22px;
  position: relative;
}
.process-grid::before{
  content: '';
  position: absolute;
  top: 32px;
  left: 12%;
  right: 12%;
  height: 1px;
  background: linear-gradient(90deg,
    transparent 0%,
    rgba(34,211,238,.35) 15%,
    rgba(34,211,238,.35) 85%,
    transparent 100%);
  z-index: 0;
  pointer-events: none;
}
.process-step{
  position: relative;
  z-index: 1;
  text-align: center;
  padding: 0 8px;
}
.step-number{
  width: 64px; height: 64px;
  margin: 0 auto 22px;
  display: grid;
  place-items: center;
  border-radius: 50%;
  font-family: 'Space Grotesk', sans-serif;
  font-weight: 700;
  font-size: 1.02rem;
  letter-spacing: .04em;
  color: var(--cyan);
  background: rgba(9,14,23,.92);
  border: 1px solid var(--border-strong);
  transition: transform .4s var(--ease), background .4s ease, color .4s ease, border-color .4s ease, box-shadow .4s ease;
}
.process-step:hover .step-number{
  background: var(--grad);
  color: #04121a;
  border-color: transparent;
  transform: scale(1.08) translateY(-3px);
  box-shadow: 0 16px 36px -12px rgba(34,211,238,.75);
}
.process-step h3{
  font-family: 'Space Grotesk', sans-serif;
  font-size: 1.05rem;
  font-weight: 700;
  letter-spacing: -.015em;
  margin-bottom: 8px;
}
.process-step p{
  font-size: .88rem;
  color: var(--muted);
  line-height: 1.65;
}

/* ============ 8. PROJECTS ============ */
.projects-head{
  max-width: 640px;
  margin-bottom: 52px;
}

.project-card{
  display: grid;
  grid-template-columns: .9fr 1.1fr;
  gap: 0;
  border-radius: 24px;
  border: 1px solid var(--border-strong);
  background: linear-gradient(150deg, rgba(255,255,255,.05), rgba(255,255,255,.012));
  overflow: hidden;
  transition: border-color .45s ease, box-shadow .45s ease, transform .45s var(--ease);
}
.project-card:hover{
  transform: translateY(-6px);
  border-color: rgba(34,211,238,.42);
  box-shadow: 0 36px 80px -40px rgba(34,211,238,.6);
}

.project-visual{
  position: relative;
  min-height: 280px;
  padding: 30px;
  display: flex;
  align-items: flex-start;
  background:
    radial-gradient(600px circle at 20% 10%, rgba(59,130,246,.22), transparent 60%),
    radial-gradient(500px circle at 80% 90%, rgba(52,211,153,.16), transparent 60%),
    #070c15;
  border-right: 1px solid var(--border);
  overflow: hidden;
}
.pv-grid{
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(255,255,255,.045) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,.045) 1px, transparent 1px);
  background-size: 34px 34px;
  -webkit-mask-image: radial-gradient(circle at 50% 50%, #000 10%, transparent 75%);
  mask-image: radial-gradient(circle at 50% 50%, #000 10%, transparent 75%);
  animation: gridShift 14s linear infinite;
}
@keyframes gridShift{
  to{ background-position: 34px 34px; }
}
.pv-tag{
  position: relative;
  z-index: 1;
  font-family: 'Space Grotesk', sans-serif;
  font-size: .74rem;
  font-weight: 700;
  letter-spacing: .22em;
  padding: 8px 15px;
  border-radius: 999px;
  border: 1px solid rgba(34,211,238,.35);
  background: rgba(34,211,238,.08);
  color: var(--cyan);
}

.project-info{
  padding: 38px 36px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 16px;
}
.project-top{
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 14px;
}
.project-info h3{
  font-family: 'Space Grotesk', sans-serif;
  font-size: clamp(1.4rem, 2.6vw, 1.85rem);
  font-weight: 700;
  letter-spacing: -.025em;
}
.status{
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 6px 14px;
  border-radius: 999px;
  font-size: .74rem;
  font-weight: 700;
  letter-spacing: .08em;
  text-transform: uppercase;
  color: var(--green);
  background: rgba(52,211,153,.09);
  border: 1px solid rgba(52,211,153,.26);
}
.project-info p{
  color: var(--muted);
  font-size: .97rem;
  max-width: 460px;
}

.progress{
  height: 6px;
  width: 100%;
  max-width: 340px;
  border-radius: 99px;
  background: rgba(255,255,255,.07);
  overflow: hidden;
  margin-top: 6px;
}
.progress span{
  display: block;
  position: relative;
  height: 100%;
  width: 62%;
  border-radius: 99px;
  background: var(--grad);
  overflow: hidden;
}
.progress span::after{
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,.55), transparent);
  transform: translateX(-100%);
  animation: sweep 2.4s ease-in-out infinite;
}
@keyframes sweep{
  to{ transform: translateX(100%); }
}
.progress-label{
  font-size: .76rem;
  letter-spacing: .12em;
  text-transform: uppercase;
  color: #6d7c92;
  font-weight: 600;
}

/* ============ 9. CONTACT + FORM ============ */
.cta-card{
  position: relative;
  text-align: center;
  padding: clamp(48px, 7vw, 84px) clamp(24px, 5vw, 64px);
  border-radius: 28px;
  border: 1px solid var(--border-strong);
  background:
    radial-gradient(700px circle at 50% 0%, rgba(34,211,238,.16), transparent 65%),
    linear-gradient(165deg, rgba(255,255,255,.05), rgba(255,255,255,.012));
  overflow: hidden;
}
.cta-card::before{
  content: '';
  position: absolute;
  top: -1px; left: 50%;
  transform: translateX(-50%);
  width: 60%;
  height: 1px;
  background: linear-gradient(90deg, transparent, #22d3ee, #34d399, transparent);
  opacity: .8;
}
.cta-card .eyebrow{ justify-content: center; }
.cta-card .eyebrow::before{ display: none; }
.cta-card h2{ margin-bottom: 18px; }
.cta-card > p{
  color: var(--muted);
  max-width: 520px;
  margin: 0 auto 40px;
  font-size: 1.02rem;
}

.contact-form{
  max-width: 620px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 18px;
  text-align: left;
}
.form-row{
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 18px;
}
.form-group{
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.form-group label{
  font-size: .72rem;
  font-weight: 800;
  letter-spacing: .16em;
  text-transform: uppercase;
  color: #9aa8bd;
}
.form-group input,
.form-group textarea{
  width: 100%;
  padding: 14px 18px;
  border-radius: 14px;
  border: 1px solid var(--border-strong);
  background: rgba(255,255,255,.028);
  color: var(--text);
  font: inherit;
  font-size: .94rem;
  transition: border-color .25s ease, background .25s ease, box-shadow .25s ease;
  resize: vertical;
  min-height: 52px;
}
.form-group textarea{
  min-height: 130px;
  line-height: 1.6;
}
.form-group input::placeholder,
.form-group textarea::placeholder{
  color: #5a6779;
}
.form-group input:focus,
.form-group textarea:focus{
  outline: none;
  border-color: rgba(34,211,238,.55);
  background: rgba(34,211,238,.045);
  box-shadow: 0 0 0 4px rgba(34,211,238,.08);
}
.contact-form .btn{
  align-self: center;
  margin-top: 8px;
  min-width: 200px;
}

/* ============ 10. FOOTER ============ */
.footer{
  border-top: 1px solid var(--border);
  background: linear-gradient(180deg, rgba(255,255,255,.018), transparent);
  padding: 56px 0 30px;
  position: relative;
}
.footer::before{
  content: '';
  position: absolute;
  top: -1px; left: 50%;
  transform: translateX(-50%);
  width: 40%;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(34,211,238,.55), transparent);
  pointer-events: none;
}
.footer-inner{
  display: flex;
  flex-wrap: wrap;
  gap: 32px;
  align-items: flex-start;
  justify-content: space-between;
  padding-bottom: 34px;
  border-bottom: 1px solid var(--border);
}
.footer-brand p{
  margin-top: 12px;
  font-size: .88rem;
  color: var(--muted);
}
.footer-nav{
  display: flex;
  flex-wrap: wrap;
  gap: 10px 28px;
}
.footer-nav a{
  font-size: .9rem;
  color: var(--muted);
  transition: color .25s ease;
}
.footer-nav a:hover{ color: var(--cyan); }
.footer-bottom{
  padding-top: 24px;
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  align-items: center;
  justify-content: space-between;
}
.footer-bottom p,
.footer-bottom span{
  font-size: .82rem;
  color: #5f6d81;
}

/* ============ 11. BACK TO TOP + TOAST ============ */
.back-to-top{
  position: fixed;
  bottom: 26px;
  right: 26px;
  width: 48px; height: 48px;
  border-radius: 50%;
  display: grid;
  place-items: center;
  background: var(--grad);
  color: #04121a;
  box-shadow: 0 14px 34px -12px rgba(34,211,238,.85);
  z-index: 90;
  opacity: 0;
  visibility: hidden;
  transform: translateY(18px) scale(.9);
  transition: opacity .35s ease, visibility .35s ease, transform .4s var(--ease), box-shadow .35s ease;
}
.back-to-top.show{
  opacity: 1;
  visibility: visible;
  transform: translateY(0) scale(1);
}
.back-to-top:hover{
  transform: translateY(-4px) scale(1.05);
  box-shadow: 0 22px 46px -12px rgba(34,211,238,.95);
}
.back-to-top:active{ transform: translateY(-1px) scale(1); }
.back-to-top svg{ width: 20px; height: 20px; }

.toast{
  position: fixed;
  left: 50%;
  bottom: 34px;
  transform: translate(-50%, 130%);
  z-index: 200;
  display: inline-flex;
  align-items: center;
  gap: 11px;
  padding: 13px 24px;
  border-radius: 999px;
  border: 1px solid rgba(52,211,153,.35);
  background: rgba(8,14,22,.94);
  -webkit-backdrop-filter: blur(14px);
  backdrop-filter: blur(14px);
  font-size: .88rem;
  font-weight: 600;
  color: var(--text);
  box-shadow: 0 24px 50px -22px rgba(0,0,0,.95);
  transition: transform .5s var(--ease), opacity .4s ease;
  opacity: 0;
  pointer-events: none;
  max-width: calc(100vw - 40px);
}
.toast.show{ transform: translate(-50%, 0); opacity: 1; }

/* ============ 12. UTILITIES & ANIMATION ============ */
.reveal{
  opacity: 0;
  transform: translateY(28px);
  transition: opacity .8s var(--ease), transform .8s var(--ease);
}
.reveal.visible{ opacity: 1; transform: none; }

.grid-3 > .reveal:nth-child(2){ transition-delay: .12s; }
.grid-3 > .reveal:nth-child(3){ transition-delay: .24s; }

.process-grid > .reveal:nth-child(2){ transition-delay: .1s; }
.process-grid > .reveal:nth-child(3){ transition-delay: .2s; }
.process-grid > .reveal:nth-child(4){ transition-delay: .3s; }

.hero-copy .reveal:nth-child(1){ transition-delay: .05s; }
.hero-copy .reveal:nth-child(2){ transition-delay: .13s; }
.hero-copy .reveal:nth-child(3){ transition-delay: .21s; }
.hero-copy .reveal:nth-child(4){ transition-delay: .29s; }
.hero-copy .reveal:nth-child(5){ transition-delay: .37s; }

/* ============ RESPONSIVE ============ */
@media (max-width: 1024px){
  .hero-grid{ gap: 44px; }
  .nav-links{ gap: 24px; }
}

@media (max-width: 900px){
  .nav-links,
  .nav-cta{ display: none; }
  .hamburger{ display: block; }
  .mobile-menu{ display: flex; }

  .hero{ padding: calc(var(--nav-h) + 54px) 0 76px; }
  .hero-grid{
    grid-template-columns: 1fr;
    gap: 54px;
  }
  .hero-copy{ text-align: center; }
  .lead{ margin-left: auto; margin-right: auto; }
  .hero-actions{ justify-content: center; }
  .hero-stats{ justify-content: center; text-align: center; }
  .hero-visual{ order: 2; min-height: 320px; }

  .about-head{
    grid-template-columns: 1fr;
    gap: 20px;
  }

  .grid-3{ grid-template-columns: 1fr; }

  .process-grid{
    grid-template-columns: repeat(2, 1fr);
    gap: 38px 22px;
  }
  .process-grid::before{ display: none; }

  .project-card{ grid-template-columns: 1fr; }
  .project-visual{
    min-height: 190px;
    border-right: none;
    border-bottom: 1px solid var(--border);
  }
  .project-info{ padding: 32px 26px; }

  .toast{ bottom: 92px; }
}

@media (max-width: 640px){
  .container{ padding: 0 18px; }

  h1{ font-size: clamp(2rem, 9vw, 2.7rem); }
  .lead{ font-size: .96rem; }

  .hero-actions{
    flex-direction: column;
    align-items: stretch;
  }
  .hero-actions .btn{ width: 100%; }

  .hero-stats{
    gap: 18px 28px;
    justify-content: space-between;
  }
  .stat-num{ font-size: 1.4rem; }

  .float-card{ display: none; }

  .mock-body{
    grid-template-columns: 42px 1fr;
    gap: 12px;
    padding: 14px;
  }
  .chart{ height: 108px; gap: 6px; padding: 10px; }
  .mock-tiles{ grid-template-columns: 1fr; }

  .card{ padding: 26px 22px; }
  .team-card{ padding: 32px 22px 28px; }

  .process-grid{ grid-template-columns: 1fr; gap: 30px; }

  .form-row{ grid-template-columns: 1fr; gap: 18px; }
  .contact-form .btn{ width: 100%; }

  .back-to-top{
    width: 44px; height: 44px;
    bottom: 18px; right: 18px;
  }

  .footer-inner{
    flex-direction: column;
    gap: 24px;
  }
  .footer-nav{ gap: 10px 20px; }
  .footer-bottom{ flex-direction: column; align-items: flex-start; }
}

@media (max-width: 400px){
  .hero-stats{
    flex-direction: column;
    gap: 14px;
    align-items: center;
  }
  .badge{ font-size: .7rem; padding: 7px 14px 7px 11px; }
}

@media (prefers-reduced-motion: reduce){
  *,
  *::before,
  *::after{
    animation-duration: .001ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: .001ms !important;
    scroll-behavior: auto !important;
  }
  .reveal{ opacity: 1; transform: none; }
}
</style>
</head>
<body>

<!-- ============ SCROLL PROGRESS ============ -->
<div class="scroll-progress" aria-hidden="true"><span id="scrollBar"></span></div>

<!-- ============ BACKGROUND DECOR ============ -->
<div class="bg-decor" aria-hidden="true">
  <div class="orb orb-1"></div>
  <div class="orb orb-2"></div>
  <div class="orb orb-3"></div>
  <div class="grid-overlay"></div>
</div>

<!-- ============ NAVBAR ============ -->
<header class="nav" id="nav">
  <div class="container nav-inner">
    <a href="#home" class="logo" aria-label="NexaDev Home">
      <span class="logo-mark">
        <svg width="17" height="17" viewBox="0 0 24 24" fill="none" aria-hidden="true">
          <path d="M5 19V5l14 14V5" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </span>
      Nexa<span class="logo-accent">Dev</span>
    </a>

    <nav class="nav-links" id="navLinks" aria-label="Navigasi utama">
      <a href="#home" class="active">Home</a>
      <a href="#about">About</a>
      <a href="#team">Team</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
    </nav>

    <a href="#contact" class="btn btn-primary nav-cta">
      Let's Talk
      <svg width="15" height="15" viewBox="0 0 24 24" fill="none" aria-hidden="true">
        <path d="M5 12h14M13 6l6 6-6 6" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </a>

    <button class="hamburger" id="hamburger" aria-label="Buka menu" aria-expanded="false" aria-controls="mobileMenu">
      <span></span><span></span><span></span>
    </button>
  </div>
</header>

<!-- ============ MOBILE MENU ============ -->
<nav class="mobile-menu" id="mobileMenu" aria-label="Navigasi mobile">
  <a href="#home" class="active">Home</a>
  <a href="#about">About</a>
  <a href="#team">Team</a>
  <a href="#projects">Projects</a>
  <a href="#contact">Contact</a>
  <a href="#contact" class="btn btn-primary">Let's Talk</a>
</nav>

<main>

  <!-- ============ HERO ============ -->
  <section class="hero" id="home">
    <div class="container hero-grid">

      <div class="hero-copy">
        <span class="badge reveal">
          <span class="pulse-dot"></span>
          Software Development Team
        </span>

        <h1 class="reveal">
          We Create<br />
          <span class="grad-text">Digital Solutions.</span>
        </h1>

        <p class="lead reveal">
          NexaDev is a collaborative software development team focused on creating
          modern and useful digital solutions. Kami merancang, membangun, dan
          mengembangkan ide menjadi produk digital yang rapi, fungsional, dan berdampak.
        </p>

        <div class="hero-actions reveal">
          <a href="#projects" class="btn btn-primary">
            Explore Projects
            <svg width="15" height="15" viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="M5 12h14M13 6l6 6-6 6" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </a>
          <a href="#about" class="btn btn-ghost">About NexaDev</a>
        </div>

        <div class="hero-stats reveal" id="heroStats">
          <div class="stat">
            <span class="stat-num" data-count="3" data-pad="2">00</span>
            <span class="stat-label">Team Members</span>
          </div>
          <div class="stat">
            <span class="stat-num">Digital</span>
            <span class="stat-label">Solutions</span>
          </div>
          <div class="stat">
            <span class="stat-num">∞</span>
            <span class="stat-label">Ideas to Build</span>
          </div>
        </div>
      </div>

      <div class="hero-visual reveal">
        <div class="mockup" aria-hidden="true">
          <div class="mock-top">
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>
            <div class="mock-url"><span></span></div>
          </div>

          <div class="mock-body">
            <aside class="mock-side">
              <span class="side-item active"></span>
              <span class="side-item"></span>
              <span class="side-item"></span>
              <span class="side-item"></span>
            </aside>

            <div class="mock-main">
              <div class="mock-head">
                <div class="mock-title"></div>
                <div class="mock-pill"></div>
              </div>

              <div class="chart">
                <span style="--h:38%"></span>
                <span style="--h:62%"></span>
                <span style="--h:48%"></span>
                <span style="--h:84%"></span>
                <span style="--h:56%"></span>
                <span style="--h:96%"></span>
                <span style="--h:70%"></span>
              </div>

              <div class="mock-tiles">
                <div class="tile"><i></i><b></b></div>
                <div class="tile"><i></i><b></b></div>
              </div>
            </div>
          </div>
        </div>

        <div class="float-card fc-1">
          <span class="pulse-dot"></span>
          In Development
        </div>
        <div class="float-card fc-2">
          <span class="fc-num">∞</span>
          Ideas
        </div>
      </div>

    </div>
  </section>

  <!-- ============ ABOUT ============ -->
  <section class="section" id="about">
    <div class="container">

      <div class="about-head">
        <div class="reveal">
          <span class="eyebrow">About</span>
          <h2>About <span class="grad-text">NexaDev</span></h2>
        </div>
        <p class="section-sub reveal">
          NexaDev adalah sebuah kelompok yang bekerja sama dalam merancang dan
          mengembangkan solusi digital. Setiap ide kami olah menjadi produk yang
          terstruktur, mudah digunakan, dan relevan dengan kebutuhan pengguna.
        </p>
      </div>

      <div class="grid-3">

        <article class="card reveal">
          <div class="card-icon">
            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <rect x="3" y="4" width="18" height="16" rx="3" stroke="currentColor" stroke-width="1.8"/>
              <path d="M3 9h18" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
              <circle cx="6.5" cy="6.5" r=".9" fill="currentColor"/>
              <circle cx="9.5" cy="6.5" r=".9" fill="currentColor"/>
            </svg>
          </div>
          <h3>Web Development</h3>
          <p>Membangun pengalaman website yang modern, responsive, dan mudah digunakan.</p>
        </article>

        <article class="card reveal">
          <div class="card-icon">
            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="M9 6 4 12l5 6" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>
              <path d="m15 6 5 6-5 6" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <h3>Software Development</h3>
          <p>Mengembangkan solusi digital berdasarkan kebutuhan dan permasalahan pengguna.</p>
        </article>

        <article class="card reveal">
          <div class="card-icon">
            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="M12 3 3.5 8 12 13l8.5-5L12 3Z" stroke="currentColor" stroke-width="1.8" stroke-linejoin="round"/>
              <path d="M5 12.4 3.5 13.3 12 18.3l8.5-5-1.5-.9" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>
              <path d="M5 16.6 3.5 17.5 12 22.5l8.5-5-1.5-.9" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <h3>Learning &amp; Innovation</h3>
          <p>Terus belajar, mengeksplorasi ide baru, dan meningkatkan kemampuan dalam pengembangan software.</p>
        </article>

      </div>
    </div>
  </section>

  <!-- ============ TEAM ============ -->
  <section class="section" id="team">
    <div class="container">

      <div class="team-head reveal">
        <span class="eyebrow">Our People</span>
        <h2>Meet Our <span class="grad-text">Team</span></h2>
        <p class="section-sub">
          Tiga orang, satu tujuan: membangun solusi digital yang bermanfaat.
          Kami bekerja kolaboratif dalam setiap tahap perancangan dan pengembangan.
        </p>
      </div>

      <div class="grid-3">

        <article class="card team-card reveal">
          <div class="avatar">MH</div>
          <h3>Misbah Huddin</h3>
          <span class="team-role">Software Development / Web Development</span>
          <p class="bio">Fokus pada perancangan dan pengembangan solusi digital yang terstruktur.</p>
          <div class="team-line"></div>
        </article>

        <article class="card team-card reveal">
          <div class="avatar">MZ</div>
          <h3>Muhammad Zikral Bunaiya</h3>
          <span class="team-role">Software Development / Web Development</span>
          <p class="bio">Berperan dalam membangun pengalaman digital yang rapi dan mudah digunakan.</p>
          <div class="team-line"></div>
        </article>

        <article class="card team-card reveal">
          <div class="avatar">MA</div>
          <h3>Muhammad Amal Maulana</h3>
          <span class="team-role">Software Development / Web Development</span>
          <p class="bio">Berkontribusi pada pengembangan ide dan penyempurnaan setiap solusi.</p>
          <div class="team-line"></div>
        </article>

      </div>
    </div>
  </section>

  <!-- ============ PROCESS (HOW WE WORK) ============ -->
  <section class="section" id="process">
    <div class="container">

      <div class="process-head reveal">
        <span class="eyebrow">Process</span>
        <h2>How We <span class="grad-text">Work</span></h2>
        <p class="section-sub">
          Setiap solusi yang kami bangun melewati tahapan yang terstruktur —
          dari memahami ide hingga siap digunakan.
        </p>
      </div>

      <div class="process-grid">

        <article class="process-step reveal">
          <div class="step-number">01</div>
          <h3>Discover</h3>
          <p>Memahami ide, kebutuhan, dan tujuan dari setiap proyek yang akan dibangun.</p>
        </article>

        <article class="process-step reveal">
          <div class="step-number">02</div>
          <h3>Design</h3>
          <p>Merancang struktur dan tampilan agar solusi mudah dipahami dan digunakan.</p>
        </article>

        <article class="process-step reveal">
          <div class="step-number">03</div>
          <h3>Develop</h3>
          <p>Membangun solusi digital secara bertahap, terukur, dan berfokus pada kualitas.</p>
        </article>

        <article class="process-step reveal">
          <div class="step-number">04</div>
          <h3>Deliver</h3>
          <p>Menyempurnakan, menguji, dan menyerahkan hasil akhir yang siap digunakan.</p>
        </article>

      </div>
    </div>
  </section>

  <!-- ============ PROJECTS ============ -->
  <section class="section" id="projects">
    <div class="container">

      <div class="projects-head reveal">
        <span class="eyebrow">Projects</span>
        <h2>What We're <span class="grad-text">Building.</span></h2>
        <p class="section-sub" style="margin-top:14px">
          NexaDev sedang mengembangkan berbagai ide dan solusi digital.
          Setiap produk kami rancang dengan pendekatan yang matang sebelum dipublikasikan.
        </p>
      </div>

      <article class="project-card reveal">
        <div class="project-visual">
          <div class="pv-grid"></div>
          <span class="pv-tag">PROJECT 01</span>
        </div>

        <div class="project-info">
          <div class="project-top">
            <h3>Coming Soon</h3>
            <span class="status"><span class="pulse-dot"></span>In Development</span>
          </div>

          <p>Our next digital solution is currently in development.</p>

          <div class="progress"><span></span></div>
          <span class="progress-label">Progress · In Development</span>
        </div>
      </article>

    </div>
  </section>

  <!-- ============ CONTACT ============ -->
  <section class="section" id="contact">
    <div class="container">
      <div class="cta-card reveal">
        <span class="eyebrow">Contact</span>
        <h2>Let's build something <span class="grad-text">great.</span></h2>
        <p>Have an idea or want to collaborate? Let's create something meaningful together.</p>

        <form class="contact-form" id="contactForm" novalidate>
          <div class="form-row">
            <div class="form-group">
              <label for="name">Nama</label>
              <input type="text" id="name" name="name" placeholder="Nama lengkap" autocomplete="name" required />
            </div>
            <div class="form-group">
              <label for="email">Email</label>
              <input type="email" id="email" name="email" placeholder="nama@email.com" autocomplete="email" required />
            </div>
          </div>

          <div class="form-group">
            <label for="message">Pesan</label>
            <textarea id="message" name="message" rows="4" placeholder="Ceritakan ide atau kebutuhan Anda..." required></textarea>
          </div>

          <button type="submit" class="btn btn-primary">
            Kirim Pesan
            <svg width="15" height="15" viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="M5 12h14M13 6l6 6-6 6" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
        </form>
      </div>
    </div>
  </section>

</main>

<!-- ============ FOOTER ============ -->
<footer class="footer">
  <div class="container footer-inner">
    <div class="footer-brand">
      <a href="#home" class="logo">
        <span class="logo-mark">
          <svg width="17" height="17" viewBox="0 0 24 24" fill="none" aria-hidden="true">
            <path d="M5 19V5l14 14V5" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </span>
        Nexa<span class="logo-accent">Dev</span>
      </a>
      <p>Software Development Team</p>
    </div>

    <nav class="footer-nav" aria-label="Navigasi footer">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#team">Team</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
    </nav>
  </div>

  <div class="container footer-bottom">
    <p>© 2026 NexaDev. All rights reserved.</p>
    <span>Built with passion by NexaDev Team.</span>
  </div>
</footer>

<!-- ============ BACK TO TOP ============ -->
<button class="back-to-top" id="backToTop" aria-label="Kembali ke atas">
  <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
    <path d="M12 19V5M6 11l6-6 6 6" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"/>
  </svg>
</button>

<!-- ============ TOAST ============ -->
<div class="toast" id="toast" role="status" aria-live="polite">
  <span class="pulse-dot"></span>
  <span id="toastMsg">Terima kasih! NexaDev siap berkolaborasi dengan Anda.</span>
</div>

<script>
/* =========================================================
   NEXADEV — INTERACTIONS
   1. Navbar scroll state + scroll progress
   2. Mobile navigation
   3. Smooth scrolling
   4. Active nav on scroll
   5. Reveal animation on scroll
   6. Counter animation
   7. Back to top
   8. Button ripple + toast
   9. Contact form
   10. Card spotlight
   ========================================================= */
(function () {
  'use strict';

  var nav         = document.getElementById('nav');
  var hamburger   = document.getElementById('hamburger');
  var mobileMenu  = document.getElementById('mobileMenu');
  var navLinks    = document.querySelectorAll('.nav-links a');
  var mobLinks    = mobileMenu.querySelectorAll('a');
  var allLinks    = document.querySelectorAll('a[href^="#"]');
  var sections    = document.querySelectorAll('main section[id]');
  var toast       = document.getElementById('toast');
  var toastMsg    = document.getElementById('toastMsg');
  var scrollBar   = document.getElementById('scrollBar');
  var backToTop   = document.getElementById('backToTop');
  var heroStats   = document.getElementById('heroStats');
  var contactForm = document.getElementById('contactForm');
  var toastTimer  = null;
  var counterDone = false;

  /* ---------- 2. Mobile navigation ---------- */
  function closeMenu() {
    hamburger.classList.remove('open');
    mobileMenu.classList.remove('open');
    hamburger.setAttribute('aria-expanded', 'false');
    hamburger.setAttribute('aria-label', 'Buka menu');
  }

  function toggleMenu() {
    var isOpen = mobileMenu.classList.toggle('open');
    hamburger.classList.toggle('open', isOpen);
    hamburger.setAttribute('aria-expanded', String(isOpen));
    hamburger.setAttribute('aria-label', isOpen ? 'Tutup menu' : 'Buka menu');
  }

  hamburger.addEventListener('click', toggleMenu);

  document.addEventListener('click', function (e) {
    if (!mobileMenu.classList.contains('open')) return;
    if (mobileMenu.contains(e.target) || hamburger.contains(e.target)) return;
    closeMenu();
  });

  document.addEventListener('keydown', function (e) {
    if (e.key === 'Escape') closeMenu();
  });

  window.addEventListener('resize', function () {
    if (window.innerWidth > 900) closeMenu();
  });

  /* ---------- 3. Smooth scrolling ---------- */
  allLinks.forEach(function (link) {
    link.addEventListener('click', function (e) {
      var hash = link.getAttribute('href');
      if (!hash || hash === '#' || hash.length < 2) return;

      var target = document.querySelector(hash);
      if (!target) return;

      e.preventDefault();
      closeMenu();

      var offset = window.innerWidth > 900 ? 84 : 74;
      var top = target.getBoundingClientRect().top + window.pageYOffset - offset;

      window.scrollTo({
        top: Math.max(top, 0),
        behavior: 'smooth'
      });

      if (history.replaceState) {
        history.replaceState(null, '', hash);
      }
    });
  });

  /* ---------- 4. Active nav on scroll ---------- */
  function updateActive() {
    var scrollPos = window.pageYOffset + 140;
    var currentId = 'home';

    sections.forEach(function (section) {
      if (section.offsetTop <= scrollPos) {
        currentId = section.id;
      }
    });

    navLinks.forEach(function (link) {
      link.classList.toggle('active', link.getAttribute('href') === '#' + currentId);
    });
    mobLinks.forEach(function (link) {
      link.classList.toggle('active', link.getAttribute('href') === '#' + currentId);
    });
  }

  /* ---------- 1. Navbar scroll state + scroll progress ---------- */
  var ticking = false;

  function onScroll() {
    if (ticking) return;
    ticking = true;

    window.requestAnimationFrame(function () {
      var y = window.pageYOffset;
      var docH = document.documentElement.scrollHeight - window.innerHeight;
      var pct = docH > 0 ? (y / docH) * 100 : 0;

      nav.classList.toggle('scrolled', y > 24);
      scrollBar.style.width = pct + '%';
      backToTop.classList.toggle('show', y > 480);

      updateActive();
      ticking = false;
    });
  }

  window.addEventListener('scroll', onScroll, { passive: true });

  /* ---------- 5. Reveal animation on scroll ---------- */
  var revealEls = document.querySelectorAll('.reveal');

  if ('IntersectionObserver' in window) {
    var revealObserver = new IntersectionObserver(function (entries) {
      entries.forEach(function (entry) {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          revealObserver.unobserve(entry.target);
        }
      });
    }, {
      threshold: 0.12,
      rootMargin: '0px 0px -60px 0px'
    });

    revealEls.forEach(function (el) { revealObserver.observe(el); });
  } else {
    revealEls.forEach(function (el) { el.classList.add('visible'); });
  }

  /* ---------- 6. Counter animation ---------- */
  function runCounters() {
    if (counterDone) return;
    counterDone = true;

    document.querySelectorAll('[data-count]').forEach(function (el) {
      var target = parseInt(el.getAttribute('data-count'), 10) || 0;
      var pad = parseInt(el.getAttribute('data-pad'), 10) || 0;
      var duration = 1400;
      var start = null;

      function step(ts) {
        if (start === null) start = ts;
        var p = Math.min((ts - start) / duration, 1);
        var eased = 1 - Math.pow(1 - p, 3);
        var val = Math.round(eased * target);
        var out = String(val);
        while (out.length < pad) out = '0' + out;
        el.textContent = out;
        if (p < 1) window.requestAnimationFrame(step);
        else {
          var finalOut = String(target);
          while (finalOut.length < pad) finalOut = '0' + finalOut;
          el.textContent = finalOut;
        }
      }
      window.requestAnimationFrame(step);
    });
  }

  if (heroStats && 'IntersectionObserver' in window) {
    var counterObserver = new IntersectionObserver(function (entries) {
      entries.forEach(function (entry) {
        if (entry.isIntersecting) {
          runCounters();
          counterObserver.disconnect();
        }
      });
    }, { threshold: 0.4 });
    counterObserver.observe(heroStats);
  } else {
    runCounters();
  }

  /* ---------- 7. Back to top ---------- */
  backToTop.addEventListener('click', function () {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  });

  /* ---------- 8. Button ripple + toast ---------- */
  function showToast(msg) {
    if (msg) toastMsg.textContent = msg;
    toast.classList.add('show');
    window.clearTimeout(toastTimer);
    toastTimer = window.setTimeout(function () {
      toast.classList.remove('show');
    }, 3200);
  }

  document.querySelectorAll('.btn').forEach(function (btn) {
    btn.addEventListener('click', function (e) {
      var rect = btn.getBoundingClientRect();
      var size = Math.max(rect.width, rect.height);
      var ripple = document.createElement('span');

      ripple.className = 'ripple';
      ripple.style.width = size + 'px';
      ripple.style.height = size + 'px';
      ripple.style.left = (e.clientX - rect.left - size / 2) + 'px';
      ripple.style.top = (e.clientY - rect.top - size / 2) + 'px';

      btn.appendChild(ripple);
      window.setTimeout(function () { ripple.remove(); }, 680);
    });
  });

  document.querySelectorAll('[data-toast]').forEach(function (el) {
    el.addEventListener('click', function () {
      showToast('Terima kasih! NexaDev siap berkolaborasi dengan Anda.');
    });
  });

  /* ---------- 9. Contact form ---------- */
  if (contactForm) {
    contactForm.addEventListener('submit', function (e) {
      e.preventDefault();

      var name    = contactForm.querySelector('#name').value.trim();
      var email   = contactForm.querySelector('#email').value.trim();
      var message = contactForm.querySelector('#message').value.trim();

      if (!name || !email || !message) {
        showToast('Mohon lengkapi semua field terlebih dahulu.');
        return;
      }

      var emailOk = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
      if (!emailOk) {
        showToast('Format email belum benar. Mohon dicek kembali.');
        return;
      }

      showToast('Terima kasih, ' + name + '! Pesan Anda sudah kami terima.');
      contactForm.reset();
    });
  }

  /* ---------- 10. Card spotlight ---------- */
  if (window.matchMedia('(hover: hover) and (pointer: fine)').matches) {
    document.querySelectorAll('.card').forEach(function (card) {
      card.addEventListener('mousemove', function (e) {
        var rect = card.getBoundingClientRect();
        card.style.setProperty('--mx', (e.clientX - rect.left) + 'px');
        card.style.setProperty('--my', (e.clientY - rect.top) + 'px');
      });
    });
  }

  /* ---------- Init ---------- */
  onScroll();
  updateActive();

})();
</script>

</body>
</html>
