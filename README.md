
<style>
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600&family=Inter:wght@300;400;500;600&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --void:#07040f;
  --deep:#0d0820;
  --surface:#130e26;
  --panel:#1a1535;
  --border:#2a2250;
  --violet:#7c5ff5;
  --violet-soft:#a78bfa;
  --violet-dim:#4c3a9e;
  --indigo:#6366f1;
  --text:#f0eaff;
  --muted:#8b83aa;
  --dim:#4a4470;
  --gold:#f5b942;
  --teal:#2dd4bf;
  --green:#4ade80;
}
canvas#stars{position:absolute;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:0}
.card{
  background:var(--void);
  font-family:'Inter',sans-serif;
  color:var(--text);
  min-height:1800px;
  position:relative;
  overflow:hidden;
  width:100%;
}
.content{position:relative;z-index:2;padding:0 0 48px 0}
.hero{
  display:flex;flex-direction:column;align-items:center;
  padding:52px 32px 36px;
  text-align:center;
  border-bottom:1px solid var(--border);
}
.avatar-wrap{
  width:96px;height:96px;border-radius:50%;
  background:linear-gradient(135deg,var(--violet-dim),var(--indigo));
  display:flex;align-items:center;justify-content:center;
  font-family:'JetBrains Mono',monospace;font-size:28px;font-weight:600;
  color:var(--text);
  margin-bottom:20px;
  border:2px solid var(--violet-dim);
  box-shadow:0 0 32px rgba(124,95,245,.25);
  flex-shrink:0;
}
.hero-name{
  font-family:'JetBrains Mono',monospace;font-size:26px;font-weight:600;
  color:var(--text);letter-spacing:-.3px;margin-bottom:6px;
}
.hero-subtitle{
  font-size:13px;color:var(--violet-soft);letter-spacing:.8px;
  text-transform:uppercase;margin-bottom:16px;font-weight:500;
}
.hero-desc{
  font-size:14px;color:var(--muted);line-height:1.6;max-width:520px;margin-bottom:20px;
}
.tags{display:flex;flex-wrap:wrap;gap:8px;justify-content:center}
.tag{
  font-size:11px;font-family:'JetBrains Mono',monospace;font-weight:500;
  background:var(--panel);border:1px solid var(--border);color:var(--violet-soft);
  padding:4px 12px;border-radius:20px;letter-spacing:.4px;
}
.section{padding:28px 28px 0}
.section-label{
  font-family:'JetBrains Mono',monospace;font-size:10px;font-weight:500;
  color:var(--dim);letter-spacing:1.6px;text-transform:uppercase;
  margin-bottom:14px;display:flex;align-items:center;gap:8px;
}
.section-label::after{content:'';flex:1;height:1px;background:var(--border)}
.code-block{
  background:var(--deep);border:1px solid var(--border);border-radius:10px;
  padding:18px 20px;font-family:'JetBrains Mono',monospace;font-size:12px;line-height:1.8;
  color:var(--muted);overflow:hidden;
}
.code-block .kw{color:#c792ea}
.code-block .str{color:#c3e88d}
.code-block .cls{color:var(--gold)}
.code-block .fn{color:#82aaff}
.code-block .cmt{color:var(--dim)}
.code-block .prop{color:var(--teal)}
.code-block .val{color:#f78c6c}
.roles-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px}
.role-card{
  background:var(--panel);border:1px solid var(--border);border-radius:10px;
  padding:14px 14px;text-align:center;
}
.role-icon{font-size:20px;margin-bottom:8px}
.role-title{font-size:11px;font-weight:600;color:var(--text);letter-spacing:.3px;margin-bottom:3px}
.role-org{font-size:10px;color:var(--muted);font-family:'JetBrains Mono',monospace}
.role-since{
  font-size:9px;font-family:'JetBrains Mono',monospace;
  color:var(--green);margin-top:6px;
}
.projects-list{display:flex;flex-direction:column;gap:10px}
.proj-card{
  background:var(--panel);border:1px solid var(--border);border-radius:10px;
  padding:14px 16px;display:flex;align-items:flex-start;gap:12px;
  cursor:pointer;transition:border-color .2s;
}
.proj-card:hover{border-color:var(--violet-dim)}
.proj-dot{width:8px;height:8px;border-radius:50%;background:var(--green);margin-top:5px;flex-shrink:0}
.proj-dot.amber{background:var(--gold)}
.proj-dot.violet{background:var(--violet-soft)}
.proj-dot.teal{background:var(--teal)}
.proj-name{font-size:13px;font-weight:600;color:var(--text);margin-bottom:3px}
.proj-desc{font-size:12px;color:var(--muted);line-height:1.5}
.proj-link{font-size:11px;color:var(--violet-soft);font-family:'JetBrains Mono',monospace;margin-top:4px;display:block;text-decoration:none}
.tech-groups{display:flex;flex-direction:column;gap:14px}
.tech-group-row{display:flex;align-items:flex-start;gap:10px}
.tech-group-name{
  font-size:10px;font-family:'JetBrains Mono',monospace;color:var(--dim);
  width:72px;flex-shrink:0;padding-top:5px;letter-spacing:.6px;text-transform:uppercase;
}
.tech-chips{display:flex;flex-wrap:wrap;gap:6px}
.chip{
  font-size:11px;font-family:'JetBrains Mono',monospace;font-weight:500;
  background:var(--deep);border:1px solid var(--border);
  color:var(--muted);padding:3px 10px;border-radius:6px;
}
.chip.hi{color:var(--violet-soft);border-color:var(--violet-dim)}
.edu-rows{display:flex;flex-direction:column;gap:8px}
.edu-row{
  display:flex;align-items:flex-start;gap:12px;
  background:var(--panel);border:1px solid var(--border);border-radius:10px;padding:13px 15px;
}
.edu-year{font-size:10px;font-family:'JetBrains Mono',monospace;color:var(--dim);min-width:36px;padding-top:2px}
.edu-name{font-size:13px;font-weight:600;color:var(--text);margin-bottom:2px}
.edu-inst{font-size:11px;color:var(--muted)}
.edu-grade{
  margin-left:auto;font-family:'JetBrains Mono',monospace;font-size:12px;
  color:var(--gold);font-weight:600;flex-shrink:0;padding-left:8px;
}
.stats-row{display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px}
.stat-box{
  background:var(--panel);border:1px solid var(--border);border-radius:10px;
  padding:14px 12px;text-align:center;
}
.stat-val{font-family:'JetBrains Mono',monospace;font-size:22px;font-weight:600;color:var(--violet-soft);margin-bottom:4px}
.stat-lbl{font-size:10px;color:var(--muted);letter-spacing:.4px;text-transform:uppercase}
.links-row{display:flex;flex-wrap:wrap;gap:8px;justify-content:center;padding:20px 28px 0}
.link-btn{
  display:flex;align-items:center;gap:7px;
  background:var(--panel);border:1px solid var(--border);border-radius:8px;
  padding:8px 14px;font-size:12px;color:var(--muted);cursor:pointer;
  font-family:'JetBrains Mono',monospace;text-decoration:none;transition:all .2s;
}
.link-btn:hover{border-color:var(--violet-dim);color:var(--violet-soft)}
.link-btn .dot{width:6px;height:6px;border-radius:50%;background:var(--green);flex-shrink:0}
.research-cards{display:flex;flex-direction:column;gap:8px}
.res-card{
  background:var(--panel);border:1px solid var(--border);border-radius:10px;
  padding:13px 16px;
}
.res-title{font-size:13px;font-weight:600;color:var(--text);margin-bottom:4px}
.res-meta{font-size:11px;color:var(--dim);font-family:'JetBrains Mono',monospace;margin-bottom:4px}
.res-desc{font-size:12px;color:var(--muted);line-height:1.5}
.footer{
  text-align:center;padding:28px 28px 12px;
  border-top:1px solid var(--border);margin-top:28px;
}
.footer-text{font-size:12px;color:var(--dim);font-family:'JetBrains Mono',monospace;letter-spacing:.5px}
.scroll-top-btn{
  display:inline-block;margin-top:12px;
  background:var(--panel);border:1px solid var(--border);border-radius:8px;
  padding:8px 20px;font-size:11px;font-family:'JetBrains Mono',monospace;
  color:var(--violet-soft);cursor:pointer;transition:border-color .2s;
}
.scroll-top-btn:hover{border-color:var(--violet-dim)}
.badge{
  display:inline-flex;align-items:center;gap:4px;
  font-size:9px;font-family:'JetBrains Mono',monospace;font-weight:500;
  background:rgba(74,222,128,.1);color:var(--green);border:1px solid rgba(74,222,128,.25);
  padding:2px 8px;border-radius:20px;margin-left:8px;vertical-align:middle;
}
</style>

<div class="card" id="maincard">
<canvas id="stars"></canvas>
<div class="content">

  <div class="hero">
    <div class="avatar-wrap">AH</div>
    <div class="hero-name">MD Ahsamul Haque</div>
    <div class="hero-subtitle">ML Researcher · Database Engineer · Founder</div>
    <div class="hero-desc">
      Building at the intersection of machine learning, scalable data systems, and product — from Dhaka, Bangladesh.
      Currently pursuing MSc CS in Europe for 2026/27.
    </div>
    <div class="tags">
      <span class="tag">🔬 Techwings Lab</span>
      <span class="tag">🗄️ V2 Technologies</span>
      <span class="tag">🛒 Founder · adiari.shop</span>
      <span class="tag">🎓 AIUB · GPA 3.72</span>
      <span class="tag">📸 Travel Photographer</span>
    </div>
  </div>

  <div class="section">
    <div class="section-label">whoami</div>
    <div class="code-block">
<span class="kw">class</span> <span class="cls">Ahsam</span><span style="color:var(--text)">:</span>
  <span class="prop">name</span>      <span style="color:var(--text)">=</span> <span class="str">"MD Ahsamul Haque"</span>
  <span class="prop">location</span>  <span style="color:var(--text)">=</span> <span class="str">"Dhaka, Bangladesh 🇧🇩"</span>
  <span class="prop">roles</span>     <span style="color:var(--text)">=</span> <span style="color:var(--text)">[</span><span class="str">"ML Researcher"</span><span style="color:var(--text)">,</span> <span class="str">"DB Engineer"</span><span style="color:var(--text)">,</span> <span class="str">"Founder"</span><span style="color:var(--text)">]</span>
  <span class="prop">education</span> <span style="color:var(--text)">=</span> <span class="str">"B.Sc. CSE @ AIUB  |  GPA: 3.72 / 4.00"</span>
  <span class="prop">pursuing</span>  <span style="color:var(--text)">=</span> <span class="str">"MSc CS in Europe — 2026/27 🎓"</span>
  <span class="prop">venture</span>   <span style="color:var(--text)">=</span> <span class="str">"adiari.shop — Online Retail"</span>
  <span class="prop">portfolio</span> <span style="color:var(--text)">=</span> <span class="str">"ahsam.iam.bd"</span>

  <span class="kw">def</span> <span class="fn">say_hi</span><span style="color:var(--text)">(</span><span class="kw">self</span><span style="color:var(--text)">):</span>
    <span class="fn">print</span><span style="color:var(--text)">(</span><span class="str">"Thanks for stopping by! Let's build. ✦"</span><span style="color:var(--text)">)</span>
    </div>
  </div>

  <div class="section" style="margin-top:24px">
    <div class="section-label">currently working at</div>
    <div class="roles-grid">
      <div class="role-card">
        <div class="role-icon">🔬</div>
        <div class="role-title">Techwings Lab</div>
        <div class="role-org">ML Researcher</div>
        <div style="font-size:11px;color:var(--muted);margin-top:5px;line-height:1.4">Publishing ML &amp; CS papers at conferences &amp; journals</div>
        <div class="role-since">● 2025 – Present</div>
      </div>
      <div class="role-card">
        <div class="role-icon">🏢</div>
        <div class="role-title">V2 Technologies</div>
        <div class="role-org">Database Engineer</div>
        <div style="font-size:11px;color:var(--muted);margin-top:5px;line-height:1.4">MySQL · PostgreSQL · Oracle infrastructure</div>
        <div class="role-since">● 2025 – Present</div>
      </div>
      <div class="role-card">
        <div class="role-icon">🛒</div>
        <div class="role-title">Adiari</div>
        <div class="role-org">Founder &amp; Operator</div>
        <div style="font-size:11px;color:var(--muted);margin-top:5px;line-height:1.4">Full-stack e-commerce &amp; POS platform</div>
        <div class="role-since">● 2024 – Present</div>
      </div>
    </div>
  </div>

  <div class="section" style="margin-top:24px">
    <div class="section-label">stats</div>
    <div class="stats-row">
      <div class="stat-box">
        <div class="stat-val">3.72</div>
        <div class="stat-lbl">GPA / 4.00</div>
      </div>
      <div class="stat-box">
        <div class="stat-val">4+</div>
        <div class="stat-lbl">Live Projects</div>
      </div>
      <div class="stat-box">
        <div class="stat-val">5+</div>
        <div class="stat-lbl">Research Papers</div>
      </div>
    </div>
  </div>

  <div class="section" style="margin-top:24px">
    <div class="section-label">research highlights</div>
    <div class="research-cards">
      <div class="res-card">
        <div class="res-title">MFDS-RCNN Object Detector</div>
        <div class="res-meta">Python · PyTorch · RCNN · 2025</div>
        <div class="res-desc">Novel multi-feature dense sampling approach for object detection. Conference &amp; journal submission in progress at Techwings Lab.</div>
      </div>
      <div class="res-card">
        <div class="res-title">Garments Defect Detection System</div>
        <div class="res-meta">Python · TensorFlow · ML · 2024</div>
        <div class="res-desc">Sensor-integrated eco-friendly QA pipeline using deep learning for textile defect classification.</div>
      </div>
    </div>
  </div>

  <div class="section" style="margin-top:24px">
    <div class="section-label">live projects</div>
    <div class="projects-list">
      <div class="proj-card" onclick="openLink('https://adiari.shop')">
        <div class="proj-dot amber"></div>
        <div>
          <div class="proj-name">Adiari — Online Retail <span class="badge">live</span></div>
          <div class="proj-desc">Full-stack e-commerce + POS with barcode scanning, multilingual support (EN/JP/BN), guest cart & real-time inventory. PHP · MySQL · React · Hostinger.</div>
          <a class="proj-link">adiari.shop ↗</a>
        </div>
      </div>
      <div class="proj-card" onclick="openLink('https://ahsam.iam.bd')">
        <div class="proj-dot violet"></div>
        <div>
          <div class="proj-name">Portfolio <span class="badge">live</span></div>
          <div class="proj-desc">Personal developer portfolio — research, projects & professional journey. GitHub Pages + custom .iam.bd domain.</div>
          <a class="proj-link">ahsam.iam.bd ↗</a>
        </div>
      </div>
      <div class="proj-card" onclick="openLink('https://bhaibachao.vercel.app')">
        <div class="proj-dot"></div>
        <div>
          <div class="proj-name">BhaiBachao <span class="badge">live</span></div>
          <div class="proj-desc">Community coordination platform & student resource hub built for AIUB undergrads. JavaScript · Vercel.</div>
          <a class="proj-link">bhaibachao.vercel.app ↗</a>
        </div>
      </div>
      <div class="proj-card" onclick="openLink('https://vetconsult.vercel.app')">
        <div class="proj-dot teal"></div>
        <div>
          <div class="proj-name">VetConsult <span class="badge">live</span></div>
          <div class="proj-desc">Remote vet consultation platform connecting pet owners with licensed veterinarians. React · Vercel.</div>
          <a class="proj-link">vetconsult.vercel.app ↗</a>
        </div>
      </div>
    </div>
  </div>

  <div class="section" style="margin-top:24px">
    <div class="section-label">tech arsenal</div>
    <div class="tech-groups">
      <div class="tech-group-row">
        <div class="tech-group-name">Lang</div>
        <div class="tech-chips">
          <span class="chip hi">Python</span><span class="chip hi">PHP</span><span class="chip">C#</span><span class="chip">Java</span><span class="chip">C++</span><span class="chip">Bash</span><span class="chip">TypeScript</span>
        </div>
      </div>
      <div class="tech-group-row">
        <div class="tech-group-name">Web</div>
        <div class="tech-chips">
          <span class="chip hi">React</span><span class="chip">HTML5</span><span class="chip">CSS3</span><span class="chip">JavaScript</span><span class="chip">TailwindCSS</span><span class="chip">.NET</span>
        </div>
      </div>
      <div class="tech-group-row">
        <div class="tech-group-name">ML</div>
        <div class="tech-chips">
          <span class="chip hi">PyTorch</span><span class="chip hi">TensorFlow</span><span class="chip">Keras</span><span class="chip">Pandas</span><span class="chip">NumPy</span><span class="chip">Matplotlib</span><span class="chip">Selenium</span>
        </div>
      </div>
      <div class="tech-group-row">
        <div class="tech-group-name">DB</div>
        <div class="tech-chips">
          <span class="chip hi">MySQL</span><span class="chip hi">PostgreSQL</span><span class="chip">Oracle SQL</span><span class="chip">SQL Server</span><span class="chip">PL/SQL</span>
        </div>
      </div>
      <div class="tech-group-row">
        <div class="tech-group-name">Tools</div>
        <div class="tech-chips">
          <span class="chip">Git</span><span class="chip">AWS</span><span class="chip">Vercel</span><span class="chip">LaTeX</span><span class="chip">Figma</span><span class="chip">Premiere Pro</span><span class="chip">Photoshop</span>
        </div>
      </div>
    </div>
  </div>

  <div class="section" style="margin-top:24px">
    <div class="section-label">education &amp; certifications</div>
    <div class="edu-rows">
      <div class="edu-row">
        <div class="edu-year">2022</div>
        <div>
          <div class="edu-name">B.Sc. Computer Science &amp; Engineering</div>
          <div class="edu-inst">American International University — Bangladesh (AIUB)</div>
        </div>
        <div class="edu-grade">3.72/4.00</div>
      </div>
      <div class="edu-row">
        <div class="edu-year">2023</div>
        <div>
          <div class="edu-name">CCNA — Cisco Certified Network Associate</div>
          <div class="edu-inst">Cisco</div>
        </div>
        <div class="edu-grade" style="color:var(--green)">Certified</div>
      </div>
      <div class="edu-row">
        <div class="edu-year">2020</div>
        <div>
          <div class="edu-name">HSC — Higher Secondary Certificate</div>
          <div class="edu-inst">Comilla Residential College</div>
        </div>
        <div class="edu-grade">4.83/5.00</div>
      </div>
      <div class="edu-row">
        <div class="edu-year">2018</div>
        <div>
          <div class="edu-name">SSC — Secondary School Certificate</div>
          <div class="edu-inst">Muradnagar D.R. Pilot Govt. HS</div>
        </div>
        <div class="edu-grade">4.50/5.00</div>
      </div>
    </div>
  </div>

  <div class="links-row">
    <a class="link-btn" href="https://linkedin.com/in/md-ahsamul-haque"><span class="dot"></span>LinkedIn</a>
    <a class="link-btn" href="mailto:ahsamulhaque.aiub@gmail.com"><span class="dot" style="background:var(--gold)"></span>Gmail</a>
    <a class="link-btn" href="https://ahsam.iam.bd"><span class="dot" style="background:var(--violet-soft)"></span>Portfolio</a>
    <a class="link-btn" href="https://github.com/ahsam991"><span class="dot" style="background:var(--muted)"></span>GitHub</a>
    <a class="link-btn" href="https://adiari.shop"><span class="dot" style="background:var(--teal)"></span>Adiari</a>
  </div>

  <div class="footer">
    <div class="footer-text">// Dhaka, Bangladesh · Open to MSc opportunities 2026/27</div>
    <div class="scroll-top-btn" onclick="sendPrompt('Tell me more about Ahsam\\'s research work and MSc application strategy')">Ask about MSc strategy ↗</div>
  </div>

</div>
</div>

<script>
(function(){
  const canvas = document.getElementById('stars');
  const ctx = canvas.getContext('2d');
  const card = document.getElementById('maincard');

  let W, H, nodes = [], edges = [], animId;

  function resize(){
    W = canvas.width = card.offsetWidth;
    H = canvas.height = card.offsetHeight||1800;
  }

  function randNode(){
    return {
      x: Math.random()*W,
      y: Math.random()*H,
      vx: (Math.random()-.5)*.3,
      vy: (Math.random()-.5)*.3,
      r: Math.random()*1.2+.4,
      a: Math.random()*.7+.2
    }
  }

  function init(){
    resize();
    nodes = [];
    for(let i=0;i<80;i++) nodes.push(randNode());
  }

  function draw(){
    ctx.clearRect(0,0,W,H);
    for(let i=0;i<nodes.length;i++){
      const n = nodes[i];
      n.x += n.vx; n.y += n.vy;
      if(n.x<0||n.x>W) n.vx*=-1;
      if(n.y<0||n.y>H) n.vy*=-1;
      ctx.beginPath();
      ctx.arc(n.x,n.y,n.r,0,Math.PI*2);
      ctx.fillStyle=`rgba(167,139,250,${n.a})`;
      ctx.fill();
    }
    for(let i=0;i<nodes.length;i++){
      for(let j=i+1;j<nodes.length;j++){
        const a=nodes[i], b=nodes[j];
        const dx=a.x-b.x, dy=a.y-b.y;
        const d=Math.sqrt(dx*dx+dy*dy);
        if(d<120){
          ctx.beginPath();
          ctx.moveTo(a.x,a.y);ctx.lineTo(b.x,b.y);
          ctx.strokeStyle=`rgba(124,95,245,${.18*(1-d/120)})`;
          ctx.lineWidth=.5;ctx.stroke();
        }
      }
    }
    animId=requestAnimationFrame(draw);
  }

  init();
  draw();

  const ro = new ResizeObserver(()=>{
    cancelAnimationFrame(animId);
    resize();
    draw();
  });
  ro.observe(card);
})();
</script>
