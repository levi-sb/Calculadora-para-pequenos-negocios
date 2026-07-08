<html lang="pt-BR">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Calculadora da Reforma Tributária — ME e EPP</title>
<meta name="description" content="Simule o impacto da Reforma Tributária (CBS e IBS) no seu negócio. Comparação clara para microempresas e pequenos empresários." />
<style>
  :root{
    --primary:#005EB8; --primary-2:#0072CE; --secondary:#00B0B9; --secondary-2:#7AC143;
    --success:#16a34a; --warning:#d97706; --danger:#dc2626;
    --bg:#F4F7FB; --card:#ffffff; --text:#0F2C46; --muted:#5b6b80;
    --border:#e3e9f1; --ring:rgba(0,94,184,.25);
    --radius:16px; --shadow:0 8px 24px -12px rgba(15,44,70,.18);
  }
  *{box-sizing:border-box}
  html,body{margin:0;padding:0}
  body{font-family:'Inter',system-ui,-apple-system,Segoe UI,Roboto,Helvetica,Arial,sans-serif;background:var(--bg);color:var(--text);line-height:1.5;-webkit-font-smoothing:antialiased}
  a{color:var(--primary);text-decoration:none}
  a:hover{text-decoration:underline}
  h1,h2,h3,h4{margin:0}
  
  .wrap{max-width:1100px;margin:0 auto;padding:0 16px}
  
  /* Header */
  header{position:sticky;top:0;z-index:10;background:rgba(255,255,255,.9);backdrop-filter:saturate(180%) blur(12px);border-bottom:1px solid var(--border)}
  .hd{display:flex;align-items:center;justify-content:space-between;padding:12px 0}
  .logo{display:flex;gap:12px;align-items:center}
  .logo .ic{width:40px;height:40px;border-radius:10px;background:linear-gradient(135deg,var(--primary),var(--secondary));display:flex;align-items:center;justify-content:center;color:#fff;flex-shrink:0}
  .logo h1{font-size:16px;font-weight:700;line-height:1.2}
  .logo p{font-size:12px;color:var(--muted);margin:2px 0 0}
  .tag{text-align:right;font-size:10px;color:var(--muted);background:var(--border);padding:6px 10px;border-radius:6px;font-weight:500;line-height:1.35}
  
  /* Hero */
  .hero {background: linear-gradient(180deg,#EAF3FB 0%,#F4F7FB 100%);border-bottom: 1px solid var(--border);padding: 32px 0 20px; }
  .badge{display:inline-flex;gap:6px;align-items:center;font-size:12px;font-weight:600;padding:6px 14px;border-radius999px;background:rgba(0,176,185,.1);color:#0a7c83;border:1px solid rgba(0,176,185,.25)}
  .hero h2{font-size:24px;font-weight:800;letter-spacing:-.02em;margin-top:16px;line-height:1.25;color:#071D31}
  .hero h2 .hl{color:var(--primary);position:relative}
  .hero p{font-size:15px;color:var(--muted);margin:12px 0 0;line-height:1.6}
  
  /* Disclaimer */
  .disclaimer {display: flex;gap: 12px;background: rgba(0, 176, 185, .05);border: 1px solid rgba(0, 176, 185, .2);padding: 16px;border-radius: var(--radius);margin: 20px 0 24px; }
  .disclaimer svg{flex-shrink:0;color:var(--secondary);margin-top:2px}
  .disclaimer p{margin:0;font-size:13.5px;color:#3a4a60;line-height:1.6}
  
  /* Main */
  main {padding: 0 0 40px; display: grid; grid-template-columns: 1fr; gap: 24px;}
  .card{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);box-shadow:var(--shadow);padding:20px}
  .card h3{font-size:18px;font-weight:700}
  .card .sub{font-size:13px;color:var(--muted);margin:4px 0 0}
  
  .field{margin-top:24px}
  .field label{display:block;font-size:13.5px;font-weight:600;margin-bottom:10px}
  
  .row-label{display:flex;justify-content:space-between;align-items:center;width:100%;margin-bottom:10px}
  .row-label label{margin-bottom:0!important}
  .row-label .val{color:var(--primary);font-weight:700;font-size:15px;background:rgba(0,94,184,.08);padding:2px 8px;border-radius:6px}
  
  .opts{display:grid;grid-template-columns:1fr;gap:15px}
  .opt{cursor:pointer;text-align:left;padding:28px;border:1px solid var(--border);border-radius:12px;background:#fff;transition:all .2s ease;min-height:48px;width:100%}
  .opt:hover{border-color:rgba(0,94,184,.4);background:#fafafa}
  .opt.active{border-color:var(--primary);background:rgba(0,94,184,.04);box-shadow:0 0 0 3px var(--ring)}
  .opt b{display:block;font-size:15px;font-weight:700;color:var(--text)}
  .opt span{display:block;font-size:12px;color:var(--muted);margin-top:2px}
  
  select{width:100%;height:48px;padding:0 14px;border:1px solid var(--border);border-radius:12px;background:#fff;font-size:14px;color:var(--text);appearance:none;background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%235b6b80' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'%3E%3C/polyline%3E%3C/svg%3E");background-repeat:no-repeat;background-position:right 14px center;background-size:16px}
  select:focus{outline:none;box-shadow:0 0 0 3px var(--ring);border-color:var(--primary)}
  
  input[type=range]{width:100%;accent-color:var(--primary);margin-top:8px;display:block;height:6px;background:var(--border);border-radius:999px;appearance:none;cursor:pointer}
  
  /* Painel de Resultados */
  .results{display:grid;gap:20px}
  .grid2{display:grid;grid-template-columns:1fr;gap:16px}
  
  .res{border:1px solid var(--border);border-radius:var(--radius);padding:20px;background:#fff;box-shadow:var(--shadow)}
  .res.warn{border-color:rgba(217,119,6,.3);background:linear-gradient(180deg,#fff,rgba(217,119,6,.02))}
  .res.good{border-color:rgba(22,163,74,.3);background:linear-gradient(180deg,#fff,rgba(22,163,74,.02))}
  .res .lbl{font-size:11px;font-weight:700;color:var(--muted);text-transform:uppercase;letter-spacing:.08em}
  .res .slbl{font-size:13px;color:#4a5568;margin-top:4px;line-height:1.4}
  .res .v{font-size:28px;font-weight:800;margin-top:14px;color:var(--text);letter-spacing:-.01em}
  .res .v small{font-size:13px;font-weight:500;color:var(--muted)}
  .res .pct{font-size:12.5px;color:var(--muted);margin-top:6px;font-weight:500}
  
  .bk{margin-top:16px;padding-top:14px;border-top:1px solid var(--border);font-size:12.5px;color:var(--muted)}
  .bk div{display:flex;justify-content:space-between;padding:4px 0}
  .bk div b{color:var(--text);font-weight:600}
  
  /* Perfil do Negócio */
  .perfil{background:#fff;border:1px solid var(--border);border-radius:var(--radius);padding:20px;box-shadow:var(--shadow)}
  .perfil .lbl{font-size:11px;font-weight:700;color:var(--muted);text-transform:uppercase;letter-spacing:.08em}
  .perfil p.help{font-size:12.5px;color:var(--muted);margin:4px 0 16px}
  .perfil .reco{display:flex;gap:12px;background:#F8FAFC;border:1px solid var(--border);border-radius:12px;padding:16px;margin-top:16px}
  .perfil .reco .ic{flex:0 0 40px;height:40px;background:rgba(0,94,184,.08);color:var(--primary);border-radius:10px;display:flex;align-items:center;justify-content:center}
  .perfil .reco b{display:block;font-size:14px;font-weight:700;color:var(--text)}
  .perfil .reco p{margin:4px 0 0;font-size:13px;color:var(--muted);line-height:1.6}
  
  /* Notas e Alertas Legais */
  .meinote{background:#fff;border:1px solid var(--border);border-radius:var(--radius);padding:16px;display:flex;gap:12px;box-shadow:var(--shadow)}
  .meinote .ic{flex:0 0 40px;height:40px;background:rgba(22,163,74,.1);color:var(--success);border-radius:10px;display:flex;align-items:center;justify-content:center}
  .meinote b{font-size:14.5px;font-weight:700}
  .meinote p{margin:4px 0 0;font-size:13px;color:var(--muted);line-height:1.6}
  
  /* Timeline */
  .tl{background:#fff;border:1px solid var(--border);border-radius:var(--radius);padding:20px;box-shadow:var(--shadow)}
  .tl h4{font-size:15px;font-weight:700;display:flex;align-items:center;gap:8px}
  .tl h4 svg{color:var(--primary)}
  .tl .it{display:flex;flex-direction:column;gap:4px;margin-top:16px;padding-left:12px;border-left:2px solid var(--border);position:relative}
  .tl .it::before{content:'';position:absolute;left:-5px;top:6px;width:8px;height:8px;border-radius:999px;background:var(--border)}
  .tl .it:hover::before{background:var(--primary)}
  .tl .yr{font-weight:700;color:var(--primary);font-size:14px}
  .tl .desc{font-size:13px;color:var(--muted);line-height:1.55}
  
  /* Footer Disclaimer Premium */
  .legal-footer{background:#fff;border:1px solid var(--border);border-radius:var(--radius);padding:24px;margin-top:20px;box-shadow:var(--shadow)}
  .legal-footer h5{margin:0 0 10px 0;font-size:14px;font-weight:700;color:var(--text);text-transform:uppercase;letter-spacing:0.03em}
  .legal-footer p{margin:0 0 12px 0;font-size:12px;color:var(--muted);line-height:1.6;text-align:justify}
  .legal-footer .meta-info{display:flex;flex-wrap:wrap;gap:16px;border-top:1px solid var(--border);padding-top:12px;margin-top:12px;font-size:11px;color:var(--muted);font-weight:500}
  .legal-footer .meta-info strong{color:var(--text)}

  footer{border-top:1px solid var(--border);margin-top:40px;padding:24px 16px;text-align:center;font-size:12px;color:var(--muted);line-height:1.5}

  @media(min-width:480px){
  .opts{
    grid-template-columns:repeat(3,1fr);
  }

  /* Mantém somente ME e EPP centralizados */
  #opt-porte{
    display:flex;
    justify-content:center;
    gap:24px;
  }
}
  @media(min-width:768px) {
    .hero h2{font-size:32px}
    .grid2{grid-template-columns:1fr 1fr}
    .tl .it{flex-direction:row;gap:16px}
    .tl .it .yr{flex:0 0 70px}
  }
  @media(min-width:900px){
    main{grid-template-columns:1fr 1.4fr;gap:28px;align-items:start}
    .card{position:sticky;top:90px;padding:28px}
    .results{gap:24px}
    .hero{padding:48px 0}
    .hero h2{font-size:38px}
  }
</style>
</head>
<body>

<header>
  <div class="wrap hd">
    <div class="logo">
      <div class="ic"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="4" y="2" width="16" height="20" rx="2"/><line x1="8" y1="6" x2="16" y2="6"/><line x1="16" y1="14" x2="16" y2="18"/><path d="M16 10h.01"/><path d="M12 10h.01"/><path d="M8 10h.01"/><path d="M12 14h.01"/><path d="M8 14h.01"/><path d="M12 18h.01"/><path d="M8 18h.01"/></svg></div>
      <div><h1>Reforma Tributária</h1><p>Calculadora para pequenos negócios</p></div>
    </div>
    <span class="tag">Versão didática<br>Dados de referência 2027–2028<br>Atualizada conforme LC 214/2025</span>
  </div>
</header>

<section class="hero">
  <div class="wrap hero-inner">
    <span class="badge"><svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 3v3M12 18v3M3 12h3M18 12h3M5.6 5.6l2.1 2.1M16.3 16.3l2.1 2.1M5.6 18.4l2.1-2.1M16.3 7.7l2.1-2.1"/></svg> Simule em menos de 1 minuto</span>
    <h2>Como a <span class="hl">Reforma Tributária</span> afeta o seu negócio?</h2>
    <p>Descubra se a sua empresa se enquadra nos cenários onde a permanência no Simples Nacional unificado é vantajosa ou se vale avaliar o modelo de apuração de <strong>CBS e IBS por fora do DAS</strong>, com foco nas transições de 2027/2028.</p>
  </div>
</section>

<div class="wrap">
  <div class="disclaimer">
    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><line x1="12" y1="16" x2="12" y2="12"/><line x1="12" y1="8" x2="12.01" y2="8"/></svg>
    <p><strong>Como usar:</strong> esta calculadora complementa, não substitui, a análise das variáveis decorrentes do tipo de atividade da empresa, da estrutura de custos internos e do perfil de clientes e fornecedores. Use-a como ponto de partida para conversar com seu contador.</p>
  </div>
</div>

<main class="wrap">
  <section class="card">
    <h3>Seu negócio</h3>
    <p class="sub">Preencha os dados para simular</p>

    <div class="field">
      <label>Porte da empresa</label>
      <div class="opts" id="opt-porte">
        <button class="opt active" data-v="me"><b>ME</b><span>até R$ 360k/ano</span></button>
        <button class="opt" data-v="epp"><b>EPP</b><span>até R$ 4.8M/ano</span></button>
      </div>
    </div>

    <div class="field">
      <label>Setor de atuação</label>
      <select id="setor">
        <option value="comercio">Comércio</option>
        <option value="industria">Indústria</option>
        <option value="servicos">Serviços em geral</option>
        <option value="servicos_intelectuais">Serviços intelectuais (consultoria, advocacia…)</option>
      </select>
    </div>

    <div class="field">
      <div class="row-label">
        <label for="fat">Faturamento mensal médio</label>
        <span class="val" id="fatLabel">R$ 15.000</span>
      </div>
      <input type="range" id="fat" min="1000" max="30000" step="1000" value="15000" />
    </div>
  </section>

  <section class="results">
    <!-- Aviso de Escopo e Parâmetros Exigido pela Revisão -->
    <div class="disclaimer" style="margin: 0; background: rgba(217,119,6,0.04); border-color: rgba(217,119,6,0.25);">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="#d97706" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="7.86 2 16.14 2 22 7.86 22 16.14 16.14 22 7.86 22 2 16.14 2 7.86 7.86 2"/><line x1="12" y1="8" x2="12" y2="12"/><line x1="12" y1="16" x2="12.01" y2="16"/></svg>
      <p style="color: #92400e; font-size: 13px; margin: 0;"><strong>Resultados desta simulação:</strong> Os valores apresentados utilizam parâmetros de referência para os exercícios de 2027 e 2028, conforme a Lei Complementar nº 214/2025 e a regulamentação vigente. As alíquotas da CBS, do IBS, os fatores de redução do DAS e demais parâmetros poderão sofrer alterações em exercícios posteriores.</p>
    </div>

    <div class="grid2" id="cards"></div>
    <div id="perfilBox"></div>

    <div class="tl">
      <h4><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><line x1="12" y1="16" x2="12" y2="12"/><line x1="12" y1="8" x2="12.01" y2="8"/></svg> Linha do tempo da Reforma</h4>
      <div class="it"><div class="yr">2026</div><div class="desc">Optantes pelo Simples Nacional permanecem dispensados do recolhimento da CBS e do IBS durante o período de testes. Este é o momento recomendado para avaliar os impactos da Reforma Tributária e planejar a manutenção no regime tradicional do Simples Nacional ou a eventual opção pela apuração segregada a partir de 2027.</div></div>
      <div class="it"><div class="yr">2027</div><div class="desc">Início da fase de testes da CBS e do IBS, com aplicação de alíquotas reduzidas previstas na legislação, sem impacto relevante na carga tributária. Nesta etapa, inicia-se a adaptação às novas regras, incluindo a possibilidade de apuração segregada pelos optantes do Simples Nacional.</div></div>
      <div class="it"><div class="yr">2029–2032</div><div class="desc">Período de transição do sistema atual para o novo modelo tributário. As alíquotas do ICMS e do ISS serão gradualmente reduzidas, enquanto o IBS assumirá progressivamente a tributação sobre o consumo.</div></div>
      <div class="it"><div class="yr">2033</div><div class="desc">Conclusão da transição. O novo sistema de tributação sobre o consumo passa a vigorar integralmente, com a extinção definitiva do PIS, Cofins, ICMS, ISS e demais tributos substituídos pela CBS e pelo IBS.</div></div>
    </div>

    <!-- Bloco de Disclaimer Robusto Exigido pela Revisão -->
    <div class="legal-footer">
      <h5>Aviso importante &amp; Notas Legais</h5>
      <p>Esta calculadora possui finalidade exclusivamente educativa e informativa. Os cálculos utilizam premissas e parâmetros de referência aplicáveis ao período inicial de implementação da Reforma Tributária (2027–2028), conforme a Lei Complementar nº 214/2025 e demais normas vigentes na data da atualização. Os percentuais apresentados não constituem alíquotas permanentes nem representam interpretação oficial da Receita Federal, do Comitê Gestor do IBS ou de qualquer órgão governamental.</p>
      <p>Atualmente, não estão contemplados os cálculos relacionados à opção pela apuração segregada da CBS e do IBS pelos optantes do Simples Nacional, nem a apropriação de créditos gerados por compras de mercadorias, insumos ou contratação de serviços. Como esses fatores podem influenciar significativamente o resultado final, os valores apresentados devem ser interpretados apenas como uma estimativa simplificada dos possíveis impactos da Reforma Tributária.</p>
      <div class="meta-info">
        <div><strong>Última atualização:</strong> Junho de 2026</div>
        <div><strong>Base normativa:</strong> Lei Complementar nº 214/2025</div>
      </div>
    </div>
  </section>
</main>

<footer>Feito para apoiar pequenos empresários cearenses· Inspirado nos simuladores da RFB.</footer>

<script>
// Estrutura de parâmetros recomendada pela revisão para mitigar riscos jurídicos
const PARAMETROS = {
  referencia: "2027–2028",
  cbs: 0.088,
  ibs: 0.001,
  total: 0.089,
  observacao: "Alíquotas de referência utilizadas apenas para simulação da fase inicial da transição."
};

const state = { porte:"me", setor:"comercio", fat:15000, perfil:"b2c" };
const brl = v => v.toLocaleString("pt-BR",{style:"currency",currency:"BRL",maximumFractionDigits:0});

function obterRegrasFaixa(setor, fatMensal) {
  const anual = fatMensal * 12;
  let faixa = 1;
  
  if (anual <= 180000) faixa = 1;
  else if (anual <= 360000) faixa = 2;
  else if (anual <= 720000) faixa = 3;
  else if (anual <= 1800000) faixa = 4;
  else faixa = 5;

  if (setor === 'comercio') {
    const nominal = [0.04, 0.073, 0.095, 0.107, 0.143][faixa-1];
    const deducao = [0, 5940, 13860, 22500, 87300][faixa-1];
    const rateEfetivo = anual > 0 ? (anual * nominal - deducao) / anual : 0.04;
    const proReducao = [0.155, 0.150, 0.145, 0.141, 0.137][faixa-1];
    return { anexo: `Anexo I — Comércio (Faixa ${faixa})`, rate: rateEfetivo, substituido: rateEfetivo * proReducao };
  }
  if (setor === 'industria') {
    const nominal = [0.045, 0.078, 0.10, 0.112, 0.147][faixa-1];
    const deducao = [0, 5940, 13860, 22500, 85500][faixa-1];
    const rateEfetivo = anual > 0 ? (anual * nominal - deducao) / anual : 0.045;
    const proReducao = [0.142, 0.138, 0.134, 0.130, 0.125][faixa-1];
    return { anexo: `Anexo II — Indústria (Faixa ${faixa})`, rate: rateEfetivo, substituido: rateEfetivo * proReducao };
  }
  if (setor === 'servicos') {
    const nominal = [0.06, 0.112, 0.135, 0.16, 0.21][faixa-1];
    const deducao = [0, 9360, 17640, 35640, 125640][faixa-1];
    const rateEfetivo = anual > 0 ? (anual * nominal - deducao) / anual : 0.06;
    const proReducao = [0.213, 0.205, 0.198, 0.192, 0.185][faixa-1];
    return { anexo: `Anexo III — Serviços (Faixa ${faixa})`, rate: rateEfetivo, substituido: rateEfetivo * proReducao };
  }
  if (setor === 'servicos_intelectuais') {
    const nominal = [0.155, 0.18, 0.195, 0.22, 0.27][faixa-1];
    const deducao = [0, 4500, 9900, 27900, 117900][faixa-1];
    const rateEfetivo = anual > 0 ? (anual * nominal - deducao) / anual : 0.155;
    const proReducao = [0.245, 0.238, 0.231, 0.224, 0.218][faixa-1];
    return { anexo: `Anexo V — Serviços Intel. (Faixa ${faixa})`, rate: rateEfetivo, substituido: rateEfetivo * proReducao };
  }
}

function compute(){
  if(state.porte==="mei"){
    const das = state.setor==="industria"?76.9: (state.setor==="servicos"||state.setor==="servicos_intelectuais")?75.9 : 71.9;
    return {regimeAtualLabel:"MEI — DAS unificado fixo", atual:das, pctA:(das/Math.max(state.fat,1))*100, hib:false};
  }
  
  const info = obterRegrasFaixa(state.setor, state.fat);
  const trib = state.fat * info.rate;
  
  const rateRed = info.rate - info.substituido;
  const dasRed = state.fat * rateRed;
  const cbsIbs = state.fat * PARAMETROS.total;
  
  return {
    regimeAtualLabel: `${info.anexo} · Alíquota Efetiva: ${(info.rate * 100).toFixed(2)}%`, 
    atual: trib, 
    pctA: info.rate * 100, 
    hib: true, 
    hibTot: dasRed + cbsIbs, 
    hibPct: ((dasRed + cbsIbs) / Math.max(state.fat, 1)) * 100, 
    dasRed, 
    cbsIbs,
    pctDasRed: rateRed * 100 
  };
}

function resCard({label,sub,val,pct,tone,breakdown}){
  const bk = breakdown? `<div class="bk">${breakdown.map(([k,v])=>`<div><span>${k}</span><b>${v}</b></div>`).join("")}</div>`:"";
  return `<div class="res ${tone==='good'?'good':tone==='warn'?'warn':''}"><div class="lbl">${label}</div><div class="slbl">${sub}</div><div class="v">${brl(val)}<small>/mês</small></div><div class="pct">≈ ${pct.toFixed(2)}% do faturamento</div>${bk}</div>`;
}

// Textos suavizados e condicionalizados conforme a análise de risco jurídico
const PERFIL = {
  b2c:{
    t:"Em cenários B2C, o Simples tradicional tende a apresentar menor carga tributária direta", 
    d:"Seu cliente final (consumidor pessoa física) não se beneficia de créditos de CBS/IBS. Desse modo, a apuração separada por fora do DAS pode elevar a carga tributária direta do seu negócio sem trazer vantagem competitiva mercadológica imediata.", 
    ic:'<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>'
  },
  b2b:{
    t:"A apuração separada pode aumentar a competitividade em determinadas cadeias B2B", 
    d:"Empresas compradoras (PJ) sob o regime não cumulativo rotineiramente demandam notas fiscais com destaque de CBS e IBS para apuração de seus próprios créditos tributários. Avalie com sua contabilidade o impacto dessa preferência comercial em seu faturamento.", 
    ic:'<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M6 22V4a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v18Z"/><path d="M6 12H4a2 2 0 0 0-2 2v6a2 2 0 0 0 2 2h2"/><path d="M18 9h2a2 2 0 0 1 2 2v9a2 2 0 0 1-2 2h-2"/><path d="M10 6h4"/><path d="M10 10h4"/><path d="M10 14h4"/><path d="M10 18h4"/></svg>'
  },
  meio:{
    t:"A viabilidade da alteração de regime depende da estrutura de custos e clientes", 
    d:"Em modelos comerciais mistos, a conveniência da apuração separada é multifatorial, dependendo do volume real das operações B2B e da capacidade de apropriação de créditos sobre insumos. Recomenda-se modelagem contábil individualizada.", 
    ic:'<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m16 16 3-8 3 8c-.87.65-1.92 1-3 1s-2.13-.35-3-1Z"/><path d="m2 16 3-8 3 8c-.87.65-1.92 1-3 1s-2.13-.35-3-1Z"/><path d="M7 21h10"/><path d="M12 3v18"/><path d="M3 7h2c2 0 5-1 7-2 2 1 5 2 7 2h2"/></svg>'
  }
};

function render(){
  const r = compute();
  document.getElementById("fatLabel").textContent = brl(state.fat);

  const cards = document.getElementById("cards");
  let html = resCard({label:"Regime atual unificado", sub:r.regimeAtualLabel, val:r.atual, pct:r.pctA, tone:"neutral"});
  if(r.hib){
    html += resCard({
      label:"Apuração Separada (Modelo Opcional)*", 
      sub:`Alíquota de referência na simulação (${PARAMETROS.referencia})`, 
      val:r.hibTot, 
      pct:r.hibPct, 
      tone:"warn", 
      breakdown:[
        [`DAS Reduzido* (Estimado - Anexo 20) — Alíquota: ${r.pctDasRed.toFixed(2)}%`, brl(r.dasRed)],
        [`CBS + IBS Provisório (Referência) — Alíquota: ${(PARAMETROS.total * 100).toFixed(1)}%`, brl(r.cbsIbs)]
      ]
    });
  } else {
    html += resCard({label:"Após a reforma", sub:"Modelo unificado do MEI preservado", val:r.atual, pct:r.pctA, tone:"good"});
  }
  cards.innerHTML = html;

  const pbox = document.getElementById("perfilBox");
  if(r.hib){
    const p = PERFIL[state.perfil];
    pbox.innerHTML = `<div class="perfil">
      <div class="lbl">Perfil do seu negócio</div>
      <p class="help">Informativo — parâmetro comercial orientativo que não altera as fórmulas aritméticas abaixo.</p>
      <div class="opts" id="opt-perfil">
        <button class="opt ${state.perfil==='b2c'?'active':''}" data-v="b2c"><b>Majoritariamente B2C</b><span>Vendas para consumidor final</span></button>
        <button class="opt ${state.perfil==='b2b'?'active':''}" data-v="b2b"><b>Majoritariamente B2B</b><span>Vendas para outras empresas</span></button>
        <button class="opt ${state.perfil==='meio'?'active':''}" data-v="meio"><b>Perfil Misto</b><span>Divisão entre B2C e B2B</span></button>
      </div>
      <div class="reco"><div class="ic">${p.ic}</div><div><b>${p.t}</b><p>${p.d}</p></div></div>
    </div>`;
    pbox.querySelectorAll("#opt-perfil .opt").forEach(b=>b.addEventListener("click",()=>{state.perfil=b.dataset.v;render();}));
  } else pbox.innerHTML = "";

  const mbox = document.getElementById("meiBox");

  if(state.porte==="epp"){
    mbox.innerHTML = `<div class="meinote" style="border-color: rgba(217,119,6,.4); background: rgba(217,119,6,.03);"><div class="ic" style="background: rgba(217,119,6,.15); color: var(--warning);"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><line x1="12" y1="8" x2="12" y2="12"/><line x1="12" y1="16" x2="12.01" y2="16"/></svg></div><div><b>Nota Técnica sobre o Sublimite Legal (R$ 3,6 Milhões)</b><p>Conforme regramento da transição, empresas com faturamento acumulado superior a R$ 3,6 milhões anuais ultrapassam o sublimite para recolhimento de tributos sobre o consumo dentro do Simples Nacional. Nesses casos, a apuração externa de CBS e IBS deixa de ser opcional e passa a seguir obrigatoriamente o regime de débito e crédito.</p></div></div>`;
  } else {
    mbox.innerHTML = "";
  }
}

document.querySelectorAll("#opt-porte .opt").forEach(b=>b.addEventListener("click",()=>{
  state.porte=b.dataset.v;
  document.querySelectorAll("#opt-porte .opt").forEach(x=>x.classList.toggle("active",x.dataset.v===state.porte));
  
  const slider = document.getElementById("fat");
  if (state.porte === "me") {
    slider.max = 30000;
    slider.step = 1000;
    if (state.fat > 30000) state.fat = 30000;
    if (state.fat < 1000) state.fat = 15000;
  } else if (state.porte === "epp") {
    slider.max = 300000;
    slider.step = 5000;
    if (state.fat > 300000) state.fat = 300000;
    if (state.fat < 30000) state.fat = 100000;
  }
  slider.value = state.fat;
  render();
}));

document.getElementById("setor").addEventListener("change",e=>{state.setor=e.target.value;render();});
document.getElementById("fat").addEventListener("input",e=>{state.fat=Number(e.target.value);render();});
render();
</script>
</body>
</html>
