<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ATTA Capital</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Space+Mono:ital,wght@0,400;0,700;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
:root{
  --bg:#080808;--bg2:#101010;--bg3:#141414;--bg4:#1a1a1a;
  --gold:#c8a84b;--gold2:#e8c96b;
  --gold-dim:rgba(200,168,75,0.1);
  --gold-line:rgba(200,168,75,0.15);
  --text:#ddd8ce;--muted:#666058;--muted2:#3a3830;
  --red-text:#e05555;--green-text:#3dac6c;
}
html{scroll-behavior:smooth;}
body{background:var(--bg);color:var(--text);font-family:'DM Sans',sans-serif;font-size:16px;line-height:1.6;overflow-x:hidden;}

body::before{
  content:'';position:fixed;inset:0;
  background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,0.06) 2px,rgba(0,0,0,0.06) 4px);
  pointer-events:none;z-index:9999;opacity:0.35;
}

/* NAV */
nav{
  position:fixed;top:0;left:0;right:0;z-index:500;height:56px;
  background:rgba(8,8,8,0.96);border-bottom:1px solid var(--gold-line);
  display:flex;align-items:center;justify-content:space-between;padding:0 2rem;
}
.nav-logo{font-family:'Bebas Neue',sans-serif;font-size:26px;letter-spacing:4px;color:var(--gold);text-decoration:none;}
.nav-logo span{color:var(--muted);font-size:11px;letter-spacing:2px;margin-left:12px;font-family:'Space Mono',monospace;}
.nav-links{display:flex;gap:2rem;list-style:none;}
.nav-links a{font-family:'Space Mono',monospace;font-size:10px;letter-spacing:2px;text-transform:uppercase;color:var(--muted);text-decoration:none;transition:color 0.2s;}
.nav-links a:hover{color:var(--gold);}
.nav-cta{font-family:'Space Mono',monospace;font-size:10px;font-weight:700;letter-spacing:2px;text-transform:uppercase;background:var(--gold);color:#080808;padding:9px 18px;text-decoration:none;clip-path:polygon(6px 0%,100% 0%,calc(100% - 6px) 100%,0% 100%);transition:background 0.2s;}
.nav-cta:hover{background:var(--gold2);}

/* TICKER */
.ticker{position:fixed;bottom:0;left:0;right:0;z-index:500;height:30px;background:rgba(8,8,8,0.96);border-top:1px solid var(--gold-line);overflow:hidden;display:flex;align-items:center;}
.ticker-inner{display:inline-flex;gap:3rem;white-space:nowrap;animation:tick 24s linear infinite;font-family:'Space Mono',monospace;font-size:10px;letter-spacing:1px;}
.ticker-item{color:var(--muted);}
.ticker-item .label{color:var(--gold);margin-right:6px;}
.ticker-item .up{color:var(--green-text);}
@keyframes tick{from{transform:translateX(0);}to{transform:translateX(-50%);}}

/* HERO */
.hero{min-height:100vh;padding:100px 2rem 80px;display:flex;align-items:center;position:relative;overflow:hidden;}
.hero-grid{position:absolute;inset:0;background:repeating-linear-gradient(0deg,transparent,transparent 59px,rgba(200,168,75,0.025) 60px),repeating-linear-gradient(90deg,transparent,transparent 59px,rgba(200,168,75,0.025) 60px);pointer-events:none;}
.hero-glow{position:absolute;right:-5%;top:15%;width:700px;height:700px;background:radial-gradient(circle,rgba(200,168,75,0.04) 0%,transparent 65%);pointer-events:none;}
.hero-content{max-width:1100px;margin:0 auto;width:100%;position:relative;}

.hero-tag{font-family:'Space Mono',monospace;font-size:10px;letter-spacing:3px;text-transform:uppercase;color:var(--gold);margin-bottom:2rem;display:flex;align-items:center;gap:1rem;}
.hero-tag::before{content:'';width:30px;height:1px;background:var(--gold);}

.hero-h1{font-family:'Bebas Neue',sans-serif;font-size:clamp(72px,12vw,160px);line-height:0.9;letter-spacing:1px;color:var(--text);margin-bottom:0.5rem;}
.hero-h1 .gold{color:var(--gold);}
.hero-h1 .dim{-webkit-text-stroke:1px rgba(200,168,75,0.3);color:transparent;}

.hero-sub{font-size:15px;color:var(--muted);margin:1.75rem 0 2.5rem;max-width:460px;line-height:1.9;}
.hero-sub em{color:var(--text);font-style:normal;}

.hero-stats{display:flex;gap:2.5rem;flex-wrap:wrap;margin-bottom:2.5rem;}
.stat{border-left:2px solid var(--gold);padding-left:1rem;}
.stat-n{font-family:'Bebas Neue',sans-serif;font-size:36px;color:var(--gold);line-height:1;}
.stat-l{font-family:'Space Mono',monospace;font-size:9px;color:var(--muted);letter-spacing:2px;text-transform:uppercase;margin-top:3px;}

.hero-btns{display:flex;gap:1rem;flex-wrap:wrap;}
.btn-g{font-family:'Space Mono',monospace;font-size:10px;font-weight:700;letter-spacing:3px;text-transform:uppercase;background:var(--gold);color:#080808;padding:13px 24px;text-decoration:none;clip-path:polygon(8px 0%,100% 0%,calc(100% - 8px) 100%,0% 100%);transition:all 0.2s;display:inline-block;}
.btn-g:hover{background:var(--gold2);transform:translateY(-2px);}
.btn-o{font-family:'Space Mono',monospace;font-size:10px;letter-spacing:3px;text-transform:uppercase;background:transparent;color:var(--text);border:1px solid rgba(221,216,206,0.15);padding:13px 24px;text-decoration:none;clip-path:polygon(8px 0%,100% 0%,calc(100% - 8px) 100%,0% 100%);transition:all 0.2s;display:inline-block;}
.btn-o:hover{border-color:var(--gold);color:var(--gold);}

/* LAYOUT */
.wrap{max-width:1100px;margin:0 auto;padding:90px 2rem;}
.rule{width:100%;height:1px;background:var(--gold-line);max-width:1100px;margin:0 auto;}
.sec-tag{font-family:'Space Mono',monospace;font-size:10px;letter-spacing:4px;text-transform:uppercase;color:var(--gold);margin-bottom:1rem;display:flex;align-items:center;gap:1rem;}
.sec-tag::after{content:'';flex:1;height:1px;background:var(--gold-line);}
.sec-h2{font-family:'Bebas Neue',sans-serif;font-size:clamp(42px,5.5vw,72px);letter-spacing:2px;line-height:1;color:var(--text);margin-bottom:3rem;}

/* DAILY UPDATES */
.updates-grid{display:grid;grid-template-columns:1fr 1fr;gap:1px;background:var(--gold-line);}
.update-card{background:var(--bg);padding:2rem;transition:background 0.2s;}
.update-card:hover{background:var(--bg2);}
.update-card.featured{grid-column:1/-1;background:var(--bg2);}
.update-date{font-family:'Space Mono',monospace;font-size:9px;letter-spacing:3px;color:var(--muted);text-transform:uppercase;margin-bottom:1rem;display:flex;align-items:center;gap:1rem;}
.update-date::before{content:'';width:6px;height:6px;border-radius:50%;background:var(--gold);flex-shrink:0;}
.update-title{font-family:'Bebas Neue',sans-serif;font-size:22px;letter-spacing:1px;color:var(--text);margin-bottom:0.75rem;}
.update-card.featured .update-title{font-size:30px;}
.update-body{font-size:13px;color:var(--muted);line-height:1.8;}
.update-card.featured .update-body{max-width:680px;font-size:14px;}
.update-tags{display:flex;gap:0.5rem;flex-wrap:wrap;margin-top:1.25rem;}
.tag{font-family:'Space Mono',monospace;font-size:9px;letter-spacing:1px;text-transform:uppercase;border:1px solid var(--gold-line);padding:3px 9px;color:var(--muted);}
.live-dot{display:inline-flex;align-items:center;gap:6px;font-family:'Space Mono',monospace;font-size:9px;letter-spacing:2px;text-transform:uppercase;color:var(--green-text);margin-left:auto;}
.live-dot::before{content:'';width:6px;height:6px;border-radius:50%;background:var(--green-text);animation:pulse 1.5s ease-in-out infinite;}
@keyframes pulse{0%,100%{opacity:1;}50%{opacity:0.3;}}

/* JOURNAL */
.journal-list{display:flex;flex-direction:column;gap:1px;background:var(--gold-line);}
.journal-header{background:var(--bg3);display:grid;grid-template-columns:120px 1fr auto auto;gap:2rem;padding:0.75rem 2rem;font-family:'Space Mono',monospace;font-size:9px;letter-spacing:3px;text-transform:uppercase;color:var(--muted2);}
.journal-row{background:var(--bg);display:grid;grid-template-columns:120px 1fr auto auto;gap:2rem;align-items:center;padding:1.5rem 2rem;transition:background 0.2s;cursor:pointer;text-decoration:none;}
.journal-row:hover{background:var(--bg2);}
.j-date{font-family:'Space Mono',monospace;font-size:10px;color:var(--muted);letter-spacing:1px;}
.j-title{font-size:15px;color:var(--text);}
.j-title small{display:block;font-size:11px;color:var(--muted);margin-top:3px;font-family:'Space Mono',monospace;letter-spacing:0.5px;}
.j-result{font-family:'Space Mono',monospace;font-size:13px;font-weight:700;text-align:right;}
.j-result.win{color:var(--green-text);}
.j-result.loss{color:var(--red-text);}
.j-result.be{color:var(--muted);}
.j-firm{font-family:'Space Mono',monospace;font-size:9px;letter-spacing:2px;text-transform:uppercase;color:var(--muted);text-align:right;}

/* RESOURCES */
.res-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--gold-line);}
.res-card{background:var(--bg);padding:2rem;text-decoration:none;display:block;position:relative;overflow:hidden;transition:background 0.2s;}
.res-card:hover{background:var(--bg2);}
.res-card::before{content:attr(data-num);position:absolute;right:1.5rem;bottom:1rem;font-family:'Bebas Neue',sans-serif;font-size:80px;color:rgba(200,168,75,0.05);line-height:1;pointer-events:none;}
.res-cat{font-family:'Space Mono',monospace;font-size:9px;letter-spacing:3px;text-transform:uppercase;color:var(--gold);margin-bottom:1rem;}
.res-title{font-family:'Bebas Neue',sans-serif;font-size:22px;letter-spacing:1px;color:var(--text);margin-bottom:0.75rem;}
.res-body{font-size:12px;color:var(--muted);line-height:1.8;}
.res-link{display:inline-block;margin-top:1.5rem;font-family:'Space Mono',monospace;font-size:9px;letter-spacing:2px;text-transform:uppercase;color:var(--gold);border-bottom:1px solid var(--gold-line);padding-bottom:2px;}

/* FIRMS */
.firms-wrap{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--gold-line);}
.firm{background:var(--bg);padding:2.5rem 2rem;text-decoration:none;display:block;text-align:center;transition:background 0.2s;position:relative;}
.firm:hover{background:var(--bg2);}
.firm::after{content:'';position:absolute;bottom:0;left:0;right:0;height:2px;background:var(--gold);transform:scaleX(0);transform-origin:left;transition:transform 0.25s;}
.firm:hover::after{transform:scaleX(1);}
.firm-badge{display:inline-block;margin-bottom:1rem;background:var(--gold-dim);color:var(--gold);font-family:'Space Mono',monospace;font-size:9px;letter-spacing:2px;text-transform:uppercase;padding:3px 10px;}
.firm-name{font-family:'Bebas Neue',sans-serif;font-size:42px;letter-spacing:3px;color:var(--text);line-height:1;margin-bottom:0.75rem;}
.firm-desc{font-size:12px;color:var(--muted);line-height:1.8;margin-bottom:1.5rem;}
.firm-cta{font-family:'Space Mono',monospace;font-size:9px;letter-spacing:2px;text-transform:uppercase;color:var(--gold);border:1px solid var(--gold-line);display:inline-block;padding:6px 16px;}

/* DISCORD */
.discord-block{background:var(--bg2);border:1px solid var(--gold-line);padding:4rem 3rem;position:relative;overflow:hidden;display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:center;}
.discord-block::after{content:'ATTA';position:absolute;right:-2rem;top:50%;transform:translateY(-50%);font-family:'Bebas Neue',sans-serif;font-size:240px;color:rgba(200,168,75,0.02);pointer-events:none;letter-spacing:-8px;line-height:1;}
.discord-h{font-family:'Bebas Neue',sans-serif;font-size:clamp(40px,5vw,64px);line-height:0.95;letter-spacing:2px;margin-bottom:1.25rem;}
.discord-h span{color:var(--gold);}
.discord-p{font-size:13px;color:var(--muted);line-height:1.9;margin-bottom:2rem;}
.discord-list{list-style:none;display:flex;flex-direction:column;gap:1rem;}
.discord-list li{font-family:'Space Mono',monospace;font-size:11px;letter-spacing:1px;color:var(--muted);display:flex;align-items:center;gap:1rem;border-bottom:1px solid rgba(200,168,75,0.06);padding-bottom:1rem;}
.discord-list li::before{content:'';width:6px;height:6px;background:var(--gold);flex-shrink:0;}

/* FOOTER */
footer{border-top:1px solid var(--gold-line);padding:3rem 2rem 4rem;max-width:1100px;margin:0 auto;}
.footer-top{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:1.5rem;margin-bottom:2rem;padding-bottom:2rem;border-bottom:1px solid var(--muted2);}
.footer-logo{font-family:'Bebas Neue',sans-serif;font-size:24px;letter-spacing:4px;color:var(--gold);}
.footer-links{display:flex;gap:2rem;list-style:none;flex-wrap:wrap;}
.footer-links a{font-family:'Space Mono',monospace;font-size:10px;letter-spacing:2px;text-transform:uppercase;color:var(--muted);text-decoration:none;transition:color 0.2s;}
.footer-links a:hover{color:var(--gold);}
.disclaimer{font-family:'Space Mono',monospace;font-size:9px;color:var(--muted2);line-height:2;letter-spacing:0.5px;}

@media(max-width:768px){
  .nav-links{display:none;}
  .updates-grid,.firms-wrap,.res-grid{grid-template-columns:1fr;}
  .update-card.featured{grid-column:1;}
  .discord-block{grid-template-columns:1fr;}
  .journal-row,.journal-header{grid-template-columns:80px 1fr auto;gap:1rem;}
  .j-firm{display:none;}
}
</style>
</head>
<body>

<nav>
  <a class="nav-logo" href="#">ATTA <span>CAPITAL</span></a>
  <ul class="nav-links">
    <li><a href="#updates">Daily</a></li>
    <li><a href="#journal">Journal</a></li>
    <li><a href="#resources">Resources</a></li>
    <li><a href="#firms">Prop Firms</a></li>
    <li><a href="#community">Community</a></li>
  </ul>
  <a class="nav-cta" href="#community">Join Free</a>
</nav>

<!-- HERO -->
<div class="hero">
  <div class="hero-grid"></div>
  <div class="hero-glow"></div>
  <div class="hero-content">
    <div class="hero-tag">ATTA Capital &mdash; Mindset Dictates Outcomes</div>
    <h1 class="hero-h1">
      JUST A GUY<br>
      <span class="gold">TRADING</span><br>
      <span class="dim">FUTURES.</span>
    </h1>
    <p class="hero-sub">
      Part-time prop firm trader. <em>NQ/MNQ</em> during a 3-hour window every morning.<br><br>
      I kind of suck at trading. I also have <em>$45K+ in payouts</em>. Both things are true &mdash; and that's kind of the whole point of this place.
    </p>
    <div class="hero-stats">
      <div class="stat">
        <div class="stat-n">$45K+</div>
        <div class="stat-l">Payouts</div>
      </div>
      <div class="stat">
        <div class="stat-n">20+</div>
        <div class="stat-l">Months Live</div>
      </div>
      <div class="stat">
        <div class="stat-n">3</div>
        <div class="stat-l">Active Firms</div>
      </div>
    </div>
    <div class="hero-btns">
      <a class="btn-g" href="#community">Join the Community</a>
      <a class="btn-o" href="#updates">Today's Brief</a>
    </div>
  </div>
</div>

<!-- TICKER -->
<div class="ticker">
  <div class="ticker-inner">
    <span class="ticker-item"><span class="label">NQ/MNQ</span>Futures &bull; Vol Profile &bull; TBR Levels &bull; EMA Stack</span>
    <span class="ticker-item"><span class="label">SESSION</span>10:00AM &mdash; 1:00PM ET</span>
    <span class="ticker-item"><span class="label">APEX</span><span class="up">Funded &#9650;</span></span>
    <span class="ticker-item"><span class="label">TOPSTEP</span><span class="up">Funded &#9650;</span></span>
    <span class="ticker-item"><span class="label">TRADEIFY</span><span class="up">Funded &#9650;</span></span>
    <span class="ticker-item"><span class="label">MDO</span>Mindset Dictates Outcomes</span>
    <span class="ticker-item"><span class="label">NQ/MNQ</span>Futures &bull; Vol Profile &bull; TBR Levels &bull; EMA Stack</span>
    <span class="ticker-item"><span class="label">SESSION</span>10:00AM &mdash; 1:00PM ET</span>
    <span class="ticker-item"><span class="label">APEX</span><span class="up">Funded &#9650;</span></span>
    <span class="ticker-item"><span class="label">TOPSTEP</span><span class="up">Funded &#9650;</span></span>
    <span class="ticker-item"><span class="label">TRADEIFY</span><span class="up">Funded &#9650;</span></span>
    <span class="ticker-item"><span class="label">MDO</span>Mindset Dictates Outcomes</span>
  </div>
</div>

<!-- DAILY UPDATES -->
<div class="rule"></div>
<div class="wrap" id="updates">
  <div class="sec-tag">Daily Updates</div>
  <h2 class="sec-h2">TODAY'S BRIEF</h2>
  <div class="updates-grid">
    <div class="update-card featured">
      <div class="update-date">
        April 2, 2025 &mdash; Pre-Session
        <span class="live-dot">Live</span>
      </div>
      <div class="update-title">NQ STRUCTURE WATCH: KEY LEVELS HEADING INTO THE OPEN</div>
      <div class="update-body">
        Market bounced off the overnight low into a key structural zone. Volume profile shows a thin area above current price &mdash; watch for a push into the upper half of yesterday's range before any reversal play. TBR levels are set, EMA stack is mixed on the 5m. Bias is neutral-to-short on opens into the 24,200&ndash;24,240 zone. Stay patient, let the open settle before committing.
      </div>
      <div class="update-tags">
        <span class="tag">NQ Futures</span>
        <span class="tag">Pre-Session</span>
        <span class="tag">Volume Profile</span>
        <span class="tag">TBR</span>
      </div>
    </div>
    <div class="update-card">
      <div class="update-date">April 1, 2025 &mdash; Recap</div>
      <div class="update-title">ONE TRADE. ONE SETUP. DONE.</div>
      <div class="update-body">Waited on the 10:30 tendency, got a clean rejection off the top of the morning range. One entry, one exit. Didn't overstay. Called it after the setup resolved.</div>
      <div class="update-tags">
        <span class="tag">Recap</span><span class="tag">Reversal</span><span class="tag">Discipline</span>
      </div>
    </div>
    <div class="update-card">
      <div class="update-date">March 31, 2025 &mdash; Macro Note</div>
      <div class="update-title">QUARTER-END FLOWS &amp; WHAT THEY MEAN</div>
      <div class="update-body">Q1 end brought institutional rebalancing noise. Price moved away from value and snapped back. These aren't setups &mdash; they're liquidity grabs. Rule: don't fight quarter-end flow, wait for it to resolve.</div>
      <div class="update-tags">
        <span class="tag">Macro</span><span class="tag">Institutional Flow</span>
      </div>
    </div>
  </div>
</div>

<!-- JOURNAL -->
<div class="rule"></div>
<div class="wrap" id="journal">
  <div class="sec-tag">Trading Journal</div>
  <h2 class="sec-h2">THE RECORD</h2>
  <div class="journal-list">
    <div class="journal-header">
      <span>Date</span><span>Setup / Notes</span><span>Result</span><span>Firm</span>
    </div>
    <a class="journal-row" href="#">
      <div class="j-date">Apr 1, 2025</div>
      <div class="j-title">Level rejection short at 24,242 zone<small>1 contract &bull; 10:45 entry &bull; clean setup, no chasing</small></div>
      <div class="j-result win">+$312</div>
      <div class="j-firm">Topstep</div>
    </a>
    <a class="journal-row" href="#">
      <div class="j-date">Mar 31, 2025</div>
      <div class="j-title">Missed entry into VAH by 2 ticks, didn't force it<small>No trade taken &bull; sometimes that's the win</small></div>
      <div class="j-result be">$0</div>
      <div class="j-firm">Apex</div>
    </a>
    <a class="journal-row" href="#">
      <div class="j-date">Mar 28, 2025</div>
      <div class="j-title">Continuation long off 10:30 pullback<small>2 contracts &bull; trailed stop, closed half early</small></div>
      <div class="j-result win">+$560</div>
      <div class="j-firm">Topstep</div>
    </a>
    <a class="journal-row" href="#">
      <div class="j-date">Mar 27, 2025</div>
      <div class="j-title">Oversized. Moved stop. Full loss.<small>Broke the 2-contract rule &bull; took the L, wrote it down</small></div>
      <div class="j-result loss">&minus;$880</div>
      <div class="j-firm">Tradeify</div>
    </a>
    <a class="journal-row" href="#">
      <div class="j-date">Mar 26, 2025</div>
      <div class="j-title">TBR level short &mdash; textbook<small>Pre-planned zone &bull; market came to me &bull; 1:3 R</small></div>
      <div class="j-result win">+$748</div>
      <div class="j-firm">Apex</div>
    </a>
  </div>
  <div style="margin-top:2rem;">
    <a class="btn-o" href="#">View Full Journal &rarr;</a>
  </div>
</div>

<!-- RESOURCES -->
<div class="rule"></div>
<div class="wrap" id="resources">
  <div class="sec-tag">Free Resources</div>
  <h2 class="sec-h2">STUFF THAT HELPED ME</h2>
  <div class="res-grid">
    <a class="res-card" href="#" data-num="01">
      <div class="res-cat">Prop Firms</div>
      <div class="res-title">Prop Firm Rulebook</div>
      <div class="res-body">Drawdown limits, payout mechanics, trailing vs. EOD rules across Apex, Topstep, and Tradeify. Plain language, no spin.</div>
      <div class="res-link">Free Download &rarr;</div>
    </a>
    <a class="res-card" href="#" data-num="02">
      <div class="res-cat">Methodology</div>
      <div class="res-title">Volume Profile Primer</div>
      <div class="res-body">How I use VAH, VAL, and POC to find high-probability reversal zones. The base layer of every trade I take.</div>
      <div class="res-link">Free Read &rarr;</div>
    </a>
    <a class="res-card" href="#" data-num="03">
      <div class="res-cat">Methodology</div>
      <div class="res-title">TBR Level Framework</div>
      <div class="res-body">9AM and 3PM ET hourly candles with Fib extensions at .3/.5/.7. The structure I map every morning before the open.</div>
      <div class="res-link">Free Read &rarr;</div>
    </a>
    <a class="res-card" href="#" data-num="04">
      <div class="res-cat">Planning</div>
      <div class="res-title">Session Prep Template</div>
      <div class="res-body">My exact pre-market workflow: HTF levels, value area, TBR, EMA context. A blank template you can actually use.</div>
      <div class="res-link">Free Template &rarr;</div>
    </a>
    <a class="res-card" href="#" data-num="05">
      <div class="res-cat">Evaluations</div>
      <div class="res-title">Eval Survival Guide</div>
      <div class="res-body">How to pass without blowing up. Sizing, drawdown tracking, and the mental side of evaluations that nobody talks about.</div>
      <div class="res-link">Free Guide &rarr;</div>
    </a>
    <a class="res-card" href="#" data-num="06">
      <div class="res-cat">Psychology</div>
      <div class="res-title">Behavioral Breakdown</div>
      <div class="res-body">The patterns that cost me accounts: oversizing, session drift, abandoning the process. My failures, documented honestly.</div>
      <div class="res-link">Free Read &rarr;</div>
    </a>
  </div>
</div>

<!-- FIRMS -->
<div class="rule"></div>
<div class="wrap" id="firms">
  <div class="sec-tag">Affiliates</div>
  <h2 class="sec-h2">FIRMS I ACTUALLY TRADE</h2>
  <p style="font-size:13px;color:var(--muted);max-width:520px;line-height:1.9;margin-bottom:3rem;font-family:'Space Mono',monospace;letter-spacing:0.5px;">
    These are the three firms I hold funded accounts on right now. Affiliate links help keep this site free &mdash; no extra cost to you, and I'd never send you somewhere I don't actually trade.
  </p>
  <div class="firms-wrap">
    <a class="firm" href="#">
      <div class="firm-badge">Currently Funded</div>
      <div class="firm-name">APEX</div>
      <div class="firm-desc">Flexible eval rules, multiple account scaling. Good for building a base of simultaneous funded accounts.</div>
      <div class="firm-cta">Get Eval &rarr;</div>
    </a>
    <a class="firm" href="#">
      <div class="firm-badge">Currently Funded</div>
      <div class="firm-name">TOPSTEP</div>
      <div class="firm-desc">My highest payout total over 20 months. Clean platform, consistent payout process, solid track record.</div>
      <div class="firm-cta">Get Eval &rarr;</div>
    </a>
    <a class="firm" href="#">
      <div class="firm-badge">Currently Funded</div>
      <div class="firm-name">TRADEIFY</div>
      <div class="firm-desc">Newer addition to the rotation. Worth adding once you've got the first two dialed in and want to scale further.</div>
      <div class="firm-cta">Get Eval &rarr;</div>
    </a>
  </div>
</div>

<!-- COMMUNITY -->
<div class="rule"></div>
<div class="wrap" id="community">
  <div class="discord-block">
    <div>
      <div class="sec-tag" style="margin-bottom:1rem;">Community</div>
      <h2 class="discord-h">PULL UP.<br><span>IT'S FREE.</span></h2>
      <p class="discord-p">
        Just a group of traders chopping it up. Pre-session planning, trade reviews, prop firm talk, and the occasional loss post. No paid tiers, no signal alerts, no guru energy. Come as you are.
      </p>
      <div style="display:flex;gap:1rem;flex-wrap:wrap;">
        <a class="btn-g" href="#">Join on Discord</a>
        <a class="btn-o" href="https://x.com/ATTA_Capital" target="_blank">Follow on X</a>
      </div>
    </div>
    <ul class="discord-list">
      <li>Pre-session level planning</li>
      <li>Post-session trade reviews</li>
      <li>Prop firm strategy &amp; tips</li>
      <li>Psychology &amp; process talk</li>
      <li>Zero paid tiers or upsells</li>
    </ul>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div class="footer-logo">ATTA Capital</div>
    <ul class="footer-links">
      <li><a href="https://x.com/ATTA_Capital" target="_blank">X / Twitter</a></li>
      <li><a href="#updates">Daily</a></li>
      <li><a href="#journal">Journal</a></li>
      <li><a href="#resources">Resources</a></li>
      <li><a href="#firms">Affiliates</a></li>
      <li><a href="#community">Discord</a></li>
    </ul>
  </div>
  <div class="disclaimer">
    RISK DISCLAIMER: Trading futures involves substantial risk of loss and is not appropriate for all investors. Past performance is not indicative of future results. All content on this site is for educational and informational purposes only and does not constitute financial advice. Affiliate links may earn ATTA Capital a commission at no additional cost to you.
  </div>
</footer>

</body>
</html>
