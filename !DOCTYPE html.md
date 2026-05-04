<!DOCTYPE html>  
<html lang="en">  
<head>  
<meta charset="UTF-8">  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
<title>Elegance Hotels International — Marmaris</title>  
<link rel="preconnect" href="https://fonts.googleapis.com">  
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,700;1,400;1,500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">  
<style>  
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}  
:root{  
  --gold:#C9A96E;--gold2:#E8D5A3;--gold3:#8B6914;  
  --deep:#07090C;--dark:#0F1419;--mid:#18222C;--card:#1E2B38;  
  --muted:#7A95A8;--text:#EAE4D8;--white:#F9F5EF;  
  --radius:2px;  
}  
html{scroll-behavior:smooth;font-size:16px}  
body{background:var(--deep);color:var(--text);font-family:'DM Sans',sans-serif;font-weight:300;overflow-x:hidden}  
img{display:block;max-width:100%}  
a{color:inherit;text-decoration:none}  
  
/* ══ CURSOR ══ */  
.cur,.cur-r{position:fixed;border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%)}  
.cur{width:8px;height:8px;background:var(--gold);transition:width.2s,height.2s}  
.cur-r{width:32px;height:32px;border:1px solid rgba(201,169,110,.4);transition:left.12s ease,top.12s ease}  
@media(hover:none){.cur,.cur-r{display:none}}  
  
/* ══ NAVBAR ══ */  
#nav{position:fixed;top:0;left:0;width:100%;z-index:500;padding:24px 5%;display:flex;align-items:center;justify-content:space-between;transition:background.5s,padding.4s,backdrop-filter.5s}  
#nav.solid{background:rgba(7,9,12,.94);backdrop-filter:blur(20px);padding:14px 5%;border-bottom:1px solid rgba(201,169,110,.1)}  
.logo{font-family:'Playfair Display',serif;font-size:1.35rem;letter-spacing:.08em;color:var(--gold)}  
.logo span{font-style:italic}  
.nav-links{display:flex;gap:36px;list-style:none}  
.nav-links a{font-size:.7rem;letter-spacing:.18em;text-transform:uppercase;opacity:.65;transition:opacity.3s,color.3s}  
.nav-links a:hover{opacity:1;color:var(--gold)}  
.nav-book{background:var(--gold);color:var(--deep);padding:10px 26px;font-size:.68rem;letter-spacing:.2em;text-transform:uppercase;font-weight:500;transition:background.3s,transform.2s;white-space:nowrap}  
.nav-book:hover{background:var(--gold2);transform:translateY(-1px)}  
.burger{display:none;flex-direction:column;gap:5px;cursor:pointer;padding:4px}  
.burger span{display:block;width:24px;height:1px;background:var(--text);transition:transform.3s,opacity.3s}  
  
/* Mobile menu */  
.mob-menu{position:fixed;inset:0;background:var(--deep);z-index:490;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:36px;transform:translateX(100%);transition:transform.4s cubic-bezier(.77,0,.18,1)}  
.mob-menu.open{transform:translateX(0)}  
.mob-menu a{font-family:'Playfair Display',serif;font-size:2rem;font-style:italic;color:var(--text);transition:color.3s}  
.mob-menu a:hover{color:var(--gold)}  
  
/* ══ HERO SLIDESHOW ══ */  
.hero{position:relative;height:100vh;min-height:600px;overflow:hidden}  
.slides{position:absolute;inset:0;display:flex;transition:transform.9s cubic-bezier(.77,0,.18,1)}  
.slide{min-width:100%;height:100%;position:relative;flex-shrink:0}  
.slide-bg{position:absolute;inset:0;background-size:cover;background-position:center;transform:scale(1.08);transition:transform 8s ease}  
.slide.active .slide-bg{transform:scale(1)}  
.slide-overlay{position:absolute;inset:0;background:linear-gradient(180deg,rgba(7,9,12,.25) 0%,rgba(7,9,12,.5) 50%,rgba(7,9,12,.92) 100%)}  
  
.hero-content{position:absolute;bottom:12%;left:50%;transform:translateX(-50%);width:90%;max-width:900px;text-align:center;z-index:2}  
.hero-tag{font-size:.65rem;letter-spacing:.45em;text-transform:uppercase;color:var(--gold);margin-bottom:28px;opacity:0;animation:fu .9s ease .3s forwards;display:flex;align-items:center;justify-content:center;gap:18px}  
.hero-tag::before,.hero-tag::after{content:'';flex:0 0 40px;height:1px;background:var(--gold);opacity:.5}  
.hero-h1{font-family:'Playfair Display',serif;font-size:clamp(2.8rem,7vw,6.5rem);font-weight:400;line-height:.95;letter-spacing:-.01em;margin-bottom:28px;opacity:0;animation:fu .9s ease .55s forwards}  
.hero-h1 em{font-style:italic;color:var(--gold2)}  
.hero-sub{font-size:.95rem;line-height:1.9;color:var(--muted);margin:0 auto 48px;max-width:520px;opacity:0;animation:fu .9s ease .8s forwards}  
.hero-btns{display:flex;gap:16px;justify-content:center;flex-wrap:wrap;opacity:0;animation:fu .9s ease 1s forwards}  
.btn-g{background:var(--gold);color:var(--deep);padding:15px 40px;font-size:.7rem;letter-spacing:.22em;text-transform:uppercase;font-weight:500;transition:background.3s,transform.2s;cursor:pointer;border:none;font-family:'DM Sans',sans-serif}  
.btn-g:hover{background:var(--gold2);transform:translateY(-2px)}  
.btn-o{border:1px solid rgba(255,255,255,.3);color:var(--white);padding:15px 40px;font-size:.7rem;letter-spacing:.22em;text-transform:uppercase;transition:border-color.3s,color.3s;background:none;cursor:pointer;font-family:'DM Sans',sans-serif}  
.btn-o:hover{border-color:var(--gold);color:var(--gold)}  
  
/* Slide dots */  
.slide-dots{position:absolute;bottom:36px;left:50%;transform:translateX(-50%);display:flex;gap:10px;z-index:3}  
.dot{width:28px;height:2px;background:rgba(255,255,255,.3);cursor:pointer;transition:background.3s,width.3s}  
.dot.active{background:var(--gold);width:48px}  
  
/* Slide arrows */  
.arr{position:absolute;top:50%;transform:translateY(-50%);z-index:3;background:rgba(201,169,110,.12);border:1px solid rgba(201,169,110,.25);color:var(--gold);width:50px;height:50px;display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:1.2rem;transition:background.3s;backdrop-filter:blur(8px)}  
.arr:hover{background:rgba(201,169,110,.25)}  
.arr-l{left:30px}  
.arr-r{right:30px}  
  
@keyframes fu{from{opacity:0;transform:translateY(28px)}to{opacity:1;transform:translateY(0)}}  
  
/* ══ LANG SWITCHER ══ */  
.lang-bar{background:var(--mid);border-bottom:1px solid rgba(201,169,110,.08);display:flex;justify-content:flex-end;padding:10px 5%;gap:20px}  
.lang-btn{font-size:.65rem;letter-spacing:.15em;text-transform:uppercase;cursor:pointer;color:var(--muted);transition:color.3s;background:none;border:none;font-family:'DM Sans',sans-serif}  
.lang-btn.active,.lang-btn:hover{color:var(--gold)}  
  
/* ══ BOOKING WIDGET ══ */  
.booking-wrap{background:var(--dark);padding:50px 5%;border-bottom:1px solid rgba(201,169,110,.08)}  
.booking-inner{max-width:1100px;margin:0 auto}  
.booking-title{font-family:'Playfair Display',serif;font-size:1.6rem;font-style:italic;color:var(--gold);margin-bottom:30px;text-align:center}  
.booking-form{display:grid;grid-template-columns:1fr 1fr 1fr 1fr auto;gap:12px;align-items:end}  
.form-group{display:flex;flex-direction:column;gap:8px}  
.form-label{font-size:.6rem;letter-spacing:.2em;text-transform:uppercase;color:var(--gold)}  
.form-input{background:var(--mid);border:1px solid rgba(201,169,110,.2);color:var(--white);padding:14px 16px;font-size:.88rem;font-family:'DM Sans',sans-serif;transition:border-color.3s;-webkit-appearance:none;border-radius:0}  
.form-input:focus{outline:none;border-color:var(--gold)}  
.form-input option{background:var(--mid)}  
.book-submit{background:var(--gold);color:var(--deep);padding:14px 32px;font-size:.7rem;letter-spacing:.2em;text-transform:uppercase;font-weight:500;border:none;cursor:pointer;font-family:'DM Sans',sans-serif;white-space:nowrap;transition:background.3s;height:50px}  
.book-submit:hover{background:var(--gold2)}  
.booking-note{text-align:center;margin-top:18px;font-size:.75rem;color:var(--muted)}  
.booking-note a{color:var(--gold);text-decoration:underline}  
  
/* ══ STATS ══ */  
.stats{display:grid;grid-template-columns:repeat(4,1fr);border-top:1px solid rgba(201,169,110,.08);border-bottom:1px solid rgba(201,169,110,.08)}  
.stat{padding:44px 20px;text-align:center;border-right:1px solid rgba(201,169,110,.08);transition:background.3s}  
.stat:last-child{border-right:none}  
.stat:hover{background:rgba(201,169,110,.03)}  
.stat-n{font-family:'Playfair Display',serif;font-size:2.8rem;color:var(--gold);line-height:1;margin-bottom:8px}  
.stat-l{font-size:.62rem;letter-spacing:.22em;text-transform:uppercase;color:var(--muted)}  
  
/* ══ SECTION BASE ══ */  
.section{padding:110px 5%}  
.tag{font-size:.62rem;letter-spacing:.38em;text-transform:uppercase;color:var(--gold);display:flex;align-items:center;gap:14px;margin-bottom:22px}  
.tag::before{content:'';display:block;width:28px;height:1px;background:var(--gold)}  
.sec-h{font-family:'Playfair Display',serif;font-size:clamp(2.2rem,4.5vw,4rem);font-weight:400;line-height:1.08;margin-bottom:22px}  
.sec-h em{font-style:italic;color:var(--gold2)}  
.sec-p{font-size:.92rem;line-height:2;color:var(--muted);max-width:500px}  
  
/* ══ REVEAL ══ */  
.rv{opacity:0;transform:translateY(36px);transition:opacity.85s ease,transform.85s ease}  
.rv.in{opacity:1;transform:translateY(0)}  
.rv1{transition-delay:.15s}.rv2{transition-delay:.3s}.rv3{transition-delay:.45s}.rv4{transition-delay:.6s}  
  
/* ══ ROOMS ══ */  
.rooms-sec{background:var(--dark);padding-bottom:0}  
.rooms-hd{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:60px}  
.rooms-grid{display:grid;grid-template-columns:1.55fr 1fr 1fr;gap:3px;margin:0 -5%}  
.room-c{position:relative;overflow:hidden;cursor:pointer}  
.room-c:first-child{grid-row:span 2}  
.room-bg{width:100%;height:100%;min-height:280px;background-size:cover;background-position:center;transition:transform.9s cubic-bezier(.25,.46,.45,.94),filter.5s}  
.room-c:first-child .room-bg{min-height:100%}  
.room-bg{filter:brightness(.6)}  
.room-c:hover .room-bg{transform:scale(1.07);filter:brightness(.42)}  
.room-info{position:absolute;bottom:0;left:0;right:0;padding:36px;background:linear-gradient(to top,rgba(0,0,0,.88) 0%,transparent);transform:translateY(8px);transition:transform.4s}  
.room-c:hover .room-info{transform:translateY(0)}  
.r-tag{font-size:.58rem;letter-spacing:.28em;text-transform:uppercase;color:var(--gold);margin-bottom:8px}  
.r-name{font-family:'Playfair Display',serif;font-size:1.65rem;font-weight:400;margin-bottom:14px;line-height:1.1}  
.r-link{font-size:.62rem;letter-spacing:.18em;text-transform:uppercase;color:var(--gold);display:flex;align-items:center;gap:8px;opacity:0;transition:opacity.4s .1s}  
.r-link::after{content:'→'}  
.room-c:hover .r-link{opacity:1}  
  
/* ══ EXPERIENCE ══ */  
.exp-sec{background:var(--deep);overflow:hidden}  
.exp-grid{display:grid;grid-template-columns:1fr 1.1fr;gap:80px;align-items:start;margin-top:60px}  
.tl-item{display:flex;gap:24px;padding:24px 0;border-bottom:1px solid rgba(255,255,255,.05);transition:border-color.3s;cursor:default}  
.tl-item:hover{border-color:rgba(201,169,110,.18)}  
.tl-t{font-family:'Playfair Display',serif;font-size:1rem;color:var(--gold);opacity:.55;min-width:52px;padding-top:2px;font-style:italic}  
.tl-h{font-size:.78rem;letter-spacing:.08em;text-transform:uppercase;color:var(--white);margin-bottom:5px;font-weight:400}  
.tl-p{font-size:.8rem;color:var(--muted);line-height:1.75}  
.exp-imgs{position:sticky;top:100px;display:flex;flex-direction:column;gap:3px}  
.exp-img-main{height:400px;background:url('https://elegancehotels.com/img/elegant/02.jpg') center/cover;filter:brightness(.75)}  
.exp-img-row{display:grid;grid-template-columns:1fr 1fr;gap:3px}  
.exp-img-row div{height:190px;background-size:cover;background-position:center;filter:brightness(.7)}  
  
/* ══ AMENITIES ══ */  
.am-sec{background:var(--mid)}  
.am-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;margin-top:60px;background:rgba(201,169,110,.06)}  
.am-card{background:var(--mid);padding:48px 40px;transition:background.4s;position:relative;overflow:hidden}  
.am-card::after{content:'';position:absolute;bottom:0;left:0;width:0;height:2px;background:var(--gold);transition:width.5s}  
.am-card:hover{background:var(--card)}  
.am-card:hover::after{width:100%}  
.am-ico{font-size:1.7rem;margin-bottom:22px}  
.am-name{font-family:'Playfair Display',serif;font-size:1.38rem;margin-bottom:10px}  
.am-hrs{font-size:.6rem;letter-spacing:.22em;text-transform:uppercase;color:var(--gold);margin-bottom:14px}  
.am-desc{font-size:.8rem;color:var(--muted);line-height:1.8}  
  
/* ══ DINING ══ */  
.din-sec{background:var(--dark)}  
.din-grid{display:grid;grid-template-columns:1fr 1fr;gap:3px;margin-top:60px}  
.din-c{position:relative;height:520px;overflow:hidden;cursor:pointer}  
.din-bg{position:absolute;inset:0;background-size:cover;background-position:center;transition:transform.8s ease;filter:brightness(.48)}  
.din-c:hover .din-bg{transform:scale(1.05)}  
.din-ov{position:absolute;inset:0;background:linear-gradient(to top,rgba(0,0,0,.92) 0%,rgba(0,0,0,.15) 65%)}  
.din-ct{position:absolute;bottom:0;left:0;right:0;padding:46px}  
.din-badge{display:inline-block;border:1px solid var(--gold);padding:5px 14px;font-size:.56rem;letter-spacing:.28em;text-transform:uppercase;color:var(--gold);margin-bottom:18px}  
.din-name{font-family:'Playfair Display',serif;font-size:2.1rem;margin-bottom:10px;font-weight:400}  
.din-p{font-size:.8rem;color:var(--muted);line-height:1.8;margin-bottom:26px}  
.din-lnk{font-size:.62rem;letter-spacing:.18em;text-transform:uppercase;color:var(--gold);display:flex;align-items:center;gap:12px}  
.din-lnk::after{content:'';display:inline-block;width:28px;height:1px;background:var(--gold);transition:width.4s}  
.din-c:hover .din-lnk::after{width:56px}  
  
/* ══ GALLERY ══ */  
.gal-sec{background:var(--deep)}  
.gal-grid{display:grid;grid-template-columns:repeat(4,1fr);grid-template-rows:220px 220px;gap:3px;margin-top:60px}  
.gal-item{overflow:hidden;cursor:zoom-in;position:relative}  
.gal-item:nth-child(1){grid-column:span 2;grid-row:span 2}  
.gal-bg{width:100%;height:100%;background-size:cover;background-position:center;transition:transform.7s ease,filter.5s;filter:brightness(.75)}  
.gal-item:hover .gal-bg{transform:scale(1.08);filter:brightness(.55)}  
.gal-overlay{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;opacity:0;transition:opacity.4s;background:rgba(0,0,0,.3)}  
.gal-item:hover .gal-overlay{opacity:1}  
.gal-icon{width:52px;height:52px;border:1px solid rgba(255,255,255,.5);border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:1.2rem;color:#fff}  
  
/* Lightbox */  
.lb{position:fixed;inset:0;background:rgba(0,0,0,.95);z-index:1000;display:none;align-items:center;justify-content:center}  
.lb.open{display:flex}  
.lb-img{max-width:90vw;max-height:90vh;object-fit:contain}  
.lb-close{position:absolute;top:24px;right:28px;color:#fff;font-size:2rem;cursor:pointer;opacity:.7;background:none;border:none;line-height:1}  
.lb-close:hover{opacity:1}  
  
/* ══ MAP ══ */  
.map-sec{background:var(--mid)}  
.map-layout{display:grid;grid-template-columns:1fr 1fr;gap:0;margin-top:60px;min-height:480px}  
.map-frame{width:100%;height:100%;min-height:480px;border:none;filter:saturate(.8) brightness(.75)}  
.map-info{background:var(--card);padding:60px 50px;display:flex;flex-direction:column;gap:32px;justify-content:center}  
.map-item{display:flex;gap:20px;align-items:flex-start}  
.map-ico{width:42px;height:42px;border:1px solid rgba(201,169,110,.22);display:flex;align-items:center;justify-content:center;flex-shrink:0;font-size:1rem;color:var(--gold)}  
.map-lbl{font-size:.58rem;letter-spacing:.22em;text-transform:uppercase;color:var(--gold);margin-bottom:5px}  
.map-val{font-size:.88rem;line-height:1.65;color:var(--white)}  
.map-val a{color:var(--white);transition:color.3s}  
.map-val a:hover{color:var(--gold)}  
  
/* ══ REVIEWS ══ */  
.rev-sec{background:var(--dark)}  
.rev-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:20px;margin-top:60px}  
.rev-card{background:var(--card);padding:36px;border:1px solid rgba(201,169,110,.08);transition:border-color.4s}  
.rev-card:hover{border-color:rgba(201,169,110,.25)}  
.rev-stars{color:var(--gold);letter-spacing:3px;font-size:.95rem;margin-bottom:18px}  
.rev-text{font-family:'Playfair Display',serif;font-size:1rem;font-style:italic;line-height:1.7;color:var(--text);margin-bottom:22px}  
.rev-author{font-size:.68rem;letter-spacing:.12em;text-transform:uppercase;color:var(--muted)}  
.rev-src{font-size:.6rem;color:var(--gold);margin-top:4px;opacity:.7}  
  
/* ══ QUOTE ══ */  
.quote-sec{background:var(--deep);text-align:center;padding:130px 5%;position:relative;overflow:hidden}  
.quote-big{font-family:'Playfair Display',serif;font-size:clamp(1.6rem,3.5vw,2.9rem);font-style:italic;font-weight:400;line-height:1.55;max-width:780px;margin:0 auto 36px;color:var(--white)}  
.quote-src{font-size:.62rem;letter-spacing:.32em;text-transform:uppercase;color:var(--muted);display:flex;align-items:center;justify-content:center;gap:18px}  
.quote-src::before,.quote-src::after{content:'';display:inline-block;width:36px;height:1px;background:var(--gold);opacity:.4}  
  
/* ══ CTA ══ */  
.cta-sec{background:var(--mid);text-align:center;padding:140px 5%;position:relative;overflow:hidden}  
.cta-pattern{position:absolute;inset:0;opacity:.035;background-image:repeating-linear-gradient(45deg,var(--gold) 0,var(--gold) 1px,transparent 0,transparent 50%);background-size:36px 36px}  
.cta-h{font-family:'Playfair Display',serif;font-size:clamp(2.5rem,5vw,5rem);font-weight:400;line-height:1.05;margin-bottom:24px;position:relative}  
.cta-h em{font-style:italic;color:var(--gold)}  
.cta-p{font-size:.92rem;color:var(--muted);margin-bottom:52px;position:relative}  
.cta-btns{display:flex;justify-content:center;gap:16px;flex-wrap:wrap;position:relative}  
  
/* ══ FOOTER ══ */  
footer{background:#050709;padding:80px 5% 36px;border-top:1px solid rgba(201,169,110,.08)}  
.foot-g{display:grid;grid-template-columns:2fr 1fr 1fr 1fr;gap:52px;margin-bottom:60px}  
.foot-logo{font-family:'Playfair Display',serif;font-size:1.25rem;color:var(--gold);margin-bottom:18px;display:block;letter-spacing:.06em}  
.foot-logo span{font-style:italic}  
.foot-about{font-size:.82rem;color:var(--muted);line-height:1.9;max-width:280px}  
.foot-col-t{font-size:.6rem;letter-spacing:.28em;text-transform:uppercase;color:var(--gold);margin-bottom:22px}  
.foot-links{list-style:none;display:flex;flex-direction:column;gap:13px}  
.foot-links a{font-size:.8rem;color:var(--muted);transition:color.3s}  
.foot-links a:hover{color:var(--white)}  
.foot-bot{border-top:1px solid rgba(255,255,255,.05);padding-top:28px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:16px}  
.foot-c{font-size:.7rem;color:rgba(255,255,255,.22)}  
.socials{display:flex;gap:12px}  
.soc{width:36px;height:36px;border:1px solid rgba(255,255,255,.08);display:flex;align-items:center;justify-content:center;color:var(--muted);font-size:.8rem;transition:border-color.3s,color.3s}  
.soc:hover{border-color:var(--gold);color:var(--gold)}  
  
/* ══ SCROLL BAR ══ */  
::-webkit-scrollbar{width:2px}::-webkit-scrollbar-track{background:var(--deep)}::-webkit-scrollbar-thumb{background:var(--gold3)}  
  
/* ══ RESPONSIVE ══ */  
@media(max-width:900px){  
  .nav-links,.nav-book{display:none}  
  .burger{display:flex}  
  .booking-form{grid-template-columns:1fr 1fr}  
  .stats{grid-template-columns:repeat(2,1fr)}  
  .stat:nth-child(2){border-right:none}  
  .stat:nth-child(3){border-right:1px solid rgba(201,169,110,.08)}  
  .rooms-grid{grid-template-columns:1fr}  
  .room-c:first-child{grid-row:span 1}  
  .exp-grid{grid-template-columns:1fr}  
  .exp-imgs{display:none}  
  .am-grid{grid-template-columns:1fr 1fr}  
  .din-grid{grid-template-columns:1fr}  
  .gal-grid{grid-template-columns:1fr 1fr;grid-template-rows:auto}  
  .gal-item:nth-child(1){grid-column:span 2;grid-row:span 1}  
  .map-layout{grid-template-columns:1fr}  
  .map-frame{min-height:320px}  
  .rev-grid{grid-template-columns:1fr}  
  .foot-g{grid-template-columns:1fr 1fr;gap:36px}  
}  
@media(max-width:600px){  
  .booking-form{grid-template-columns:1fr}  
  .stats{grid-template-columns:1fr 1fr}  
  .am-grid{grid-template-columns:1fr}  
  .din-c{height:380px}  
  .rooms-hd{flex-direction:column;gap:20px;align-items:flex-start}  
  .gal-grid{grid-template-columns:1fr;grid-template-rows:auto}  
  .gal-item:nth-child(1){grid-column:span 1}  
  .foot-g{grid-template-columns:1fr}  
  .hero-btns{flex-direction:column;align-items:center}  
}  
  
/* ══ NOTIFICATION ══ */  
.notif{position:fixed;bottom:30px;right:30px;background:var(--gold);color:var(--deep);padding:16px 28px;font-size:.8rem;font-weight:500;z-index:2000;transform:translateY(100px);opacity:0;transition:transform.5s,opacity.5s;max-width:320px}  
.notif.show{transform:translateY(0);opacity:1}  
  
/* Progress bar */  
.progress{position:fixed;top:0;left:0;height:2px;background:var(--gold);z-index:9999;width:0%;transition:width.1s}  
</style>  
</head>  
<body>  
  
<div class="progress" id="prog"></div>  
<div class="cur" id="cur"></div>  
<div class="cur-r" id="curR"></div>  
  
<!-- NOTIFICATION -->  
<div class="notif" id="notif">✓ Your enquiry has been sent! We'll contact you within 24 hours.</div>  
  
<!-- LIGHTBOX -->  
<div class="lb" id="lb">  
  <button class="lb-close" onclick="closeLB()">✕</button>  
  <img class="lb-img" id="lbImg" src="" alt="">  
</div>  
  
<!-- MOBILE MENU -->  
<div class="mob-menu" id="mobMenu">  
  <a href="#rooms" onclick="closeMob()">Rooms</a>  
  <a href="#experience" onclick="closeMob()">Experience</a>  
  <a href="#dining" onclick="closeMob()">Dining</a>  
  <a href="#gallery" onclick="closeMob()">Gallery</a>  
  <a href="#location" onclick="closeMob()">Location</a>  
  <a href="#booking" onclick="closeMob()" style="color:var(--gold)">Book Now</a>  
</div>  
  
<!-- NAV -->  
<nav id="nav">  
  <a href="#" class="logo">Elegan<span>ce</span></a>  
  <ul class="nav-links">  
    <li><a href="#rooms">Rooms</a></li>  
    <li><a href="#experience">Experience</a></li>  
    <li><a href="#dining">Dining</a></li>  
    <li><a href="#gallery">Gallery</a></li>  
    <li><a href="#location">Location</a></li>  
  </ul>  
  <a href="#booking" class="nav-book">Book Now</a>  
  <div class="burger" id="burger" onclick="toggleMob()">  
    <span></span><span></span><span></span>  
  </div>  
</nav>  
  
<!-- HERO SLIDESHOW -->  
<section class="hero" id="hero">  
  <div class="slides" id="slides">  
    <div class="slide active">  
      <div class="slide-bg" style="background-image:url('https://images.unsplash.com/photo-1540541338287-41700207dee6?w=1800&q=85')"></div>  
      <div class="slide-overlay"></div>  
    </div>  
    <div class="slide">  
      <div class="slide-bg" style="background-image:url('https://images.unsplash.com/photo-1520250497591-112f2f40a3f4?w=1800&q=85')"></div>  
      <div class="slide-overlay"></div>  
    </div>  
    <div class="slide">  
      <div class="slide-bg" style="background-image:url('https://images.unsplash.com/photo-1582719478250-c89cae4dc85b?w=1800&q=85')"></div>  
      <div class="slide-overlay"></div>  
    </div>  
    <div class="slide">  
      <div class="slide-bg" style="background-image:url('https://images.unsplash.com/photo-1571896349842-33c89424de2d?w=1800&q=85')"></div>  
      <div class="slide-overlay"></div>  
    </div>  
    <div class="slide">  
      <div class="slide-bg" style="background-image:url('https://images.unsplash.com/photo-1573843981267-be1999ff37cd?w=1800&q=85')"></div>  
      <div class="slide-overlay"></div>  
    </div>  
  </div>  
  
  <div class="hero-content">  
    <p class="hero-tag" data-i18n="hero_tag">Marmaris · Turkey · 5 Star Luxury</p>  
    <h1 class="hero-h1">Where the <em>Mediterranean</em><br>meets Elegance</h1>  
    <p class="hero-sub" data-i18n="hero_sub">Boutique luxury on the turquoise shores of Marmaris. A world-class escape awaits you.</p>  
    <div class="hero-btns">  
      <button class="btn-g" onclick="document.getElementById('booking').scrollIntoView({behavior:'smooth'})" data-i18n="book_stay">Book Your Stay</button>  
      <a href="#rooms" class="btn-o" data-i18n="explore_rooms">Explore Rooms</a>  
    </div>  
  </div>  
  
  <button class="arr arr-l" onclick="changeSlide(-1)">‹</button>  
  <button class="arr arr-r" onclick="changeSlide(1)">›</button>  
  <div class="slide-dots" id="dots"></div>  
</section>  
  
<!-- LANGUAGE BAR -->  
<div class="lang-bar">  
  <button class="lang-btn active" onclick="setLang('en')">EN</button>  
  <button class="lang-btn" onclick="setLang('ru')">RU</button>  
  <button class="lang-btn" onclick="setLang('de')">DE</button>  
  <button class="lang-btn" onclick="setLang('tr')">TR</button>  
  <button class="lang-btn" onclick="setLang('ar')">AR</button>  
</div>  
  
<!-- BOOKING WIDGET -->  
<div class="booking-wrap" id="booking">  
  <div class="booking-inner">  
    <p class="booking-title" data-i18n="book_title">Reserve Your Stay</p>  
    <div class="booking-form">  
      <div class="form-group">  
        <label class="form-label" data-i18n="check_in">Check-in</label>  
        <input type="date" class="form-input" id="checkin">  
      </div>  
      <div class="form-group">  
        <label class="form-label" data-i18n="check_out">Check-out</label>  
        <input type="date" class="form-input" id="checkout">  
      </div>  
      <div class="form-group">  
        <label class="form-label" data-i18n="guests">Guests</label>  
        <select class="form-input" id="guests">  
          <option>1 Adult</option>  
          <option selected>2 Adults</option>  
          <option>2 Adults + 1 Child</option>  
          <option>2 Adults + 2 Children</option>  
          <option>3 Adults</option>  
          <option>4 Adults</option>  
        </select>  
      </div>  
      <div class="form-group">  
        <label class="form-label" data-i18n="room_type">Room Type</label>  
        <select class="form-input" id="roomtype">  
          <option data-i18n="any_room">Any Room</option>  
          <option>Executive Room</option>  
          <option>Corner Suite</option>  
          <option>De-Luxe Suite</option>  
          <option>Penthouse Suite</option>  
        </select>  
      </div>  
      <button class="book-submit" onclick="submitBooking()" data-i18n="check_avail">Check Availability</button>  
    </div>  
    <p class="booking-note" data-i18n="book_note">Best rate guaranteed · Free cancellation up to 48h · <a href="mailto:reservation@elegancehotels.com">reservation@elegancehotels.com</a></p>  
  </div>  
</div>  
  
<!-- STATS -->  
<div class="stats">  
  <div class="stat rv"><div class="stat-n">5★</div><div class="stat-l" data-i18n="s1">Star Rating</div></div>  
  <div class="stat rv rv1"><div class="stat-n">30+</div><div class="stat-l" data-i18n="s2">Years of Excellence</div></div>  
  <div class="stat rv rv2"><div class="stat-n">4</div><div class="stat-l" data-i18n="s3">Dining Venues</div></div>  
  <div class="stat rv rv3"><div class="stat-n">∞</div><div class="stat-l" data-i18n="s4">Mediterranean Views</div></div>  
</div>  
  
<!-- ROOMS -->  
<section class="section rooms-sec" id="rooms">  
  <div class="rooms-hd">  
    <div>  
      <p class="tag rv" data-i18n="accom">Accommodation</p>  
      <h2 class="sec-h rv rv1" data-i18n="rooms_h">Rooms &amp; <em>Suites</em></h2>  
    </div>  
    <a href="https://elegancehotels.com/en/rooms-suites" class="btn-o rv">View All</a>  
  </div>  
  <div class="rooms-grid">  
    <div class="room-c">  
      <div class="room-bg" style="background-image:url('https://images.unsplash.com/photo-1631049307264-da0ec9d70304?w=1200&q=80');min-height:600px"></div>  
      <div class="room-info">  
        <div class="r-tag" data-i18n="signature">Signature</div>  
        <h3 class="r-name">Executive Room</h3>  
        <a href="https://elegancehotels.com/en/rooms-suites/executive-room" class="r-link" data-i18n="discover">Discover</a>  
      </div>  
    </div>  
    <div class="room-c">  
      <div class="room-bg" style="background-image:url('https://images.unsplash.com/photo-1618773928121-c32242e63f39?w=900&q=80')"></div>  
      <div class="room-info">  
        <div class="r-tag" data-i18n="prestige">Prestige</div>  
        <h3 class="r-name">Corner Suite</h3>  
        <a href="https://elegancehotels.com/en/rooms-suites/corner-suit" class="r-link" data-i18n="discover">Discover</a>  
      </div>  
    </div>  
    <div class="room-c">  
      <div class="room-bg" style="background-image:url('https://images.unsplash.com/photo-1578683010236-d716f9a3f461?w=900&q=80')"></div>  
      <div class="room-info">  
        <div class="r-tag" data-i18n="ultimate">Ultimate</div>  
        <h3 class="r-name">De-Luxe Suite</h3>  
        <a href="https://elegancehotels.com/en/rooms-suites" class="r-link" data-i18n="discover">Discover</a>  
      </div>  
    </div>  
  </div>  
</section>  
  
<!-- EXPERIENCE TIMELINE -->  
<section class="section exp-sec" id="experience">  
  <p class="tag rv" data-i18n="day_tag">A Day at Elegance</p>  
  <h2 class="sec-h rv rv1" data-i18n="day_h">Your <em>Perfect</em> Day</h2>  
  <div class="exp-grid">  
    <div class="tl">  
      <div class="tl-item rv"><div class="tl-t">07:00</div><div><div class="tl-h" data-i18n="t1h">Breakfast Pleasure</div><p class="tl-p" data-i18n="t1p">A lavish open buffet at Begonville Restaurant. Turkish and world cuisine under the morning sun.</p></div></div>  
      <div class="tl-item rv rv1"><div class="tl-t">09:00</div><div><div class="tl-h" data-i18n="t2h">Life Spa & Wellness</div><p class="tl-p" data-i18n="t2p">Restore your body and soul with expert massages and aromatherapy treatments.</p></div></div>  
      <div class="tl-item rv rv2"><div class="tl-t">10:00</div><div><div class="tl-h" data-i18n="t3h">Hana Beach</div><p class="tl-p" data-i18n="t3p">Crystal Mediterranean waters and a private wooden pier. Your sun lounger awaits.</p></div></div>  
      <div class="tl-item rv"><div class="tl-t">13:00</div><div><div class="tl-h" data-i18n="t4h">Poolside Lunch</div><p class="tl-p" data-i18n="t4p">Fresh Mediterranean snacks at Silence Bar, with your feet in the cool water.</p></div></div>  
      <div class="tl-item rv rv1"><div class="tl-t">15:00</div><div><div class="tl-h" data-i18n="t5h">Water Sports</div><p class="tl-p" data-i18n="t5p">Parasailing, jet ski, banana boat — the Aegean is your playground.</p></div></div>  
      <div class="tl-item rv rv2"><div class="tl-t">19:00</div><div><div class="tl-h" data-i18n="t6h">Sunset at the Bay</div><p class="tl-p" data-i18n="t6p">The bay turns golden and still. One last swim before the evening begins.</p></div></div>  
      <div class="tl-item rv"><div class="tl-t">20:00</div><div><div class="tl-h" data-i18n="t7h">À La Carte Dinner</div><p class="tl-p" data-i18n="t7p">Candlelit dinner with panoramic bay views and impeccable Mediterranean cuisine.</p></div></div>  
      <div class="tl-item rv rv1"><div class="tl-t">21:30</div><div><div class="tl-h" data-i18n="t8h">Night Entertainment</div><p class="tl-p" data-i18n="t8p">Live shows and animation by the pool under the Marmaris stars.</p></div></div>  
      <div class="tl-item rv rv2"><div class="tl-t">23:00</div><div><div class="tl-h" data-i18n="t9h">Moonlit Cocktails</div><p class="tl-p" data-i18n="t9p">Phosphorescence on the sea and your favourite cocktail. A night to never forget.</p></div></div>  
    </div>  
    <div class="exp-imgs">  
      <div class="exp-img-main"></div>  
      <div class="exp-img-row">  
        <div style="background-image:url('https://images.unsplash.com/photo-1544161515-4ab6ce6db874?w=600&q=80')"></div>  
        <div style="background-image:url('https://images.unsplash.com/photo-1566073771259-6a8506099945?w=600&q=80')"></div>  
      </div>  
    </div>  
  </div>  
</section>  
  
<!-- AMENITIES -->  
<section class="section am-sec" id="amenities">  
  <p class="tag rv" data-i18n="fac_tag">Facilities</p>  
  <h2 class="sec-h rv rv1" data-i18n="fac_h">Everything You <em>Desire</em></h2>  
  <div class="am-grid">  
    <div class="am-card rv"><div class="am-ico">🏖️</div><div class="am-name">Hana Beach</div><div class="am-hrs">08:00 — 19:00</div><p class="am-desc" data-i18n="am1">Private beach with wooden pier and clear Mediterranean waters. Sun loungers, shade, and sea in perfect harmony.</p></div>  
    <div class="am-card rv rv1"><div class="am-ico">💆</div><div class="am-name">Life Spa & Wellness</div><div class="am-hrs">09:00 — 21:00</div><p class="am-desc" data-i18n="am2">Expert therapists, aromatic treatments, and a complete sanctuary from the everyday world.</p></div>  
    <div class="am-card rv rv2"><div class="am-ico">🏋️</div><div class="am-name">Life Athletic Club</div><div class="am-hrs">09:00 — 21:00</div><p class="am-desc" data-i18n="am3">Fully equipped fitness center with experienced trainers. Your routine, uninterrupted.</p></div>  
    <div class="am-card rv"><div class="am-ico">🌊</div><div class="am-name">Water Sports</div><div class="am-hrs">08:00 — 20:00</div><p class="am-desc" data-i18n="am4">Parasailing, jet skiing, banana boat and more. The Aegean is your playground.</p></div>  
    <div class="am-card rv rv1"><div class="am-ico">🎭</div><div class="am-name">Night Entertainment</div><div class="am-hrs">21:30 — 00:00</div><p class="am-desc" data-i18n="am5">Live shows and themed evenings by the pool — every night a different experience.</p></div>  
    <div class="am-card rv rv2"><div class="am-ico">🏊</div><div class="am-name">Silence Pool</div><div class="am-hrs">08:00 — 18:30</div><p class="am-desc" data-i18n="am6">Tranquil adults-only pool with snack service. Pure relaxation in hushed surroundings.</p></div>  
  </div>  
</section>  
  
<!-- DINING -->  
<section class="section din-sec" id="dining">  
  <p class="tag rv" data-i18n="din_tag">Gastronomy</p>  
  <h2 class="sec-h rv rv1" data-i18n="din_h">The Art of <em>Fine Dining</em></h2>  
  <div class="din-grid">  
    <div class="din-c rv">  
      <div class="din-bg" style="background-image:url('https://images.unsplash.com/photo-1414235077428-338989a2e8c0?w=1000&q=80')"></div>  
      <div class="din-ov"></div>  
      <div class="din-ct">  
        <span class="din-badge" data-i18n="open_buf">Open Buffet</span>  
        <h3 class="din-name">Begonville Restaurant</h3>  
        <p class="din-p" data-i18n="din1">Turkish and world cuisine at its finest. Lavish breakfast spreads and evening feasts morning to night.</p>  
        <a href="https://elegancehotels.com/en/restaurant-bar/open-buffet" class="din-lnk" data-i18n="explore_menu">Explore Menu</a>  
      </div>  
    </div>  
    <div class="din-c rv rv1">  
      <div class="din-bg" style="background-image:url('https://images.unsplash.com/photo-1559339352-11d035aa65de?w=1000&q=80')"></div>  
      <div class="din-ov"></div>  
      <div class="din-ct">  
        <span class="din-badge" data-i18n="a_la_c">À La Carte</span>  
        <h3 class="din-name">A La Carte Restaurant</h3>  
        <p class="din-p" data-i18n="din2">Mediterranean flavors elevated to art. Spectacular bay views, candlelit evenings, impeccable service.</p>  
        <a href="https://elegancehotels.com/en/restaurant-bar/a-la-carte" class="din-lnk" data-i18n="explore_menu">Explore Menu</a>  
      </div>  
    </div>  
  </div>  
</section>  
  
<!-- GALLERY -->  
<section class="section gal-sec" id="gallery">  
  <p class="tag rv" data-i18n="gal_tag">Gallery</p>  
  <h2 class="sec-h rv rv1" data-i18n="gal_h">Captured <em>Moments</em></h2>  
  <div class="gal-grid">  
    <div class="gal-item rv" onclick="openLB('https://images.unsplash.com/photo-1540541338287-41700207dee6?w=1600&q=90')">  
      <div class="gal-bg" style="background-image:url('https://images.unsplash.com/photo-1540541338287-41700207dee6?w=800&q=80')"></div>  
      <div class="gal-overlay"><div class="gal-icon">⊕</div></div>  
    </div>  
    <div class="gal-item rv rv1" onclick="openLB('https://images.unsplash.com/photo-1520250497591-112f2f40a3f4?w=1600&q=90')">  
      <div class="gal-bg" style="background-image:url('https://images.unsplash.com/photo-1520250497591-112f2f40a3f4?w=600&q=80')"></div>  
      <div class="gal-overlay"><div class="gal-icon">⊕</div></div>  
    </div>  
    <div class="gal-item rv rv2" onclick="openLB('https://images.unsplash.com/photo-1582719478250-c89cae4dc85b?w=1600&q=90')">  
      <div class="gal-bg" style="background-image:url('https://images.unsplash.com/photo-1582719478250-c89cae4dc85b?w=600&q=80')"></div>  
      <div class="gal-overlay"><div class="gal-icon">⊕</div></div>  
    </div>  
    <div class="gal-item rv" onclick="openLB('https://images.unsplash.com/photo-1571896349842-33c89424de2d?w=1600&q=90')">  
      <div class="gal-bg" style="background-image:url('https://images.unsplash.com/photo-1571896349842-33c89424de2d?w=600&q=80')"></div>  
      <div class="gal-overlay"><div class="gal-icon">⊕</div></div>  
    </div>  
    <div class="gal-item rv rv1" onclick="openLB('https://images.unsplash.com/photo-1414235077428-338989a2e8c0?w=1600&q=90')">  
      <div class="gal-bg" style="background-image:url('https://images.unsplash.com/photo-1414235077428-338989a2e8c0?w=600&q=80')"></div>  
      <div class="gal-overlay"><div class="gal-icon">⊕</div></div>  
    </div>  
    <div class="gal-item rv rv2" onclick="openLB('https://images.unsplash.com/photo-1573843981267-be1999ff37cd?w=1600&q=90')">  
      <div class="gal-bg" style="background-image:url('https://images.unsplash.com/photo-1573843981267-be1999ff37cd?w=600&q=80')"></div>  
      <div class="gal-overlay"><div class="gal-icon">⊕</div></div>  
    </div>  
    <div class="gal-item rv" onclick="openLB('https://images.unsplash.com/photo-1559339352-11d035aa65de?w=1600&q=90')">  
      <div class="gal-bg" style="background-image:url('https://images.unsplash.com/photo-1559339352-11d035aa65de?w=600&q=80')"></div>  
      <div class="gal-overlay"><div class="gal-icon">⊕</div></div>  
    </div>  
  </div>  
</section>  
  
<!-- REVIEWS -->  
<section class="section rev-sec">  
  <p class="tag rv" data-i18n="rev_tag">Guest Reviews</p>  
  <h2 class="sec-h rv rv1" data-i18n="rev_h">What Our Guests <em>Say</em></h2>  
  <div class="rev-grid">  
    <div class="rev-card rv">  
      <div class="rev-stars">★★★★★</div>  
      <p class="rev-text" data-i18n="rv1">"Absolutely breathtaking. The service was impeccable and the views from our suite were beyond anything we imagined. We will return every summer."</p>  
      <div class="rev-author">Sarah & Michael T.</div>  
      <div class="rev-src">TripAdvisor · London, UK</div>  
    </div>  
    <div class="rev-card rv rv1">  
      <div class="rev-stars">★★★★★</div>  
      <p class="rev-text" data-i18n="rv2">"Das beste Hotel, in dem wir je übernachtet haben. Das Essen war außergewöhnlich und das Personal überaus freundlich. Einfach perfekt."</p>  
      <div class="rev-author">Klaus & Ingrid M.</div>  
      <div class="rev-src">Booking.com · München, DE</div>  
    </div>  
    <div class="rev-card rv rv2">  
      <div class="rev-stars">★★★★★</div>  
      <p class="rev-text" data-i18n="rv3">"Незабываемый отдых. Пляж, спа, рестораны — всё на высшем уровне. Персонал относится к гостям как к королям."</p>  
      <div class="rev-author">Алексей В.</div>  
      <div class="rev-src">TripAdvisor · Москва, RU</div>  
    </div>  
  </div>  
</section>  
  
<!-- QUOTE -->  
<section class="quote-sec">  
  <p class="quote-big rv" data-i18n="q_text">"The real and the imaginary merge — where stars dance with the moon, and the scent of a thousand flowers fills the warm sea air."</p>  
  <div class="quote-src rv rv1" data-i18n="q_src">Elegance Hotels International · Marmaris, Turkey</div>  
</section>  
  
<!-- MAP & CONTACT -->  
<section class="section map-sec" id="location">  
  <p class="tag rv" data-i18n="loc_tag">Find Us</p>  
  <h2 class="sec-h rv rv1" data-i18n="loc_h">In the Heart of <em>Marmaris</em></h2>  
  <div class="map-layout">  
    <iframe class="map-frame"  
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3194.5!2d28.2718!3d36.8552!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x14be7b9c4de6c5e3%3A0x4cfda0e7e9f79af9!2sElegance%20Hotels%20International!5e0!3m2!1sen!2str!4v1683000000000!5m2!1sen!2str"  
      allowfullscreen="" loading="lazy">  
    </iframe>  
    <div class="map-info">  
      <div class="map-item rv">  
        <div class="map-ico">📍</div>  
        <div>  
          <div class="map-lbl" data-i18n="addr">Address</div>  
          <div class="map-val">Siteler Mh. 209 Sk. No:4<br>Marmaris, Muğla 48700<br>Turkey</div>  
        </div>  
      </div>  
      <div class="map-item rv rv1">  
        <div class="map-ico">📞</div>  
        <div>  
          <div class="map-lbl" data-i18n="phone">Phone</div>  
          <div class="map-val"><a href="tel:+902524177878">+90 252 417 78 78</a></div>  
        </div>  
      </div>  
      <div class="map-item rv rv2">  
        <div class="map-ico">✉️</div>  
        <div>  
          <div class="map-lbl" data-i18n="email_lbl">Email</div>  
          <div class="map-val">  
            <a href="mailto:reservation@elegancehotels.com">reservation@elegancehotels.com</a><br>  
            <a href="mailto:sales@elegancehotels.com">sales@elegancehotels.com</a>  
          </div>  
        </div>  
      </div>  
      <div class="map-item rv rv3">  
        <div class="map-ico">✈️</div>  
        <div>  
          <div class="map-lbl" data-i18n="airport">Airport</div>  
          <div class="map-val" data-i18n="airport_v">Dalaman Airport (DLM) — 90 km<br>Transfer available on request</div>  
        </div>  
      </div>  
      <a href="https://goo.gl/maps/marmaris" class="btn-g" style="width:fit-content;margin-top:8px;padding:12px 28px" target="_blank" data-i18n="get_dir">Get Directions →</a>  
    </div>  
  </div>  
</section>  
  
<!-- CTA -->  
<section class="cta-sec">  
  <div class="cta-pattern"></div>  
  <h2 class="cta-h rv" data-i18n="cta_h">Ready for your<br><em>Elegance</em> escape?</h2>  
  <p class="cta-p rv rv1" data-i18n="cta_p">Reserve your stay and let us craft the holiday of your dreams.</p>  
  <div class="cta-btns">  
    <button class="btn-g rv rv2" onclick="document.getElementById('booking').scrollIntoView({behavior:'smooth'})" data-i18n="book_now">Book Now</button>  
    <a href="mailto:reservation@elegancehotels.com" class="btn-o rv rv3" data-i18n="contact_us">Contact Us</a>  
  </div>  
</section>  
  
<!-- FOOTER -->  
<footer>  
  <div class="foot-g">  
    <div>  
      <a href="#" class="foot-logo">Elegan<span>ce</span></a>  
      <p class="foot-about" data-i18n="foot_about">A five-star boutique hotel on the turquoise shores of Marmaris, where Mediterranean luxury and warm Turkish hospitality meet.</p>  
    </div>  
    <div>  
      <p class="foot-col-t" data-i18n="f_explore">Explore</p>  
      <ul class="foot-links">  
        <li><a href="https://elegancehotels.com/en/overview" data-i18n="f_about">About Us</a></li>  
        <li><a href="https://elegancehotels.com/en/rooms-suites" data-i18n="f_rooms">Rooms & Suites</a></li>  
        <li><a href="#gallery" data-i18n="f_gal">Gallery</a></li>  
        <li><a href="https://elegancehotels.com/en/meeting/balo-conference" data-i18n="f_meet">Meetings & Events</a></li>  
        <li><a href="https://elegancehotels.com/en/opportunities" data-i18n="f_opp">Opportunities</a></li>  
      </ul>  
    </div>  
    <div>  
      <p class="foot-col-t" data-i18n="f_world">Elegance World</p>  
      <ul class="foot-links">  
        <li><a href="https://elegancehotels.com/en/activities/beach-pool/hana-beach" data-i18n="f_beach">Beach & Pool</a></li>  
        <li><a href="https://elegancehotels.com/en/activities/spa-wellness/massage" data-i18n="f_spa">Spa & Wellness</a></li>  
        <li><a href="https://elegancehotels.com/en/activities/water-sports" data-i18n="f_ws">Water Sports</a></li>  
        <li><a href="https://elegancehotels.com/en/activities/entertainment" data-i18n="f_ent">Entertainment</a></li>  
        <li><a href="https://elegancehotels.com/en/restaurant-bar/a-la-carte" data-i18n="f_din">Dining</a></li>  
      </ul>  
    </div>  
    <div>  
      <p class="foot-col-t" data-i18n="f_con">Contact</p>  
      <ul class="foot-links">  
        <li><a href="tel:+902524177878">+90 252 417 78 78</a></li>  
        <li><a href="mailto:reservation@elegancehotels.com" data-i18n="f_res">Reservations</a></li>  
        <li><a href="mailto:sales@elegancehotels.com" data-i18n="f_sales">Sales</a></li>  
        <li><a href="#location" data-i18n="f_dir">Directions</a></li>  
      </ul>  
    </div>  
  </div>  
  <div class="foot-bot">  
    <p class="foot-c">© 2026 Elegance Hotels International · Marmaris, Turkey</p>  
    <div class="socials">  
      <a href="http://www.tripadvisor.com.tr/Hotel_Review-g298033-d300033-Reviews-Elegance_Hotel-Marmaris_Mugla_Province_Turkish_Aegean_Coast.html" class="soc" target="_blank" title="TripAdvisor">★</a>  
      <a href="#" class="soc" title="Instagram">◈</a>  
      <a href="#" class="soc" title="Facebook">ƒ</a>  
    </div>  
  </div>  
</footer>  
  
<script>  
// ── CURSOR  
const cur=document.getElementById('cur'),curR=document.getElementById('curR');  
let mx=0,my=0;  
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;cur.style.left=mx+'px';cur.style.top=my+'px'});  
(function animR(){curR.style.left=mx+'px';curR.style.top=my+'px';requestAnimationFrame(animR)})();  
  
// ── PROGRESS BAR  
window.addEventListener('scroll',()=>{  
  const p=window.scrollY/(document.documentElement.scrollHeight-window.innerHeight);  
  document.getElementById('prog').style.width=(p*100)+'%';  
  document.getElementById('nav').classList.toggle('solid',window.scrollY>80);  
});  
  
// ── MOBILE MENU  
let mobOpen=false;  
function toggleMob(){mobOpen=!mobOpen;document.getElementById('mobMenu').classList.toggle('open',mobOpen)}  
function closeMob(){mobOpen=false;document.getElementById('mobMenu').classList.remove('open')}  
  
// ── HERO SLIDESHOW  
let cur_s=0,timer;  
const slides=document.querySelectorAll('.slide');  
const dotsEl=document.getElementById('dots');  
slides.forEach((_,i)=>{const d=document.createElement('div');d.className='dot'+(i===0?' active':'');d.onclick=()=>goSlide(i);dotsEl.appendChild(d)});  
function goSlide(n){slides[cur_s].classList.remove('active');cur_s=(n+slides.length)%slides.length;slides[cur_s].classList.add('active');document.querySelectorAll('.dot').forEach((d,i)=>d.classList.toggle('active',i===cur_s));clearInterval(timer);timer=setInterval(()=>changeSlide(1),6000)}  
function changeSlide(d){goSlide(cur_s+d)}  
timer=setInterval(()=>changeSlide(1),6000);  
  
// ── REVEAL  
const rvEls=document.querySelectorAll('.rv');  
const rvObs=new IntersectionObserver(es=>{es.forEach(e=>{if(e.isIntersecting){e.target.classList.add('in');rvObs.unobserve(e.target)}})},{threshold:.1});  
rvEls.forEach(el=>rvObs.observe(el));  
  
// ── LIGHTBOX  
function openLB(src){document.getElementById('lbImg').src=src;document.getElementById('lb').classList.add('open')}  
function closeLB(){document.getElementById('lb').classList.remove('open')}  
document.getElementById('lb').onclick=e=>{if(e.target===document.getElementById('lb'))closeLB()};  
document.addEventListener('keydown',e=>{if(e.key==='Escape')closeLB()});  
  
// ── BOOKING  
function submitBooking(){  
  const ci=document.getElementById('checkin').value;  
  const co=document.getElementById('checkout').value;  
  if(!ci||!co){showNotif('Please select your check-in and check-out dates.');return}  
  if(new Date(co)<=new Date(ci)){showNotif('Check-out must be after check-in.');return}  
  window.open('https://be.extranetwork.com/33fc1929-864c-212b-fef1-05c2f6418a3a/en','_blank');  
  showNotif(translations[currentLang]?.notif_ok||'Redirecting to booking system...');  
}  
function showNotif(msg){const n=document.getElementById('notif');n.textContent=msg;n.classList.add('show');setTimeout(()=>n.classList.remove('show'),4000)}  
  
// Set today as default check-in, tomorrow as check-out  
const today=new Date(),tmrw=new Date(today);tmrw.setDate(tmrw.getDate()+1);  
document.getElementById('checkin').value=today.toISOString().split('T')[0];  
document.getElementById('checkout').value=tmrw.toISOString().split('T')[0];  
  
// ── I18N  
let currentLang='en';  
const translations={  
  en:{  
    hero_tag:'Marmaris · Turkey · 5 Star Luxury',hero_sub:'Boutique luxury on the turquoise shores of Marmaris. A world-class escape awaits you.',  
    book_stay:'Book Your Stay',explore_rooms:'Explore Rooms',book_title:'Reserve Your Stay',  
    check_in:'Check-in',check_out:'Check-out',guests:'Guests',room_type:'Room Type',check_avail:'Check Availability',any_room:'Any Room',  
    book_note:'Best rate guaranteed · Free cancellation up to 48h · reservation@elegancehotels.com',  
    s1:'Star Rating',s2:'Years of Excellence',s3:'Dining Venues',s4:'Mediterranean Views',  
    accom:'Accommodation',rooms_h:'Rooms & Suites',  
    day_tag:'A Day at Elegance',day_h:'Your Perfect Day',  
    t1h:'Breakfast Pleasure',t1p:'A lavish open buffet at Begonville Restaurant. Turkish and world cuisine under the morning sun.',  
    t2h:'Life Spa & Wellness',t2p:'Restore body and soul with expert massages and aromatherapy treatments.',  
    t3h:'Hana Beach',t3p:'Crystal Mediterranean waters and a private wooden pier. Your sun lounger awaits.',  
    t4h:'Poolside Lunch',t4p:'Fresh Mediterranean snacks at Silence Bar, with your feet in the cool water.',  
    t5h:'Water Sports',t5p:'Parasailing, jet ski, banana boat — the Aegean is your playground.',  
    t6h:'Sunset at the Bay',t6p:'The bay turns golden and still. One last swim before the evening begins.',  
    t7h:'À La Carte Dinner',t7p:'Candlelit dinner with panoramic bay views and impeccable Mediterranean cuisine.',  
    t8h:'Night Entertainment',t8p:'Live shows and animation by the pool under the Marmaris stars.',  
    t9h:'Moonlit Cocktails',t9p:'Phosphorescence on the sea and your favourite cocktail. A night to never forget.',  
    fac_tag:'Facilities',fac_h:'Everything You Desire',  
    am1:'Private beach with wooden pier. Sun loungers, shade, and sea in perfect harmony.',  
    am2:'Expert therapists, aromatic treatments, and a complete sanctuary from the everyday.',  
    am3:'Fully equipped fitness center with experienced trainers. Your routine, uninterrupted.',  
    am4:'Parasailing, jet skiing, banana boat and more. The Aegean is your playground.',  
    am5:'Live shows and themed evenings by the pool — every night a different experience.',  
    am6:'Tranquil adults-only pool with snack service. Pure relaxation in hushed surroundings.',  
    din_tag:'Gastronomy',din_h:'The Art of Fine Dining',  
    open_buf:'Open Buffet',a_la_c:'À La Carte',  
    din1:'Turkish and world cuisine at its finest. Lavish breakfast spreads and evening feasts morning to night.',  
    din2:'Mediterranean flavors elevated to art. Spectacular bay views, candlelit evenings, impeccable service.',  
    explore_menu:'Explore Menu',  
    gal_tag:'Gallery',gal_h:'Captured Moments',  
    rev_tag:'Guest Reviews',rev_h:'What Our Guests Say',  
    rv1:'"Absolutely breathtaking. The service was impeccable and the views from our suite were beyond anything we imagined."',  
    rv2:'"Das beste Hotel, in dem wir je übernachtet haben. Das Essen war außergewöhnlich und das Personal überaus freundlich."',  
    rv3:'"Незабываемый отдых. Пляж, спа, рестораны — всё на высшем уровне."',  
    q_text:'"The real and the imaginary merge — where stars dance with the moon, and the scent of a thousand flowers fills the warm sea air."',  
    q_src:'Elegance Hotels International · Marmaris, Turkey',  
    loc_tag:'Find Us',loc_h:'In the Heart of Marmaris',  
    addr:'Address',phone:'Phone',email_lbl:'Email',airport:'Nearest Airport',airport_v:'Dalaman Airport (DLM) — 90 km · Transfer available on request',get_dir:'Get Directions →',  
    cta_h:'Ready for your Elegance escape?',cta_p:'Reserve your stay and let us craft the holiday of your dreams.',  
    book_now:'Book Now',contact_us:'Contact Us',  
    foot_about:'A five-star boutique hotel on the turquoise shores of Marmaris, where Mediterranean luxury meets warm Turkish hospitality.',  
    f_explore:'Explore',f_about:'About Us',f_rooms:'Rooms & Suites',f_gal:'Gallery',f_meet:'Meetings & Events',f_opp:'Opportunities',  
    f_world:'Elegance World',f_beach:'Beach & Pool',f_spa:'Spa & Wellness',f_ws:'Water Sports',f_ent:'Entertainment',f_din:'Dining',  
    f_con:'Contact',f_res:'Reservations',f_sales:'Sales',f_dir:'Directions',  
    signature:'Signature',prestige:'Prestige',ultimate:'Ultimate',discover:'Discover',  
    notif_ok:'Redirecting to booking system...'  
  },  
  ru:{  
    hero_tag:'Мармарис · Турция · Люкс 5 Звёзд',hero_sub:'Бутик-отель на бирюзовых берегах Мармариса. Отдых мирового класса ждёт вас.',  
    book_stay:'Забронировать',explore_rooms:'Смотреть номера',book_title:'Забронировать проживание',  
    check_in:'Заезд',check_out:'Выезд',guests:'Гости',room_type:'Тип номера',check_avail:'Проверить доступность',any_room:'Любой номер',  
    book_note:'Лучшая цена гарантирована · Бесплатная отмена за 48ч · reservation@elegancehotels.com',  
    s1:'Звёздный рейтинг',s2:'Лет совершенства',s3:'Ресторана и бара',s4:'Виды на Средиземноморье',  
    accom:'Размещение',rooms_h:'Номера и Люксы',  
    day_tag:'День в Elegance',day_h:'Ваш идеальный день',  
    t1h:'Завтрак',t1p:'Роскошный шведский стол в ресторане Begonville. Турецкая и мировая кухня под утренним солнцем.',  
    t2h:'Life Spa & Wellness',t2p:'Восстановите тело и душу с профессиональными массажами и ароматерапией.',  
    t3h:'Пляж Hana',t3p:'Кристально чистые воды Средиземного моря и частный деревянный пирс.',  
    t4h:'Обед у бассейна',t4p:'Свежие средиземноморские закуски в Silence Bar.',  
    t5h:'Водные виды спорта',t5p:'Парасейлинг, джет-ски, банан — Эгейское море в вашем распоряжении.',  
    t6h:'Закат в бухте',t6p:'Бухта становится золотой и тихой. Последний заплыв перед вечером.',  
    t7h:'Ужин à la carte',t7p:'Ужин при свечах с панорамным видом на бухту и превосходной средиземноморской кухней.',  
    t8h:'Ночные шоу',t8p:'Живые выступления и анимация у бассейна под звёздами Мармариса.',  
    t9h:'Коктейли при луне',t9p:'Биолюминесценция моря и ваш любимый коктейль. Ночь, которую невозможно забыть.',  
    fac_tag:'Удобства',fac_h:'Всё что вы пожелаете',  
    am1:'Частный пляж с деревянным пирсом. Шезлонги, тень и море в идеальной гармонии.',  
    am2:'Профессиональные терапевты, ароматические процедуры и полное убежище от повседневного мира.',  
    am3:'Полностью оборудованный фитнес-центр с опытными тренерами.',  
    am4:'Парасейлинг, джет-ски, банан и многое другое. Эгейское море — ваша площадка.',  
    am5:'Живые шоу и тематические вечера у бассейна — каждую ночь новые впечатления.',  
    am6:'Спокойный бассейн только для взрослых со снек-сервисом. Чистый отдых.',  
    din_tag:'Гастрономия',din_h:'Искусство изысканной кухни',  
    open_buf:'Шведский стол',a_la_c:'À La Carte',  
    din1:'Турецкая и мировая кухня в лучшем виде. Роскошные завтраки и вечерние пиры.',  
    din2:'Средиземноморская кухня, возведённая в искусство. Вид на бухту, свечи, безупречный сервис.',  
    explore_menu:'Посмотреть меню',  
    gal_tag:'Галерея',gal_h:'Запечатлённые мгновения',  
    rev_tag:'Отзывы гостей',rev_h:'Что говорят наши гости',  
    rv1:'"Абсолютно захватывающе. Сервис был безупречен, а виды из люкса превзошли все ожидания."',  
    rv2:'"Das beste Hotel, in dem wir je übernachtet haben. Einfach perfekt."',  
    rv3:'"Незабываемый отдых. Пляж, спа, рестораны — всё на высшем уровне. Персонал относится к гостям как к королям."',  
    q_text:'"Реальное и воображаемое сливаются воедино — где звёзды танцуют с луной, а аромат тысяч цветов наполняет тёплый морской воздух."',  
    q_src:'Elegance Hotels International · Мармарис, Турция',  
    loc_tag:'Как нас найти',loc_h:'В сердце Мармариса',  
    addr:'Адрес',phone:'Телефон',email_lbl:'Электронная почта',airport:'Ближайший аэропорт',airport_v:'Аэропорт Даламан (DLM) — 90 км · Трансфер по запросу',get_dir:'Проложить маршрут →',  
    cta_h:'Готовы к отдыху в Elegance?',cta_p:'Забронируйте номер и позвольте нам создать отпуск вашей мечты.',  
    book_now:'Забронировать',contact_us:'Связаться с нами',  
    foot_about:'Пятизвёздочный бутик-отель на бирюзовых берегах Мармариса, где средиземноморская роскошь встречается с тёплым турецким гостеприимством.',  
    f_explore:'Навигация',f_about:'О нас',f_rooms:'Номера и люксы',f_gal:'Галерея',f_meet:'Конференции',f_opp:'Вакансии',  
    f_world:'Мир Elegance',f_beach:'Пляж и бассейн',f_spa:'Спа и велнес',f_ws:'Водные виды спорта',f_ent:'Развлечения',f_din:'Рестораны',  
    f_con:'Контакты',f_res:'Бронирование',f_sales:'Продажи',f_dir:'Маршрут',  
    signature:'Сигнатурный',prestige:'Престиж',ultimate:'Ультима',discover:'Узнать больше',  
    notif_ok:'Переходим к системе бронирования...'  
  },  
  de:{  
    hero_tag:'Marmaris · Türkei · 5-Sterne Luxus',hero_sub:'Boutique-Luxus an der türkisfarbenen Küste von Marmaris. Ein erstklassiger Rückzugsort erwartet Sie.',  
    book_stay:'Jetzt buchen',explore_rooms:'Zimmer entdecken',book_title:'Ihren Aufenthalt reservieren',  
    check_in:'Anreise',check_out:'Abreise',guests:'Gäste',room_type:'Zimmertyp',check_avail:'Verfügbarkeit prüfen',any_room:'Beliebiges Zimmer',  
    book_note:'Bestpreisgarantie · Kostenlose Stornierung bis 48h · reservation@elegancehotels.com',  
    s1:'Sternebewertung',s2:'Jahre Exzellenz',s3:'Restaurants & Bars',s4:'Mittelmeerblicke',  
    accom:'Unterkunft',rooms_h:'Zimmer & Suiten',  
    day_tag:'Ein Tag im Elegance',day_h:'Ihr perfekter Tag',  
    t1h:'Frühstücksgenuss',t1p:'Ein üppiges Buffet im Begonville Restaurant. Türkische und internationale Küche.',  
    t2h:'Life Spa & Wellness',t2p:'Erholen Sie sich mit Massagen und Aromatherapie.',  
    t3h:'Hana Beach',t3p:'Kristallklares Mittelmeer und ein privater Holzsteg.',  
    t4h:'Mittagessen am Pool',t4p:'Frische mediterrane Snacks an der Silence Bar.',  
    t5h:'Wassersport',t5p:'Parasailing, Jetski, Banane — das Ägäische Meer gehört Ihnen.',  
    t6h:'Sonnenuntergang in der Bucht',t6p:'Die Bucht wird golden und still. Ein letztes Bad vor dem Abend.',  
    t7h:'À La Carte Abendessen',t7p:'Kerzenschein-Dinner mit Panoramablick auf die Bucht.',  
    t8h:'Nachtshow',t8p:'Live-Shows und Animation am Pool unter den Sternen von Marmaris.',  
    t9h:'Cocktails im Mondschein',t9p:'Meeresleuchten und Ihr Lieblingscocktail. Eine unvergessliche Nacht.',  
    fac_tag:'Einrichtungen',fac_h:'Alles was Sie wünschen',  
    am1:'Privater Strand mit Holzsteg. Liegestühle, Schatten und Meer in perfekter Harmonie.',  
    am2:'Professionelle Therapeuten, aromatische Behandlungen und ein vollständiges Refugium.',  
    am3:'Voll ausgestattetes Fitnesscenter mit erfahrenen Trainern.',  
    am4:'Parasailing, Jetski, Banane und mehr. Das Ägäische Meer ist Ihr Spielplatz.',  
    am5:'Live-Shows und Themenabende am Pool — jede Nacht ein neues Erlebnis.',  
    am6:'Ruhiger Erwachsenenpool mit Snackservice. Pure Entspannung.',  
    din_tag:'Gastronomie',din_h:'Die Kunst der feinen Küche',  
    open_buf:'Offenes Buffet',a_la_c:'À La Carte',  
    din1:'Türkische und internationale Küche vom Feinsten. Üppige Frühstücke und Abendessen.',  
    din2:'Mediterrane Aromen als Kunst. Panoramablick, Kerzenlicht, tadelloser Service.',  
    explore_menu:'Speisekarte entdecken',  
    gal_tag:'Galerie',gal_h:'Festgehaltene Momente',  
    rev_tag:'Gästebewertungen',rev_h:'Was unsere Gäste sagen',  
    rv1:'"Absolut atemberaubend. Der Service war tadellos und die Aussicht von unserer Suite war unbeschreiblich."',  
    rv2:'"Das beste Hotel, in dem wir je übernachtet haben. Das Essen war außergewöhnlich und das Personal überaus freundlich. Einfach perfekt."',  
    rv3:'"Незабываемый отдых. Всё на высшем уровне."',  
    q_text:'"Das Reale und Vorgestellte verschmelzen — wo Sterne mit dem Mond tanzen und der Duft tausend Blumen die warme Meeresluft erfüllt."',  
    q_src:'Elegance Hotels International · Marmaris, Türkei',  
    loc_tag:'Uns finden',loc_h:'Im Herzen von Marmaris',  
    addr:'Adresse',phone:'Telefon',email_lbl:'E-Mail',airport:'Nächster Flughafen',airport_v:'Flughafen Dalaman (DLM) — 90 km · Transfer auf Anfrage',get_dir:'Route planen →',  
    cta_h:'Bereit für Ihren Elegance-Urlaub?',cta_p:'Reservieren Sie Ihren Aufenthalt und lassen Sie uns Ihren Traumurlaub gestalten.',  
    book_now:'Jetzt buchen',contact_us:'Kontaktieren Sie uns',  
    foot_about:'Ein Fünf-Sterne-Boutiquehotel an der türkisfarbenen Küste von Marmaris.',  
    f_explore:'Erkunden',f_about:'Über uns',f_rooms:'Zimmer & Suiten',f_gal:'Galerie',f_meet:'Konferenzen',f_opp:'Stellenangebote',  
    f_world:'Elegance Welt',f_beach:'Strand & Pool',f_spa:'Spa & Wellness',f_ws:'Wassersport',f_ent:'Unterhaltung',f_din:'Gastronomie',  
    f_con:'Kontakt',f_res:'Reservierungen',f_sales:'Verkauf',f_dir:'Wegbeschreibung',  
    signature:'Signature',prestige:'Prestige',ultimate:'Ultimate',discover:'Entdecken',  
    notif_ok:'Weiterleitung zum Buchungssystem...'  
  },  
  tr:{  
    hero_tag:'Marmaris · Türkiye · 5 Yıldızlı Lüks',hero_sub:'Marmaris\'in turkuaz kıyılarında butik lüks. Dünya standartlarında bir kaçış sizi bekliyor.',  
    book_stay:'Rezervasyon Yap',explore_rooms:'Odaları Keşfet',book_title:'Konaklamanızı Rezerve Edin',  
    check_in:'Giriş Tarihi',check_out:'Çıkış Tarihi',guests:'Misafirler',room_type:'Oda Tipi',check_avail:'Uygunluk Kontrol Et',any_room:'Herhangi Bir Oda',  
    book_note:'En iyi fiyat garantisi · 48 saate kadar ücretsiz iptal · reservation@elegancehotels.com',  
    s1:'Yıldız Derecelendirmesi',s2:'Yıllık Mükemmellik',s3:'Yeme-İçme Mekanı',s4:'Akdeniz Manzarası',  
    accom:'Konaklama',rooms_h:'Odalar ve Süitler',  
    day_tag:'Elegance\'ta Bir Gün',day_h:'Mükemmel Gününüz',  
    t1h:'Kahvaltı Keyfi',t1p:'Begonville Restoran\'da açık büfe. Türk ve dünya mutfağından lezzetler.',  
    t2h:'Life Spa & Wellness',t2p:'Uzman masajlar ve aromaterapi ile beden ve ruhu yenileyin.',  
    t3h:'Hana Beach',t3p:'Kristal berraklığında Akdeniz suları ve özel ahşap iskele.',  
    t4h:'Havuz Başında Öğle',t4p:'Silence Bar\'da taze Akdeniz mezeler, ayaklarınız serin suda.',  
    t5h:'Su Sporları',t5p:'Parasailing, jet ski, muz tekne — Ege sizin oyun alanınız.',  
    t6h:'Koyda Gün Batımı',t6p:'Koy altın rengi ve sakin. Akşam başlamadan son bir yüzüş.',  
    t7h:'À La Carte Akşam Yemeği',t7p:'Koy manzaralı mum ışığında akşam yemeği ve enfes Akdeniz mutfağı.',  
    t8h:'Gece Gösterileri',t8p:'Marmaris yıldızları altında havuz başında canlı şovlar.',  
    t9h:'Ay Işığında Kokteyller',t9p:'Denizin biyolüminesansı ve favori kokteylniz. Unutulmaz bir gece.',  
    fac_tag:'Tesisler',fac_h:'Her İstediğiniz Burada',  
    am1:'Ahşap iskeleli özel plaj. Şezlonglar, gölge ve deniz mükemmel uyum içinde.',  
    am2:'Uzman terapistler, aromatik tedaviler ve günlük hayattan tam bir kaçış.',  
    am3:'Deneyimli antrenörlerle tam donanımlı fitness merkezi.',  
    am4:'Parasailing, jet ski, muz tekne ve daha fazlası.',  
    am5:'Havuz başında canlı şovlar — her gece farklı bir deneyim.',  
    am6:'Yalnızca yetişkinlere özel sakin havuz ve atıştırmalık servisi.',  
    din_tag:'Gastronomi',din_h:'İnce Yemek Sanatı',  
    open_buf:'Açık Büfe',a_la_c:'À La Carte',  
    din1:'Türk ve dünya mutfağının en iyisi. Sabahtan geceye kadar zengin seçenekler.',  
    din2:'Sanata dönüştürülmüş Akdeniz lezzetleri. Muhteşem koy manzarası ve mum ışığı.',  
    explore_menu:'Menüyü Keşfet',  
    gal_tag:'Galeri',gal_h:'Yakalanan Anlar',  
    rev_tag:'Misafir Yorumları',rev_h:'Misafirlerimiz Ne Diyor',  
    rv1:'"Nefes kesici güzellikte. Hizmet mükemmeldi ve süitimizdeki manzara hayal ettiğimizin çok ötesindeydi."',  
    rv2:'"Das beste Hotel, in dem wir je übernachtet haben. Einfach perfekt."',  
    rv3:'"Unutulmaz bir tatil. Her şey mükemmeldi."',  
    q_text:'"Gerçek ve hayal birleşiyor — yıldızların ay ile dans ettiği, binlerce çiçeğin kokusunun sıcak deniz havasını doldurduğu bir yer."',  
    q_src:'Elegance Hotels International · Marmaris, Türkiye',  
    loc_tag:'Bizi Bulun',loc_h:'Marmaris\'in Kalbinde',  
    addr:'Adres',phone:'Telefon',email_lbl:'E-posta',airport:'En Yakın Havalimanı',airport_v:'Dalaman Havalimanı (DLM) — 90 km · Transfer talep üzerine',get_dir:'Yol Tarifi Al →',  
    cta_h:'Elegance kaçışına hazır mısınız?',cta_p:'Konaklamanızı rezerve edin ve hayalinizdeki tatili birlikte yaratalım.',  
    book_now:'Şimdi Rezervasyon Yap',contact_us:'Bize Ulaşın',  
    foot_about:'Marmaris\'in turkuaz kıyılarında, Akdeniz lüksü ve sıcak Türk misafirperverliğinin buluştuğu beş yıldızlı butik otel.',  
    f_explore:'Keşfet',f_about:'Hakkımızda',f_rooms:'Odalar ve Süitler',f_gal:'Galeri',f_meet:'Toplantılar ve Etkinlikler',f_opp:'Fırsatlar',  
    f_world:'Elegance Dünyası',f_beach:'Plaj ve Havuz',f_spa:'Spa ve Wellness',f_ws:'Su Sporları',f_ent:'Eğlence',f_din:'Yeme-İçme',  
    f_con:'İletişim',f_res:'Rezervasyon',f_sales:'Satış',f_dir:'Yön',  
    signature:'Özel',prestige:'Prestij',ultimate:'Üstün',discover:'Keşfet',  
    notif_ok:'Rezervasyon sistemine yönlendiriliyor...'  
  },  
  ar:{  
    hero_tag:'مرماريس · تركيا · فاخر ٥ نجوم',hero_sub:'رفاهية فندقية على شواطئ مرماريس الفيروزية. تجربة استثنائية في انتظارك.',  
    book_stay:'احجز إقامتك',explore_rooms:'استكشف الغرف',book_title:'احجز إقامتك',  
    check_in:'تاريخ الوصول',check_out:'تاريخ المغادرة',guests:'الضيوف',room_type:'نوع الغرفة',check_avail:'تحقق من الإتاحة',any_room:'أي غرفة',  
    book_note:'ضمان أفضل سعر · إلغاء مجاني حتى 48 ساعة · reservation@elegancehotels.com',  
    s1:'التقييم النجمي',s2:'سنوات من التميز',s3:'أماكن تناول الطعام',s4:'إطلالات على المتوسط',  
    accom:'الإقامة',rooms_h:'الغرف والأجنحة',  
    day_tag:'يوم في إليغانس',day_h:'يومك المثالي',  
    t1h:'متعة الإفطار',t1p:'بوفيه مفتوح فاخر في مطعم بيغونفيل. مأكولات تركية وعالمية.',  
    t2h:'سبا الحياة والعافية',t2p:'جدد جسمك وروحك مع المساج والعلاجات العطرية.',  
    t3h:'شاطئ هانا',t3p:'مياه البحر المتوسط الصافية ورصيف خشبي خاص.',  
    t4h:'غداء على حافة المسبح',t4p:'مقبلات متوسطية طازجة في سيلنس بار.',  
    t5h:'رياضات مائية',t5p:'التزلج الهوائي، جت سكي، موز — بحر إيجه ملعبك.',  
    t6h:'غروب الشمس في الخليج',t6p:'الخليج يتحول ذهبياً وهادئاً. سباحة أخيرة قبل المساء.',  
    t7h:'عشاء à la carte',t7p:'عشاء رومانسي بإطلالة بانورامية على الخليج.',  
    t8h:'عروض ليلية',t8p:'عروض حية وأنيميشن عند المسبح تحت نجوم مرماريس.',  
    t9h:'كوكتيل تحت ضوء القمر',t9p:'بيولومينيسنس البحر وكوكتيلك المفضل. ليلة لا تُنسى.',  
    fac_tag:'المرافق',fac_h:'كل ما تتمناه',  
    am1:'شاطئ خاص مع رصيف خشبي. كراسي شمسية وظل ومياه صافية.',  
    am2:'معالجون خبراء وعلاجات عطرية في ملاذ هادئ بعيد عن صخب الحياة.',  
    am3:'مركز لياقة بدنية مجهز بالكامل مع مدربين متمرسين.',  
    am4:'التزلج الهوائي، جت سكي، موز والمزيد.',  
    am5:'عروض حية وأمسيات مميزة عند المسبح — تجربة مختلفة كل ليلة.',  
    am6:'مسبح هادئ للبالغين فقط مع خدمة المقبلات.',  
    din_tag:'فن الطهي',din_h:'فن المطبخ الراقي',  
    open_buf:'بوفيه مفتوح',a_la_c:'À La Carte',  
    din1:'أفضل المأكولات التركية والعالمية. إفطارات فاخرة وولائم مسائية.',  
    din2:'النكهات المتوسطية ترتقي إلى مستوى الفن. إطلالة على الخليج وشموع وخدمة لا تشوبها شائبة.',  
    explore_menu:'استكشف القائمة',  
    gal_tag:'معرض الصور',gal_h:'لحظات مُلتقطة',  
    rev_tag:'آراء الضيوف',rev_h:'ماذا يقول ضيوفنا',  
    rv1:'"خلاب للغاية. الخدمة كانت لا تشوبها شائبة والإطلالة من الجناح فاقت كل توقعاتنا."',  
    rv2:'"أفضل فندق نزلنا فيه على الإطلاق. الطعام رائع والموظفون ودودون للغاية."',  
    rv3:'"إجازة لا تُنسى. الشاطئ والسبا والمطاعم — كل شيء على أعلى مستوى."',  
    q_text:'"يتلاقى الواقع والخيال — حيث ترقص النجوم مع القمر وتملأ رائحة آلاف الزهور الهواء البحري الدافئ."',  
    q_src:'إليغانس هوتيلز إنترناشيونال · مرماريس، تركيا',  
    loc_tag:'ابحث عنا',loc_h:'في قلب مرماريس',  
    addr:'العنوان',phone:'الهاتف',email_lbl:'البريد الإلكتروني',airport:'أقرب مطار',airport_v:'مطار دالامان (DLM) — 90 كم · التوصيل متاح عند الطلب',get_dir:'الحصول على الاتجاهات ←',  
    cta_h:'هل أنت مستعد لتجربة إليغانس؟',cta_p:'احجز إقامتك ودعنا نصمم لك إجازة أحلامك.',  
    book_now:'احجز الآن',contact_us:'تواصل معنا',  
    foot_about:'فندق بوتيك خمس نجوم على شواطئ مرماريس الفيروزية، حيث يلتقي الفخر المتوسطي بالضيافة التركية الدافئة.',  
    f_explore:'استكشف',f_about:'من نحن',f_rooms:'الغرف والأجنحة',f_gal:'المعرض',f_meet:'الاجتماعات والفعاليات',f_opp:'الفرص',  
    f_world:'عالم إليغانس',f_beach:'الشاطئ والمسبح',f_spa:'سبا وعافية',f_ws:'رياضات مائية',f_ent:'الترفيه',f_din:'المطاعم',  
    f_con:'تواصل',f_res:'الحجوزات',f_sales:'المبيعات',f_dir:'الاتجاهات',  
    signature:'مميز',prestige:'بريستيج',ultimate:'ألتيميت',discover:'اكتشف',  
    notif_ok:'يتم التوجيه إلى نظام الحجز...'  
  }  
};  
  
function setLang(lang){  
  currentLang=lang;  
  document.querySelectorAll('.lang-btn').forEach(b=>b.classList.toggle('active',b.textContent===lang.toUpperCase()));  
  const t=translations[lang];  
  if(!t)return;  
  document.querySelectorAll('[data-i18n]').forEach(el=>{  
    const key=el.getAttribute('data-i18n');  
    if(t[key])el.textContent=t[key];  
  });  
  // RTL for Arabic  
  document.body.style.direction=lang==='ar'?'rtl':'ltr';  
}  
</script>  
</body>  
</html>  
