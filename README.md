#reviewer-site
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>IUPAC Step-by-Step — Interactive</title>
<style>
  :root{
    --bg:#f6f9fb;
    --card:#fff;
    --accent:#2b6777;
    --green:#9ae6b4;
    --yellow:#f6e05e;
    --red:#e53e3e;
    --blue:#63b3ed;
    --purple:#8b5cf6;
    --muted:#6b7280;
    --maxw:900px;
  }
  *{box-sizing:border-box;font-family:Inter,Segoe UI,Helvetica,Arial,sans-serif}
  body{margin:0;background:var(--bg);color:#111;display:flex;justify-content:center;padding:24px}
  .container{width:100%;max-width:var(--maxw);background:var(--card);border-radius:12px;padding:18px;box-shadow:0 8px 28px rgba(10,15,25,0.08)}
  header{display:flex;align-items:center;gap:12px}
  header h1{margin:0;font-size:20px}
  .layout{display:flex;flex-direction:column;gap:14px;margin-top:8px}
  .viewer{background:linear-gradient(180deg,#fff,#fbfdff);border-radius:10px;padding:14px;display:flex;gap:18px;align-items:center}
  .svg-area{flex:1;display:flex;align-items:center;justify-content:center;min-height:260px}
  svg{max-width:100%;height:auto;display:block}
  .meta{width:320px;min-width:240px}
  .meta h2{margin:0 0 6px;font-size:16px}
  .meta p{margin:0;color:var(--muted);line-height:1.45}
  .controls{display:flex;gap:10px;align-items:center;margin-top:8px}
  button{padding:10px 14px;border-radius:8px;border:0;background:var(--accent);color:white;font-weight:700;cursor:pointer}
  button:disabled{background:#cbd5d1;cursor:not-allowed}
  .progress{margin-left:auto;color:var(--muted);font-size:14px}
  /* fade transitions */
  .svg-step{position:absolute;opacity:0;transform:translateY(6px);transition:opacity .4s ease, transform .4s ease;pointer-events:none}
  .svg-step.active{opacity:1;transform:none;pointer-events:auto}
  .svg-wrap{position:relative;flex:1;min-height:280px}
  /* color-coded inline labels */
  .green{color:var(--green);font-weight:700}
  .yellow{color:var(--yellow);font-weight:700}
  .red{color:var(--red);font-weight:700}
  .blue{color:var(--blue);font-weight:700}
  .purple{color:var(--purple);font-weight:700}
  @media (max-width:880px){
    .viewer{flex-direction:column}
    .meta{width:100%}
    .svg-area{width:100%}
  }
</style>
</head>
<body>
  <div class="container" role="application" aria-label="IUPAC step-by-step interactive">
    <header>
      <h1>IUPAC Naming — Step-by-Step</h1>
      <div style="margin-left:auto;color:var(--muted)">Realistic skeletal diagrams (color-coded)</div>
    </header>

    <div class="layout">
      <div class="viewer">
        <div class="svg-wrap" aria-live="polite">
          <div class="svg-area" id="svgArea">
            <!-- STEP 1 -->
            <svg class="svg-step" data-step="1" viewBox="0 0 600 260" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Step 1: Find the parent chain">
              <style>
                .bond{stroke:#333;stroke-width:4;fill:none;stroke-linecap:round}
                .parent{stroke:var(--green);stroke-width:8;fill:none;opacity:0;stroke-linecap:round}
                .sub{stroke:var(--yellow);stroke-width:8;fill:none;opacity:0;stroke-linecap:round}
                .num{fill:var(--red);font-weight:700;opacity:0}
                .atom{fill:#333;font-size:12px}
              </style>
              <g transform="translate(20,40)">
                <path class="bond" d="M40 140 L160 140 L280 140 L400 140" />
                <path class="bond" d="M160 140 L160 80" />
                <path class="parent" d="M40 140 L160 140 L280 140 L400 140" stroke-dasharray="600"/>
                <path class="sub" d="M160 140 L160 80" stroke-dasharray="120"/>
                <text class="num" x="34" y="120">1</text>
                <text class="num" x="154" y="120">2</text>
                <text class="num" x="274" y="120">3</text>
                <text class="num" x="394" y="120">4</text>
                <text class="atom" x="30" y="160">C</text>
                <text class="atom" x="150" y="160">C</text>
                <text class="atom" x="270" y="160">C</text>
                <text class="atom" x="390" y="160">C</text>
                <text class="atom" x="146" y="60">C</text>
              </g>
            </svg>

            <!-- STEP 2 -->
            <svg class="svg-step" data-step="2" viewBox="0 0 600 260" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Step 2: Number the chain">
              <style>
                .bond{stroke:#333;stroke-width:4;fill:none;stroke-linecap:round}
                .parent{stroke:var(--green);stroke-width:8;fill:none;opacity:0;stroke-linecap:round}
                .num{fill:var(--red);font-weight:700;opacity:0}
              </style>
              <g transform="translate(10,30)">
                <path class="bond" d="M20 180 L100 100 L180 180 L260 100 L340 180 L420 100" />
                <path class="parent" d="M20 180 L100 100 L180 180 L260 100 L340 180 L420 100" stroke-dasharray="800"/>
                <text class="num" x="12" y="200">1</text>
                <text class="num" x="92" y="80">2</text>
                <text class="num" x="172" y="200">3</text>
                <text class="num" x="252" y="80">4</text>
                <text class="num" x="332" y="200">5</text>
                <text class="num" x="412" y="80">6</text>
              </g>
            </svg>

            <!-- STEP 3 -->
            <svg class="svg-step" data-step="3" viewBox="0 0 600 260" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Step 3: Identify substituents">
              <style>
                .bond{stroke:#333;stroke-width:4;fill:none;stroke-linecap:round}
                .sub{stroke:var(--yellow);stroke-width:8;fill:none;opacity:0;stroke-linecap:round}
                .parent{stroke:var(--green);stroke-width:6;fill:none;opacity:0;stroke-linecap:round}
                .num{fill:var(--red);font-weight:700;opacity:0}
                .label{font-size:12px;fill:#222;opacity:0}
              </style>
              <g transform="translate(10,30)">
                <path class="bond" d="M20 180 L140 180 L260 180 L380 180" />
                <path class="bond" d="M140 180 L140 120" />
                <path class="bond" d="M260 180 L260 120" />
                <path class="parent" d="M20 180 L140 180 L260 180 L380 180" stroke-dasharray="500"/>
                <path class="sub" d="M140 180 L140 120" stroke-dasharray="120"/>
                <path class="sub" d="M260 180 L260 120" stroke-dasharray="120"/>
                <text class="label" x="124" y="100">methyl</text>
                <text class="label" x="244" y="100">methyl</text>
                <text class="num" x="16" y="160">1</text>
                <text class="num" x="136" y="160">2</text>
                <text class="num" x="256" y="160">3</text>
                <text class="num" x="376" y="160">4</text>
              </g>
            </svg>

            <!-- STEP 4 -->
            <svg class="svg-step" data-step="4" viewBox="0 0 700 260" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Step 4: Assign locants">
              <style>
                .bond{stroke:#333;stroke-width:4;fill:none;stroke-linecap:round}
                .parent{stroke:var(--green);stroke-width:6;fill:none;opacity:0;stroke-linecap:round}
                .sub{stroke:var(--yellow);stroke-width:8;fill:none;opacity:0;stroke-linecap:round}
                .num{fill:var(--red);font-weight:700;opacity:0}
                .lbl{font-size:12px;fill:#222;opacity:0}
                .arrow{stroke:#333;stroke-width:2;opacity:0;marker-end:url(#a) }
              </style>
              <defs>
                <marker id="a" markerWidth="8" markerHeight="8" refX="6" refY="4" orient="auto">
                  <path d="M0 0 L8 4 L0 8 z" fill="#333" />
                </marker>
              </defs>
              <g transform="translate(10,30)">
                <path class="bond" d="M20 200 L140 200 L260 200 L380 200 L500 200" />
                <path class="bond" d="M140 200 L140 140" />
                <path class="bond" d="M260 200 L260 140" />
                <path class="parent" d="M20 200 L140 200 L260 200 L380 200 L500 200" stroke-dasharray="800"/>
                <path class="sub" d="M140 200 L140 140" stroke-dasharray="120"/>
                <path class="sub" d="M260 200 L260 140" stroke-dasharray="120"/>
                <text class="lbl" x="126" y="120">methyl</text>
                <text class="lbl" x="246" y="120">methyl</text>
                <text class="num" x="16" y="180">1</text>
                <text class="num" x="136" y="180">2</text>
                <text class="num" x="256" y="180">3</text>
                <text class="num" x="376" y="180">4</text>
                <text class="num" x="496" y="180">5</text>
                <line class="arrow" x1="136" y1="170" x2="140" y2="150" />
                <line class="arrow" x1="256" y1="170" x2="260" y2="150" />
              </g>
            </svg>

            <!-- STEP 5 -->
            <svg class="svg-step" data-step="5" viewBox="0 0 700 260" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Step 5: Functional group priority">
              <style>
                .bond{stroke:#333;stroke-width:4;fill:none;stroke-linecap:round}
                .func{stroke:var(--blue);stroke-width:8;fill:none;opacity:0;stroke-linecap:round}
                .num{fill:var(--red);font-weight:700;opacity:0}
                .lbl{font-size:12px;fill:#222}
              </style>
              <g transform="translate(10,30)">
                <path class="bond" d="M20 200 L140 200 L260 200 L380 200" />
                <path class="bond" d="M20 200 L20 120" />
                <text class="lbl" x="6" y="110">COOH</text>
                <path class="bond" d="M260 200 L260 140" />
                <text class="lbl" x="248" y="130">OH</text>
                <path class="func" d="M20 200 L20 120" stroke-dasharray="160"/>
                <path class="func" d="M260 200 L260 140" stroke-dasharray="160"/>
                <text class="lbl" x="8" y="220">COOH has higher priority → suffix</text>
                <text class="num" x="14" y="180">1</text>
                <text class="num" x="134" y="180">2</text>
                <text class="num" x="254" y="180">3</text>
                <text class="num" x="374" y="180">4</text>
              </g>
            </svg>

            <!-- STEP 6 -->
            <svg class="svg-step" data-step="6" viewBox="0 0 700 260" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Step 6: Final name">
              <style>
                .bond{stroke:#333;stroke-width:4;fill:none;stroke-linecap:round}
                .parent{stroke:var(--green);stroke-width:6;fill:none;opacity:0;stroke-linecap:round}
                .sub{stroke:var(--yellow);stroke-width:8;fill:none;opacity:0;stroke-linecap:round}
                .num{fill:var(--red);font-weight:700;opacity:0}
                .namepart{font-size:16px;fill:var(--purple);opacity:0}
              </style>
              <g transform="translate(10,30)">
                <path class="bond" d="M20 200 L140 200 L260 200 L380 200 L500 200" />
                <path class="bond" d="M260 200 L260 140" />
                <path class="parent" d="M20 200 L140 200 L260 200 L380 200 L500 200" stroke-dasharray="800"/>
                <path class="sub" d="M260 200 L260 140" stroke-dasharray="120"/>
                <text class="num" x="14" y="180">1</text>
                <text class="num" x="134" y="180">2</text>
                <text class="num" x="254" y="180">3</text>
                <text class="num" x="374" y="180">4</text>
                <text class="num" x="494" y="180">5</text>
                <text id="p1" class="namepart" x="20" y="30">2-</text>
                <text id="p2" class="namepart" x="60" y="30">methyl-</text>
                <text id="p3" class="namepart" x="150" y="30">pentane</text>
                <text id="p4" class="namepart" x="260" y="30">-1-ol</text>
              </g>
            </svg>

          </div>
        </div>

        <aside class="meta" aria-hidden="false">
          <h2 id="stepTitle">Step 1 — Find the Parent Chain</h2>
          <p id="stepDesc">
            Locate the longest continuous carbon chain. That chain gives the root name (e.g., <span class="green">meth-, eth-, prop-, but-</span>). If there is a tie, choose the chain with more <span class="yellow">substituents</span> or containing the highest-priority <span class="blue">functional group</span>.
          </p>

          <div class="controls" role="navigation" aria-label="Step controls">
            <button id="prevBtn" aria-label="Previous step" disabled>◀ Back</button>
            <button id="playBtn" aria-label="Replay step">Play</button>
            <button id="nextBtn" aria-label="Next step">Next ▶</button>
            <div class="progress" id="progressText">1 / 6</div>
          </div>
        </aside>
      </div>
    </div>
  </div>

<script>
(function(){
  const total = 6;
  let current = 1;

  const steps = {
    1: { title: "Step 1 — Find the Parent Chain",
         desc: "Locate the longest continuous carbon chain. That chain gives the root name (e.g., <span class='green'>meth-, eth-, prop-, but-</span>). If tied, choose chain with more <span class='yellow'>substituents</span> or the highest-priority <span class='blue'>functional group</span>." },
    2: { title: "Step 2 — Number the Chain",
         desc: "Number the chain from the end closest to the first substituent or highest-priority group. Numbers are shown in <span class='red'>red</span>." },
    3: { title: "Step 3 — Identify Substituents",
         desc: "Find and name groups attached to the parent chain (methyl, ethyl, halogens). These are highlighted in <span class='yellow'>yellow</span>." },
    4: { title: "Step 4 — Assign Locants",
         desc: "Assign position numbers (locants) for each substituent. Use prefixes like di-, tri- for repeats (e.g., <span class='red'>2,3</span>-dimethyl)." },
    5: { title: "Step 5 — Functional Group Priority",
         desc: "Highest-priority functional group becomes the suffix (e.g., <span class='blue'>COOH</span> &gt; <span class='blue'>OH</span>). Others become prefixes." },
    6: { title: "Step 6 — Final Name",
         desc: "Combine locants + substituents (alphabetized) + parent + main suffix to form the full IUPAC name (example shown in <span class='purple'>purple</span>)." }
  };

  const updateUI = (n) => {
    // show SVG with data-step === n
    document.querySelectorAll('.svg-step').forEach(svg=>{
      svg.classList.toggle('active', Number(svg.getAttribute('data-step'))===n);
      // reset inline text reveals (for step 6)
      svg.querySelectorAll('.num, .namepart, .lbl, .label, .func, .parent, .sub, .multi').forEach(el=>{
        el.style.opacity = '';
      });
    });

    // update title and desc
    const md = steps[n];
    document.getElementById('stepTitle').innerHTML = md.title;
    document.getElementById('stepDesc').innerHTML = md.desc;
    document.getElementById('progressText').textContent = n + " / " + total;

    // set buttons
    document.getElementById('prevBtn').disabled = n === 1;
    document.getElementById('nextBtn').disabled = n === total;
  };

  // animate highlights by toggling an "animate" class (CSS handles transitions)
  function playAnimation(n){
    const svg = document.querySelector('.svg-step[data-step="'+n+'"]');
    if(!svg) return;
    // clear then force reflow so transitions re-run
    svg.classList.remove('animated');
    void svg.offsetWidth;
    svg.classList.add('animated');

    // JS-driven reveals for special elements
    // reveal numbers
    svg.querySelectorAll('.num').forEach((el, i)=>{
      el.style.opacity = 0;
      setTimeout(()=> el.style.opacity = 1, 220 + i*120);
    });
    // reveal labels or name parts for step 6
    if(n === 6){
      const parts = ['#p1','#p2','#p3','#p4'];
      parts.forEach((sel,i)=>{
        const el = svg.querySelector(sel);
        if(el) { el.style.opacity = 0; setTimeout(()=> el.style.opacity = 1, 300 + i*320); }
      });
      // show parent/sub highlights
      svg.querySelectorAll('.parent, .sub').forEach((el, i)=>{ el.style.opacity = 0; setTimeout(()=> el.style.opacity = 1, 160 + i*200); });
    } else {
      // reveal parent/sub/func etc if present
      svg.querySelectorAll('.parent, .sub, .func, .multi, .label, .lbl').forEach((el, i)=>{
        el.style.opacity = 0;
        setTimeout(()=> el.style.opacity = 1, 160 + i*160);
      });
    }
  }

  // initial
  updateUI(current);
  playAnimation(current);

  // controls
  document.getElementById('prevBtn').addEventListener('click', ()=>{
    if(current>1) { current--; updateUI(current); playAnimation(current); }
  });
  document.getElementById('nextBtn').addEventListener('click', ()=>{
    if(current<total){ current++; updateUI(current); playAnimation(current); }
  });
  document.getElementById('playBtn').addEventListener('click', ()=> playAnimation(current));

  // keyboard
  document.addEventListener('keydown', (e)=>{
    if(e.key === 'ArrowRight') document.getElementById('nextBtn').click();
    if(e.key === 'ArrowLeft') document.getElementById('prevBtn').click();
  });
})();
</script>
</body>
</html>
