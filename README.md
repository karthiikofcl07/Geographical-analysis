# ================================================================
# PASTE THESE AS MARKDOWN CELLS IN YOUR JUPYTER NOTEBOOK
# Cell 1 = INTRO  |  Cell 2 = CONCLUSION
# ================================================================

INTRO_CELL = """
<style>
.intro-wrap{font-family:sans-serif;padding:0}
.top-bar{background:#f7f7f8;border:0.5px solid #e0e0e0;border-radius:12px;padding:10px 20px;display:flex;align-items:center;justify-content:space-between;margin-bottom:16px}
.org-tag{font-size:11px;font-weight:600;color:#666;letter-spacing:1.5px;text-transform:uppercase}
.task-tag{font-size:11px;font-weight:600;background:#e8f0fe;color:#1a56db;padding:4px 12px;border-radius:8px}
.hero{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:16px}
.profile-card{background:#fff;border:0.5px solid #e0e0e0;border-radius:12px;padding:24px;display:flex;flex-direction:column;gap:16px}
.avatar-row{display:flex;align-items:center;gap:16px}
.avatar{width:56px;height:56px;border-radius:50%;background:#e8f0fe;display:flex;align-items:center;justify-content:center;font-size:20px;font-weight:600;color:#1a56db;flex-shrink:0;border:0.5px solid #c3d5fc}
.name-block .name{font-size:18px;font-weight:600;color:#111;margin:0 0 4px}
.name-block .role{font-size:13px;color:#666;margin:0}
.divider{height:0.5px;background:#e0e0e0}
.links-grid{display:flex;flex-direction:column;gap:10px}
.link-row{display:flex;align-items:center;gap:10px;text-decoration:none}
.link-icon{width:30px;height:30px;border-radius:8px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.link-icon.li{background:#e8f0fe}
.link-icon.gh{background:#f7f7f8;border:0.5px solid #e0e0e0}
.link-icon svg{width:15px;height:15px}
.link-text .lbl{font-size:11px;color:#999;text-transform:uppercase;letter-spacing:1px;font-weight:600;margin:0 0 1px}
.link-text .val{font-size:13px;color:#1a56db;margin:0}
.stats-card{background:#fff;border:0.5px solid #e0e0e0;border-radius:12px;padding:24px}
.stats-title{font-size:11px;font-weight:600;color:#666;text-transform:uppercase;letter-spacing:1.5px;margin:0 0 16px}
.stats-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.stat-item{background:#f7f7f8;border-radius:8px;padding:14px}
.stat-num{font-size:22px;font-weight:600;color:#111;margin:0 0 3px;line-height:1}
.stat-lbl{font-size:11px;color:#666;margin:0}
.tech-row{display:flex;flex-wrap:wrap;gap:8px;margin-top:16px}
.tech-badge{font-size:12px;font-weight:500;padding:4px 10px;border-radius:8px;background:#f7f7f8;color:#444;border:0.5px solid #e0e0e0}
.bottom-bar{background:#f7f7f8;border:0.5px solid #e0e0e0;border-radius:12px;padding:14px 20px;display:flex;align-items:center;justify-content:space-between}
.bottom-text{font-size:13px;color:#666;margin:0}
.status-dot{width:7px;height:7px;border-radius:50%;background:#22c55e;display:inline-block;margin-right:7px}
</style>

<div class="intro-wrap">
  <div class="top-bar">
    <span class="org-tag">Cognifyz Technologies &nbsp;·&nbsp; Data Science Internship</span>
    <span class="task-tag">Geographic Analysis</span>
  </div>
  <div class="hero">
    <div class="profile-card">
      <div class="avatar-row">
        <div class="avatar">KT</div>
        <div class="name-block">
          <p class="name">Karthikeyan Thirunavukkarasu</p>
          <p class="role">Data Science Intern</p>
        </div>
      </div>
      <div class="divider"></div>
      <div class="links-grid">
        <a class="link-row" href="https://www.linkedin.com/in/karthikeyan-thirunavukkarasu-2a2949305">
          <div class="link-icon li">
            <svg viewBox="0 0 24 24" fill="none"><rect x="2" y="2" width="20" height="20" rx="4" fill="#1a56db"/><path d="M7 10v7M7 7v.5M12 17v-4a2 2 0 014 0v4M12 10v7" stroke="#fff" stroke-width="1.8" stroke-linecap="round"/></svg>
          </div>
          <div class="link-text">
            <p class="lbl">LinkedIn</p>
            <p class="val">karthikeyan-thirunavukkarasu-2a2949305</p>
          </div>
        </a>
        <a class="link-row" href="https://github.com/karthiikofcl07">
          <div class="link-icon gh">
            <svg viewBox="0 0 24 24" fill="#111"><path d="M12 2C6.477 2 2 6.477 2 12c0 4.418 2.865 8.166 6.839 9.489.5.092.682-.217.682-.482 0-.237-.009-.866-.013-1.7-2.782.604-3.369-1.34-3.369-1.34-.454-1.154-1.11-1.462-1.11-1.462-.908-.62.069-.608.069-.608 1.003.07 1.531 1.03 1.531 1.03.892 1.529 2.341 1.087 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.11-4.555-4.943 0-1.091.39-1.984 1.029-2.683-.103-.253-.446-1.27.098-2.647 0 0 .84-.268 2.75 1.026A9.578 9.578 0 0112 6.836a9.59 9.59 0 012.504.337c1.909-1.294 2.747-1.026 2.747-1.026.546 1.377.202 2.394.1 2.647.64.699 1.028 1.592 1.028 2.683 0 3.842-2.339 4.687-4.566 4.935.359.309.678.919.678 1.852 0 1.336-.012 2.415-.012 2.743 0 .267.18.578.688.48C19.138 20.163 22 16.418 22 12c0-5.523-4.477-10-10-10z"/></svg>
          </div>
          <div class="link-text">
            <p class="lbl">GitHub</p>
            <p class="val">karthiikofcl07</p>
          </div>
        </a>
      </div>
    </div>
    <div class="stats-card">
      <p class="stats-title">Project at a glance</p>
      <div class="stats-grid">
        <div class="stat-item"><p class="stat-num">9,551</p><p class="stat-lbl">Restaurants</p></div>
        <div class="stat-item"><p class="stat-num">15</p><p class="stat-lbl">Countries</p></div>
        <div class="stat-item"><p class="stat-num">141</p><p class="stat-lbl">Cities</p></div>
        <div class="stat-item"><p class="stat-num">7</p><p class="stat-lbl">Visualizations</p></div>
      </div>
      <div class="tech-row">
        <span class="tech-badge">Python</span><span class="tech-badge">Matplotlib</span>
        <span class="tech-badge">DBSCAN</span><span class="tech-badge">KDE</span>
        <span class="tech-badge">Seaborn</span><span class="tech-badge">scikit-learn</span>
      </div>
    </div>
  </div>
  <div class="bottom-bar">
    <p class="bottom-text"><span class="status-dot"></span>Geospatial Analysis &nbsp;·&nbsp; Cluster Detection &nbsp;·&nbsp; Location Intelligence</p>
    <p class="bottom-text" style="font-size:12px;color:#999">Cognifyz Technologies · 2024</p>
  </div>
</div>
"""

CONCLUSION_CELL = """
<style>
.conc-wrap{font-family:sans-serif;padding:0}
.conc-header{background:#f7f7f8;border:0.5px solid #e0e0e0;border-radius:12px;padding:14px 20px;display:flex;align-items:center;justify-content:space-between;margin-bottom:16px}
.conc-label{font-size:11px;font-weight:600;color:#666;text-transform:uppercase;letter-spacing:1.5px}
.complete-badge{font-size:11px;font-weight:600;background:#dcfce7;color:#16a34a;padding:4px 12px;border-radius:8px}
.findings-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:12px;margin-bottom:16px}
.finding-card{background:#fff;border:0.5px solid #e0e0e0;border-radius:12px;padding:16px}
.f-num{font-size:11px;font-weight:600;color:#1a56db;text-transform:uppercase;letter-spacing:1px;margin:0 0 8px}
.f-stat{font-size:22px;font-weight:600;color:#111;margin:0 0 4px;line-height:1}
.f-desc{font-size:12px;color:#666;margin:0;line-height:1.5}
.bottom-grid{display:grid;grid-template-columns:1fr 1fr;gap:16px}
.analyst-card{background:#fff;border:0.5px solid #e0e0e0;border-radius:12px;padding:20px}
.card-title{font-size:11px;font-weight:600;color:#666;text-transform:uppercase;letter-spacing:1.5px;margin:0 0 14px}
.analyst-row{display:flex;align-items:center;gap:12px;margin-bottom:14px}
.av-sm{width:44px;height:44px;border-radius:50%;background:#e8f0fe;display:flex;align-items:center;justify-content:center;font-size:15px;font-weight:600;color:#1a56db;flex-shrink:0;border:0.5px solid #c3d5fc}
.an-name{font-size:15px;font-weight:600;color:#111;margin:0 0 3px}
.an-org{font-size:12px;color:#666;margin:0}
.prof-links{display:flex;flex-direction:column;gap:8px}
.pl-row{display:flex;align-items:center;gap:10px;text-decoration:none;padding:8px 10px;background:#f7f7f8;border-radius:8px;border:0.5px solid #e0e0e0}
.pl-icon{width:26px;height:26px;border-radius:6px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.pl-icon.li{background:#e8f0fe}
.pl-icon.gh{background:#f7f7f8;border:0.5px solid #e0e0e0}
.pl-icon svg{width:13px;height:13px}
.pl-lbl{font-size:11px;color:#999;margin:0 0 1px}
.pl-val{font-size:12px;font-weight:600;color:#1a56db;margin:0}
.outputs-card{background:#fff;border:0.5px solid #e0e0e0;border-radius:12px;padding:20px}
.fig-list{display:flex;flex-direction:column;gap:7px}
.fig-row{display:flex;align-items:center;justify-content:space-between;padding:7px 10px;background:#f7f7f8;border-radius:8px}
.fig-name{font-size:12px;color:#111;margin:0}
.fig-tag{font-size:11px;color:#666;background:#fff;border:0.5px solid #e0e0e0;padding:2px 8px;border-radius:8px}
.foot{display:flex;align-items:center;justify-content:space-between;margin-top:16px;background:#f7f7f8;border:0.5px solid #e0e0e0;border-radius:12px;padding:12px 20px}
.foot-text{font-size:12px;color:#999;margin:0}
</style>

<div class="conc-wrap">
  <div class="conc-header">
    <span class="conc-label">Cognifyz Technologies &nbsp;·&nbsp; Geographic Analysis &nbsp;·&nbsp; Conclusion</span>
    <span class="complete-badge">Analysis complete</span>
  </div>
  <div class="findings-grid">
    <div class="finding-card"><p class="f-num">Finding 1</p><p class="f-stat">90.1%</p><p class="f-desc">India's share of the global dataset — driven by New Delhi, Gurgaon &amp; Noida</p></div>
    <div class="finding-card"><p class="f-num">Finding 2</p><p class="f-stat">DBSCAN</p><p class="f-desc">Multiple spatial clusters detected via Haversine distance — 3.2% noise outliers</p></div>
    <div class="finding-card"><p class="f-num">Finding 3</p><p class="f-stat">0.15°</p><p class="f-desc">IQR latitude span — 50% of all records within ~17 km of each other</p></div>
    <div class="finding-card"><p class="f-num">Finding 4</p><p class="f-stat">2.73</p><p class="f-desc">Global average aggregate rating — only 12% of restaurants score above 4.0</p></div>
    <div class="finding-card"><p class="f-num">Finding 5</p><p class="f-stat">434</p><p class="f-desc">US restaurants — the largest international cluster outside South Asia</p></div>
    <div class="finding-card"><p class="f-num">Finding 6</p><p class="f-stat">7 figs</p><p class="f-desc">Publication-quality visualizations spanning global, regional &amp; cluster views</p></div>
  </div>
  <div class="bottom-grid">
    <div class="analyst-card">
      <p class="card-title">Analyst</p>
      <div class="analyst-row">
        <div class="av-sm">KT</div>
        <div><p class="an-name">Karthikeyan Thirunavukkarasu</p><p class="an-org">Data Science Intern · Cognifyz Technologies</p></div>
      </div>
      <div class="prof-links">
        <a class="pl-row" href="https://www.linkedin.com/in/karthikeyan-thirunavukkarasu-2a2949305">
          <div class="pl-icon li"><svg viewBox="0 0 24 24" fill="none"><rect x="2" y="2" width="20" height="20" rx="4" fill="#1a56db"/><path d="M7 10v7M7 7v.5M12 17v-4a2 2 0 014 0v4M12 10v7" stroke="#fff" stroke-width="1.8" stroke-linecap="round"/></svg></div>
          <div><p class="pl-lbl">LinkedIn</p><p class="pl-val">karthikeyan-thirunavukkarasu-2a2949305</p></div>
        </a>
        <a class="pl-row" href="https://github.com/karthiikofcl07">
          <div class="pl-icon gh"><svg viewBox="0 0 24 24" fill="#111"><path d="M12 2C6.477 2 2 6.477 2 12c0 4.418 2.865 8.166 6.839 9.489.5.092.682-.217.682-.482 0-.237-.009-.866-.013-1.7-2.782.604-3.369-1.34-3.369-1.34-.454-1.154-1.11-1.462-1.11-1.462-.908-.62.069-.608.069-.608 1.003.07 1.531 1.03 1.531 1.03.892 1.529 2.341 1.087 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.11-4.555-4.943 0-1.091.39-1.984 1.029-2.683-.103-.253-.446-1.27.098-2.647 0 0 .84-.268 2.75 1.026A9.578 9.578 0 0112 6.836a9.59 9.59 0 012.504.337c1.909-1.294 2.747-1.026 2.747-1.026.546 1.377.202 2.394.1 2.647.64.699 1.028 1.592 1.028 2.683 0 3.842-2.339 4.687-4.566 4.935.359.309.678.919.678 1.852 0 1.336-.012 2.415-.012 2.743 0 .267.18.578.688.48C19.138 20.163 22 16.418 22 12c0-5.523-4.477-10-10-10z"/></svg></div>
          <div><p class="pl-lbl">GitHub</p><p class="pl-val">karthiikofcl07</p></div>
        </a>
      </div>
    </div>
    <div class="outputs-card">
      <p class="card-title">Deliverables produced</p>
      <div class="fig-list">
        <div class="fig-row"><p class="fig-name">Global scatter map</p><span class="fig-tag">fig1</span></div>
        <div class="fig-row"><p class="fig-name">KDE density heatmap</p><span class="fig-tag">fig2</span></div>
        <div class="fig-row"><p class="fig-name">DBSCAN cluster map</p><span class="fig-tag">fig3</span></div>
        <div class="fig-row"><p class="fig-name">City bubble map</p><span class="fig-tag">fig4</span></div>
        <div class="fig-row"><p class="fig-name">4-panel deep-dive</p><span class="fig-tag">fig5</span></div>
        <div class="fig-row"><p class="fig-name">Marginal distributions</p><span class="fig-tag">fig6</span></div>
        <div class="fig-row"><p class="fig-name">Cluster quality matrix</p><span class="fig-tag">fig7</span></div>
      </div>
    </div>
  </div>
  <div class="foot">
    <p class="foot-text">All analysis, code, and visualizations are original work by the analyst.</p>
    <p class="foot-text">Cognifyz Technologies · Data Science Internship · 2024</p>
  </div>
</div>
"""

print("Intro cell length  :", len(INTRO_CELL), "chars")
print("Conclusion cell len:", len(CONCLUSION_CELL), "chars")
