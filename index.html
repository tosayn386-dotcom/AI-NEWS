#!/usr/bin/env python
# =====================================================
# AI NEWS – PRODUCT STYLE DIGEST
# Theme: Lunar New Year hero (reference style)
# Fixes requested:
# 1) Quick View summary popup works for ALL cards (robust dataset click)
# 2) Scroll-to-top arrow appears on scroll and works
# 3) Contact signature moved BELOW contact text
# 4) Read More opens a legend popover that is NOT clipped
# =====================================================

import feedparser
import requests
from bs4 import BeautifulSoup
from pathlib import Path
import datetime
import html as html_lib

MAX_PER_SOURCE = 8
TIMEOUT = 8
OUTPUT = Path('index.html')
TODAY = datetime.date.today().strftime('%d-%m-%Y')

SOURCES = {
    'OpenAI': 'https://openai.com/blog/rss.xml',
    'Google AI': 'https://blog.google/technology/ai/rss/',
    'Meta AI': 'https://ai.facebook.com/blog/rss/',
    'HuggingFace': 'https://huggingface.co/blog/feed.xml',
    'Towards Data Science': 'https://towardsdatascience.com/feed',
    'Analytics Vidhya': 'https://www.analyticsvidhya.com/feed/'
}


def clean(text: str) -> str:
    return html_lib.escape((text or '').replace('\n', ' ').strip())


def attr_escape(text: str) -> str:
    """Escape for putting into HTML attributes."""
    # escape &,<,>," and '
    return html_lib.escape(text or '', quote=True)


def get_og_image(url: str):
    try:
        r = requests.get(url, timeout=TIMEOUT, headers={'User-Agent': 'Mozilla/5.0'})
        soup = BeautifulSoup(r.text, 'html.parser')
        og = soup.find('meta', property='og:image')
        if og and og.get('content'):
            return og['content']
    except Exception:
        pass
    return None


with_image = []
no_image = []

for source, rss in SOURCES.items():
    feed = feedparser.parse(rss)
    for e in feed.entries[:MAX_PER_SOURCE]:
        img = None
        if 'media_content' in e:
            try:
                img = e.media_content[0].get('url')
            except Exception:
                img = None

        link = getattr(e, 'link', '')
        if not img and link:
            img = get_og_image(link)

        item = {
            'source': source,
            'title': clean(getattr(e, 'title', '')),
            'summary': clean(e.get('summary', '')),
            'link': link,
            'image': img
        }

        if img:
            with_image.append(item)
        else:
            no_image.append(item)


HEAD = """<!DOCTYPE html>
<html lang=\"en\">
<head>
<meta charset=\"utf-8\">
<title>AI NEWS – __TODAY__</title>
<meta name=\"viewport\" content=\"width=device-width, initial-scale=1\">

<link rel=\"icon\" type=\"image/svg+xml\" href=\"data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%2064%2064'%3E%3Ctext%20x='2'%20y='52'%20font-size='52'%3E%F0%9F%A4%96%3C/text%3E%3C/svg%3E\">

<style>
:root{
  --wine:#5b0a2b;
  --wine2:#3b071e;
  --gold:#f6c453;
  --cream:#ffe9d6;
  --text:#f7e7dd;
  --muted:rgba(255,233,214,.80);
  --card:rgba(255,255,255,.06);
}
*{box-sizing:border-box}
html,body{height:100%}
html{
  background:
    radial-gradient(1200px 600px at 75% 30%, rgba(246,196,83,.12), transparent 55%),
    radial-gradient(900px 500px at 20% 15%, rgba(255,122,165,.12), transparent 58%),
    linear-gradient(180deg, var(--wine), #2b0818);
}
body{
  margin:0;
  min-height:100vh;
  font-family:Inter, Segoe UI, system-ui, -apple-system, sans-serif;
  color:var(--text);
  background:transparent; /* prevents horizontal cut */
  overflow-x:hidden;
}
a{color:inherit;text-decoration:none}
.container{max-width:1200px;margin:0 auto;padding:0 22px}

.topbar{position:relative;z-index:5;padding:18px 0 10px}
.nav{display:flex;align-items:center;justify-content:space-between;gap:16px}
.brand{display:flex;align-items:center;gap:10px}
.brand-badge{
  width:34px;height:34px;border-radius:12px;display:grid;place-items:center;
  background: radial-gradient(circle at 30% 30%, rgba(246,196,83,.35), rgba(255,122,165,.10));
  border:1px solid rgba(255,255,255,.18);
  box-shadow:0 12px 30px rgba(0,0,0,.35);
}
.brand-name{font-weight:1000;letter-spacing:.6px}
.menu{display:flex;gap:22px;align-items:center;opacity:.95;font-size:12px;text-transform:uppercase;letter-spacing:.9px}
.menu a{padding:10px 10px;border-radius:999px;border:1px solid transparent}
.menu a:hover{border-color:rgba(255,255,255,.20);background:rgba(255,255,255,.06)}
.right-tools{display:flex;align-items:center;gap:12px}
#google_translate_element{min-width:120px;transform:scale(.92);transform-origin:right center}

.hero{position:relative;padding:28px 0 36px}
.hero-wrap{
  position:relative;border-radius:26px;overflow:hidden;
  background:
    radial-gradient(1200px 600px at 75% 45%, rgba(255,122,165,.10), transparent 60%),
    radial-gradient(900px 500px at 25% 20%, rgba(246,196,83,.14), transparent 58%),
    linear-gradient(135deg, #6b0b33, var(--wine2));
  border:1px solid rgba(255,255,255,.10);
  box-shadow: 0 28px 80px rgba(0,0,0,.55);
}
.hero-wrap::before{
  content:"";
  position:absolute;inset:0;
  background:
    radial-gradient(40px 22px at 8% 18%, rgba(255,255,255,.07), transparent 70%),
    radial-gradient(60px 30px at 18% 22%, rgba(255,255,255,.06), transparent 72%),
    radial-gradient(52px 26px at 32% 14%, rgba(255,255,255,.05), transparent 72%),
    radial-gradient(62px 30px at 86% 24%, rgba(255,255,255,.05), transparent 74%),
    radial-gradient(46px 22px at 74% 18%, rgba(255,255,255,.06), transparent 74%),
    radial-gradient(66px 32px at 90% 44%, rgba(255,255,255,.05), transparent 74%),
    linear-gradient(90deg, rgba(255,255,255,.03), transparent 30%, rgba(255,255,255,.02));
  opacity:.75;pointer-events:none;
}
.hero-inner{position:relative;display:grid;grid-template-columns: 1.05fr .95fr;gap:18px;padding:34px 34px 30px}
.hero-left{padding:10px 6px}
.kicker{display:inline-flex;align-items:center;gap:10px;padding:8px 12px;border-radius:999px;background:rgba(0,0,0,.18);border:1px solid rgba(255,255,255,.16);font-size:12px;letter-spacing:.8px;text-transform:uppercase;color:rgba(255,233,214,.92)}
.kicker .dot{width:8px;height:8px;border-radius:999px;background:var(--gold);box-shadow:0 0 0 6px rgba(246,196,83,.18)}
.hero-title{margin:18px 0 10px;font-size:54px;line-height:.95;font-weight:1000;text-transform:uppercase;letter-spacing:1px}
.hero-sub{margin:0 0 14px;font-size:22px;color:rgba(255,233,214,.92)}
.hero-desc{margin:0;max-width:520px;color:var(--muted);font-size:14px;line-height:1.7}
.hero-actions{position:relative;display:flex;gap:12px;margin-top:18px;align-items:center;flex-wrap:wrap}
.btn{display:inline-flex;align-items:center;justify-content:center;gap:10px;height:42px;padding:0 16px;border-radius:999px;border:1px solid rgba(255,255,255,.18);background:rgba(0,0,0,.18);cursor:pointer;font-weight:900}
.btn.primary{background: linear-gradient(180deg, rgba(246,196,83,.95), rgba(246,196,83,.70));color:#2b0818;border-color:rgba(0,0,0,.12);box-shadow:0 16px 30px rgba(246,196,83,.18)}
.btn.primary:hover{filter:brightness(1.03)}
.btn.ghost:hover{background:rgba(255,255,255,.08)}

/* Legend popover (fixed so it won't be clipped) */
#legendPopover{
  position:fixed;
  width:min(360px, calc(100vw - 40px));
  background:rgba(25,7,18,.86);
  backdrop-filter: blur(14px);
  border:1px solid rgba(255,255,255,.18);
  border-radius:16px;
  padding:14px 14px 12px;
  box-shadow:0 18px 70px rgba(0,0,0,.55);
  display:none;
  z-index:12000;
}
#legendPopover.show{display:block;animation:popMini .22s cubic-bezier(.2,1.4,.3,1) both}
@keyframes popMini{0%{opacity:0;transform:translateY(-6px) scale(.96)}100%{opacity:1;transform:translateY(0) scale(1)}}
#legendPopover h4{margin:0 0 8px;font-size:14px;letter-spacing:.2px}
#legendPopover p{margin:0;color:rgba(255,233,214,.88);line-height:1.6;font-size:13px}

.logo{font-weight:1000;letter-spacing:.5px;position:relative;display:inline-block;cursor:pointer}
.logo::after{content: attr(data-text);position:absolute;inset:0;background:linear-gradient(90deg, red,orange,yellow,green,cyan,blue,violet);background-size:300%;-webkit-background-clip:text;-webkit-text-fill-color:transparent;opacity:0;pointer-events:none}
.logo:hover::after{opacity:1;animation:rainbow 1.8s linear infinite}
@keyframes rainbow{0%{background-position:0%}100%{background-position:100%}}

.hero-art{position:relative;display:flex;align-items:center;justify-content:center;padding:10px 0 0}
.art-shell{width:100%;max-width:430px;aspect-ratio:1/1;border-radius:22px;background: radial-gradient(circle at 30% 30%, rgba(246,196,83,.18), rgba(0,0,0,0) 55%);border:1px solid rgba(255,255,255,.10);overflow:hidden}
#fireworks{position:absolute;left:0;right:0;top:0;height:160px;width:100%;pointer-events:none;opacity:.92}

.section{padding:26px 0 40px}
.section h3{margin:0 0 14px;font-size:18px;letter-spacing:.2px;color:rgba(255,233,214,.95)}
.grid-image{display:grid;grid-template-columns:repeat(auto-fill,minmax(360px,1fr));gap:20px}
.grid-text{display:grid;grid-template-columns:repeat(auto-fill,minmax(320px,1fr));gap:18px}
.image-card,.text-card{border-radius:18px;overflow:hidden;cursor:pointer;background:var(--card);border:1px solid rgba(255,255,255,.12);box-shadow:0 18px 50px rgba(0,0,0,.35);transition: transform .15s ease, box-shadow .15s ease}
.image-card:hover,.text-card:hover{transform: translateY(-2px);box-shadow:0 22px 62px rgba(0,0,0,.45)}
.image-card img{width:100%;height:210px;object-fit:cover;display:block}
.card-pad{padding:16px 16px 18px}
.source{font-size:12px;opacity:.78;margin-bottom:6px}
.card-pad h3{margin:0;font-size:18px;line-height:1.25}

#quickView{position:fixed;top:50%;right:22px;transform:translateY(-50%) scale(.92);width:420px;max-height:70vh;overflow:auto;background:rgba(25, 7, 18, .72);backdrop-filter: blur(14px);border:1px solid rgba(255,255,255,.18);border-radius:18px;padding:18px 18px 16px;display:none;opacity:0;box-shadow:0 18px 70px rgba(0,0,0,.62);z-index:9999;transition: opacity .22s ease, transform .28s cubic-bezier(.2,1.4,.3,1)}
#quickView.show{opacity:1;transform:translateY(-50%) scale(1);animation:qvPop .45s cubic-bezier(.2,1.4,.3,1) both}
@keyframes qvPop{0%{transform:translateY(-50%) scale(.86)}60%{transform:translateY(-50%) scale(1.03)}100%{transform:translateY(-50%) scale(1)}}
#quickView #qv-title{margin:0 0 10px;font-size:18px}
#quickView #qv-summary{margin:0 0 14px;color:rgba(255,233,214,.88);line-height:1.65;font-size:14px}
#quickView a{display:inline-flex;align-items:center;gap:8px;padding:10px 12px;border-radius:12px;border:1px solid rgba(255,255,255,.18);background:linear-gradient(90deg, rgba(246,196,83,.35), rgba(255,122,165,.14));font-weight:900}
#quickView::-webkit-scrollbar{width:10px}
#quickView::-webkit-scrollbar-thumb{background:rgba(255,255,255,.16);border-radius:20px}
#quickView::-webkit-scrollbar-track{background:rgba(255,255,255,.05)}

/* Scroll to top button */
#toTop{
  position:fixed;
  right:18px;
  bottom:18px;
  width:44px;
  height:44px;
  border-radius:999px;
  border:1px solid rgba(255,255,255,.18);
  background:rgba(25,7,18,.65);
  backdrop-filter: blur(12px);
  display:none;
  align-items:center;
  justify-content:center;
  cursor:pointer;
  box-shadow:0 18px 60px rgba(0,0,0,.55);
  z-index:13000;
}
#toTop.show{display:flex;animation:popMini .18s ease-out both}
#toTop span{font-size:18px;line-height:1;transform:translateY(-1px)}
#toTop:hover{background:rgba(255,255,255,.10)}

@media (max-width: 980px){.hero-inner{grid-template-columns:1fr}.hero-title{font-size:46px}#quickView{right:12px;width:min(420px, calc(100vw - 24px))}.menu{display:none}}
</style>

<script>
window.addEventListener('load', function () {
  var s = document.createElement('script');
  s.src = '//translate.google.com/translate_a/element.js?cb=googleTranslateElementInit';
  document.body.appendChild(s);
});
function googleTranslateElementInit() {
  new google.translate.TranslateElement({
    pageLanguage: 'en',
    includedLanguages: 'en,vi',
    autoDisplay: false
  }, 'google_translate_element');
}

function openQuickView(title, summary, link) {
  document.getElementById('qv-title').innerText = title;
  document.getElementById('qv-summary').innerText = summary;
  document.getElementById('qv-link').href = link;
  const qv = document.getElementById('quickView');
  qv.style.display = 'block';
  void qv.offsetHeight;
  qv.classList.add('show');
}
function closeQuickView() {
  const qv = document.getElementById('quickView');
  qv.classList.remove('show');
  setTimeout(() => { qv.style.display = 'none'; }, 240);
}

function showLegend() {
  const btn = document.getElementById('btnReadMore');
  const pop = document.getElementById('legendPopover');
  if (!btn || !pop) return;
  const r = btn.getBoundingClientRect();
  const gap = 10;
  // default: pop under the button
  let top = r.bottom + gap;
  let left = r.left;
  // keep inside viewport
  const maxLeft = window.innerWidth - pop.offsetWidth - 10;
  if (left > maxLeft) left = maxLeft;
  if (left < 10) left = 10;
  // if too low, show above
  if (top + pop.offsetHeight > window.innerHeight - 10) {
    top = r.top - pop.offsetHeight - gap;
  }
  pop.style.top = top + 'px';
  pop.style.left = left + 'px';
  pop.classList.add('show');
}
function hideLegend() {
  const pop = document.getElementById('legendPopover');
  if (pop) pop.classList.remove('show');
}
function toggleLegend(){
  const pop = document.getElementById('legendPopover');
  if (!pop) return;
  if (pop.classList.contains('show')) hideLegend();
  else showLegend();
}

// DOM ready: bind card clicks + scroll-to-top
document.addEventListener('DOMContentLoaded', () => {
  // card click -> quick view
  document.querySelectorAll('.image-card,.text-card').forEach(card => {
    card.addEventListener('click', () => {
      const t = card.getAttribute('data-title') || '';
      const s = card.getAttribute('data-summary') || '';
      const l = card.getAttribute('data-link') || '';
      if (t && l) openQuickView(t, s, l);
    });
  });

  // scroll-to-top
  const btn = document.getElementById('toTop');
  const onScroll = () => {
    if (!btn) return;
    if (window.scrollY > 420) btn.classList.add('show');
    else btn.classList.remove('show');
  };
  window.addEventListener('scroll', onScroll, {passive:true});
  onScroll();
  if (btn) {
    btn.addEventListener('click', () => {
      window.scrollTo({top:0, behavior:'smooth'});
    });
  }
});

// close popups when click outside
document.addEventListener('click', e => {
  if (!e.target.closest('.image-card,.text-card,#quickView')) {
    closeQuickView();
  }
  if (!e.target.closest('#legendPopover,#btnReadMore')) {
    hideLegend();
  }
});

document.addEventListener('keydown', e => {
  if (e.key === 'Escape') { closeQuickView(); hideLegend(); }
});

// update legend position on resize/scroll
window.addEventListener('resize', () => {
  const pop = document.getElementById('legendPopover');
  if (pop && pop.classList.contains('show')) showLegend();
});
window.addEventListener('scroll', () => {
  const pop = document.getElementById('legendPopover');
  if (pop && pop.classList.contains('show')) showLegend();
}, {passive:true});

// Fireworks (safe: NO `${}` template literals)
(function() {
  const canvas = document.getElementById('fireworks');
  if (!canvas) return;
  const ctx = canvas.getContext('2d');

  function resize() {
    const rect = canvas.getBoundingClientRect();
    canvas.width = Math.floor(rect.width * devicePixelRatio);
    canvas.height = Math.floor(rect.height * devicePixelRatio);
    ctx.setTransform(devicePixelRatio, 0, 0, devicePixelRatio, 0, 0);
  }
  window.addEventListener('resize', resize);
  resize();

  const colors = ['#f6c453','#ffe9d6','#ff7aa5','#f97316','#22c55e','#60a5fa'];
  const particles = [];

  function burst(x, y) {
    const count = 42 + Math.floor(Math.random() * 22);
    for (let i = 0; i < count; i++) {
      const a = Math.random() * Math.PI * 2;
      const sp = 1.0 + Math.random() * 3.6;
      particles.push({
        x:x, y:y,
        vx: Math.cos(a)*sp,
        vy: Math.sin(a)*sp,
        life: 58 + Math.random()*26,
        r: 1 + Math.random()*2,
        c: colors[(Math.random()*colors.length)|0]
      });
    }
  }

  function hexToRgba(hex, alpha) {
    const h = hex.replace('#','');
    const r = parseInt(h.substring(0,2),16);
    const g = parseInt(h.substring(2,4),16);
    const b = parseInt(h.substring(4,6),16);
    return 'rgba(' + r + ',' + g + ',' + b + ',' + alpha + ')';
  }

  let t = 0;
  function step() {
    t++;
    const W = canvas.clientWidth;
    const H = canvas.clientHeight;
    ctx.fillStyle = 'rgba(0,0,0,0.18)';
    ctx.fillRect(0,0,W,H);

    if (t % 26 === 0) burst(60 + Math.random()*(W-120), 24 + Math.random()*55);

    for (let i = particles.length - 1; i >= 0; i--) {
      const p = particles[i];
      p.life -= 1;
      p.vy += 0.03;
      p.vx *= 0.988;
      p.vy *= 0.988;
      p.x += p.vx;
      p.y += p.vy;

      const alpha = Math.max(0, Math.min(1, p.life/84));
      ctx.beginPath();
      ctx.fillStyle = hexToRgba(p.c, alpha);
      ctx.arc(p.x, p.y, p.r, 0, Math.PI*2);
      ctx.fill();

      if (p.life <= 0 || p.y > H + 30) particles.splice(i, 1);
    }

    requestAnimationFrame(step);
  }

  setTimeout(() => { burst(canvas.clientWidth*0.5, 28); }, 280);
  requestAnimationFrame(step);
})();
</script>
</head>
<body>

<div class=\"topbar\">\
  <div class=\"container nav\">\
    <div class=\"brand\">\
      <div class=\"brand-badge\">🤖</div>\
      <div class=\"brand-name\"><span class=\"logo\" data-text=\"AI NEWS\">AI NEWS</span></div>\
    </div>\
    <div class=\"menu\">\
      <a href=\"#featured\">Featured</a>\
      <a href=\"#more\">More</a>\
      <a href=\"#how\">How it works</a>\
      <a href=\"#contact\">Contact</a>\
    </div>\
    <div class=\"right-tools\">\
      <div id=\"google_translate_element\"></div>\
    </div>\
  </div>\
</div>

<section class=\"hero\">\
  <div class=\"container\">\
    <div class=\"hero-wrap\">\
      <canvas id=\"fireworks\"></canvas>\
      <div class=\"hero-inner\">\
        <div class=\"hero-left\">\
          <div class=\"kicker\"><span class=\"dot\"></span> Lunar New Year Digest</div>\
          <div class=\"hero-title\">CHINESE<br>NEW YEAR</div>\
          <div class=\"hero-sub\">Celebration</div>\
          <p class=\"hero-desc\">Click any card to preview in Quick View, then open full article. Cards stay minimal — full summary appears in the pop-up.</p>\
          <div class=\"hero-actions\">\
            <button id=\"btnReadMore\" class=\"btn primary\" type=\"button\" onclick=\"toggleLegend()\">Read More →</button>\
            <a class=\"btn ghost\" href=\"#more\">More News</a>\
          </div>\
        </div>\
        <div class=\"hero-art\" aria-hidden=\"true\">\
          <div class=\"art-shell\">\
            <svg viewBox=\"0 0 520 520\" width=\"100%\" height=\"100%\" xmlns=\"http://www.w3.org/2000/svg\">\
              <defs>\
                <radialGradient id=\"g1\" cx=\"30%\" cy=\"30%\" r=\"70%\">\
                  <stop offset=\"0%\" stop-color=\"#f6c453\" stop-opacity=\"0.55\"/>\
                  <stop offset=\"60%\" stop-color=\"#ff7aa5\" stop-opacity=\"0.12\"/>\
                  <stop offset=\"100%\" stop-color=\"#000000\" stop-opacity=\"0\"/>\
                </radialGradient>\
                <linearGradient id=\"g2\" x1=\"0\" y1=\"0\" x2=\"1\" y2=\"1\">\
                  <stop offset=\"0%\" stop-color=\"#ffb84d\"/>\
                  <stop offset=\"100%\" stop-color=\"#f6c453\"/>\
                </linearGradient>\
              </defs>\
              <circle cx=\"270\" cy=\"260\" r=\"220\" fill=\"url(#g1)\"/>\
              <path d=\"M90 350c0-42 34-76 76-76 14 0 27 4 38 10 14-30 44-50 79-50 40 0 74 26 86 62 8-3 16-4 25-4 39 0 71 32 71 71 0 39-32 71-71 71H170c-44 0-80-36-80-80z\" fill=\"rgba(255,255,255,0.08)\" stroke=\"rgba(255,255,255,0.12)\"/>\
              <path d=\"M260 365c-12-58 8-118 56-156 16-13 17-29 2-38-30-18-68 12-83 50-14-24-38-44-64-41-22 3-33 25-17 42 29 30 55 74 62 143z\" fill=\"#2b0818\" opacity=\"0.78\"/>\
              <g>\
                <path d=\"M165 170c22-30 64-40 96-22 34-26 85-16 105 22 22 42-10 93-62 96-20 1-32-6-45-17-23 22-60 28-90 10-44-26-55-68-4-89z\" fill=\"url(#g2)\" opacity=\"0.95\"/>\
                <path d=\"M315 210c12-16 34-21 52-12 18-14 44-9 54 12 12 22-5 49-31 50-11 1-17-3-24-9-12 11-30 14-46 6-22-13-27-36-5-47z\" fill=\"rgba(246,196,83,.88)\"/>\
              </g>\
              <g fill=\"#ffe9d6\" opacity=\"0.95\">\
                <circle cx=\"184\" cy=\"222\" r=\"10\"/><circle cx=\"200\" cy=\"210\" r=\"7\"/><circle cx=\"215\" cy=\"224\" r=\"6\"/>\
                <circle cx=\"345\" cy=\"238\" r=\"10\"/><circle cx=\"360\" cy=\"226\" r=\"7\"/><circle cx=\"372\" cy=\"242\" r=\"6\"/>\
              </g>\
            </svg>\
          </div>\
        </div>\
      </div>\
    </div>\
  </div>\
</section>

<!-- Legend popover element (fixed layer, not clipped) -->
<div id=\"legendPopover\">\
  <h4>Legend of Chinese Lunar New Year</h4>\
  <p>According to legend, a beast named Nian came each year to harm villages. People discovered Nian feared loud sounds, bright lights, and the color red. So they hung red decorations, lit firecrackers, and used lanterns to drive it away—forming the traditions we celebrate today.</p>\
</div>

<section class=\"section\" id=\"featured\">\
  <div class=\"container\">\
    <h3>Featured</h3>\
    <div class=\"grid-image\">\
"""

TAIL = """
    </div>
  </div>
</section>

<section class=\"section\" id=\"more\">\
  <div class=\"container\">\
    <h3>More news</h3>\
    <div class=\"grid-text\">\

    </div>
  </div>
</section>

<section class=\"section\" id=\"how\">\
  <div class=\"container\">\
    <h3>How it works</h3>\
    <div style=\"opacity:.82; line-height:1.7; max-width:880px;\">Click any card → preview in Quick View → open full article. Use Translate at the top right.</div>\
  </div>\
</section>

<section class=\"section\" id=\"contact\">\
  <div class=\"container\">\
    <h3>Contact</h3>\
    <div style=\"opacity:.82; line-height:1.7;\">Want thêm lồng đèn rủ xuống, dây pháo, hoa mai/hoa đào? Nói mình chỉnh tiếp.</div>\
    <div style=\"margin-top:14px; font-weight:1000; letter-spacing:.8px; color:rgba(255,233,214,.95);\">FROM MR. THOR WITH LOVE</div>\
  </div>\
</section>

<div id=\"quickView\">\
  <h3 id=\"qv-title\"></h3>\
  <p id=\"qv-summary\"></p>\
  <a id=\"qv-link\" target=\"_blank\">Open full article →</a>\
</div>\

<div id=\"toTop\" title=\"Back to top\"><span>↑</span></div>

</body>
</html>
"""

parts = [HEAD]

# Featured cards with data-* (no inline JS args => no random broken cards)
for n in with_image:
    title_attr = attr_escape(html_lib.unescape(n['title']))
    summary_attr = attr_escape(html_lib.unescape(n['summary']))
    link_attr = attr_escape(n['link'])

    img_tag = ''
    if n.get('image'):
        img_url = attr_escape(n['image'])
        img_tag = f'<img src="{img_url}" onerror="this.style.display=\'none\'">'

    parts.append(
        '  <div class="image-card" '
        + f'data-title="{title_attr}" data-summary="{summary_attr}" data-link="{link_attr}">\n'
        + img_tag + '\n'
        + '    <div class="card-pad">\n'
        + f'      <div class="source">{n["source"]}</div>\n'
        + f'      <h3>{n["title"]}</h3>\n'
        + '    </div>\n'
        + '  </div>\n'
    )

parts.append("""
    </div>
  </div>
</section>

<section class=\"section\" id=\"more\">\
  <div class=\"container\">\
    <h3>More news</h3>\
    <div class=\"grid-text\">\
""")

for n in no_image:
    title_attr = attr_escape(html_lib.unescape(n['title']))
    summary_attr = attr_escape(html_lib.unescape(n['summary']))
    link_attr = attr_escape(n['link'])

    parts.append(
        '  <div class="text-card" '
        + f'data-title="{title_attr}" data-summary="{summary_attr}" data-link="{link_attr}">\n'
        + '    <div class="card-pad">\n'
        + f'      <div class="source">{n["source"]}</div>\n'
        + f'      <h3>{n["title"]}</h3>\n'
        + '    </div>\n'
        + '  </div>\n'
    )

parts.append(TAIL)

html_out = ''.join(parts)
html_out = html_out.replace('__TODAY__', TODAY)

OUTPUT.write_text(html_out, encoding='utf-8')
print('🎉 DONE!')
print('👉 index.html updated')
