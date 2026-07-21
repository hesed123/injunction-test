[Uploading index.html…]()
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>금지명령(Injunction) 자기이해 검사</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+KR:wght@300;400;600;700&family=Noto+Sans+KR:wght@300;400;500;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #f7f4ef;
    --paper: #fffdf9;
    --ink: #1a1714;
    --ink-light: #5a5450;
    --ink-muted: #9a9390;
    --accent: #7b5c3e;
    --accent-light: #c4a882;
    --accent-pale: #ede5d8;
    --warn: #b85c38;
    --border: #ddd5c8;
    --section-A: #eef2eb;
    --section-A-accent: #5a7a4a;
    --section-B: #eaf0f5;
    --section-B-accent: #3a6a8a;
    --section-C: #f5eef0;
    --section-C-accent: #8a3a5a;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--ink);
    font-family: 'Noto Sans KR', sans-serif;
    font-size: 14px;
    line-height: 1.7;
    min-height: 100vh;
  }

  /* ── COVER ── */
  .cover {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background: var(--ink);
    color: var(--bg);
    padding: 60px 40px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .cover::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse at 30% 20%, rgba(196,168,130,0.15) 0%, transparent 60%),
                radial-gradient(ellipse at 70% 80%, rgba(123,92,62,0.2) 0%, transparent 50%);
  }

  .cover-ornament {
    font-family: 'Noto Serif KR', serif;
    font-size: 11px;
    letter-spacing: 0.4em;
    color: var(--accent-light);
    text-transform: uppercase;
    margin-bottom: 40px;
    position: relative;
  }

  .cover-ornament::before,
  .cover-ornament::after {
    content: '— ';
  }
  .cover-ornament::after {
    content: ' —';
  }

  .cover h1 {
    font-family: 'Noto Serif KR', serif;
    font-size: clamp(28px, 5vw, 48px);
    font-weight: 700;
    line-height: 1.3;
    margin-bottom: 8px;
    position: relative;
  }

  .cover h1 em {
    display: block;
    font-style: normal;
    font-size: 0.55em;
    font-weight: 300;
    letter-spacing: 0.15em;
    color: var(--accent-light);
    margin-bottom: 12px;
  }

  .cover-sub {
    font-size: 13px;
    color: rgba(247,244,239,0.6);
    margin-top: 20px;
    line-height: 1.8;
    position: relative;
  }

  .cover-divider {
    width: 60px;
    height: 1px;
    background: var(--accent-light);
    margin: 32px auto;
    position: relative;
  }

  .cover-start {
    margin-top: 48px;
    display: inline-block;
    padding: 14px 36px;
    border: 1px solid var(--accent-light);
    color: var(--accent-light);
    font-size: 12px;
    letter-spacing: 0.2em;
    cursor: pointer;
    background: transparent;
    transition: all 0.3s;
    position: relative;
    font-family: 'Noto Sans KR', sans-serif;
  }

  .cover-start:hover {
    background: var(--accent-light);
    color: var(--ink);
  }

  /* ── PAGES ── */
  .page {
    display: none;
    max-width: 760px;
    margin: 0 auto;
    padding: 40px 24px 80px;
    animation: fadeIn 0.4s ease;
  }

  .page.active { display: block; }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(12px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ── PROGRESS ── */
  .progress-bar-wrap {
    position: sticky;
    top: 0;
    z-index: 100;
    background: var(--bg);
    padding: 12px 24px;
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: center;
    gap: 12px;
    font-size: 11px;
    color: var(--ink-muted);
    letter-spacing: 0.05em;
  }

  .progress-track {
    flex: 1;
    height: 3px;
    background: var(--border);
    border-radius: 2px;
    overflow: hidden;
  }

  .progress-fill {
    height: 100%;
    background: var(--accent);
    border-radius: 2px;
    transition: width 0.5s ease;
  }

  /* ── SECTION HEADER ── */
  .section-header {
    margin-bottom: 32px;
  }

  .section-tag {
    display: inline-block;
    font-size: 10px;
    letter-spacing: 0.25em;
    font-weight: 700;
    padding: 4px 10px;
    border-radius: 2px;
    margin-bottom: 12px;
    text-transform: uppercase;
  }

  .tag-A { background: var(--section-A); color: var(--section-A-accent); }
  .tag-B { background: var(--section-B); color: var(--section-B-accent); }
  .tag-C { background: var(--section-C); color: var(--section-C-accent); }
  .tag-neutral { background: var(--accent-pale); color: var(--accent); }

  .section-header h2 {
    font-family: 'Noto Serif KR', serif;
    font-size: clamp(20px, 3vw, 28px);
    font-weight: 700;
    line-height: 1.4;
    margin-bottom: 8px;
  }

  .section-header p {
    font-size: 13px;
    color: var(--ink-light);
    line-height: 1.8;
  }

  /* ── INSTRUCTIONS BOX ── */
  .instr-box {
    background: var(--paper);
    border: 1px solid var(--border);
    border-left: 3px solid var(--accent);
    padding: 20px 24px;
    margin-bottom: 28px;
    font-size: 13px;
    line-height: 1.85;
    color: var(--ink-light);
  }

  .instr-box strong { color: var(--ink); }

  .scale-guide {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 6px;
    margin-top: 16px;
    text-align: center;
  }

  .scale-guide-item {
    padding: 8px 4px;
    background: var(--accent-pale);
    border-radius: 4px;
    font-size: 11px;
    line-height: 1.4;
  }

  .scale-guide-item strong {
    display: block;
    font-size: 16px;
    color: var(--accent);
    font-family: 'Noto Serif KR', serif;
  }

  /* ── INJUNCTION CARD ── */
  .inj-card {
    background: var(--paper);
    border: 1px solid var(--border);
    margin-bottom: 28px;
    overflow: hidden;
  }

  .inj-card-header {
    padding: 16px 20px;
    display: flex;
    align-items: center;
    gap: 12px;
    border-bottom: 1px solid var(--border);
    cursor: pointer;
  }

  .inj-number {
    width: 32px;
    height: 32px;
    border-radius: 50%;
    background: var(--ink);
    color: var(--bg);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Noto Serif KR', serif;
    font-size: 13px;
    font-weight: 700;
    flex-shrink: 0;
  }

  .inj-title-wrap { flex: 1; }

  .inj-title {
    font-family: 'Noto Serif KR', serif;
    font-size: 16px;
    font-weight: 700;
  }

  .inj-title-en {
    font-size: 11px;
    color: var(--ink-muted);
    letter-spacing: 0.05em;
  }

  .inj-score-badge {
    font-size: 11px;
    color: var(--ink-muted);
    background: var(--accent-pale);
    padding: 3px 8px;
    border-radius: 10px;
    white-space: nowrap;
  }

  /* ── SUB-SECTION LABEL ── */
  .sub-label {
    font-size: 10px;
    letter-spacing: 0.2em;
    font-weight: 700;
    text-transform: uppercase;
    padding: 8px 20px;
    border-bottom: 1px solid var(--border);
  }

  .sub-label-exp {
    background: var(--section-A);
    color: var(--section-A-accent);
  }

  .sub-label-dec {
    background: var(--section-B);
    color: var(--section-B-accent);
  }

  /* ── QUESTION ROW ── */
  .q-row {
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: start;
    gap: 12px;
    padding: 14px 20px;
    border-bottom: 1px solid var(--bg);
    transition: background 0.15s;
  }

  .q-row:hover { background: var(--accent-pale); }
  .q-row:last-child { border-bottom: none; }

  .q-text {
    font-size: 13.5px;
    line-height: 1.7;
    padding-top: 2px;
  }

  .q-scale {
    display: flex;
    gap: 4px;
    align-items: center;
    flex-shrink: 0;
  }

  .q-scale label {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 3px;
    cursor: pointer;
  }

  .q-scale input[type=radio] { display: none; }

  .q-scale .dot {
    width: 26px;
    height: 26px;
    border-radius: 50%;
    border: 1.5px solid var(--border);
    background: var(--paper);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 11px;
    color: var(--ink-muted);
    transition: all 0.15s;
    font-family: 'Noto Serif KR', serif;
  }

  .q-scale input[type=radio]:checked + .dot {
    background: var(--ink);
    border-color: var(--ink);
    color: var(--bg);
  }

  .q-scale label:hover .dot {
    border-color: var(--accent);
    color: var(--accent);
  }

  .q-scale input[type=radio]:checked + .dot {
    background: var(--accent);
    border-color: var(--accent);
    color: var(--bg);
    transform: scale(1.1);
  }

  /* ── VALIDATION WARNING ── */
  .val-warn {
    display: none;
    font-size: 11px;
    color: var(--warn);
    padding: 6px 20px;
    background: #fff5f2;
    border-top: 1px solid #f0d0c8;
  }

  /* ── NAVIGATION ── */
  .nav-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 40px;
    gap: 12px;
  }

  .btn {
    padding: 12px 28px;
    font-family: 'Noto Sans KR', sans-serif;
    font-size: 13px;
    border: none;
    cursor: pointer;
    transition: all 0.2s;
    letter-spacing: 0.05em;
  }

  .btn-primary {
    background: var(--ink);
    color: var(--bg);
  }

  .btn-primary:hover { background: var(--accent); }

  .btn-secondary {
    background: transparent;
    color: var(--ink-light);
    border: 1px solid var(--border);
  }

  .btn-secondary:hover { border-color: var(--ink); color: var(--ink); }

  /* ── SIGNAL CHECKLIST (몸이 보내는 신호) ── */
  .signal-group {
    background: var(--paper);
    border: 1px solid var(--border);
    margin-bottom: 20px;
    padding: 18px 20px 20px;
  }

  .signal-group-title {
    font-family: 'Noto Serif KR', serif;
    font-size: 14px;
    font-weight: 700;
    margin-bottom: 4px;
  }

  .signal-group-hint {
    font-size: 12px;
    color: var(--ink-muted);
    margin-bottom: 14px;
  }

  .signal-chip-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .signal-chip {
    display: inline-flex;
    align-items: center;
  }

  .signal-chip input[type=checkbox] { display: none; }

  .signal-chip span {
    padding: 7px 14px;
    border: 1px solid var(--border);
    border-radius: 20px;
    font-size: 12.5px;
    color: var(--ink-light);
    background: var(--bg);
    cursor: pointer;
    transition: all 0.15s;
  }

  .signal-chip input[type=checkbox]:checked + span {
    background: var(--ink);
    border-color: var(--ink);
    color: var(--bg);
  }

  .signal-result-chip {
    display: inline-block;
    padding: 5px 12px;
    margin: 0 6px 6px 0;
    border-radius: 20px;
    background: var(--accent-pale);
    color: var(--accent);
    font-size: 12px;
  }

  /* ── COMPOUND DECISION (복합결정) ── */
  .compound-box {
    margin-top: 10px;
    padding: 10px 14px;
    background: rgba(247,244,239,0.08);
    border-left: 2px solid var(--accent-light);
    font-size: 12.5px;
    line-height: 1.7;
    color: rgba(247,244,239,0.85);
  }

  .compound-label {
    font-size: 10px;
    letter-spacing: 0.15em;
    color: var(--accent-light);
    text-transform: uppercase;
    margin-bottom: 3px;
  }

  .trigger-box {
    background: var(--paper);
    border: 1px solid var(--border);
    border-top: 3px solid var(--accent);
    padding: 22px 24px;
    margin-bottom: 28px;
  }

  .trigger-box h3 {
    font-family: 'Noto Serif KR', serif;
    font-size: 16px;
    margin-bottom: 8px;
  }

  .trigger-box p {
    font-size: 13px;
    color: var(--ink-light);
    line-height: 1.8;
    margin-bottom: 14px;
  }

  /* ── REFLECTIVE SECTION ── */
  .refl-group {
    background: var(--paper);
    border: 1px solid var(--border);
    margin-bottom: 20px;
    overflow: hidden;
  }

  .refl-q-num {
    background: var(--ink);
    color: var(--bg);
    width: 28px;
    height: 28px;
    border-radius: 50%;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    font-size: 12px;
    font-family: 'Noto Serif KR', serif;
    margin-right: 10px;
    flex-shrink: 0;
  }

  .refl-header {
    padding: 16px 20px;
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: flex-start;
    gap: 0;
  }

  .refl-question {
    font-family: 'Noto Serif KR', serif;
    font-size: 15px;
    font-weight: 600;
    line-height: 1.5;
  }

  .refl-hint {
    font-size: 12px;
    color: var(--ink-muted);
    margin-top: 4px;
  }

  .refl-body {
    padding: 16px 20px;
  }

  .refl-field {
    width: 100%;
    min-height: 80px;
    border: 1px solid var(--border);
    background: var(--bg);
    padding: 12px;
    font-family: 'Noto Sans KR', sans-serif;
    font-size: 13px;
    line-height: 1.7;
    color: var(--ink);
    resize: vertical;
    outline: none;
    transition: border-color 0.2s;
  }

  .refl-field:focus { border-color: var(--accent); }

  .refl-field-sm { min-height: 52px; }

  .scene-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .scene-item label {
    display: block;
    font-size: 11px;
    color: var(--ink-muted);
    letter-spacing: 0.1em;
    margin-bottom: 6px;
    text-transform: uppercase;
  }

  /* ── PERMISSION SECTION ── */
  .permission-intro {
    background: var(--paper);
    border: 1px solid var(--border);
    border-top: 3px solid var(--accent);
    padding: 24px;
    margin-bottom: 24px;
    font-size: 13.5px;
    line-height: 1.85;
  }

  .permission-intro h3 {
    font-family: 'Noto Serif KR', serif;
    font-size: 17px;
    margin-bottom: 12px;
  }

  .permission-example {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 12px;
  }

  .perm-chip {
    background: var(--accent-pale);
    border: 1px solid var(--border);
    padding: 5px 12px;
    font-size: 12px;
    border-radius: 20px;
    color: var(--accent);
    cursor: pointer;
    transition: all 0.15s;
  }

  .perm-chip:hover { background: var(--accent); color: white; }

  .permission-rows {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .permission-row {
    display: grid;
    grid-template-columns: 24px 1fr;
    align-items: start;
    gap: 12px;
    background: var(--paper);
    border: 1px solid var(--border);
    padding: 14px 16px;
  }

  .permission-num {
    font-family: 'Noto Serif KR', serif;
    font-size: 14px;
    color: var(--accent-light);
    padding-top: 10px;
  }

  .permission-input {
    width: 100%;
    border: none;
    border-bottom: 1px solid var(--border);
    background: transparent;
    padding: 10px 0;
    font-family: 'Noto Sans KR', sans-serif;
    font-size: 14px;
    color: var(--ink);
    outline: none;
  }

  .permission-input:focus { border-bottom-color: var(--accent); }

  .permission-input::placeholder { color: var(--ink-muted); }

  /* ── RESULT ── */
  #page-result { display: none; }
  #page-result.active { display: block; }

  .result-header {
    text-align: center;
    padding: 40px 20px 32px;
    border-bottom: 1px solid var(--border);
    margin-bottom: 32px;
  }

  .result-header h2 {
    font-family: 'Noto Serif KR', serif;
    font-size: 26px;
    margin-bottom: 8px;
  }

  .result-header p { color: var(--ink-light); font-size: 13px; }

  .result-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    margin-bottom: 32px;
  }

  @media (max-width: 500px) {
    .result-grid { grid-template-columns: 1fr; }
    .scene-grid { grid-template-columns: 1fr; }
    .q-scale .dot { width: 22px; height: 22px; font-size: 10px; }
  }

  .result-item {
    background: var(--paper);
    border: 1px solid var(--border);
    padding: 14px 16px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .result-item.highlight {
    border-color: var(--accent);
    background: var(--accent-pale);
  }

  .result-rank {
    font-family: 'Noto Serif KR', serif;
    font-size: 12px;
    color: var(--ink-muted);
    width: 20px;
    flex-shrink: 0;
  }

  .result-name {
    flex: 1;
    font-size: 13px;
    font-weight: 500;
  }

  .result-bar-wrap {
    width: 80px;
    height: 6px;
    background: var(--border);
    border-radius: 3px;
    overflow: hidden;
    flex-shrink: 0;
  }

  .result-bar-fill {
    height: 100%;
    background: var(--accent);
    border-radius: 3px;
    transition: width 0.8s ease;
  }

  .result-item.highlight .result-bar-fill { background: var(--ink); }

  .result-score {
    font-family: 'Noto Serif KR', serif;
    font-size: 16px;
    font-weight: 700;
    color: var(--accent);
    width: 36px;
    text-align: right;
    flex-shrink: 0;
  }

  .result-item.highlight .result-score { color: var(--ink); }

  /* ── SUMMARY BOX ── */
  .summary-box {
    background: var(--ink);
    color: var(--bg);
    padding: 28px 24px;
    margin-bottom: 28px;
  }

  .summary-box h3 {
    font-family: 'Noto Serif KR', serif;
    font-size: 18px;
    margin-bottom: 16px;
    color: var(--accent-light);
  }

  .summary-top-items {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .summary-top-item {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    padding: 14px 0;
    border-bottom: 1px solid rgba(255,255,255,0.1);
  }

  .summary-top-item:last-child { border-bottom: none; }

  .summary-rank-badge {
    width: 24px;
    height: 24px;
    border-radius: 50%;
    background: rgba(255,255,255,0.1);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 11px;
    color: var(--accent-light);
    flex-shrink: 0;
  }

  .summary-name { flex: 1; font-size: 14px; }

  .summary-meaning {
    font-size: 12px;
    color: rgba(247,244,239,0.6);
    margin-top: 3px;
    line-height: 1.5;
  }

  .summary-score {
    font-family: 'Noto Serif KR', serif;
    font-size: 20px;
    font-weight: 700;
    color: var(--accent-light);
  }

  .summary-max { font-size: 11px; color: rgba(247,244,239,0.4); }

  /* ── REFLECTION RESULT ── */
  .refl-result-box {
    background: var(--paper);
    border: 1px solid var(--border);
    padding: 20px 24px;
    margin-bottom: 16px;
  }

  .refl-result-box h4 {
    font-size: 11px;
    letter-spacing: 0.2em;
    color: var(--ink-muted);
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .refl-result-box p {
    font-size: 14px;
    line-height: 1.8;
    color: var(--ink);
  }

  .perm-result-list {
    display: flex;
    flex-direction: column;
    gap: 8px;
    margin-top: 8px;
  }

  .perm-result-item {
    background: var(--accent-pale);
    border-left: 3px solid var(--accent);
    padding: 10px 16px;
    font-size: 14px;
    font-family: 'Noto Serif KR', serif;
  }

  /* ── PRINT BTN ── */
  .print-note {
    text-align: center;
    font-size: 12px;
    color: var(--ink-muted);
    margin-top: 12px;
  }

  /* ── PERMISSION SUGGESTION ── */
  .perm-inj-block {
    margin-bottom: 12px;
    border: 1px solid var(--border);
    overflow: hidden;
  }

  .perm-inj-label {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px 14px;
    background: var(--paper);
    border-bottom: 1px solid var(--border);
  }

  .perm-inj-rank {
    font-size: 9px;
    letter-spacing: 0.15em;
    color: white;
    background: var(--accent);
    padding: 2px 7px;
    border-radius: 10px;
    flex-shrink: 0;
  }

  .perm-inj-name {
    font-family: 'Noto Serif KR', serif;
    font-size: 13px;
    font-weight: 700;
    flex: 1;
  }

  .perm-inj-score {
    font-family: 'Noto Serif KR', serif;
    font-size: 15px;
    font-weight: 700;
    color: var(--accent);
    flex-shrink: 0;
  }

  .perm-inj-chips {
    padding: 10px 14px;
    display: flex;
    flex-wrap: wrap;
    gap: 7px;
    background: var(--bg);
  }

  .perm-inj-chip {
    background: var(--paper);
    border: 1px solid var(--border);
    padding: 6px 12px;
    font-size: 12px;
    border-radius: 20px;
    color: var(--ink-light);
    cursor: pointer;
    transition: all 0.15s;
    line-height: 1.4;
  }

  .perm-inj-chip:hover {
    background: var(--accent);
    border-color: var(--accent);
    color: white;
  }

  .perm-inj-chip.used {
    background: var(--accent-pale);
    border-color: var(--accent-light);
    color: var(--accent);
    cursor: default;
  }

  /* ── SCORE SUMMARY PANEL ── */
  .ss-row {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 8px 14px;
    border-bottom: 1px solid rgba(255,255,255,0.05);
    transition: background 0.2s;
  }

  .ss-row:last-child { border-bottom: none; }

  .ss-row.ss-top {
    background: rgba(196,168,130,0.12);
  }

  .ss-num {
    font-size: 11px;
    color: var(--accent-light);
    width: 18px;
    flex-shrink: 0;
    opacity: 0.7;
  }

  .ss-name {
    font-size: 11px;
    color: rgba(247,244,239,0.75);
    flex: 1;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  .ss-bar-wrap {
    width: 60px;
    height: 4px;
    background: rgba(255,255,255,0.1);
    border-radius: 2px;
    overflow: hidden;
    flex-shrink: 0;
  }

  .ss-bar {
    height: 100%;
    background: var(--accent-light);
    border-radius: 2px;
    width: 0%;
    transition: width 0.4s ease;
  }

  .ss-row.ss-top .ss-bar { background: #f7f4ef; }

  .ss-score {
    font-family: 'Noto Serif KR', serif;
    font-size: 14px;
    font-weight: 700;
    color: var(--accent-light);
    width: 24px;
    text-align: right;
    flex-shrink: 0;
    transition: color 0.2s;
  }

  .ss-row.ss-top .ss-score { color: #f7f4ef; }

  @media print {
    .progress-bar-wrap, .nav-row, .cover-start { display: none !important; }
    .page { display: block !important; }
    .cover { min-height: auto; padding: 40px; }
    body { background: white; }
  }

  /* ── MIND HARBOR BRANDING ── */
  .cover-logo {
    width: 92px;
    height: auto;
    margin: 0 auto 28px;
    display: block;
    opacity: 0.96;
  }

  .mh-watermark {
    position: fixed;
    top: 64px;
    right: 24px;
    font-family: 'Noto Sans KR', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 0.15em;
    color: var(--ink);
    opacity: 0;
    pointer-events: none;
    z-index: 40;
    transition: opacity 0.3s;
  }

  body.assessing .mh-watermark { opacity: 0.16; }

  @media print {
    .mh-watermark { display: none !important; }
  }

  .footer-logo {
    width: 16px;
    height: auto;
    vertical-align: -3px;
    margin-right: 6px;
    opacity: 0.55;
  }

</style>
</head>
<body>

<div class="mh-watermark">MIND HARBOR</div>

<!-- COVER -->
<div class="cover" id="cover">
  <img src="data:image/png;base64,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" alt="Mind Harbor" class="cover-logo">
  <div class="cover-ornament">Transactional Analysis</div>
  <h1>
    <em>Injunction Scale</em>
    금지명령<br>자기이해 검사
  </h1>
  <div class="cover-divider"></div>
  <p class="cover-sub">
    어린 시절 내면에 새겨진 삶의 규칙을 탐색합니다<br>
    교류분석 이론 기반 · 경험요인 + 결정요인 통합 구성<br>
    총 3부 · 약 15~20분 소요
  </p>
  <button class="cover-start btn" onclick="startAssessment()">검사 시작하기 →</button>
</div>

<!-- PROGRESS BAR -->
<div class="progress-bar-wrap" id="progress-wrap" style="display:none;">
  <span id="progress-label">1 / 4</span>
  <div class="progress-track">
    <div class="progress-fill" id="progress-fill" style="width:25%"></div>
  </div>
  <span id="progress-step-label">경험 탐색</span>
</div>

<!-- PAGE 1: INSTRUCTIONS + PART A -->
<div class="page" id="page-1">
  <div class="section-header">
    <span class="section-tag tag-A">Part 1 — 경험 탐색</span>
    <h2>어린 시절, 어떤 메시지를 받았나요?</h2>
    <p>아래 문항들은 양육자(부모나 주양육자)로부터 경험한 메시지와 관계 방식을 묻습니다.<br>
    현재의 나에게 얼마나 해당되는지도 함께 떠올리며 응답해주세요.</p>
  </div>

  <div class="instr-box">
    <strong>응답 방법</strong><br>
    각 문항을 읽고, <strong>직관적인 첫 느낌</strong>을 기준으로 1~5점 중 하나를 선택하세요.<br>
    과거 경험과 현재 패턴을 함께 고려하셔도 됩니다. 정답은 없습니다.
    <div class="scale-guide">
      <div class="scale-guide-item"><strong>1</strong>전혀<br>그렇지 않다</div>
      <div class="scale-guide-item"><strong>2</strong>별로<br>그렇지 않다</div>
      <div class="scale-guide-item"><strong>3</strong>보통이다</div>
      <div class="scale-guide-item"><strong>4</strong>대체로<br>그렇다</div>
      <div class="scale-guide-item"><strong>5</strong>매우<br>그렇다</div>
    </div>
  </div>

  <!-- INJUNCTION 1~6 -->

  <!-- 1. 존재하지 말라 -->
  <div class="inj-card">
    <div class="inj-card-header">
      <div class="inj-number">1</div>
      <div class="inj-title-wrap">
        <div class="inj-title">존재하지 말라</div>
        <div class="inj-title-en">Don't exist</div>
      </div>
      <div class="inj-score-badge" id="badge-1">0 / 25점</div>
    </div>
    <div class="sub-label sub-label-exp">경험 — 어떤 메시지를 받았나</div>
    <div class="q-row">
      <div class="q-text">나를 온전히 보살펴 주는 사람이 없었다.</div>
      <div class="q-scale" data-inj="1" data-part="exp">
        <label><input type="radio" name="q1_e1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q1_e1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q1_e1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q1_e1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q1_e1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">아무도 나의 존재에 대해 진지하게 관심을 갖지 않았다.</div>
      <div class="q-scale" data-inj="1" data-part="exp">
        <label><input type="radio" name="q1_e2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q1_e2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q1_e2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q1_e2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q1_e2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="sub-label sub-label-dec">결정 — 그때 내린 삶의 결론</div>
    <div class="q-row">
      <div class="q-text">나는 존재할 가치가 없다는 느낌이 든다.</div>
      <div class="q-scale" data-inj="1" data-part="dec">
        <label><input type="radio" name="q1_d1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q1_d1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q1_d1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q1_d1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q1_d1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">나는 누구에게도 특별한 존재가 아니라는 생각이 자주 든다.</div>
      <div class="q-scale" data-inj="1" data-part="dec">
        <label><input type="radio" name="q1_d2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q1_d2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q1_d2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q1_d2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q1_d2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">내가 있어도 괜찮은가, 라는 의문이 드는 순간이 있다.</div>
      <div class="q-scale" data-inj="1" data-part="dec">
        <label><input type="radio" name="q1_d3" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q1_d3" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q1_d3" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q1_d3" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q1_d3" value="5"><span class="dot">5</span></label>
      </div>
    </div>
  </div>

  <!-- 2. 너여서는 안 돼 -->
  <div class="inj-card">
    <div class="inj-card-header">
      <div class="inj-number">2</div>
      <div class="inj-title-wrap">
        <div class="inj-title">너 자신이 되지 말라</div>
        <div class="inj-title-en">Don't be you</div>
      </div>
      <div class="inj-score-badge" id="badge-2">0 / 25점</div>
    </div>
    <div class="sub-label sub-label-exp">경험 — 어떤 메시지를 받았나</div>
    <div class="q-row">
      <div class="q-text">나는 부모나 주양육자가 원하는 모습에 맞추려 노력해야 했다.</div>
      <div class="q-scale" data-inj="2" data-part="exp">
        <label><input type="radio" name="q2_e1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q2_e1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q2_e1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q2_e1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q2_e1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">나의 성향이나 특성을 그대로 드러냈을 때 부정적인 반응을 받았다.</div>
      <div class="q-scale" data-inj="2" data-part="exp">
        <label><input type="radio" name="q2_e2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q2_e2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q2_e2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q2_e2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q2_e2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="sub-label sub-label-dec">결정 — 그때 내린 삶의 결론</div>
    <div class="q-row">
      <div class="q-text">있는 그대로의 내 모습은 받아들여지지 않을 것이라는 생각이 든다.</div>
      <div class="q-scale" data-inj="2" data-part="dec">
        <label><input type="radio" name="q2_d1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q2_d1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q2_d1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q2_d1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q2_d1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">나다운 행동을 하면 이상해 보이거나 문제가 될 것 같아 조심한다.</div>
      <div class="q-scale" data-inj="2" data-part="dec">
        <label><input type="radio" name="q2_d2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q2_d2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q2_d2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q2_d2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q2_d2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">나는 '이런 나'는 안 된다는 생각을 자주 한다.</div>
      <div class="q-scale" data-inj="2" data-part="dec">
        <label><input type="radio" name="q2_d3" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q2_d3" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q2_d3" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q2_d3" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q2_d3" value="5"><span class="dot">5</span></label>
      </div>
    </div>
  </div>

  <!-- 3. 아이처럼 굴지 말라 -->
  <div class="inj-card">
    <div class="inj-card-header">
      <div class="inj-number">3</div>
      <div class="inj-title-wrap">
        <div class="inj-title">아이가 되지 말라</div>
        <div class="inj-title-en">Don't be a child</div>
      </div>
      <div class="inj-score-badge" id="badge-3">0 / 25점</div>
    </div>
    <div class="sub-label sub-label-exp">경험 — 어떤 메시지를 받았나</div>
    <div class="q-row">
      <div class="q-text">나는 일찍부터 철들어야 했고, 다른 사람을 먼저 챙겨야 했다.</div>
      <div class="q-scale" data-inj="3" data-part="exp">
        <label><input type="radio" name="q3_e1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q3_e1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q3_e1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q3_e1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q3_e1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">나는 어린아이처럼 놀거나 즐기는 것이 허용되지 않았다는 느낌이 있다.</div>
      <div class="q-scale" data-inj="3" data-part="exp">
        <label><input type="radio" name="q3_e2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q3_e2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q3_e2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q3_e2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q3_e2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="sub-label sub-label-dec">결정 — 그때 내린 삶의 결론</div>
    <div class="q-row">
      <div class="q-text">도움을 요청하거나 다른 사람에게 기대는 것이 어렵다.</div>
      <div class="q-scale" data-inj="3" data-part="dec">
        <label><input type="radio" name="q3_d1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q3_d1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q3_d1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q3_d1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q3_d1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">내 일은 남의 도움 없이 스스로 해결해야 한다고 생각한다.</div>
      <div class="q-scale" data-inj="3" data-part="dec">
        <label><input type="radio" name="q3_d2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q3_d2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q3_d2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q3_d2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q3_d2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">편하게 쉬거나 즐기고 있으면 죄책감이나 불안이 올라온다.</div>
      <div class="q-scale" data-inj="3" data-part="dec">
        <label><input type="radio" name="q3_d3" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q3_d3" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q3_d3" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q3_d3" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q3_d3" value="5"><span class="dot">5</span></label>
      </div>
    </div>
  </div>

  <!-- 4. 성장하지 말라 -->
  <div class="inj-card">
    <div class="inj-card-header">
      <div class="inj-number">4</div>
      <div class="inj-title-wrap">
        <div class="inj-title">성장하지 말라</div>
        <div class="inj-title-en">Don't grow up</div>
      </div>
      <div class="inj-score-badge" id="badge-4">0 / 25점</div>
    </div>
    <div class="sub-label sub-label-exp">경험 — 어떤 메시지를 받았나</div>
    <div class="q-row">
      <div class="q-text">부모나 주양육자가 나의 일에 과도하게 간섭하거나 대신 결정해주었다.</div>
      <div class="q-scale" data-inj="4" data-part="exp">
        <label><input type="radio" name="q4_e1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q4_e1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q4_e1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q4_e1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q4_e1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">스스로 선택하거나 결정해본 경험이 별로 없다.</div>
      <div class="q-scale" data-inj="4" data-part="exp">
        <label><input type="radio" name="q4_e2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q4_e2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q4_e2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q4_e2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q4_e2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="sub-label sub-label-dec">결정 — 그때 내린 삶의 결론</div>
    <div class="q-row">
      <div class="q-text">독립적으로 살아가거나 새로운 환경에 적응하는 것이 두렵게 느껴진다.</div>
      <div class="q-scale" data-inj="4" data-part="dec">
        <label><input type="radio" name="q4_d1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q4_d1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q4_d1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q4_d1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q4_d1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">무언가를 결정할 때 여전히 누군가의 허락이나 확인이 필요하다고 느낀다.</div>
      <div class="q-scale" data-inj="4" data-part="dec">
        <label><input type="radio" name="q4_d2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q4_d2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q4_d2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q4_d2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q4_d2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">스스로는 혼자 감당하기 어렵다는 생각이 자주 든다.</div>
      <div class="q-scale" data-inj="4" data-part="dec">
        <label><input type="radio" name="q4_d3" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q4_d3" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q4_d3" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q4_d3" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q4_d3" value="5"><span class="dot">5</span></label>
      </div>
    </div>
  </div>

  <!-- 5. 성공하지 말라 -->
  <div class="inj-card">
    <div class="inj-card-header">
      <div class="inj-number">5</div>
      <div class="inj-title-wrap">
        <div class="inj-title">성공하지 말라</div>
        <div class="inj-title-en">Don't make it</div>
      </div>
      <div class="inj-score-badge" id="badge-5">0 / 25점</div>
    </div>
    <div class="sub-label sub-label-exp">경험 — 어떤 메시지를 받았나</div>
    <div class="q-row">
      <div class="q-text">잘 해도 충분히 인정받지 못했거나, 오히려 비난이나 평가절하를 받았다.</div>
      <div class="q-scale" data-inj="5" data-part="exp">
        <label><input type="radio" name="q5_e1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q5_e1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q5_e1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q5_e1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q5_e1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">무엇을 해도 실패감이나 무능함을 전달받는 경험이 있었다.</div>
      <div class="q-scale" data-inj="5" data-part="exp">
        <label><input type="radio" name="q5_e2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q5_e2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q5_e2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q5_e2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q5_e2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="sub-label sub-label-dec">결정 — 그때 내린 삶의 결론</div>
    <div class="q-row">
      <div class="q-text">내가 제대로 해낼 수 있는 일은 없다는 생각이 자주 든다.</div>
      <div class="q-scale" data-inj="5" data-part="dec">
        <label><input type="radio" name="q5_d1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q5_d1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q5_d1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q5_d1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q5_d1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">잘될 것 같은 상황에서 오히려 불안해지거나, 스스로 발목을 잡는 경향이 있다.</div>
      <div class="q-scale" data-inj="5" data-part="dec">
        <label><input type="radio" name="q5_d2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q5_d2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q5_d2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q5_d2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q5_d2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">성공하거나 앞서가면 중요한 사람과 멀어질 것 같은 느낌이 든다.</div>
      <div class="q-scale" data-inj="5" data-part="dec">
        <label><input type="radio" name="q5_d3" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q5_d3" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q5_d3" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q5_d3" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q5_d3" value="5"><span class="dot">5</span></label>
      </div>
    </div>
  </div>

  <!-- 6. 실행하지 말라 -->
  <div class="inj-card">
    <div class="inj-card-header">
      <div class="inj-number">6</div>
      <div class="inj-title-wrap">
        <div class="inj-title">실행하지 말라</div>
        <div class="inj-title-en">Don't do anything</div>
      </div>
      <div class="inj-score-badge" id="badge-6">0 / 25점</div>
    </div>
    <div class="sub-label sub-label-exp">경험 — 어떤 메시지를 받았나</div>
    <div class="q-row">
      <div class="q-text">뭔가 하려고 할 때 주양육자가 "하지 마라", "위험해"라는 말을 자주 했다.</div>
      <div class="q-scale" data-inj="6" data-part="exp">
        <label><input type="radio" name="q6_e1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q6_e1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q6_e1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q6_e1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q6_e1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">스스로 선택하고 행동하기보다 승인이나 지시를 기다려야 했다.</div>
      <div class="q-scale" data-inj="6" data-part="exp">
        <label><input type="radio" name="q6_e2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q6_e2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q6_e2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q6_e2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q6_e2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="sub-label sub-label-dec">결정 — 그때 내린 삶의 결론</div>
    <div class="q-row">
      <div class="q-text">무언가를 시작하기 전에 오래 망설이고 생각만 하는 경우가 많다.</div>
      <div class="q-scale" data-inj="6" data-part="dec">
        <label><input type="radio" name="q6_d1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q6_d1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q6_d1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q6_d1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q6_d1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">실수할까봐 행동을 미루거나, 아무것도 하지 않는 것이 더 안전하다고 느낀다.</div>
      <div class="q-scale" data-inj="6" data-part="dec">
        <label><input type="radio" name="q6_d2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q6_d2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q6_d2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q6_d2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q6_d2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">'괜히 했다가 잘못될까봐'라는 생각이 행동을 가로막는다.</div>
      <div class="q-scale" data-inj="6" data-part="dec">
        <label><input type="radio" name="q6_d3" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q6_d3" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q6_d3" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q6_d3" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q6_d3" value="5"><span class="dot">5</span></label>
      </div>
    </div>
  </div>

  <div class="val-warn" id="warn-1">응답하지 않은 문항이 있습니다. 모든 문항에 응답한 후 다음으로 넘어가주세요.</div>
  <div class="nav-row">
    <div></div>
    <button class="btn btn-primary" onclick="goNext(1)">다음 → 7~12번</button>
  </div>
</div>

<!-- PAGE 2: INJUNCTIONS 7~12 -->
<div class="page" id="page-2">
  <div class="section-header">
    <span class="section-tag tag-A">Part 1 — 경험 탐색 (계속)</span>
    <h2>나를 둘러싼 메시지들</h2>
    <p>관계, 소속감, 감정, 생각에 관한 금지명령을 탐색합니다.</p>
  </div>

  <!-- 7. 중요한 인물이 되지 말라 -->
  <div class="inj-card">
    <div class="inj-card-header">
      <div class="inj-number">7</div>
      <div class="inj-title-wrap">
        <div class="inj-title">중요해지지 말라</div>
        <div class="inj-title-en">Don't be important</div>
      </div>
      <div class="inj-score-badge" id="badge-7">0 / 25점</div>
    </div>
    <div class="sub-label sub-label-exp">경험 — 어떤 메시지를 받았나</div>
    <div class="q-row">
      <div class="q-text">내 욕구나 의견은 자주 무시당하거나 중요하게 다루어지지 않았다.</div>
      <div class="q-scale" data-inj="7" data-part="exp">
        <label><input type="radio" name="q7_e1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q7_e1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q7_e1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q7_e1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q7_e1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">책임 있는 역할을 맡거나 중요한 일에 참여하는 것을 허용받지 못했다.</div>
      <div class="q-scale" data-inj="7" data-part="exp">
        <label><input type="radio" name="q7_e2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q7_e2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q7_e2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q7_e2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q7_e2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="sub-label sub-label-dec">결정 — 그때 내린 삶의 결론</div>
    <div class="q-row">
      <div class="q-text">내 욕구나 바람을 앞세우는 것이 불편하거나 부담스럽다.</div>
      <div class="q-scale" data-inj="7" data-part="dec">
        <label><input type="radio" name="q7_d1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q7_d1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q7_d1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q7_d1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q7_d1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">중요한 역할이나 자리를 맡는 것을 피하려는 경향이 있다.</div>
      <div class="q-scale" data-inj="7" data-part="dec">
        <label><input type="radio" name="q7_d2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q7_d2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q7_d2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q7_d2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q7_d2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">나보다 다른 사람이 더 중요하다고 느끼며 그들의 욕구를 먼저 충족시키려 한다.</div>
      <div class="q-scale" data-inj="7" data-part="dec">
        <label><input type="radio" name="q7_d3" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q7_d3" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q7_d3" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q7_d3" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q7_d3" value="5"><span class="dot">5</span></label>
      </div>
    </div>
  </div>

  <!-- 8. 소속되지 말라 -->
  <div class="inj-card">
    <div class="inj-card-header">
      <div class="inj-number">8</div>
      <div class="inj-title-wrap">
        <div class="inj-title">소속되지 말라</div>
        <div class="inj-title-en">Don't belong</div>
      </div>
      <div class="inj-score-badge" id="badge-8">0 / 25점</div>
    </div>
    <div class="sub-label sub-label-exp">경험 — 어떤 메시지를 받았나</div>
    <div class="q-row">
      <div class="q-text">가족이 다른 사람들과 어울리지 않거나, 고립된 생활방식을 유지했다.</div>
      <div class="q-scale" data-inj="8" data-part="exp">
        <label><input type="radio" name="q8_e1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q8_e1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q8_e1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q8_e1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q8_e1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">나는 다른 아이들과 다르다거나 특별하다는 말을 자주 들었다.</div>
      <div class="q-scale" data-inj="8" data-part="exp">
        <label><input type="radio" name="q8_e2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q8_e2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q8_e2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q8_e2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q8_e2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="sub-label sub-label-dec">결정 — 그때 내린 삶의 결론</div>
    <div class="q-row">
      <div class="q-text">집단 속에 있어도 어딘가 소속되지 않은 느낌이 든다.</div>
      <div class="q-scale" data-inj="8" data-part="dec">
        <label><input type="radio" name="q8_d1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q8_d1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q8_d1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q8_d1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q8_d1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">어디에도 완전히 속하지 못한다는 느낌이 있다.</div>
      <div class="q-scale" data-inj="8" data-part="dec">
        <label><input type="radio" name="q8_d2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q8_d2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q8_d2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q8_d2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q8_d2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">관계 속에서 거리감을 유지하거나 혼자 있는 것이 더 편하다.</div>
      <div class="q-scale" data-inj="8" data-part="dec">
        <label><input type="radio" name="q8_d3" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q8_d3" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q8_d3" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q8_d3" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q8_d3" value="5"><span class="dot">5</span></label>
      </div>
    </div>
  </div>

  <!-- 9. 가까이 오지 말라 -->
  <div class="inj-card">
    <div class="inj-card-header">
      <div class="inj-number">9</div>
      <div class="inj-title-wrap">
        <div class="inj-title">친밀해지지 말라</div>
        <div class="inj-title-en">Don't be close</div>
      </div>
      <div class="inj-score-badge" id="badge-9">0 / 25점</div>
    </div>
    <div class="sub-label sub-label-exp">경험 — 어떤 메시지를 받았나</div>
    <div class="q-row">
      <div class="q-text">애정 표현이 거의 없는 가정에서 자랐거나, 친밀감을 표현했을 때 거절당한 경험이 있다.</div>
      <div class="q-scale" data-inj="9" data-part="exp">
        <label><input type="radio" name="q9_e1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q9_e1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q9_e1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q9_e1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q9_e1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">가족 내에서 신뢰가 자주 깨지거나, 가까운 관계가 상처를 주는 경험이 반복되었다.</div>
      <div class="q-scale" data-inj="9" data-part="exp">
        <label><input type="radio" name="q9_e2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q9_e2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q9_e2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q9_e2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q9_e2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="sub-label sub-label-dec">결정 — 그때 내린 삶의 결론</div>
    <div class="q-row">
      <div class="q-text">마음을 주면 결국 상처받을 것이라는 생각이 있어 깊은 관계를 경계한다.</div>
      <div class="q-scale" data-inj="9" data-part="dec">
        <label><input type="radio" name="q9_d1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q9_d1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q9_d1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q9_d1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q9_d1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">속마음을 쉽게 드러내지 않고, 가까워질수록 거리를 두고 싶어진다.</div>
      <div class="q-scale" data-inj="9" data-part="dec">
        <label><input type="radio" name="q9_d2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q9_d2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q9_d2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q9_d2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q9_d2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">친밀감을 나누는 것이 어색하거나 불편하게 느껴질 때가 있다.</div>
      <div class="q-scale" data-inj="9" data-part="dec">
        <label><input type="radio" name="q9_d3" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q9_d3" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q9_d3" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q9_d3" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q9_d3" value="5"><span class="dot">5</span></label>
      </div>
    </div>
  </div>

  <!-- 10. 건강하지 말라 -->
  <div class="inj-card">
    <div class="inj-card-header">
      <div class="inj-number">10</div>
      <div class="inj-title-wrap">
        <div class="inj-title">건강하지 말라</div>
        <div class="inj-title-en">Don't be well / Don't be sane</div>
      </div>
      <div class="inj-score-badge" id="badge-10">0 / 25점</div>
    </div>
    <div class="sub-label sub-label-exp">경험 — 어떤 메시지를 받았나</div>
    <div class="q-row">
      <div class="q-text">아프거나 힘들 때에만 주양육자가 관심을 주었다.</div>
      <div class="q-scale" data-inj="10" data-part="exp">
        <label><input type="radio" name="q10_e1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q10_e1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q10_e1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q10_e1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q10_e1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">신체적으로 약하다는 이야기를 자주 들었거나, 가족 중 병약한 모델이 있었다.</div>
      <div class="q-scale" data-inj="10" data-part="exp">
        <label><input type="radio" name="q10_e2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q10_e2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q10_e2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q10_e2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q10_e2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="sub-label sub-label-dec">결정 — 그때 내린 삶의 결론</div>
    <div class="q-row">
      <div class="q-text">내가 힘들거나 아파야 사람들이 나를 신경 써줄 것 같은 느낌이 든다.</div>
      <div class="q-scale" data-inj="10" data-part="dec">
        <label><input type="radio" name="q10_d1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q10_d1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q10_d1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q10_d1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q10_d1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">컨디션이 좋거나 상황이 잘 풀릴 때 오히려 불안해지거나 경계하게 된다.</div>
      <div class="q-scale" data-inj="10" data-part="dec">
        <label><input type="radio" name="q10_d2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q10_d2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q10_d2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q10_d2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q10_d2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">괜찮아지는 것이 낯설게 느껴지거나, 회복되는 것에 저항감이 든다.</div>
      <div class="q-scale" data-inj="10" data-part="dec">
        <label><input type="radio" name="q10_d3" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q10_d3" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q10_d3" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q10_d3" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q10_d3" value="5"><span class="dot">5</span></label>
      </div>
    </div>
  </div>

  <!-- 11. 생각하지 말라 -->
  <div class="inj-card">
    <div class="inj-card-header">
      <div class="inj-number">11</div>
      <div class="inj-title-wrap">
        <div class="inj-title">생각하지 말라</div>
        <div class="inj-title-en">Don't think</div>
      </div>
      <div class="inj-score-badge" id="badge-11">0 / 25점</div>
    </div>
    <div class="sub-label sub-label-exp">경험 — 어떤 메시지를 받았나</div>
    <div class="q-row">
      <div class="q-text">나의 질문이나 생각이 자주 무시당하거나, 부모의 생각을 강요받았다.</div>
      <div class="q-scale" data-inj="11" data-part="exp">
        <label><input type="radio" name="q11_e1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q11_e1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q11_e1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q11_e1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q11_e1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">가족 내에서 특정 주제(돈, 성, 갈등 등)에 대해 이야기하는 것이 금지되었다.</div>
      <div class="q-scale" data-inj="11" data-part="exp">
        <label><input type="radio" name="q11_e2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q11_e2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q11_e2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q11_e2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q11_e2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="sub-label sub-label-dec">결정 — 그때 내린 삶의 결론</div>
    <div class="q-row">
      <div class="q-text">내 생각이나 의견을 표현하는 것이 조심스럽고, 틀릴까봐 쉽게 말하지 않는다.</div>
      <div class="q-scale" data-inj="11" data-part="dec">
        <label><input type="radio" name="q11_d1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q11_d1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q11_d1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q11_d1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q11_d1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">스스로 판단하기보다 다른 사람의 의견이나 지시를 따르는 것이 더 편하다.</div>
      <div class="q-scale" data-inj="11" data-part="dec">
        <label><input type="radio" name="q11_d2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q11_d2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q11_d2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q11_d2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q11_d2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">내 생각은 중요하지 않다는 느낌이 들어 주장하기보다 이해한 척 넘어간다.</div>
      <div class="q-scale" data-inj="11" data-part="dec">
        <label><input type="radio" name="q11_d3" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q11_d3" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q11_d3" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q11_d3" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q11_d3" value="5"><span class="dot">5</span></label>
      </div>
    </div>
  </div>

  <!-- 12. 감정을 느끼지 말라 -->
  <div class="inj-card">
    <div class="inj-card-header">
      <div class="inj-number">12</div>
      <div class="inj-title-wrap">
        <div class="inj-title">느끼지 말라</div>
        <div class="inj-title-en">Don't feel</div>
      </div>
      <div class="inj-score-badge" id="badge-12">0 / 25점</div>
    </div>
    <div class="sub-label sub-label-exp">경험 — 어떤 메시지를 받았나</div>
    <div class="q-row">
      <div class="q-text">감정 표현이 통제되거나 비난받은 경험이 있고, 가족 내 정서 교류가 거의 없었다.</div>
      <div class="q-scale" data-inj="12" data-part="exp">
        <label><input type="radio" name="q12_e1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q12_e1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q12_e1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q12_e1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q12_e1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">나의 감정을 제대로 이해해주는 사람이 없었다.</div>
      <div class="q-scale" data-inj="12" data-part="exp">
        <label><input type="radio" name="q12_e2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q12_e2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q12_e2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q12_e2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q12_e2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="sub-label sub-label-dec">결정 — 그때 내린 삶의 결론</div>
    <div class="q-row">
      <div class="q-text">감정을 드러내는 것이 위험하거나 약해 보인다고 느껴 억누르는 편이다.</div>
      <div class="q-scale" data-inj="12" data-part="dec">
        <label><input type="radio" name="q12_d1" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q12_d1" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q12_d1" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q12_d1" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q12_d1" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">내 감정보다 다른 사람의 감정이 더 중요하다고 느끼며 내 감정을 뒤로 미룬다.</div>
      <div class="q-scale" data-inj="12" data-part="dec">
        <label><input type="radio" name="q12_d2" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q12_d2" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q12_d2" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q12_d2" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q12_d2" value="5"><span class="dot">5</span></label>
      </div>
    </div>
    <div class="q-row">
      <div class="q-text">내 감정이 무엇인지 스스로도 잘 모를 때가 있다.</div>
      <div class="q-scale" data-inj="12" data-part="dec">
        <label><input type="radio" name="q12_d3" value="1"><span class="dot">1</span></label>
        <label><input type="radio" name="q12_d3" value="2"><span class="dot">2</span></label>
        <label><input type="radio" name="q12_d3" value="3"><span class="dot">3</span></label>
        <label><input type="radio" name="q12_d3" value="4"><span class="dot">4</span></label>
        <label><input type="radio" name="q12_d3" value="5"><span class="dot">5</span></label>
      </div>
    </div>
  </div>

  <div class="val-warn" id="warn-2">응답하지 않은 문항이 있습니다. 모든 문항에 응답한 후 다음으로 넘어가주세요.</div>
  <div class="nav-row">
    <button class="btn btn-secondary" onclick="goPrev(2)">← 이전</button>
    <button class="btn btn-primary" onclick="goNext(2)">다음 → 몸이 보내는 신호</button>
  </div>
</div>

<!-- PAGE 3: BODY & EMOTION SIGNALS -->
<div class="page" id="page-3">
  <div class="section-header">
    <span class="section-tag tag-B">Part 2 — 몸이 보내는 신호</span>
    <h2>말보다 먼저, 몸과 마음이 보내는 신호</h2>
    <p>금지명령은 말이 아니라 비언어로 각인되기 때문에, 머리로 떠올리는 것만으로는 잘 잡히지 않을 때가 많습니다.<br>
    최근 한두 주를 떠올리며, 자주 느꼈던 감정과 몸의 반응을 편하게 골라보세요. 몇 개를 골라도 정답은 없습니다.</p>
  </div>

  <div class="signal-group">
    <div class="signal-group-title">정서 신호</div>
    <div class="signal-group-hint">이 중 최근 자주 느꼈던 감정에 표시해보세요.</div>
    <div class="signal-chip-grid">
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="좌절감"><span>좌절감</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="후회스러움"><span>후회스러움</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="부끄러움"><span>부끄러움</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="불안함"><span>불안함</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="초조함"><span>초조함</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="외로움"><span>외로움</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="고립감"><span>고립감</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="헛헛함"><span>헛헛함</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="실망스러움"><span>실망스러움</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="두려움"><span>두려움</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="위축감"><span>위축감</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="무력감"><span>무력감</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="상실감"><span>상실감</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="슬픔"><span>슬픔</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="분노"><span>분노</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="미움"><span>미움</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="우울"><span>우울</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="정서" value="무덤덤함"><span>무덤덤함(아무 느낌이 없음)</span></label>
    </div>
  </div>

  <div class="signal-group">
    <div class="signal-group-title">신체 신호</div>
    <div class="signal-group-hint">스트레스 상황에서 몸이 먼저 보내는 반응을 골라보세요.</div>
    <div class="signal-chip-grid">
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="신체" value="손발이 차가워짐"><span>손발이 차가워짐</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="신체" value="두통"><span>두통</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="신체" value="속이 쓰리거나 체함"><span>속이 쓰리거나 체함</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="신체" value="어지러움"><span>어지러움</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="신체" value="심장이 빨리 뜀"><span>심장이 빨리 뜀</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="신체" value="식은땀"><span>식은땀</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="신체" value="목이 조이는 느낌"><span>목이 조이는 느낌</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="신체" value="손톱·입술을 물어뜯음"><span>손톱·입술을 물어뜯음</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="신체" value="갑자기 몸에 힘이 빠짐"><span>갑자기 몸에 힘이 빠짐</span></label>
      <label class="signal-chip"><input type="checkbox" class="signal-check" data-cat="신체" value="가슴이 답답함"><span>가슴이 답답함</span></label>
    </div>
  </div>

  <div class="instr-box" style="border-left-color: var(--section-B-accent);">
    <strong>왜 이 페이지가 필요한가요?</strong><br>
    금지명령은 대개 언어를 배우기 이전, 영유아기부터 6~8세 사이에 비언어로 새겨집니다. 그래서 "왜 그런지" 설명하기는 어려운데
    몸과 감정은 먼저 반응합니다. 여기서 고른 항목들은 결과 해석에서 함께 참고됩니다.
  </div>

  <!-- 점수 총람 패널 -->
  <div id="score-summary-panel" style="
    background: var(--ink);
    color: var(--bg);
    margin-top: 32px;
    overflow: hidden;
  ">
    <div style="
      padding: 14px 20px 10px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: 1px solid rgba(255,255,255,0.1);
    ">
      <div>
        <div style="font-size:10px;letter-spacing:0.2em;color:var(--accent-light);text-transform:uppercase;margin-bottom:3px;">Score Summary</div>
        <div style="font-family:'Noto Serif KR',serif;font-size:16px;font-weight:700;">12개 금지명령 점수 총람</div>
      </div>
      <div style="text-align:right;font-size:11px;color:rgba(247,244,239,0.45);line-height:1.6;">
        각 항목 최대 25점<br>
        실시간 업데이트
      </div>
    </div>

    <div style="display:grid;grid-template-columns:1fr 1fr;gap:0;">
      <!-- 1~6 -->
      <div style="border-right:1px solid rgba(255,255,255,0.07);">
        <div id="ss-1" class="ss-row"><div class="ss-num">①</div><div class="ss-name">존재하지 말라</div><div class="ss-bar-wrap"><div class="ss-bar" id="ssb-1"></div></div><div class="ss-score" id="sss-1">0</div></div>
        <div id="ss-2" class="ss-row"><div class="ss-num">②</div><div class="ss-name">너 자신이 되지 말라</div><div class="ss-bar-wrap"><div class="ss-bar" id="ssb-2"></div></div><div class="ss-score" id="sss-2">0</div></div>
        <div id="ss-3" class="ss-row"><div class="ss-num">③</div><div class="ss-name">아이가 되지 말라</div><div class="ss-bar-wrap"><div class="ss-bar" id="ssb-3"></div></div><div class="ss-score" id="sss-3">0</div></div>
        <div id="ss-4" class="ss-row"><div class="ss-num">④</div><div class="ss-name">성장하지 말라</div><div class="ss-bar-wrap"><div class="ss-bar" id="ssb-4"></div></div><div class="ss-score" id="sss-4">0</div></div>
        <div id="ss-5" class="ss-row"><div class="ss-num">⑤</div><div class="ss-name">성공하지 말라</div><div class="ss-bar-wrap"><div class="ss-bar" id="ssb-5"></div></div><div class="ss-score" id="sss-5">0</div></div>
        <div id="ss-6" class="ss-row"><div class="ss-num">⑥</div><div class="ss-name">실행하지 말라</div><div class="ss-bar-wrap"><div class="ss-bar" id="ssb-6"></div></div><div class="ss-score" id="sss-6">0</div></div>
      </div>
      <!-- 7~12 -->
      <div>
        <div id="ss-7" class="ss-row"><div class="ss-num">⑦</div><div class="ss-name">중요해지지 말라</div><div class="ss-bar-wrap"><div class="ss-bar" id="ssb-7"></div></div><div class="ss-score" id="sss-7">0</div></div>
        <div id="ss-8" class="ss-row"><div class="ss-num">⑧</div><div class="ss-name">소속되지 말라</div><div class="ss-bar-wrap"><div class="ss-bar" id="ssb-8"></div></div><div class="ss-score" id="sss-8">0</div></div>
        <div id="ss-9" class="ss-row"><div class="ss-num">⑨</div><div class="ss-name">친밀해지지 말라</div><div class="ss-bar-wrap"><div class="ss-bar" id="ssb-9"></div></div><div class="ss-score" id="sss-9">0</div></div>
        <div id="ss-10" class="ss-row"><div class="ss-num">⑩</div><div class="ss-name">건강하지 말라</div><div class="ss-bar-wrap"><div class="ss-bar" id="ssb-10"></div></div><div class="ss-score" id="sss-10">0</div></div>
        <div id="ss-11" class="ss-row"><div class="ss-num">⑪</div><div class="ss-name">생각하지 말라</div><div class="ss-bar-wrap"><div class="ss-bar" id="ssb-11"></div></div><div class="ss-score" id="sss-11">0</div></div>
        <div id="ss-12" class="ss-row"><div class="ss-num">⑫</div><div class="ss-name">느끼지 말라</div><div class="ss-bar-wrap"><div class="ss-bar" id="ssb-12"></div></div><div class="ss-score" id="sss-12">0</div></div>
      </div>
    </div>

    <div style="padding:10px 20px;border-top:1px solid rgba(255,255,255,0.1);display:flex;align-items:center;justify-content:space-between;">
      <div style="font-size:11px;color:rgba(247,244,239,0.4);">
        ★ 표시는 현재 최고 점수 항목
      </div>
      <div style="font-size:11px;color:rgba(247,244,239,0.4);">
        총점 <span id="ss-total" style="font-family:'Noto Serif KR',serif;font-size:14px;color:var(--accent-light);font-weight:700;">0</span> / 300
      </div>
    </div>
  </div>

  <div class="nav-row">
    <button class="btn btn-secondary" onclick="goPrev(3)">← 이전</button>
    <button class="btn btn-primary" onclick="goNext(3)">다음 → 허가 문장</button>
  </div>
</div>

<!-- PAGE 4: PERMISSION -->
<div class="page" id="page-4">
  <div class="section-header">
    <span class="section-tag tag-C">Part 3 — 허가 문장</span>
    <h2>나 자신에게 보내는 새로운 메시지</h2>
    <p>금지명령의 반대편에는 <strong>허가(permission)</strong>가 있습니다.<br>
    지금의 나에게 필요한 말, 들어야 했지만 듣지 못한 말을 직접 써보세요.</p>
  </div>

  <div class="permission-intro">
    <h3>허가 문장이란?</h3>
    금지명령이 "~하지 말라"는 제한이라면, 허가 문장은 "~해도 괜찮다"는 내면의 승인입니다.<br>
    어린 시절 받지 못했던 말, 지금의 나에게 진심으로 필요한 말을 적어보세요.<br>
    마음에 닿는 문장을 클릭하면 아래 입력란에 바로 추가됩니다.
    <div class="permission-example" id="perm-chip-box" style="margin-top:14px;"></div>
  </div>

  <div class="permission-rows" id="permission-rows">
    <div class="permission-row">
      <div class="permission-num">1.</div>
      <div style="flex:1;">
        <input class="permission-input" placeholder="나는 ______________ 해도 괜찮다" id="perm1">
      </div>
    </div>
    <div class="permission-row">
      <div class="permission-num">2.</div>
      <div style="flex:1;">
        <input class="permission-input" placeholder="나는 ______________ 해도 괜찮다" id="perm2">
      </div>
    </div>
    <div class="permission-row">
      <div class="permission-num">3.</div>
      <div style="flex:1;">
        <input class="permission-input" placeholder="나는 ______________ 해도 괜찮다" id="perm3">
      </div>
    </div>
    <div class="permission-row">
      <div class="permission-num">4.</div>
      <div style="flex:1;">
        <input class="permission-input" placeholder="나는 ______________ 해도 괜찮다" id="perm4">
      </div>
    </div>
  </div>

  <div style="background:var(--accent-pale);border:1px solid var(--border);padding:16px 20px;margin-top:20px;font-size:13px;color:var(--ink-light);line-height:1.8;">
    <strong style="color:var(--accent);">Tip.</strong> 다 쓰셨다면, 소리 내어 한 번 읽어보세요.<br>
    어색하거나 불편하게 느껴지는 문장이 있다면, 그것이 지금 가장 필요한 허가일 수 있습니다.
  </div>

  <div class="nav-row">
    <button class="btn btn-secondary" onclick="goPrev(4)">← 이전</button>
    <button class="btn btn-primary" onclick="showResult()">결과 보기 →</button>
  </div>
</div>

<!-- RESULT PAGE -->
<div class="page" id="page-result">
  <div class="result-header">
    <div class="section-tag tag-neutral" style="margin-bottom:16px;">검사 결과</div>
    <h2>나의 금지명령 프로파일</h2>
    <p>아래 결과는 자기이해를 위한 탐색 자료입니다.<br>높은 점수는 그 영역의 메시지가 지금도 강하게 작동하고 있음을 의미합니다.</p>
  </div>

  <div class="summary-box" id="summary-box">
    <h3>주요 금지명령 (상위 3개)</h3>
    <div class="summary-top-items" id="summary-top-items"></div>
  </div>

  <div class="result-grid" id="result-grid"></div>

  <div style="margin-bottom:28px;">
    <div class="section-tag tag-B" style="margin-bottom:16px;">몸이 보내는 신호</div>
    <div class="refl-result-box" id="signal-result-list"></div>
  </div>

  <div>
    <div class="section-tag tag-C" style="margin-bottom:16px;">나의 허가 문장</div>
    <div class="perm-result-list" id="perm-result-list"></div>
  </div>

  <div class="nav-row" style="margin-top:40px;">
    <button class="btn btn-secondary" onclick="window.print()">🖨 인쇄하기</button>
    <button class="btn btn-primary" onclick="restart()">처음으로</button>
  </div>
  <p class="print-note">인쇄 시 결과지 전체가 출력됩니다</p>
  <img src="data:image/png;base64,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" alt="Mind Harbor" style="display:block;margin:32px auto 12px;width:118px;height:auto;opacity:0.95;">
  <p style="text-align:center;font-size:11px;color:var(--ink-muted);margin-top:8px;line-height:1.6;">
이 검사는 강남욱(2021), 경상국립대학교 박사학위논문의 금지명령 척도 프레임(경험요인·결정요인)과<br>
    김정현, 《에릭 번의 감정 수업》(유노북스, 2022)의 스토퍼·복합결정·신체신호 개념을 참고하여 재구성한 자기이해용 도구이며, 표준화된 심리검사가 아닙니다.
  </p>
</div>

<script>
const injNames = [
  '', '존재하지 말라', '너 자신이 되지 말라', '아이가 되지 말라',
  '성장하지 말라', '성공하지 말라', '실행하지 말라',
  '중요해지지 말라', '소속되지 말라', '친밀해지지 말라',
  '건강하지 말라', '생각하지 말라', '느끼지 말라'
];

const injMeaning = [
  '',
  '존재감·자기 가치에 대한 근본적인 의문',
  '있는 그대로의 자신을 드러내기 어려운 패턴',
  '의존·휴식·즐김에 대한 죄책감과 혼자 해결 경향',
  '독립과 분리에 대한 두려움, 허락 필요 패턴',
  '자기 효능감 저하, 성취 앞에서의 자기 방해',
  '행동 시작에 대한 강한 내적 브레이크와 미루기',
  '자신의 욕구를 뒤로 미루고 타인 우선 패턴',
  '소속감 결핍, 집단 속 이방인 느낌',
  '친밀감에 대한 경계, 깊은 관계 회피',
  '아프거나 힘들어야 관심받는다는 무의식적 패턴',
  '자신의 생각·판단에 대한 불신과 복종 경향',
  '감정 억압, 타인 감정 우선, 자기 감정 무감각'
];

// 각 금지명령별 허가 문장 3개
const injPermissions = [
  [],
  // 1. 존재하지 말라
  [
    '나는 여기 있어도 괜찮다',
    '나의 존재 자체가 이미 충분하다',
    '나는 무언가를 증명하지 않아도 사랑받을 수 있다',
  ],
  // 2. 너 자신이 되지 말라
  [
    '나는 있는 그대로의 나로 괜찮다',
    '나다운 모습을 드러내도 안전하다',
    '나는 나 자신이어도 받아들여진다',
  ],
  // 3. 아이가 되지 말라
  [
    '나는 도움을 받아도 괜찮다',
    '나는 쉬고 즐겨도 괜찮다',
    '나는 다른 사람에게 기대어도 괜찮다',
  ],
  // 4. 성장하지 말라
  [
    '나는 내 삶을 스스로 선택할 수 있다',
    '나는 독립적으로 살아가도 괜찮다',
    '나는 혼자서도 잘 해낼 수 있다',
  ],
  // 5. 성공하지 말라
  [
    '나는 잘 해내도 괜찮다',
    '나의 성공은 누군가를 위협하지 않는다',
    '나는 노력한 만큼 인정받아도 괜찮다',
  ],
  // 6. 실행하지 말라
  [
    '나는 시도해도 괜찮다',
    '실수는 배움의 일부이고, 나는 도전해도 안전하다',
    '나는 내 판단을 믿고 행동해도 괜찮다',
  ],
  // 7. 중요해지지 말라
  [
    '나의 욕구는 중요하다',
    '나는 내 필요를 표현해도 괜찮다',
    '나는 중요한 역할을 맡아도 괜찮다',
  ],
  // 8. 소속되지 말라
  [
    '나는 어딘가에 속해도 괜찮다',
    '나는 사람들과 어울려도 안전하다',
    '나는 집단의 일원이 되어도 나를 잃지 않는다',
  ],
  // 9. 친밀해지지 말라
  [
    '나는 마음을 열어도 괜찮다',
    '가까워지는 것은 안전할 수 있다',
    '나는 사랑받고 사랑해도 괜찮다',
  ],
  // 10. 건강하지 말라
  [
    '나는 건강해도 관심을 받을 수 있다',
    '괜찮아지는 것은 안전하다',
    '나는 아프지 않아도 충분히 돌봄을 받을 자격이 있다',
  ],
  // 11. 생각하지 말라
  [
    '나의 생각은 가치 있다',
    '나는 내 판단을 믿어도 괜찮다',
    '나는 내 의견을 표현해도 안전하다',
  ],
  // 12. 느끼지 말라
  [
    '나는 감정을 느껴도 괜찮다',
    '내 감정은 중요하고 표현해도 안전하다',
    '나는 슬퍼하고 화내고 기뻐해도 괜찮다',
  ],
];

// 각 금지명령별 복합결정 문장 — 금지명령을 감추기 위해 강화해온 드라이버 문장
const injCompound = [
  '',
  '완벽하게 해내는 한, 나는 존재해도 돼.',
  '다른 사람이 원하는 모습으로 있는 한, 나는 인정받을 수 있어.',
  '혼자서 다 해내는 한, 나는 짐이 되지 않을 수 있어.',
  '곁을 지키는 한, 나는 버림받지 않을 수 있어.',
  '적당히만 해내는 한, 나는 안전할 수 있어.',
  '신중하게 계속 미루는 한, 나는 실패하지 않을 수 있어.',
  '내 욕구를 뒤로 미루는 한, 나는 자리를 지킬 수 있어.',
  '혼자 버티는 한, 나는 상처받지 않을 수 있어.',
  '거리를 두는 한, 나는 실망하지 않을 수 있어.',
  '아프거나 힘들어야, 나는 돌봄을 받을 수 있어.',
  '내 생각을 접어두는 한, 나는 갈등을 피할 수 있어.',
  '감정을 누르는 한, 나는 무너지지 않을 수 있어.',
];

function renderPermissionSuggestions() {
  const box = document.getElementById('perm-chip-box');
  if (!box) return;

  // 점수 순 정렬, 점수 없으면 전체 순서대로
  const ranked = [];
  for (let i = 1; i <= 12; i++) ranked.push({ idx: i, score: scores[i] });
  ranked.sort((a, b) => b.score - a.score);

  // 각 금지명령에서 허가 문장 순서대로 모아서 하나의 칩 목록 생성
  const chips = [];
  ranked.forEach(item => {
    injPermissions[item.idx].forEach(text => chips.push(text));
  });

  box.innerHTML = chips.map(text =>
    `<span class="perm-chip" onclick="addPermissionText(this, '${text.replace(/'/g, "\\'")}')">${text}</span>`
  ).join('');
}

let scores = new Array(13).fill(0);
let permCount = 0;

function startAssessment() {
  document.body.classList.add('assessing');
  document.getElementById('cover').style.display = 'none';
  document.getElementById('progress-wrap').style.display = 'flex';
  showPage(1);
  updateProgress(1);
}

function showPage(n) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  const id = (n === 'result') ? 'page-result' : 'page-' + n;
  const target = document.getElementById(id);
  if (target) target.classList.add('active');
  window.scrollTo(0, 0);
  // 허가 문장 페이지 진입 시 예시 렌더링
  if (n === 4) renderPermissionSuggestions();
}

function addPermissionText(chipEl, text) {
  // 이미 사용된 칩이면 무시
  if (chipEl.classList.contains('used')) return;
  for (let i = 1; i <= 4; i++) {
    const inp = document.getElementById('perm' + i);
    if (inp && !inp.value) {
      inp.value = text;
      chipEl.classList.add('used');
      chipEl.textContent = '✓ ' + text;
      return;
    }
  }
}

function updateProgress(step) {
  const labels = ['경험 탐색 1~6', '경험 탐색 7~12', '몸이 보내는 신호', '허가 문장'];
  const pct = [25, 50, 75, 100];
  const fill = document.getElementById('progress-fill');
  const label = document.getElementById('progress-label');
  const stepLabel = document.getElementById('progress-step-label');
  if (!fill || step < 1 || step > 4) return;
  label.textContent = step + ' / 5';
  fill.style.width = pct[step - 1] + '%';
  stepLabel.textContent = labels[step - 1];
}

function collectScores() {
  scores = new Array(13).fill(0);
  document.querySelectorAll('.q-scale').forEach(scale => {
    const inj = parseInt(scale.dataset.inj);
    const checked = scale.querySelector('input[type=radio]:checked');
    if (checked) scores[inj] += parseInt(checked.value);
  });
  for (let i = 1; i <= 12; i++) {
    const badge = document.getElementById('badge-' + i);
    if (badge) badge.textContent = scores[i] + ' / 25점';
  }
  updateScoreSummary();
}

function updateScoreSummary() {
  const maxScore = Math.max(...scores.slice(1));
  let total = 0;
  for (let i = 1; i <= 12; i++) {
    total += scores[i];
    const scoreEl = document.getElementById('sss-' + i);
    const barEl   = document.getElementById('ssb-' + i);
    const rowEl   = document.getElementById('ss-' + i);
    if (!scoreEl) continue;
    scoreEl.textContent = scores[i];
    barEl.style.width = (scores[i] / 25 * 100) + '%';
    // 최고점 강조
    if (scores[i] > 0 && scores[i] === maxScore) {
      rowEl.classList.add('ss-top');
      scoreEl.textContent = scores[i] + ' ★';
    } else {
      rowEl.classList.remove('ss-top');
    }
  }
  const totalEl = document.getElementById('ss-total');
  if (totalEl) totalEl.textContent = total;
}

function validatePage(pageNum) {
  const page = document.getElementById('page-' + pageNum);
  if (!page) return true;
  const scales = page.querySelectorAll('.q-scale');
  let allAnswered = true;
  scales.forEach(scale => {
    if (!scale.querySelector('input[type=radio]:checked')) allAnswered = false;
  });
  return allAnswered;
}

function goNext(fromPage) {
  collectScores();
  // 유효성 검사 (라디오 문항 있는 페이지만)
  if (fromPage === 1 || fromPage === 2) {
    if (!validatePage(fromPage)) {
      const warn = document.getElementById('warn-' + fromPage);
      if (warn) warn.style.display = 'block';
      return;
    }
    const warn = document.getElementById('warn-' + fromPage);
    if (warn) warn.style.display = 'none';
  }
  const next = fromPage + 1;
  showPage(next);
  updateProgress(Math.min(next, 4));
}

function goPrev(fromPage) {
  const prev = fromPage - 1;
  showPage(prev);
  updateProgress(Math.max(prev, 1));
}

function showResult() {
  collectScores();
  buildResult();
  showPage('result');
  const fill = document.getElementById('progress-fill');
  const label = document.getElementById('progress-label');
  const stepLabel = document.getElementById('progress-step-label');
  if (fill) fill.style.width = '100%';
  if (label) label.textContent = '완료';
  if (stepLabel) stepLabel.textContent = '결과 확인';
}

function buildResult() {
  // Sort scores
  const ranked = [];
  for (let i = 1; i <= 12; i++) ranked.push({ idx: i, score: scores[i] });
  ranked.sort((a, b) => b.score - a.score);

  // Summary top 3
  const summaryEl = document.getElementById('summary-top-items');
  summaryEl.innerHTML = '';
  for (let r = 0; r < 3; r++) {
    const item = ranked[r];
    summaryEl.innerHTML += `
      <div class="summary-top-item">
        <div class="summary-rank-badge">${r+1}</div>
        <div style="flex:1;">
          <div class="summary-name">${injNames[item.idx]}</div>
          <div class="summary-meaning">${injMeaning[item.idx]}</div>
          ${item.score > 0 ? `
          <div class="compound-box">
            <div class="compound-label">이 명령을 덮어온 문장 (복합결정)</div>
            “${injCompound[item.idx]}”
          </div>` : ''}
        </div>
        <div style="text-align:right;">
          <div class="summary-score">${item.score}</div>
          <div class="summary-max">/ 25</div>
        </div>
      </div>`;
  }

  // 몸이 보내는 신호 — 체크된 항목 정리
  const signalEl = document.getElementById('signal-result-list');
  if (signalEl) {
    const checked = Array.from(document.querySelectorAll('.signal-check:checked')).map(c => c.value);
    if (checked.length > 0) {
      signalEl.innerHTML = checked.map(v => `<span class="signal-result-chip">${v}</span>`).join('');
    } else {
      signalEl.innerHTML = '<div style="color:var(--ink-muted);font-size:13px;padding:6px 0;">체크된 신호가 없습니다.</div>';
    }
  }

  // Full grid
  const gridEl = document.getElementById('result-grid');
  gridEl.innerHTML = '';
  ranked.forEach((item, idx) => {
    const pct = Math.round((item.score / 25) * 100);
    const isTop = idx < 3;
    gridEl.innerHTML += `
      <div class="result-item ${isTop ? 'highlight' : ''}">
        <div class="result-rank">${idx+1}</div>
        <div>
          <div class="result-name">${injNames[item.idx]}</div>
        </div>
        <div class="result-bar-wrap"><div class="result-bar-fill" style="width:${pct}%"></div></div>
        <div class="result-score">${item.score}</div>
      </div>`;
  });

  // Permissions
  const permEl = document.getElementById('perm-result-list');
  permEl.innerHTML = '';
  for (let i = 1; i <= 4; i++) {
    const val = (document.getElementById('perm' + i)||{}).value;
    if (val && val.trim()) {
      permEl.innerHTML += `<div class="perm-result-item">${val}</div>`;
    }
  }
  if (!permEl.innerHTML) {
    permEl.innerHTML = '<div style="color:var(--ink-muted);font-size:13px;padding:10px 0;">작성된 허가 문장이 없습니다.</div>';
  }
}

function restart() {
  document.querySelectorAll('input[type=radio]').forEach(r => r.checked = false);
  document.querySelectorAll('input[type=checkbox]').forEach(c => c.checked = false);
  document.querySelectorAll('textarea, input[type=text]').forEach(t => t.value = '');
  for (let i = 1; i <= 12; i++) {
    const badge = document.getElementById('badge-' + i);
    if (badge) badge.textContent = '0 / 25점';
  }
  scores = new Array(13).fill(0);
  document.body.classList.remove('assessing');
  document.getElementById('cover').style.display = 'flex';
  document.getElementById('progress-wrap').style.display = 'none';
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  window.scrollTo(0, 0);
}

// Live score update on radio change
document.addEventListener('change', function(e) {
  if (e.target.type === 'radio') {
    collectScores();
  }
});
</script>
</body>
</html>
