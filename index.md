/* ─────────────────────────────────────────────────────────
   STYLE SHEET – Gideon Nakibinge site (compact version)
   Mirrors ibaino.net layout, but with smaller fonts and
   tighter vertical rhythm.  Updated 2025-07-04.
   ───────────────────────────────────────────────────────── */

/* 1 Base tokens */
:root{
  font-family:
    -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,
    "Helvetica Neue",Arial,"Noto Sans",sans-serif;
  line-height:1.45;                       /* tighter default */
  --accent:#0366d6;
  --dark:#2f353b;
  --card-bg:#fafafa;
  --border:#e5e5e5;
}

/* 2 Global text size & colour */
html{scroll-behavior:smooth;}
body{
  margin:0;
  color:#111;
  background:#fff;
  font:400 14.2px/1.45 system-ui,-apple-system,"Segoe UI",Roboto,
       "Helvetica Neue",Arial,"Noto Sans",sans-serif;
}

/* 3 Header & top nav (left-aligned) */
.site-header{
  background:var(--dark);
  border-bottom:1px solid rgba(255,255,255,.06);
  position:sticky;top:0;z-index:100;
}
.site-nav{
  display:flex;
  justify-content:flex-start;
  align-items:center;
  width:100%;
  padding:.8rem 1.2rem;
}
.site-nav ul{
  list-style:none;
  margin:0;padding:0;
  display:flex;gap:2rem;
}
.site-nav a,
.site-nav a:visited,
.site-nav a:hover,
.site-nav a:focus{
  color:#fff;
  text-decoration:none;
  font:600 0.95rem/1.2 inherit;           /* scaled with body size */
  letter-spacing:.02em;
}
.site-nav li.active a{
  border-bottom:2px solid #fff;
}
.site-nav a:hover,
.site-nav a:focus{opacity:.85;}

/* 4 Main grid */
.site-content{
  display:grid;
  grid-template-columns:1fr 260px;        /* main | sidebar */
  gap:2rem;                               /* slightly tighter */
  max-width:72rem;                        /* 1152 px cap */
  margin:2rem auto 5rem;
  padding:0 .5rem;
}
@media(max-width:920px){.site-content{display:block;}}
@media(min-width:921px){ .site-content{gap:2.5rem;} }

/* Sidebar placement & spacing */
@media(min-width:921px){
  .site-content>.card:first-child{margin-top:4.6rem;}  /* align with h-rule */
  .site-content>.card + .card   {margin-top:1.6rem;}
}
.site-content>.main {grid-column:1;}
.site-content>.card {grid-column:2;grid-row:auto;}

/* 5 Main column rhythm */
.main h1{
  font-size:1.8rem;                      /* was 2rem */
  font-weight:700;
  margin:0 0 1.2rem;
}
.main hr{
  border:none;border-top:1px solid #e1e4e8;
  margin:1.3rem 0;
}
.main h2{
  font-size:1.2rem;                      /* was 1.35rem */
  font-weight:700;
  margin:1.6rem 0 .6rem;
}
.main p,
.main ul{margin:.6rem 0;}                /* tighter vertical gaps */
.main li{margin:.25rem 0;}
.main strong{font-weight:700;}

/* 5a Blockquote */
.main blockquote{
  border-left:4px solid #ccc;
  margin:1.2rem 0;
  padding:.4rem 1rem;
  font-size:1.05rem;
  font-weight:600;
  line-height:1.4;
  background:var(--card-bg);
}
audio{margin-bottom:.7rem;}

/* 6 Tag badge */
.tag{
  display:inline-block;
  margin:1.4rem 0 .6rem;
  background:#ffeef0;
  border:1px solid #d73a49;
  color:#cb2431;
  border-radius:4px;
  padding:.1rem .35rem;
  font:.78rem SFMono-Regular,Consolas,"Liberation Mono",Menlo,monospace;
}

/* 7 Quick-links list */
ul.quick-links{
  list-style:none;
  margin:1.6rem 0 0;
  padding:0;
}
ul.quick-links li{margin:.25rem 0;}

/* 8 Sidebar card */
.card{
  border:1px solid var(--border);
  border-radius:8px;
  background:var(--card-bg);
  font-size:.85rem;
}
.card header{
  background:#f4f4f4;
  padding:.55rem .9rem;
  font-weight:700;
}
.card .card-body{padding:.85rem;}
.card img,
.portrait{
  width:100%;
  max-height:240px;
  object-fit:cover;
}

/* 9 Floating-action buttons */
.fab-stack{
  position:fixed;right:1rem;top:50%;
  transform:translateY(-50%);
  display:flex;flex-direction:column;gap:.75rem;
  z-index:200;
}
.fab-stack a{
  display:grid;place-items:center;
  width:44px;height:44px;
  border-radius:50%;
  background:#fff;
  border:1px solid #d0d0d0;
  box-shadow:0 1px 3px rgba(0,0,0,.12);
  font-size:1.25rem;
  text-decoration:none;
}
.fab-stack a:hover{background:#f5f5f5;}

/* 10 Bottom nav */
.page-footer-nav{
  position:fixed;bottom:0;left:0;width:100%;
  background:#f6f7f8;
  border-top:1px solid var(--border);
  font-size:.8rem;
  text-align:left;
  padding:.3rem .9rem;
}
.page-footer-nav a{
  color:var(--accent);
  text-decoration:none;
  padding:0 .2rem;
}
.page-footer-nav a:not(:last-child)::after{
  content:"|";
  margin-left:.2rem;
  color:#999;
}

/* 11 Inline links (download audio / podcast) */
.main a{
  color:var(--accent);
  text-decoration:none;
}
.main a:hover,
.main a:focus{text-decoration:underline;}

/* Hide legacy footer */
.site-footer{display:none;}
