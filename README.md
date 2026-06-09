<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Global Solution 2026 — Monitoramento de Fauna</title>
<style>
  :root {
    --bg: #0d0f14;
    --surface: #13161d;
    --surface2: #1a1e28;
    --border: rgba(255,255,255,0.07);
    --border2: rgba(255,255,255,0.13);
    --text: #e2e4ea;
    --muted: #7a7f8e;
    --accent: #4ea8de;
    --accent2: #63d4a8;
    --accent3: #c49af5;
    --warn: #f5a623;
    --radius: 10px;
    --mono: 'Cascadia Code', 'Fira Code', 'Consolas', monospace;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
    font-size: 15px;
    line-height: 1.7;
    max-width: 900px;
    margin: 0 auto;
    padding: 48px 32px 80px;
  }

  /* ── HERO ── */
  .hero {
    border-bottom: 1px solid var(--border2);
    padding-bottom: 40px;
    margin-bottom: 48px;
  }
  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: .08em;
    text-transform: uppercase;
    color: var(--accent);
    border: 1px solid rgba(78,168,222,.3);
    border-radius: 20px;
    padding: 4px 12px;
    margin-bottom: 20px;
  }
  .hero h1 {
    font-size: 32px;
    font-weight: 700;
    letter-spacing: -.02em;
    line-height: 1.2;
    color: #fff;
    margin-bottom: 10px;
  }
  .hero p {
    font-size: 16px;
    color: var(--muted);
    max-width: 600px;
  }

  /* ── TEAM TABLE ── */
  .team-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 14px;
  }
  .team-table thead th {
    text-align: left;
    padding: 8px 14px;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: .07em;
    text-transform: uppercase;
    color: var(--muted);
    border-bottom: 1px solid var(--border);
  }
  .team-table tbody td {
    padding: 10px 14px;
    border-bottom: 1px solid var(--border);
  }
  .team-table tbody tr:last-child td { border-bottom: none; }

  /* ── SECTION ── */
  .section {
    margin-bottom: 56px;
  }
  .section-label {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: .1em;
    text-transform: uppercase;
    color: var(--accent2);
    margin-bottom: 10px;
  }
  .section h2 {
    font-size: 22px;
    font-weight: 700;
    color: #fff;
    letter-spacing: -.01em;
    margin-bottom: 16px;
  }
  .section p, .section li {
    color: #b0b5c4;
    line-height: 1.75;
  }

  /* ── OBJETIVO LIST ── */
  .goal-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    list-style: none;
  }
  .goal-list li {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 12px 16px;
    font-size: 14px;
    color: var(--text);
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .goal-list li::before {
    content: '';
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--accent2);
    flex-shrink: 0;
  }

  /* ── TECH STACK ── */
  .tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 14px;
  }
  .tech-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 16px 18px;
  }
  .tech-card h4 {
    font-size: 12px;
    font-weight: 600;
    letter-spacing: .07em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 10px;
  }
  .tech-card ul { list-style: none; }
  .tech-card li {
    font-size: 13.5px;
    color: var(--text);
    padding: 3px 0;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .tech-card li::before {
    content: '';
    width: 5px;
    height: 5px;
    border-radius: 50%;
    flex-shrink: 0;
  }
  .tech-card.backend li::before { background: var(--accent); }
  .tech-card.db li::before { background: var(--accent2); }
  .tech-card.ml li::before { background: var(--accent3); }
  .tech-card.integ li::before { background: var(--warn); }

  /* ── DIAGRAMS ── */
  .diagram-wrap {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 28px 24px;
    overflow-x: auto;
  }
  .diagram-title {
    font-size: 12px;
    font-weight: 600;
    letter-spacing: .08em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 20px;
  }

  /* ── OOP CONCEITOS ── */
  .oop-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }
  .oop-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 16px 18px;
  }
  .oop-card h4 {
    font-size: 13px;
    font-weight: 600;
    color: var(--accent3);
    margin-bottom: 8px;
  }
  .oop-card p { font-size: 13.5px; color: #9097a8; }
  .code-inline {
    font-family: var(--mono);
    font-size: 12.5px;
    background: rgba(255,255,255,.06);
    border: 1px solid var(--border2);
    border-radius: 5px;
    padding: 1px 6px;
    color: var(--accent2);
  }

  /* ── ENDPOINTS ── */
  .endpoint {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    margin-bottom: 14px;
    overflow: hidden;
  }
  .endpoint-header {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 12px 16px;
    border-bottom: 1px solid var(--border);
  }
  .method {
    font-family: var(--mono);
    font-size: 11.5px;
    font-weight: 700;
    padding: 3px 8px;
    border-radius: 5px;
  }
  .method.post { background: rgba(99,212,168,.15); color: var(--accent2); border: 1px solid rgba(99,212,168,.25); }
  .method.get  { background: rgba(78,168,222,.15); color: var(--accent);  border: 1px solid rgba(78,168,222,.25); }
  .endpoint-path {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--text);
  }
  .endpoint-body { padding: 14px 16px; }
  pre {
    font-family: var(--mono);
    font-size: 13px;
    color: #a8d4f5;
    line-height: 1.6;
    overflow-x: auto;
    background: rgba(0,0,0,.3);
    border-radius: 6px;
    padding: 12px 14px;
    margin-top: 8px;
  }

  /* ── STRUCTURE TREE ── */
  .tree {
    font-family: var(--mono);
    font-size: 13px;
    color: #9097a8;
    line-height: 2;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 20px 24px;
  }
  .tree .dir { color: var(--accent); font-weight: 600; }
  .tree .file { color: #b0b5c4; }

  /* ── DIVIDER ── */
  hr { border: none; border-top: 1px solid var(--border); margin: 40px 0; }

  /* ── EXCEPTION BOX ── */
  .exception-box {
    background: rgba(245,166,35,.06);
    border: 1px solid rgba(245,166,35,.2);
    border-radius: var(--radius);
    padding: 16px 20px;
    display: flex;
    gap: 14px;
    align-items: flex-start;
  }
  .exception-icon { font-size: 18px; flex-shrink: 0; margin-top: 1px; }
  .exception-box p { font-size: 14px; color: #c4aa7a; }
  .exception-box .code-inline { background: rgba(245,166,35,.1); color: var(--warn); }

  /* ── SETUP STEPS ── */
  .steps { list-style: none; display: flex; flex-direction: column; gap: 10px; }
  .steps li {
    display: flex;
    gap: 14px;
    align-items: flex-start;
  }
  .step-num {
    width: 26px;
    height: 26px;
    border-radius: 50%;
    background: var(--surface2);
    border: 1px solid var(--border2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 12px;
    font-weight: 700;
    color: var(--accent);
    flex-shrink: 0;
    margin-top: 2px;
  }
  .steps pre { margin-top: 4px; }

  /* ── FOOTER ── */
  .footer {
    margin-top: 64px;
    padding-top: 28px;
    border-top: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
  }
  .footer p { font-size: 13px; color: var(--muted); }
  .footer a {
    font-size: 13px;
    color: var(--accent);
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 5px;
  }
  .footer a:hover { text-decoration: underline; }

  /* ── DB TABLE ── */
  .db-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  .db-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    overflow: hidden;
  }
  .db-card-header {
    background: var(--surface2);
    border-bottom: 1px solid var(--border);
    padding: 10px 14px;
    font-size: 12px;
    font-weight: 600;
    letter-spacing: .06em;
    text-transform: uppercase;
    color: var(--accent2);
  }
  .db-card ul { list-style: none; padding: 12px 14px; display: flex; flex-direction: column; gap: 6px; }
  .db-card li { font-size: 13px; color: #9097a8; display: flex; align-items: center; gap: 8px; }
  .db-card li::before { content: ''; width: 5px; height: 5px; border-radius: 50%; background: var(--border2); flex-shrink: 0; }

  @media (max-width: 640px) {
    .goal-list, .oop-grid, .db-grid { grid-template-columns: 1fr; }
    body { padding: 28px 18px 60px; }
    .hero h1 { font-size: 24px; }
  }
</style>
</head>
<body>

<!-- ═══════════════ HERO ═══════════════ -->
<div class="hero">
  <div class="hero-badge">🛰️ Global Solution 2026</div>
  <h1>Monitoramento de Fauna<br>por Telemetria Espacial</h1>
  <p>Sistema inteligente para identificação precoce de alterações comportamentais em espécies monitoradas via biotelemetria e satélites LEO.</p>
</div>

<!-- ═══════════════ INTEGRANTES ═══════════════ -->
<div class="section">
  <div class="section-label">Equipe</div>
  <table class="team-table">
    <thead>
      <tr><th>Nome</th><th>RM</th></tr>
    </thead>
    <tbody>
      <tr><td>Nome Completo</td><td>XXXXXXX</td></tr>
      <tr><td>Nome Completo</td><td>XXXXXXX</td></tr>
      <tr><td>Nome Completo</td><td>XXXXXXX</td></tr>
    </tbody>
  </table>
</div>

<!-- ═══════════════ SOBRE ═══════════════ -->
<div class="section">
  <div class="section-label">O Projeto</div>
  <h2>O que a solução faz</h2>
  <p>Dispositivos de biotelemetria acoplados aos animais transmitem dados fisiológicos e geográficos contínuos para satélites de baixa órbita (LEO). Esses dados chegam a uma API ASP.NET Core que os repassa a um serviço de Machine Learning em Python — responsável por detectar anomalias e prever eventos ambientais de risco. Os resultados ficam persistidos no SQL Server para rastreabilidade, histórico e suporte à tomada de decisão.</p>
</div>

<!-- ═══════════════ OBJETIVOS ═══════════════ -->
<div class="section">
  <div class="section-label">Objetivos</div>
  <ul class="goal-list">
    <li>Centralizar dados de telemetria animal</li>
    <li>Processar informações em tempo real</li>
    <li>Detectar padrões comportamentais anômalos</li>
    <li>Aplicar modelos de Machine Learning</li>
    <li>Gerar alertas preventivos</li>
    <li>Disponibilizar histórico de análises</li>
  </ul>
</div>

<hr>

<!-- ═══════════════ ARQUITETURA ═══════════════ -->
<div class="section">
  <div class="section-label">Arquitetura</div>
  <h2>Visão geral da solução</h2>
  <p style="margin-bottom:20px">Construída sobre SOA, WebServices, POO e Repository Pattern — cada camada tem responsabilidade única e se comunica via interfaces bem definidas.</p>
  <div class="diagram-wrap">
    <div class="diagram-title">Fluxo de dados — da tag ao consumidor</div>
    <svg width="100%" viewBox="0 0 820 200" role="img">
      <title>Diagrama de arquitetura: da tag de biotelemetria até as aplicações consumidoras</title>
      <defs>
        <marker id="arr" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
          <path d="M2 1L8 5L2 9" fill="none" stroke="context-stroke" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </marker>
      </defs>

      <!-- Node styles inline -->
      <!-- Coleta -->
      <rect x="10" y="60" width="130" height="42" rx="8" fill="#1a1e28" stroke="rgba(78,168,222,.35)" stroke-width="1"/>
      <text x="75" y="76" text-anchor="middle" fill="#4ea8de" font-size="11" font-weight="600" font-family="-apple-system,sans-serif" letter-spacing=".04em">COLETA</text>
      <text x="75" y="93" text-anchor="middle" fill="#b0b5c4" font-size="12" font-family="-apple-system,sans-serif">Tag → Satélite LEO</text>

      <!-- Arrow -->
      <line x1="142" y1="81" x2="168" y2="81" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr)"/>

      <!-- API -->
      <rect x="170" y="30" width="150" height="102" rx="8" fill="#1a1e28" stroke="rgba(99,212,168,.3)" stroke-width="1"/>
      <text x="245" y="50" text-anchor="middle" fill="#63d4a8" font-size="11" font-weight="600" font-family="-apple-system,sans-serif" letter-spacing=".04em">API ASP.NET CORE</text>
      <text x="245" y="70" text-anchor="middle" fill="#7a7f8e" font-size="11" font-family="-apple-system,sans-serif">TelemetryController</text>
      <line x1="245" y1="74" x2="245" y2="86" stroke="#3d4455" stroke-width="1"/>
      <text x="245" y="98" text-anchor="middle" fill="#7a7f8e" font-size="11" font-family="-apple-system,sans-serif">PredictionService</text>
      <line x1="245" y1="102" x2="245" y2="114" stroke="#3d4455" stroke-width="1"/>
      <text x="245" y="124" text-anchor="middle" fill="#7a7f8e" font-size="11" font-family="-apple-system,sans-serif">PredictionRepository</text>

      <!-- Arrow para ML -->
      <line x1="322" y1="65" x2="358" y2="65" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr)"/>
      <line x1="358" y1="65" x2="322" y2="65" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr)"/>
      <!-- two-way: overwrite with proper two arrows -->
      <line x1="322" y1="60" x2="358" y2="60" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr)"/>
      <line x1="358" y1="70" x2="322" y2="70" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr)"/>

      <!-- ML -->
      <rect x="360" y="40" width="140" height="62" rx="8" fill="#1a1e28" stroke="rgba(196,154,245,.3)" stroke-width="1"/>
      <text x="430" y="60" text-anchor="middle" fill="#c49af5" font-size="11" font-weight="600" font-family="-apple-system,sans-serif" letter-spacing=".04em">ML SERVICE</text>
      <text x="430" y="78" text-anchor="middle" fill="#7a7f8e" font-size="11" font-family="-apple-system,sans-serif">Python · FastAPI</text>
      <text x="430" y="94" text-anchor="middle" fill="#7a7f8e" font-size="11" font-family="-apple-system,sans-serif">Isolation Forest · LSTM · XGBoost</text>

      <!-- Arrow para DB -->
      <line x1="245" y1="132" x2="245" y2="148" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr)"/>

      <!-- DB -->
      <rect x="170" y="150" width="150" height="38" rx="8" fill="#1a1e28" stroke="rgba(99,212,168,.25)" stroke-width="1"/>
      <text x="245" y="165" text-anchor="middle" fill="#63d4a8" font-size="11" font-weight="600" font-family="-apple-system,sans-serif" letter-spacing=".04em">SQL SERVER</text>
      <text x="245" y="180" text-anchor="middle" fill="#7a7f8e" font-size="11" font-family="-apple-system,sans-serif">PredictionHistory · SpaceEquipment</text>

      <!-- Arrow para Consumer -->
      <line x1="322" y1="81" x2="548" y2="81" stroke="#3d4455" stroke-width="1.5" stroke-dasharray="5 4" marker-end="url(#arr)"/>

      <!-- Consumer -->
      <rect x="550" y="60" width="140" height="42" rx="8" fill="#1a1e28" stroke="rgba(255,255,255,.1)" stroke-width="1"/>
      <text x="620" y="76" text-anchor="middle" fill="#9097a8" font-size="11" font-weight="600" font-family="-apple-system,sans-serif" letter-spacing=".04em">CONSUMERS</text>
      <text x="620" y="93" text-anchor="middle" fill="#6a6f7e" font-size="11" font-family="-apple-system,sans-serif">REST · Aplicações externas</text>

      <!-- Labels de setas -->
      <text x="155" y="73" text-anchor="middle" fill="#4a5168" font-size="10" font-family="-apple-system,sans-serif">dados</text>
      <text x="430" y="148" text-anchor="middle" fill="#4a5168" font-size="10" font-family="-apple-system,sans-serif"></text>
      <text x="436" y="72" text-anchor="middle" fill="#4a5168" font-size="10" font-family="-apple-system,sans-serif">predict</text>
      <text x="435" y="78" text-anchor="middle" fill="#4a5168" font-size="10" font-family="-apple-system,sans-serif"></text>
    </svg>
  </div>
</div>

<!-- ═══════════════ FLUXO OPERACIONAL ═══════════════ -->
<div class="section">
  <div class="section-label">Fluxo Operacional</div>
  <h2>Do dado bruto ao alerta</h2>
  <div class="diagram-wrap">
    <div class="diagram-title">Pipeline de processamento</div>
    <svg width="100%" viewBox="0 0 820 86" role="img">
      <title>Fluxo operacional: recebimento → validação → processamento → ML → anomalia? → alerta → persistência → API</title>
      <defs>
        <marker id="arr2" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
          <path d="M2 1L8 5L2 9" fill="none" stroke="context-stroke" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </marker>
      </defs>

      <!-- Boxes -->
      <!-- 1 Recebimento -->
      <rect x="10"  y="22" width="90" height="42" rx="7" fill="#1a1e28" stroke="rgba(78,168,222,.3)" stroke-width="1"/>
      <text x="55"  y="40" text-anchor="middle" fill="#7a7f8e" font-size="10" font-family="-apple-system,sans-serif">1</text>
      <text x="55"  y="55" text-anchor="middle" fill="#b0b5c4" font-size="11" font-weight="500" font-family="-apple-system,sans-serif">Recebimento</text>

      <!-- arrow -->
      <line x1="102" y1="43" x2="118" y2="43" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr2)"/>

      <!-- 2 Validação -->
      <rect x="120" y="22" width="82" height="42" rx="7" fill="#1a1e28" stroke="rgba(78,168,222,.2)" stroke-width="1"/>
      <text x="161" y="40" text-anchor="middle" fill="#7a7f8e" font-size="10" font-family="-apple-system,sans-serif">2</text>
      <text x="161" y="55" text-anchor="middle" fill="#b0b5c4" font-size="11" font-weight="500" font-family="-apple-system,sans-serif">Validação</text>

      <line x1="204" y1="43" x2="218" y2="43" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr2)"/>

      <!-- 3 API -->
      <rect x="220" y="22" width="98" height="42" rx="7" fill="#1a1e28" stroke="rgba(99,212,168,.2)" stroke-width="1"/>
      <text x="269" y="40" text-anchor="middle" fill="#7a7f8e" font-size="10" font-family="-apple-system,sans-serif">3</text>
      <text x="269" y="55" text-anchor="middle" fill="#b0b5c4" font-size="11" font-weight="500" font-family="-apple-system,sans-serif">Processamento</text>

      <line x1="320" y1="43" x2="334" y2="43" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr2)"/>

      <!-- 4 ML -->
      <rect x="336" y="22" width="74" height="42" rx="7" fill="#1a1e28" stroke="rgba(196,154,245,.3)" stroke-width="1"/>
      <text x="373" y="40" text-anchor="middle" fill="#7a7f8e" font-size="10" font-family="-apple-system,sans-serif">4</text>
      <text x="373" y="55" text-anchor="middle" fill="#b0b5c4" font-size="11" font-weight="500" font-family="-apple-system,sans-serif">ML Analysis</text>

      <line x1="412" y1="43" x2="426" y2="43" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr2)"/>

      <!-- 5 Decisão (diamond-ish with rounded rect) -->
      <rect x="428" y="18" width="92" height="50" rx="7" fill="#1a1e28" stroke="rgba(245,166,35,.35)" stroke-width="1"/>
      <text x="474" y="38" text-anchor="middle" fill="#f5a623" font-size="10" font-family="-apple-system,sans-serif" font-weight="600">ANOMALIA?</text>
      <text x="474" y="55" text-anchor="middle" fill="#8a7040" font-size="10" font-family="-apple-system,sans-serif">sim / não</text>

      <line x1="522" y1="43" x2="536" y2="43" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr2)"/>

      <!-- 6 Alerta -->
      <rect x="538" y="22" width="76" height="42" rx="7" fill="#1a1e28" stroke="rgba(245,166,35,.2)" stroke-width="1"/>
      <text x="576" y="40" text-anchor="middle" fill="#7a7f8e" font-size="10" font-family="-apple-system,sans-serif">6</text>
      <text x="576" y="55" text-anchor="middle" fill="#b0b5c4" font-size="11" font-weight="500" font-family="-apple-system,sans-serif">Alerta</text>

      <line x1="616" y1="43" x2="630" y2="43" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr2)"/>

      <!-- 7 Persistência -->
      <rect x="632" y="22" width="90" height="42" rx="7" fill="#1a1e28" stroke="rgba(99,212,168,.2)" stroke-width="1"/>
      <text x="677" y="40" text-anchor="middle" fill="#7a7f8e" font-size="10" font-family="-apple-system,sans-serif">7</text>
      <text x="677" y="55" text-anchor="middle" fill="#b0b5c4" font-size="11" font-weight="500" font-family="-apple-system,sans-serif">Persistência</text>

      <line x1="724" y1="43" x2="738" y2="43" stroke="#3d4455" stroke-width="1.5" marker-end="url(#arr2)"/>

      <!-- 8 REST -->
      <rect x="740" y="22" width="72" height="42" rx="7" fill="#1a1e28" stroke="rgba(78,168,222,.2)" stroke-width="1"/>
      <text x="776" y="40" text-anchor="middle" fill="#7a7f8e" font-size="10" font-family="-apple-system,sans-serif">8</text>
      <text x="776" y="55" text-anchor="middle" fill="#b0b5c4" font-size="11" font-weight="500" font-family="-apple-system,sans-serif">REST API</text>
    </svg>
  </div>
</div>

<!-- ═══════════════ SEQUÊNCIA ═══════════════ -->
<div class="section">
  <div class="section-label">Sequência de Chamadas</div>
  <h2>Como os componentes se comunicam</h2>
  <div class="diagram-wrap">
    <div class="diagram-title">Diagrama de sequência simplificado</div>
    <svg width="100%" viewBox="0 0 820 320" role="img">
      <title>Sequência: BiotelemetryTag envia para Satellite, que repassa ao Controller, que aciona PredictionService, que chama ML Python, retorna resultado, persiste no DB e responde ao Controller</title>
      <defs>
        <marker id="arr3" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
          <path d="M2 1L8 5L2 9" fill="none" stroke="context-stroke" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </marker>
      </defs>

      <!-- Lifeline labels -->
      <text x="70"  y="22" text-anchor="middle" fill="#9097a8" font-size="11" font-family="-apple-system,sans-serif" font-weight="600">Tag</text>
      <text x="200" y="22" text-anchor="middle" fill="#9097a8" font-size="11" font-family="-apple-system,sans-serif" font-weight="600">Satellite</text>
      <text x="350" y="22" text-anchor="middle" fill="#9097a8" font-size="11" font-family="-apple-system,sans-serif" font-weight="600">Controller</text>
      <text x="510" y="22" text-anchor="middle" fill="#9097a8" font-size="11" font-family="-apple-system,sans-serif" font-weight="600">PredictionService</text>
      <text x="660" y="22" text-anchor="middle" fill="#9097a8" font-size="11" font-family="-apple-system,sans-serif" font-weight="600">Python ML</text>
      <text x="780" y="22" text-anchor="middle" fill="#9097a8" font-size="11" font-family="-apple-system,sans-serif" font-weight="600">Database</text>

      <!-- Lifelines -->
      <line x1="70"  y1="28" x2="70"  y2="310" stroke="#2a2e3e" stroke-width="1" stroke-dasharray="4 3"/>
      <line x1="200" y1="28" x2="200" y2="310" stroke="#2a2e3e" stroke-width="1" stroke-dasharray="4 3"/>
      <line x1="350" y1="28" x2="350" y2="310" stroke="#2a2e3e" stroke-width="1" stroke-dasharray="4 3"/>
      <line x1="510" y1="28" x2="510" y2="310" stroke="#2a2e3e" stroke-width="1" stroke-dasharray="4 3"/>
      <line x1="660" y1="28" x2="660" y2="310" stroke="#2a2e3e" stroke-width="1" stroke-dasharray="4 3"/>
      <line x1="780" y1="28" x2="780" y2="310" stroke="#2a2e3e" stroke-width="1" stroke-dasharray="4 3"/>

      <!-- Messages -->
      <!-- 1: Tag → Satellite -->
      <line x1="72" y1="60" x2="198" y2="60" stroke="#4ea8de" stroke-width="1.2" marker-end="url(#arr3)"/>
      <text x="135" y="55" text-anchor="middle" fill="#3d6a8a" font-size="10" font-family="-apple-system,sans-serif">telemetria</text>

      <!-- 2: Satellite → Controller -->
      <line x1="202" y1="90" x2="348" y2="90" stroke="#4ea8de" stroke-width="1.2" marker-end="url(#arr3)"/>
      <text x="275" y="85" text-anchor="middle" fill="#3d6a8a" font-size="10" font-family="-apple-system,sans-serif">dados coletados</text>

      <!-- 3: Controller → PredictionService -->
      <line x1="352" y1="120" x2="508" y2="120" stroke="#63d4a8" stroke-width="1.2" marker-end="url(#arr3)"/>
      <text x="430" y="115" text-anchor="middle" fill="#2d6a52" font-size="10" font-family="-apple-system,sans-serif">solicita predição</text>

      <!-- 4: PredictionService → Python ML -->
      <line x1="512" y1="152" x2="658" y2="152" stroke="#c49af5" stroke-width="1.2" marker-end="url(#arr3)"/>
      <text x="585" y="147" text-anchor="middle" fill="#5a4a7a" font-size="10" font-family="-apple-system,sans-serif">POST /predict</text>

      <!-- 5: ML → PredictionService (return) -->
      <line x1="658" y1="184" x2="512" y2="184" stroke="#c49af5" stroke-width="1.2" stroke-dasharray="5 3" marker-end="url(#arr3)"/>
      <text x="585" y="179" text-anchor="middle" fill="#5a4a7a" font-size="10" font-family="-apple-system,sans-serif">resultado da análise</text>

      <!-- 6: PredictionService → Database -->
      <line x1="512" y1="218" x2="778" y2="218" stroke="#63d4a8" stroke-width="1.2" marker-end="url(#arr3)"/>
      <text x="645" y="213" text-anchor="middle" fill="#2d6a52" font-size="10" font-family="-apple-system,sans-serif">salvar histórico</text>

      <!-- 7: Database → PredictionService (confirm) -->
      <line x1="778" y1="248" x2="512" y2="248" stroke="#63d4a8" stroke-width="1.2" stroke-dasharray="5 3" marker-end="url(#arr3)"/>
      <text x="645" y="243" text-anchor="middle" fill="#2d6a52" font-size="10" font-family="-apple-system,sans-serif">confirmação</text>

      <!-- 8: PredictionService → Controller -->
      <line x1="508" y1="280" x2="352" y2="280" stroke="#63d4a8" stroke-width="1.2" stroke-dasharray="5 3" marker-end="url(#arr3)"/>
      <text x="430" y="275" text-anchor="middle" fill="#2d6a52" font-size="10" font-family="-apple-system,sans-serif">retorno da predição</text>
    </svg>
  </div>
</div>

<hr>

<!-- ═══════════════ OOP ═══════════════ -->
<div class="section">
  <div class="section-label">Programação Orientada a Objetos</div>
  <h2>Conceitos aplicados</h2>
  <div class="oop-grid">
    <div class="oop-card">
      <h4>Encapsulamento</h4>
      <p>Atributos das entidades protegidos com acesso controlado, expondo apenas o que é necessário via propriedades e DTOs.</p>
    </div>
    <div class="oop-card">
      <h4>Herança</h4>
      <p><span class="code-inline">SpaceEquipment</span> é a classe base abstrata. <span class="code-inline">Satellite</span> e <span class="code-inline">BiotelemetryTag</span> herdam e estendem seu comportamento.</p>
    </div>
    <div class="oop-card">
      <h4>Polimorfismo</h4>
      <p>O método <span class="code-inline">TransmitDiagnostic()</span> é implementado de forma independente em cada equipamento, preservando a mesma assinatura.</p>
    </div>
    <div class="oop-card">
      <h4>Abstração</h4>
      <p><span class="code-inline">SpaceEquipment</span> define o contrato comum. Os detalhes de cada tipo de equipamento ficam encapsulados nas subclasses.</p>
    </div>
  </div>
</div>

<!-- ═══════════════ CLASSES ═══════════════ -->
<div class="section">
  <div class="section-label">Diagrama de Classes</div>
  <div class="diagram-wrap">
    <div class="diagram-title">Hierarquia e relacionamentos</div>
    <svg width="100%" viewBox="0 0 820 340" role="img">
      <title>Diagrama de classes mostrando SpaceEquipment como abstract, herdado por Satellite e BiotelemetryTag, com PredictionHistory, ITelemetryPredictionService e IGenericRepository</title>
      <defs>
        <marker id="arr4" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
          <path d="M2 1L8 5L2 9" fill="none" stroke="context-stroke" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </marker>
        <marker id="tri" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="8" markerHeight="8" orient="auto-start-reverse">
          <path d="M0 0L10 5L0 10Z" fill="#2a2e3e" stroke="#4ea8de" stroke-width="1"/>
        </marker>
        <marker id="tri2" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="8" markerHeight="8" orient="auto-start-reverse">
          <path d="M0 0L10 5L0 10Z" fill="#2a2e3e" stroke="#c49af5" stroke-width="1"/>
        </marker>
        <marker id="tri3" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="8" markerHeight="8" orient="auto-start-reverse">
          <path d="M0 0L10 5L0 10Z" fill="#2a2e3e" stroke="#63d4a8" stroke-width="1"/>
        </marker>
      </defs>

      <!-- SpaceEquipment (abstract, top center) -->
      <rect x="280" y="10" width="180" height="80" rx="8" fill="#1a1e28" stroke="rgba(78,168,222,.4)" stroke-width="1"/>
      <rect x="280" y="10" width="180" height="26" rx="8" fill="rgba(78,168,222,.08)"/>
      <rect x="280" y="28" width="180" height="8" fill="rgba(78,168,222,.08)"/>
      <text x="370" y="28" text-anchor="middle" fill="#4a6070" font-size="10" font-family="-apple-system,sans-serif" font-style="italic">«abstract»</text>
      <text x="370" y="46" text-anchor="middle" fill="#4ea8de" font-size="12" font-weight="600" font-family="-apple-system,sans-serif">SpaceEquipment</text>
      <text x="295" y="65" fill="#7a7f8e" font-size="10.5" font-family="-apple-system,sans-serif">+ Id, Name</text>
      <text x="295" y="81" fill="#7a7f8e" font-size="10.5" font-family="-apple-system,sans-serif">+ TransmitDiagnostic()</text>

      <!-- Herança → Satellite -->
      <line x1="340" y1="90" x2="170" y2="152" stroke="#4ea8de" stroke-width="1" stroke-dasharray="0" marker-end="url(#tri)"/>

      <!-- Herança → BiotelemetryTag -->
      <line x1="400" y1="90" x2="560" y2="152" stroke="#4ea8de" stroke-width="1" marker-end="url(#tri)"/>

      <!-- Satellite -->
      <rect x="80" y="154" width="170" height="80" rx="8" fill="#1a1e28" stroke="rgba(78,168,222,.25)" stroke-width="1"/>
      <text x="165" y="178" text-anchor="middle" fill="#4ea8de" font-size="12" font-weight="600" font-family="-apple-system,sans-serif">Satellite</text>
      <text x="96" y="198" fill="#7a7f8e" font-size="10.5" font-family="-apple-system,sans-serif">+ OrbitType</text>
      <text x="96" y="214" fill="#7a7f8e" font-size="10.5" font-family="-apple-system,sans-serif">+ TransmitDiagnostic()</text>
      <text x="96" y="230" fill="#7a7f8e" font-size="10.5" font-family="-apple-system,sans-serif">+ AltitudeKm</text>

      <!-- BiotelemetryTag -->
      <rect x="470" y="154" width="190" height="94" rx="8" fill="#1a1e28" stroke="rgba(78,168,222,.25)" stroke-width="1"/>
      <text x="565" y="178" text-anchor="middle" fill="#4ea8de" font-size="12" font-weight="600" font-family="-apple-system,sans-serif">BiotelemetryTag</text>
      <text x="486" y="198" fill="#7a7f8e" font-size="10.5" font-family="-apple-system,sans-serif">+ SpeciesId</text>
      <text x="486" y="213" fill="#7a7f8e" font-size="10.5" font-family="-apple-system,sans-serif">+ HeartRate</text>
      <text x="486" y="228" fill="#7a7f8e" font-size="10.5" font-family="-apple-system,sans-serif">+ Acceleration</text>
      <text x="486" y="243" fill="#7a7f8e" font-size="10.5" font-family="-apple-system,sans-serif">+ TransmitDiagnostic()</text>

      <!-- BiotelemetryTag → PredictionHistory -->
      <line x1="565" y1="248" x2="565" y2="274" stroke="#63d4a8" stroke-width="1" stroke-dasharray="4 3" marker-end="url(#arr4)"/>

      <!-- PredictionHistory -->
      <rect x="460" y="276" width="200" height="56" rx="8" fill="#1a1e28" stroke="rgba(99,212,168,.25)" stroke-width="1"/>
      <text x="560" y="296" text-anchor="middle" fill="#63d4a8" font-size="12" font-weight="600" font-family="-apple-system,sans-serif">PredictionHistory</text>
      <text x="476" y="313" fill="#7a7f8e" font-size="10.5" font-family="-apple-system,sans-serif">+ SpeciesId, Probability, AlertLevel, AnalysisDate</text>

      <!-- Interfaces - right column -->
      <!-- ITelemetryPredictionService -->
      <rect x="680" y="10" width="130" height="62" rx="8" fill="#1a1e28" stroke="rgba(196,154,245,.3)" stroke-width="1"/>
      <text x="745" y="26" text-anchor="middle" fill="#8a6aaa" font-size="9" font-family="-apple-system,sans-serif" font-style="italic">«interface»</text>
      <text x="745" y="42" text-anchor="middle" fill="#c49af5" font-size="11" font-weight="600" font-family="-apple-system,sans-serif">ITelemetryPred...</text>
      <text x="745" y="60" text-anchor="middle" fill="#7a7f8e" font-size="10" font-family="-apple-system,sans-serif">Service</text>

      <!-- IGenericRepository -->
      <rect x="680" y="100" width="130" height="50" rx="8" fill="#1a1e28" stroke="rgba(196,154,245,.3)" stroke-width="1"/>
      <text x="745" y="116" text-anchor="middle" fill="#8a6aaa" font-size="9" font-family="-apple-system,sans-serif" font-style="italic">«interface»</text>
      <text x="745" y="134" text-anchor="middle" fill="#c49af5" font-size="11" font-weight="600" font-family="-apple-system,sans-serif">IGenericRepository&lt;T&gt;</text>
    </svg>
  </div>
</div>

<hr>

<!-- ═══════════════ TECH ═══════════════ -->
<div class="section">
  <div class="section-label">Stack</div>
  <h2>Tecnologias utilizadas</h2>
  <div class="tech-grid">
    <div class="tech-card backend">
      <h4>Backend</h4>
      <ul>
        <li>ASP.NET Core</li>
        <li>C#</li>
        <li>Swagger / OpenAPI</li>
        <li>AutoMapper</li>
        <li>Dependency Injection</li>
      </ul>
    </div>
    <div class="tech-card db">
      <h4>Banco de Dados</h4>
      <ul>
        <li>SQL Server</li>
        <li>Entity Framework Core</li>
        <li>Repository Pattern</li>
      </ul>
    </div>
    <div class="tech-card ml">
      <h4>Machine Learning</h4>
      <ul>
        <li>Python · FastAPI</li>
        <li>Isolation Forest</li>
        <li>LSTM</li>
        <li>XGBoost</li>
      </ul>
    </div>
    <div class="tech-card integ">
      <h4>Integração</h4>
      <ul>
        <li>REST API</li>
        <li>HttpClientFactory</li>
        <li>WebServices (SOA)</li>
      </ul>
    </div>
  </div>
</div>

<hr>

<!-- ═══════════════ BANCO DE DADOS ═══════════════ -->
<div class="section">
  <div class="section-label">Banco de Dados</div>
  <h2>Estrutura de persistência</h2>
  <div class="db-grid">
    <div class="db-card">
      <div class="db-card-header">PredictionHistory</div>
      <ul>
        <li>Espécie monitorada (SpeciesId)</li>
        <li>Coordenadas geográficas (lat/lng)</li>
        <li>Frequência cardíaca</li>
        <li>Aceleração</li>
        <li>Tipo de anomalia</li>
        <li>Probabilidade</li>
        <li>Nível de alerta</li>
        <li>Data da análise</li>
      </ul>
    </div>
    <div class="db-card">
      <div class="db-card-header">SpaceEquipment</div>
      <ul>
        <li>Tabela base (TPH)</li>
        <li>Subtipo: Satellite</li>
        <li>Subtipo: BiotelemetryTag</li>
        <li>Id, Name, DiagnosticData</li>
        <li>Discriminator column</li>
      </ul>
    </div>
  </div>
</div>

<!-- ═══════════════ EXCEÇÕES ═══════════════ -->
<div class="section">
  <div class="section-label">Tratamento de Erros</div>
  <div class="exception-box">
    <div class="exception-icon">⚠️</div>
    <div>
      <p>A exceção customizada <span class="code-inline">SpaceTelemetryException</span> centraliza o tratamento de falhas na integração com a API Python, erros de comunicação externa, falhas de processamento e exceções não mapeadas nas integrações.</p>
    </div>
  </div>
</div>

<!-- ═══════════════ ENDPOINTS ═══════════════ -->
<div class="section">
  <div class="section-label">Endpoints</div>
  <h2>REST API</h2>

  <div class="endpoint">
    <div class="endpoint-header">
      <span class="method post">POST</span>
      <span class="endpoint-path">/api/telemetry/predict</span>
    </div>
    <div class="endpoint-body">
      <p style="font-size:13px;color:var(--muted);margin-bottom:8px">Recebe dados de biotelemetria e retorna uma predição com nível de alerta.</p>
      <pre>{
  "speciesId":    "ANIMAL-001",
  "latitude":     -23.5505,
  "longitude":    -46.6333,
  "acceleration": 8.5,
  "heartRate":    120
}</pre>
    </div>
  </div>

  <div class="endpoint">
    <div class="endpoint-header">
      <span class="method get">GET</span>
      <span class="endpoint-path">/api/telemetry/predictions</span>
    </div>
    <div class="endpoint-body">
      <p style="font-size:13px;color:var(--muted)">Retorna o histórico completo de predições armazenadas no banco.</p>
    </div>
  </div>
</div>

<hr>

<!-- ═══════════════ ESTRUTURA ═══════════════ -->
<div class="section">
  <div class="section-label">Estrutura do Projeto</div>
  <div class="tree">
<span class="dir">Controllers/</span>
   <span class="file">└── TelemetryController.cs</span>

<span class="dir">Services/</span>
   <span class="file">└── TelemetryPredictionService.cs</span>

<span class="dir">Repositories/</span>
   <span class="file">└── GenericRepository.cs</span>

<span class="dir">Interfaces/</span>
   <span class="file">├── IGenericRepository.cs</span>
   <span class="file">└── ITelemetryPredictionService.cs</span>

<span class="dir">Models/</span>
   <span class="file">├── SpaceEquipment.cs</span>
   <span class="file">├── Satellite.cs</span>
   <span class="file">├── BiotelemetryTag.cs</span>
   <span class="file">├── PredictionHistory.cs</span>
   <span class="file">└── Telemetry.cs</span>

<span class="dir">DTOs/</span>
   <span class="file">├── RequestDTOs/</span>
   <span class="file">└── ResponseDTOs/</span>

<span class="dir">Exceptions/</span>
   <span class="file">└── SpaceTelemetryException.cs</span>

<span class="dir">Data/</span>
   <span class="file">└── AppDbContext.cs</span>
  </div>
</div>

<!-- ═══════════════ SETUP ═══════════════ -->
<div class="section">
  <div class="section-label">Como Executar</div>
  <h2>Setup local</h2>
  <ul class="steps">
    <li>
      <div class="step-num">1</div>
      <div>
        <p style="font-size:14px;color:#9097a8;margin-bottom:4px">Clone o repositório</p>
        <pre>git clone URL_DO_REPOSITORIO</pre>
      </div>
    </li>
    <li>
      <div class="step-num">2</div>
      <div>
        <p style="font-size:14px;color:#9097a8;margin-bottom:4px">Aplique as migrations</p>
        <pre>dotnet ef database update</pre>
      </div>
    </li>
    <li>
      <div class="step-num">3</div>
      <div>
        <p style="font-size:14px;color:#9097a8;margin-bottom:4px">Suba a aplicação</p>
        <pre>dotnet run</pre>
      </div>
    </li>
    <li>
      <div class="step-num">4</div>
      <div>
        <p style="font-size:14px;color:#9097a8;margin-bottom:4px">Acesse o Swagger</p>
        <pre>https://localhost:[porta]/swagger</pre>
      </div>
    </li>
  </ul>
</div>

<!-- ═══════════════ FOOTER ═══════════════ -->
<div class="footer">
  <p>Global Solution 2026 · Sistema de Monitoramento de Fauna por Telemetria Espacial</p>
  <a href="https://youtu.be/5G9euYeWuxI" target="_blank">
    ▶ Ver demonstração em vídeo
  </a>
</div>

</body>
</html>
