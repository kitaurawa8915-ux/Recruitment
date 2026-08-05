[リハビリ科採用面接評価アプリ (2).html](https://github.com/user-attachments/files/30736622/2.html)
<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>リハビリ科 採用面接評価</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Zen+Kaku+Gothic+New:wght@400;500;700;900&family=Shippori+Mincho:wght@500;700&display=swap" rel="stylesheet">
<style>
:root{
  --ink:#1c2b33;
  --navy:#173b4d;
  --navy-deep:#0e2531;
  --sage:#5c8a7a;
  --sage-soft:#e7f0ec;
  --paper:#f7f5ef;
  --card:#ffffff;
  --line:#dcd8cb;
  --amber:#c98a2b;
  --amber-soft:#f8ecd8;
  --red:#b3492f;
  --red-soft:#f7e5df;
  --muted:#7c8a8f;
  --radius:14px;
  --font-head:'Shippori Mincho', serif;
  --font-body:'Zen Kaku Gothic New', 'Hiragino Sans', sans-serif;
}
*{box-sizing:border-box;}
html,body{margin:0;padding:0;}
body{
  font-family:var(--font-body);
  background:var(--paper);
  color:var(--ink);
  line-height:1.6;
  -webkit-font-smoothing:antialiased;
}
::selection{background:var(--amber-soft);}

/* ---------- App shell ---------- */
.app{max-width:980px;margin:0 auto;padding:0 20px 80px;}

.topbar{
  position:sticky; top:0; z-index:40;
  background:var(--navy-deep);
  color:#f1ece0;
  padding:14px 20px;
  display:flex; align-items:center; justify-content:space-between; gap:16px;
  box-shadow:0 2px 10px rgba(14,37,49,.25);
}
.topbar .brand{display:flex; align-items:baseline; gap:10px;}
.topbar .brand .mark{
  font-family:var(--font-head); font-weight:700; font-size:22px; letter-spacing:.04em;
}
.topbar .brand .sub{font-size:11px; color:#b8c7cc; letter-spacing:.12em;}
.topbar .actions{display:flex; gap:8px;}
.topbar button{
  background:transparent; border:1px solid rgba(241,236,224,.35); color:#f1ece0;
  padding:7px 14px; border-radius:999px; font-family:var(--font-body); font-size:12.5px;
  cursor:pointer; transition:.15s;
}
.topbar button:hover{background:rgba(241,236,224,.12);}

.hero{
  padding:30px 0 14px;
}
.hero h1{
  font-family:var(--font-head); font-size:26px; margin:0 0 6px; color:var(--navy-deep); font-weight:700;
}
.hero p{margin:0; color:var(--muted); font-size:13.5px;}

/* ---------- Setup card ---------- */
.setup{
  background:var(--card); border:1px solid var(--line); border-radius:var(--radius);
  padding:20px 22px; margin:18px 0; display:grid; grid-template-columns:repeat(4,1fr); gap:14px 16px;
}
.field{display:flex; flex-direction:column; gap:6px;}
.field label{font-size:11.5px; color:var(--muted); letter-spacing:.04em;}
.field input[type=text], .field input[type=date]{
  border:1px solid var(--line); border-radius:8px; padding:9px 10px; font-family:var(--font-body); font-size:14px;
  background:#fdfcf9;
}
.field input:focus{outline:2px solid var(--sage); outline-offset:1px;}
.jobtype-group{grid-column:span 2;}
.segmented{display:flex; border:1px solid var(--line); border-radius:8px; overflow:hidden;}
.segmented button{
  flex:1; border:none; background:#fdfcf9; padding:9px 6px; font-family:var(--font-body); font-size:13px;
  color:var(--ink); cursor:pointer; border-right:1px solid var(--line);
}
.segmented button:last-child{border-right:none;}
.segmented button.active{background:var(--navy); color:#fff;}

/* ---------- Summary dashboard ---------- */
.dashboard{
  background:var(--navy-deep); color:#f1ece0; border-radius:var(--radius);
  padding:20px 22px; margin:18px 0; display:grid; grid-template-columns:1.3fr 1fr; gap:20px; align-items:center;
}
.dashboard .stats{display:grid; grid-template-columns:repeat(3,1fr); gap:14px;}
.stat .num{font-family:var(--font-head); font-size:26px; font-weight:700;}
.stat .num.flag{color:#e8a385;}
.stat .label{font-size:11px; color:#b8c7cc; margin-top:2px; letter-spacing:.03em;}
.judgment{
  margin-top:12px; display:inline-flex; align-items:center; gap:8px; padding:6px 14px; border-radius:999px;
  font-size:13px; font-weight:700; letter-spacing:.02em;
}
.judgment.hire{background:#375c48; color:#d9f0d6;}
.judgment.cond{background:#6b5a2a; color:#f5e2ae;}
.judgment.pass{background:#5c3128; color:#f3cdbd;}
.progress-wrap{}
.progress-track{height:10px; background:rgba(241,236,224,.15); border-radius:999px; overflow:hidden;}
.progress-fill{height:100%; background:linear-gradient(90deg,var(--sage),#8fbfa8); transition:width .3s;}
.progress-labels{display:flex; justify-content:space-between; font-size:10.5px; color:#b8c7cc; margin-top:5px;}

.radar-box{display:flex; flex-direction:column; align-items:center; gap:4px;}
.radar-box svg{width:170px; height:170px;}
.radar-caption{font-size:10.5px; color:#b8c7cc; text-align:center;}

/* ---------- Consistency hint (inline, per question) ---------- */
.link-hint{
  margin-top:8px; background:var(--amber-soft); border:1px solid #e8d4a8; border-radius:8px; padding:2px 12px;
}
.link-hint summary{
  cursor:pointer; font-size:11.5px; font-weight:700; color:#8a6118; list-style:none; padding:8px 0;
}
.link-hint summary::-webkit-details-marker{display:none;}
.link-hint summary:before{content:"▸ "; font-size:10px;}
.link-hint[open] summary:before{content:"▾ ";}
.link-hint-body{padding:0 0 10px; font-size:12px; color:#6b5220; line-height:1.6;}
.link-hint-body p{margin:0;}
.link-hint-body b{color:#8a6118;}

/* ---------- Category sections ---------- */
.category{margin:22px 0 0;}
.category-head{
  display:flex; align-items:baseline; gap:10px; padding-bottom:6px; margin-bottom:10px;
  border-bottom:2px solid var(--navy);
}
.category-head h2{
  font-family:var(--font-head); font-size:17px; margin:0; color:var(--navy-deep); font-weight:700;
  white-space:pre-line;
}
.category-head .count{font-size:11.5px; color:var(--muted);}

.qcard{
  background:var(--card); border:1px solid var(--line); border-radius:var(--radius);
  padding:16px 18px; margin-bottom:12px; position:relative;
}
.qcard.flagged{border-color:var(--red); box-shadow:0 0 0 1px var(--red) inset;}
.qcard .qtop{display:flex; justify-content:space-between; gap:12px; align-items:flex-start;}
.qcard .sub{font-size:11px; color:var(--sage); font-weight:700; letter-spacing:.03em; margin-bottom:3px;}
.qcard .question{font-size:14.5px; color:var(--ink); font-weight:500;}
.weight-badge{
  flex-shrink:0; background:var(--amber-soft); color:var(--amber); font-size:11px; font-weight:700;
  padding:4px 9px; border-radius:999px; white-space:nowrap;
}
.flag-badge{
  flex-shrink:0; background:var(--red-soft); color:var(--red); font-size:11px; font-weight:700;
  padding:4px 9px; border-radius:999px; white-space:nowrap; margin-left:6px;
}

.example-toggle{
  margin-top:8px;
}
.example-toggle summary{
  cursor:pointer; font-size:12px; color:var(--muted); list-style:none; display:inline-flex; align-items:center; gap:4px;
}
.example-toggle summary::-webkit-details-marker{display:none;}
.example-toggle summary:before{content:"▸"; font-size:10px;}
.example-toggle[open] summary:before{content:"▾";}
.example-body{
  margin-top:8px; font-size:12.5px; background:#fbfaf5; border:1px dashed var(--line); border-radius:8px; padding:10px 12px;
  display:grid; grid-template-columns:1fr 1fr; gap:10px;
}
.example-body .good{color:#3f6e4f;}
.example-body .bad{color:#8f4331;}
.example-body b{display:block; font-size:11px; margin-bottom:3px;}

.score-row{
  display:grid; grid-template-columns:1fr 1fr auto auto; gap:16px; align-items:end; margin-top:14px;
}
.score-group label{display:block; font-size:11px; color:var(--muted); margin-bottom:5px;}
.score-buttons{display:flex; gap:5px;}
.score-buttons button{
  width:30px; height:30px; border-radius:8px; border:1px solid var(--line); background:#fdfcf9;
  cursor:pointer; font-size:13px; font-family:var(--font-body); color:var(--ink); transition:.12s;
}
.score-buttons button:hover{border-color:var(--sage);}
.score-buttons button.sel{background:var(--navy); color:#fff; border-color:var(--navy);}
.calc-group{text-align:center;}
.calc-group .val{font-family:var(--font-head); font-size:19px; font-weight:700; color:var(--navy);}
.calc-group .lbl{font-size:10.5px; color:var(--muted);}

.comment-wrap{margin-top:12px;}
.comment-wrap label{font-size:11px; color:var(--muted); display:block; margin-bottom:5px;}
.comment-wrap textarea{
  width:100%; min-height:44px; border:1px solid var(--line); border-radius:8px; padding:8px 10px;
  font-family:var(--font-body); font-size:13px; resize:vertical; background:#fdfcf9;
}
.comment-wrap textarea:focus{outline:2px solid var(--sage); outline-offset:1px;}

/* ---------- Saved list / drawer ---------- */
.drawer-overlay{
  position:fixed; inset:0; background:rgba(14,37,49,.45); z-index:60; display:none;
}
.drawer-overlay.open{display:block;}
.drawer{
  position:fixed; top:0; right:0; height:100%; width:360px; max-width:92vw; background:var(--paper); z-index:61;
  transform:translateX(100%); transition:transform .25s ease; box-shadow:-4px 0 24px rgba(0,0,0,.2);
  display:flex; flex-direction:column;
}
.drawer.open{transform:translateX(0);}
.drawer-head{
  padding:18px 20px; background:var(--navy-deep); color:#f1ece0; display:flex; justify-content:space-between; align-items:center;
}
.drawer-head h3{margin:0; font-family:var(--font-head); font-size:16px;}
.drawer-head button{background:none; border:none; color:#f1ece0; font-size:20px; cursor:pointer;}
.drawer-body{padding:14px 16px; overflow-y:auto; flex:1;}
.saved-item{
  background:var(--card); border:1px solid var(--line); border-radius:10px; padding:12px 14px; margin-bottom:10px;
}
.saved-item .name{font-weight:700; font-size:14px;}
.saved-item .meta{font-size:11.5px; color:var(--muted); margin:3px 0 8px;}
.saved-item .row{display:flex; gap:8px;}
.saved-item button{
  font-size:11.5px; padding:5px 10px; border-radius:999px; border:1px solid var(--line); background:#fdfcf9; cursor:pointer;
}
.saved-item button.danger{color:var(--red); border-color:var(--red-soft);}
.saved-item button.primary{background:var(--navy); color:#fff; border-color:var(--navy);}
.empty-note{color:var(--muted); font-size:13px; text-align:center; margin-top:40px;}

.toast{
  position:fixed; bottom:22px; left:50%; transform:translateX(-50%) translateY(20px); opacity:0;
  background:var(--navy-deep); color:#f1ece0; padding:10px 20px; border-radius:999px; font-size:13px; z-index:80;
  transition:.25s; pointer-events:none;
}
.toast.show{opacity:1; transform:translateX(-50%) translateY(0);}

.footer-note{text-align:center; color:var(--muted); font-size:11.5px; margin-top:30px;}

@media (max-width:720px){
  .setup{grid-template-columns:1fr 1fr;}
  .jobtype-group{grid-column:span 2;}
  .dashboard{grid-template-columns:1fr;}
  .score-row{grid-template-columns:1fr 1fr; row-gap:10px;}
  .example-body{grid-template-columns:1fr;}
  .radar-box{display:none;}
}
</style>
</head>
<body>
<div class="app" id="app"></div>
<div class="drawer-overlay" id="drawerOverlay"></div>
<div class="drawer" id="drawer">
  <div class="drawer-head">
    <h3>保存済みの評価</h3>
    <button id="drawerClose">✕</button>
  </div>
  <div class="drawer-body" id="drawerBody"></div>
</div>
<div class="toast" id="toast"></div>

<script id="data-prof" type="application/json">[{"id": "p38", "category": "①勤務姿勢・長期定着", "sub": "転職・応募理由", "question": "前職（現職）の退職理由と、当院を選んだ理由を教えてください。", "weight": 5, "target": "ALL", "good": "退職理由が他責でなく、当院への応募理由が具体的（理念・患者層・成長環境など）", "bad": "「給与」「人間関係が嫌だった」のみ。当院への志望理由が曖昧・消去法"}, {"id": "p8", "category": "②主体性", "sub": "自発的行動", "question": "指示がない状況でも自分から動いた経験を教えてください。特に臨床場面で、誰かに言われる前に動いたエピソードを具体的に。", "weight": 5, "target": "ALL", "good": "患者の急変に気づき医師に即報告した、申し送り前に記録を整理して次の担当者が動きやすくした", "bad": "「言われていなかったので動かなかった」「何をすべきか分からず待っていた」"}, {"id": "p9", "category": "②主体性", "sub": "自己研鑽・学習意欲", "question": "ご自身のスキルアップのために、現在定期的に参加されている外部の講習会や勉強会などはありますか？ 具体的にどのような手技や理論を学ばれているかも併せて教えてください。", "weight": 5, "target": "ALL", "good": "参加している講習会・勉強会名や学んでいる手技・理論を具体的に説明でき、学びを日々の臨床にどう活かしているかまで話せる", "bad": "「特に参加していない」「業務で手一杯で余裕がない」など、具体的な学びの機会や継続的な自己研鑽の姿勢が見られない"}, {"id": "p11", "category": "③報連相", "sub": "報告タイミング", "question": "患者の状態変化や判断に迷う場面で、どのタイミングで上司・医師に報告・相談しますか？基準を教えてください。", "weight": 5, "target": "ALL", "good": "「バイタルが基準値を外れた時点で即報告する」など明確な基準を持っている", "bad": "「なんとなく様子を見てから」「自分で判断してから報告する」"}, {"id": "p12", "category": "③報連相", "sub": "連絡の質", "question": "「報連相がうまくいかなかった」または「うまくできた」臨床経験を一つ教えてください。何が違いを生みましたか？", "weight": 5, "target": "ALL", "good": "「伝え方が曖昧で誤解を生んだ。以後5W1Hで簡潔に伝えるようにした」など学びがある", "bad": "「失敗したことはない」と断言、または具体的エピソードが出てこない"}, {"id": "p14", "category": "④チーム志向", "sub": "チーム最適", "question": "自分の治療方針と異なるチームの方針になった場合、どのように行動しますか？", "weight": 5, "target": "ALL", "good": "「まず方針の意図を理解しようとし、納得できなければ適切な場で意見を述べ、最終的にはチームの判断に従う」", "bad": "「自分のやり方が正しいので従えない」「黙って従うだけ」の二択思考"}, {"id": "p16", "category": "④チーム志向", "sub": "対立経験", "question": "チームメンバーと意見が食い違った際、どのようにコミュニケーションを図り、解決に導きますか？", "weight": 5, "target": "ALL", "good": "相手の意見を一度受け止めた上で、事実や患者様にとっての最善を基準に話し合い、建設的に着地させたプロセスを具体的に語れる", "bad": "「自分の意見を通す」「上司に判断を丸投げする」など、対話や歩み寄りの姿勢が見られない、または対立を避けて終わらせている"}, {"id": "p17", "category": "⑤問題解決力", "sub": "事実確認・原因分析", "question": "リハビリが計画通りに進まない、あるいは患者様の状態が思わしくないといった課題に直面した際、まずどのような事実（情報）を確認し、どのようにその原因を分析していますか？", "weight": 5, "target": "ALL", "good": "バイタルや動作状況、患者様の発言、生活環境など複数の情報源から事実を整理し、身体面・心理面・環境面など多角的な視点で原因を仮説立てて考えられている", "bad": "「なんとなく」「経験則だけで」判断する、事実確認をせず思い込みで対応を変えてしまう、原因を1つの要因だけに決めつける"}, {"id": "p19", "category": "⑤問題解決力", "sub": "解決行動", "question": "業務上や臨床上の問題（患者・業務・チーム）を自分主導で解決したエピソードを教えてください。", "weight": 5, "target": "ALL", "good": "問題の発見→自ら取った具体的な行動→結果（改善したこと）まで一連の流れを主体的に語れる", "bad": "「気づいたが誰かに相談して終わった」「解決したのは自分ではなく上司や先輩だった」など主体性が見えない"}, {"id": "p21", "category": "⑥素直さ", "sub": "フィードバック受容", "question": "上司・先輩・医師から厳しい指摘を受けたとき、どのように受け止め、その後どう行動しましたか？", "weight": 5, "target": "ALL", "good": "「最初は納得できなかったが、指摘の意図を考え直し翌日から行動を変えた」", "bad": "「理不尽だと思った」で止まる、または「そういう指摘を受けたことがない」"}, {"id": "p22", "category": "⑥素直さ", "sub": "自己認識", "question": "自分の臨床上の弱点・苦手な領域を教えてください。それに対してどう取り組んでいますか？", "weight": 4, "target": "ALL", "good": "具体的な弱点＋現在進行形の改善行動をセットで語れる", "bad": "「特に弱点はない」「弱点はあるが対策はしていない」"}, {"id": "p24", "category": "⑦患者指導・行動変容（PT）", "sub": "自立支援の哲学", "question": "リハビリの最終ゴールは何だと考えていますか？そのゴールに向けて患者にどう関わるべきか、考えを教えてください。", "weight": 5, "target": "PT", "good": "「患者さんが自分でできることを増やすこと。そのために自主トレの習慣化と生活指導を必ずセットにする」", "bad": "「患者さんに満足してもらうこと」「症状を取ること」と受動的な目標設定"}, {"id": "p25", "category": "⑦患者指導・行動変容（PT）", "sub": "迎合対応の判断", "question": "「マッサージしてほしい」と繰り返し求める患者がいます。あなたはどう対応しますか？その理由も教えてください。", "weight": 5, "target": "PT", "good": "「なぜマッサージだけでは改善しないかを丁寧に説明し、本来必要なアプローチに切り替える」", "bad": "「とりあえずマッサージをしてから本来の治療をする」「患者さんの希望なので断れない」"}, {"id": "p27", "category": "⑦患者指導・行動変容（PT）", "sub": "生活指導と信頼関係", "question": "患者様に生活習慣の改善（セルフケアの定着など）を促す際、指導の必要性を伝えつつ、患者様との良好な信頼関係を維持するために、どのような点に配慮していますか？", "weight": 5, "target": "PT", "good": "一方的に指導するのではなく、患者様の生活背景や気持ちに配慮しながら、必要性を分かりやすく伝え、小さな成功体験を積めるよう工夫している", "bad": "「言うことを聞いてもらえればいい」など患者様の意向を無視した一方的な指導、または関係性を気にするあまり必要な指導を避けてしまう"}, {"id": "p31", "category": "⑧コミュニケーション・多職種連携", "sub": "多職種間の意見相違", "question": "医師や受付など他職種と意見が合わなかった経験と、その対処法を教えてください。", "weight": 4, "target": "ALL", "good": "医師や受付など専門・役割の異なるスタッフの立場や事情を踏まえた上で、歩み寄り・調整して合意形成した具体例を話せる", "bad": "「自分の意見を通した」「関わらないようにした」など、職種の違いを踏まえた歩み寄りが見られない、または経験がないと答えて終わる"}, {"id": "p34", "category": "⑧コミュニケーション・多職種連携", "sub": "患者説明", "question": "リハビリの目的・効果・見込みを患者にどのように説明していますか？", "weight": 4, "target": "ALL", "good": "「専門用語を避け、患者の生活に即した言葉で、ゴールから逆算して説明する」", "bad": "「説明はしている」と言うが具体的な工夫が語れない"}, {"id": "p36", "category": "⑨感情コントロール・ストレス耐性", "sub": "ストレス耐性", "question": "最もストレスを感じた状況と、その対処法を教えてください。", "weight": 4, "target": "ALL", "good": "「業務後に振り返りを書く・信頼できる同僚に話すなど、具体的な対処法を持っている」", "bad": "「特にストレスは感じない」と鈍感または「ずっと引きずる」と対処なし"}]</script>
<script id="data-asst" type="application/json">[{"id": "a23", "category": "①勤務姿勢・長期定着", "sub": "転職・応募理由", "question": "前職（現職）の退職理由と、当院を選んだ理由を教えてください。", "weight": 5, "good": "退職理由が他責でなく、当院への応募理由が具体的（患者層・チーム環境など）", "bad": "「給与」「人間関係が嫌だった」のみ。志望理由が曖昧・消去法"}, {"id": "a7", "category": "②主体性", "sub": "自発的行動", "question": "指示がない状況で、自分から動いた経験を教えてください。具体的にどう判断しましたか？", "weight": 5, "good": "「患者さんが待合で不安そうだったので、声をかけて状況を確認し担当者に伝えた」など具体的", "bad": "「言われたことはやっている」「特に気になることはなかった」と受け身"}, {"id": "a8", "category": "②主体性", "sub": "自己研鑽・学習意欲", "question": "ご自身のスキルアップのために、現在定期的に参加されている外部の講習会や勉強会などはありますか？ 具体的にどのような手技や理論を学ばれているかも併せて教えてください。", "weight": 5, "good": "参加している研修・勉強会名や学んでいる内容（介助技術、患者対応、感染対策など）を具体的に説明でき、日々の業務にどう活かしているか話せる", "bad": "「特に参加していない」「余裕がない」など、学びの機会や自己研鑽への意欲が見られない"}, {"id": "a10", "category": "③報連相", "sub": "報告タイミング", "question": "業務中に判断に迷った際、どのタイミングで上司・先輩に報告・相談しますか？", "weight": 5, "good": "「患者さんが痛みを訴えた時点で即スタッフに伝える。判断は自分でしない」と明確", "bad": "「大丈夫そうだったので様子を見た」「後で言おうと思っていた」"}, {"id": "a11", "category": "③報連相", "sub": "連絡の質", "question": "「報連相で失敗した」または「うまくできた」経験を一つ教えてください。", "weight": 5, "good": "「曖昧な伝え方で誤解された。以来、5W1Hで簡潔に伝えるようにした」と学びがある", "bad": "「失敗したことはない」と断言／具体的エピソードが出てこない"}, {"id": "a13", "category": "④チーム志向", "sub": "チーム最適", "question": "自分の意見と違う方針になった場合、どのように行動しますか？", "weight": 5, "good": "「まず方針の意図を理解しようとする。意見があれば適切なタイミングで伝える」", "bad": "「自分の考えと違うので従えない」または「何も言わず不満を抱える」"}, {"id": "a15", "category": "④チーム志向", "sub": "対立経験", "question": "チームメンバーと意見が食い違った際、どのようにコミュニケーションを図り、解決に導きますか？", "weight": 5, "good": "相手の意見を受け止めた上で、業務上何が最善かを基準に歩み寄り、具体的にどう解決へ導いたか話せる", "bad": "「自分の意見を通す」「先輩に任せる」など、対話や歩み寄りの姿勢が見られない"}, {"id": "a17", "category": "⑤問題解決力", "sub": "事実確認・原因分析", "question": "業務中に「何かおかしい」「問題がありそうだ」と感じた際、まずどのような事実（情報）を確認し、どのように原因を特定していますか？", "weight": 5, "good": "患者さんの様子・環境・自分の対応など複数の視点から事実を整理し、原因をいくつかの角度から考えてから対応している", "bad": "「なんとなく」「感覚で」判断する、事実確認をせずに思い込みで対応する"}, {"id": "a20", "category": "⑥素直さ", "sub": "フィードバック受容", "question": "上司・先輩から厳しい指摘を受けたとき、どのように受け止め行動しましたか？", "weight": 5, "good": "「最初は落ち込んだが、指摘の意図を考え直して翌日から行動を変えた」", "bad": "「理不尽だと思った」で終わる、または「そういう指摘を受けたことがない」"}, {"id": "a21", "category": "⑥素直さ", "sub": "自己認識", "question": "自分の弱点・苦手なことを教えてください。それに対してどう取り組んでいますか？", "weight": 4, "good": "具体的な弱点＋現在取り組んでいることをセットで語れる", "bad": "「特に弱点はない」「弱点はあるが特に対策はしていない」"}]</script>
<script>
// ============ Data ============
const PROF = JSON.parse(document.getElementById('data-prof').textContent);
const ASST = JSON.parse(document.getElementById('data-asst').textContent);

const JOBTYPES = [
  {key:'PT', label:'PT'},
  {key:'JU', label:'柔道整復師'},
  {key:'AS', label:'リハビリ助手'}
];

const RADAR_AXES = ['②主体性','③報連相','④チーム志向','⑤問題解決力','⑥素直さ'];

// Pairs/groups of questions that probe a similar underlying trait from a different
// angle. Rendered inline on each involved question so the interviewer can check
// whether the candidate's answers are consistent with each other. Notes intentionally
// don't hardcode category numbers (numbering can change) — related items are looked
// up live from the current question set.
const PROF_CONSISTENCY_PAIRS = [
  {ids:['p8','p24','p25'], note:'患者・業務に対して自ら動く姿勢が一貫しているか'},
  {ids:['p16','p31'], note:'意見の相違・対立への対応スタイルが一貫しているか（チーム内 ⇔ 他職種）'},
  {ids:['p17','p19'], note:'考える力と実際に行動する力の一貫性'},
  {ids:['p21','p22','p38'], note:'自己理解の深さ・成長意欲の一貫性'},
  {ids:['p27','p34'], note:'患者とのコミュニケーションスタイルの一貫性'},
];
const ASST_CONSISTENCY_PAIRS = [
  {ids:['a7','a17'], note:'自ら動く姿勢と問題への向き合い方の一貫性'},
  {ids:['a15','a20'], note:'対人関係でのスタンスの一貫性'},
  {ids:['a21','a23'], note:'自己理解・成長意欲の一貫性'},
];

function currentConsistencyPairs(){
  return state.jobType === 'AS' ? ASST_CONSISTENCY_PAIRS : PROF_CONSISTENCY_PAIRS;
}

// Returns [{note, related:[{sub,category}]}] for the given item id, using only
// items that are actually visible in the current question set (so a pair that
// references a PT-only question won't show up when viewing 柔道整復師, etc).
function relatedFor(itemId, items){
  const byId = new Map(items.map(it=>[it.id, it]));
  const out = [];
  currentConsistencyPairs().forEach(p=>{
    if(!p.ids.includes(itemId)) return;
    const otherIds = p.ids.filter(id=>id!==itemId);
    const related = otherIds.map(id=>byId.get(id)).filter(Boolean);
    if(related.length>0 && byId.has(itemId)){
      out.push({note:p.note, related});
    }
  });
  return out;
}

// ============ State ============
let state = {
  id: null,
  name: '',
  date: '',
  jobType: 'PT',
  interviewer1: '',
  interviewer2: '',
  scores: {} // itemId -> {s1,s2,comment}
};

function blankScore(){ return {s1:null, s2:null, comment:''}; }

function getScore(itemId){
  if(!state.scores[itemId]) state.scores[itemId] = blankScore();
  return state.scores[itemId];
}

function currentItems(){
  if(state.jobType === 'AS') return ASST.map(x=>({...x, target:'ALL'}));
  if(state.jobType === 'PT') return PROF; // ALL + PT
  return PROF.filter(x=>x.target==='ALL'); // 柔道整復師: exclude PT-only block
}

function average(s1,s2){
  const vals=[s1,s2].filter(v=>v!==null && v!==undefined);
  if(vals.length===0) return null;
  return vals.reduce((a,b)=>a+b,0)/vals.length;
}

function computeSummary(){
  const items = currentItems();
  let total=0, max=0, flags=0;
  items.forEach(it=>{
    const sc = getScore(it.id);
    const avg = average(sc.s1, sc.s2);
    max += it.weight*5;
    if(avg!==null){
      total += avg*it.weight;
      if(avg<=2) flags++;
    }
  });
  const rate = max>0 ? total/max : 0;
  let judgment = 'pass', judgmentLabel = '✕ 見送り';
  if(rate>=0.8){ judgment='hire'; judgmentLabel='◎ 採用'; }
  else if(rate>=0.65){ judgment='cond'; judgmentLabel='△ 条件付き'; }
  return {total, max, rate, flags, judgment, judgmentLabel};
}

function radarValues(){
  // average per axis (only for professional sheet's shared 5 axes; also works for assistant sheet, same axis names)
  const items = currentItems();
  return RADAR_AXES.map(axis=>{
    const group = items.filter(it=>it.category.replace(/\s/g,'')===axis);
    let sum=0, cnt=0;
    group.forEach(it=>{
      const sc=getScore(it.id);
      const avg=average(sc.s1,sc.s2);
      if(avg!==null){ sum+=avg; cnt++; }
    });
    return cnt>0 ? sum/cnt : 0;
  });
}

// ============ Storage ============
// Wraps window.storage (persists across sessions inside the Claude app) with an
// in-memory fallback so the app still works — just without persistence — if this
// file is opened somewhere window.storage isn't available (e.g. as a plain local
// file, or in some previews/browsers).
const LIST_KEY = 'evaluations:index';
let usingFallback = false;
let fallbackWarned = false;
const memoryStore = {};

function warnFallbackOnce(){
  if(!fallbackWarned){
    fallbackWarned = true;
    showToast('この表示環境では保存が一時的（このタブを閉じると消えます）になっています');
  }
}

const db = {
  async get(key){
    if(!usingFallback){
      try{
        return await window.storage.get(key, false);
      }catch(e){
        // storage API missing or errored -> switch to fallback for the rest of the session
        usingFallback = true;
        warnFallbackOnce();
      }
    }
    return (key in memoryStore) ? {key, value: memoryStore[key]} : null;
  },
  async set(key, value){
    if(!usingFallback){
      try{
        return await window.storage.set(key, value, false);
      }catch(e){
        usingFallback = true;
        warnFallbackOnce();
      }
    }
    memoryStore[key] = value;
    return {key, value};
  },
  async delete(key){
    if(!usingFallback){
      try{
        return await window.storage.delete(key, false);
      }catch(e){
        usingFallback = true;
        warnFallbackOnce();
      }
    }
    delete memoryStore[key];
    return {key, deleted:true};
  }
};

// If window.storage doesn't exist at all, go straight to fallback (avoids a slow failed call).
if(typeof window.storage === 'undefined' || window.storage === null){
  usingFallback = true;
}

async function saveEvaluation(){
  if(!state.name.trim()){
    showToast('候補者氏名を入力してください');
    return;
  }
  if(!state.id) state.id = 'ev_' + Date.now() + '_' + Math.random().toString(36).slice(2,7);
  const record = {...state, savedAt: new Date().toISOString()};
  try{
    await db.set('eval:'+state.id, JSON.stringify(record));
    let idx = [];
    try{
      const r = await db.get(LIST_KEY);
      idx = r ? JSON.parse(r.value) : [];
    }catch(e){ idx = []; }
    idx = idx.filter(x=>x.id!==state.id);
    idx.unshift({id:state.id, name:state.name, date:state.date, jobType:state.jobType, savedAt:record.savedAt});
    await db.set(LIST_KEY, JSON.stringify(idx));
    showToast(usingFallback ? '一時保存しました（永続保存は無効です）' : '保存しました');
  }catch(e){
    console.error('save failed:', e);
    showToast('保存に失敗しました（' + (e && e.message ? e.message : '不明なエラー') + '）');
  }
}

async function loadIndex(){
  try{
    const r = await db.get(LIST_KEY);
    return r ? JSON.parse(r.value) : [];
  }catch(e){ return []; }
}

async function loadEvaluation(id){
  try{
    const r = await db.get('eval:'+id);
    if(!r) return null;
    return JSON.parse(r.value);
  }catch(e){ return null; }
}

async function deleteEvaluation(id){
  try{
    await db.delete('eval:'+id);
    let idx = await loadIndex();
    idx = idx.filter(x=>x.id!==id);
    await db.set(LIST_KEY, JSON.stringify(idx));
  }catch(e){ console.error(e); }
}

async function deleteAllEvaluations(){
  try{
    const idx = await loadIndex();
    for(const it of idx){
      await db.delete('eval:'+it.id);
    }
    await db.set(LIST_KEY, JSON.stringify([]));
  }catch(e){ console.error(e); }
}

function newEvaluation(){
  state = {id:null, name:'', date:'', jobType:'PT', interviewer1:'', interviewer2:'', scores:{}};
  render();
}

// ============ Toast ============
let toastTimer=null;
function showToast(msg){
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer = setTimeout(()=>t.classList.remove('show'), 2200);
}

// ============ Rendering ============
function jobLabel(key){
  return {PT:'PT', JU:'柔道整復師', AS:'リハビリ助手'}[key] || key;
}

function groupByCategory(items){
  const map = new Map();
  items.forEach(it=>{
    if(!map.has(it.category)) map.set(it.category, []);
    map.get(it.category).push(it);
  });
  return map;
}

function render(){
  const app = document.getElementById('app');
  const summary = computeSummary();
  const items = currentItems();
  const groups = groupByCategory(items);

  let catHtml = '';
  for(const [cat, list] of groups){
    catHtml += `<section class="category">
      <div class="category-head"><h2>${escapeHtml(cat)}</h2><span class="count">${list.length}問</span></div>
      ${list.map(q=>renderQuestion(q, items)).join('')}
    </section>`;
  }

  app.innerHTML = `
    <div class="topbar">
      <div class="brand">
        <span class="mark">採用面接評価</span>
        <span class="sub">REHABILITATION DEPT.</span>
      </div>
      <div class="actions">
        <button id="btnNew">新規</button>
        <button id="btnList">保存一覧</button>
        <button id="btnSave">保存</button>
        <button id="btnCopy">サマリーをコピー</button>
      </div>
    </div>
    <div class="hero">
      <h1>リハビリテーション科　採用面接評価シート</h1>
      <p>候補者情報を入力し、質問ごとにスコアを付けると、加重点・達成率・採用判定が自動で計算されます。</p>
    </div>

    <div class="setup">
      <div class="field"><label>候補者氏名</label><input type="text" id="f-name" value="${escapeAttr(state.name)}" placeholder="山田 太郎"></div>
      <div class="field"><label>面接日</label><input type="date" id="f-date" value="${escapeAttr(state.date)}"></div>
      <div class="field"><label>面接官①</label><input type="text" id="f-int1" value="${escapeAttr(state.interviewer1)}" placeholder="面接官氏名"></div>
      <div class="field"><label>面接官②</label><input type="text" id="f-int2" value="${escapeAttr(state.interviewer2)}" placeholder="面接官氏名"></div>
      <div class="field jobtype-group">
        <label>応募職種</label>
        <div class="segmented" id="jobtype-seg">
          ${JOBTYPES.map(j=>`<button data-job="${j.key}" class="${state.jobType===j.key?'active':''}">${j.label}</button>`).join('')}
        </div>
      </div>
    </div>

    <div class="dashboard">
      <div>
        <div class="stats">
          <div class="stat"><div class="num">${summary.total.toFixed(1)}</div><div class="label">総合加重点 / ${summary.max}</div></div>
          <div class="stat"><div class="num">${(summary.rate*100).toFixed(1)}%</div><div class="label">達成率</div></div>
          <div class="stat"><div class="num flag">${summary.flags}</div><div class="label">🚩 赤旗件数</div></div>
        </div>
        <div class="judgment ${summary.judgment}">${summary.judgmentLabel}</div>
        <div class="progress-wrap" style="margin-top:14px;">
          <div class="progress-track"><div class="progress-fill" style="width:${Math.min(summary.rate*100,100)}%"></div></div>
          <div class="progress-labels"><span>0%</span><span>65% 条件付き</span><span>80% 採用</span><span>100%</span></div>
        </div>
      </div>
      <div class="radar-box" id="radarBox">${renderRadarInner()}</div>
    </div>

    ${catHtml}

    <p class="footer-note">${jobLabel(state.jobType)} 向け評価項目：${items.length}問 ／ 判定基準：達成率80%以上で◎採用、65〜79%で△条件付き採用、65%未満で✕見送り</p>
  `;

  bindEvents();
}

function renderRadarInner(){
  const vals = radarValues(); // 0-5 scale
  const cx=85, cy=85, r=62;
  const n = RADAR_AXES.length;
  const pts = vals.map((v,i)=>{
    const angle = -Math.PI/2 + i*(2*Math.PI/n);
    const rad = (v/5)*r;
    return [cx+rad*Math.cos(angle), cy+rad*Math.sin(angle)];
  });
  const gridPts = (frac)=> RADAR_AXES.map((_,i)=>{
    const angle = -Math.PI/2 + i*(2*Math.PI/n);
    return [cx+frac*r*Math.cos(angle), cy+frac*r*Math.sin(angle)];
  });
  const polygon = (arr)=>arr.map(p=>p.join(',')).join(' ');
  const labelPts = RADAR_AXES.map((label,i)=>{
    const angle = -Math.PI/2 + i*(2*Math.PI/n);
    const rad = r+16;
    return {x:cx+rad*Math.cos(angle), y:cy+rad*Math.sin(angle), label:label.replace(/[①②③④⑤⑥⑦⑧⑨]/g,'')};
  });
  let grids='';
  [0.33,0.66,1].forEach(f=>{ grids += `<polygon points="${polygon(gridPts(f))}" fill="none" stroke="rgba(241,236,224,.18)" stroke-width="1"/>`; });
  let spokes='';
  gridPts(1).forEach(p=>{ spokes += `<line x1="${cx}" y1="${cy}" x2="${p[0]}" y2="${p[1]}" stroke="rgba(241,236,224,.18)" stroke-width="1"/>`; });
  let labels='';
  labelPts.forEach(p=>{ labels += `<text x="${p.x}" y="${p.y}" font-size="8.5" fill="#b8c7cc" text-anchor="middle" dominant-baseline="middle">${escapeHtml(p.label)}</text>`; });

  return `<svg viewBox="0 0 170 170">
      ${grids}${spokes}
      <polygon points="${polygon(pts)}" fill="rgba(143,191,168,.35)" stroke="#8fbfa8" stroke-width="2"/>
      ${labels}
    </svg>
    <div class="radar-caption">5軸コンピテンシー平均</div>`;
}

function renderQuestion(it, allItems){
  const sc = getScore(it.id);
  const avg = average(sc.s1, sc.s2);
  const weighted = avg!==null ? (avg*it.weight).toFixed(1) : '—';
  const isFlag = avg!==null && avg<=2;
  const related = relatedFor(it.id, allItems || currentItems());
  return `
  <div class="qcard ${isFlag?'flagged':''}" data-id="${it.id}">
    <div class="qtop">
      <div>
        <div class="sub">${escapeHtml(it.sub||'')}</div>
        <div class="question">${escapeHtml(it.question)}</div>
      </div>
      <div style="display:flex; align-items:center;">
        <span class="weight-badge">重要度 ${it.weight}</span>
        ${isFlag?'<span class="flag-badge">🚩 赤旗</span>':''}
      </div>
    </div>
    <details class="example-toggle">
      <summary>回答例を見る</summary>
      <div class="example-body">
        <div class="good"><b>✅ 良い回答例</b>${escapeHtml(it.good)}</div>
        <div class="bad"><b>🚫 注意すべき回答</b>${escapeHtml(it.bad)}</div>
      </div>
    </details>
    ${related.length>0 ? `
    <details class="link-hint">
      <summary>🔗 一貫性チェック（関連する設問あり）</summary>
      <div class="link-hint-body">
        ${related.map(r=>`<p><b>${escapeHtml(r.note)}</b><br>この設問は「${r.related.map(x=>escapeHtml(x.sub)).join('」「')}」（${escapeHtml(r.related[0].category)}）とも関連しています。回答内容に一貫性があるか確認してみましょう。</p>`).join('')}
      </div>
    </details>` : ''}
    <div class="score-row">
      <div class="score-group">
        <label>面接官①</label>
        <div class="score-buttons" data-role="s1">
          ${[1,2,3,4,5].map(n=>`<button data-val="${n}" class="${sc.s1===n?'sel':''}">${n}</button>`).join('')}
        </div>
      </div>
      <div class="score-group">
        <label>面接官②</label>
        <div class="score-buttons" data-role="s2">
          ${[1,2,3,4,5].map(n=>`<button data-val="${n}" class="${sc.s2===n?'sel':''}">${n}</button>`).join('')}
        </div>
      </div>
      <div class="calc-group"><div class="val">${avg!==null?avg.toFixed(1):'—'}</div><div class="lbl">平均点</div></div>
      <div class="calc-group"><div class="val">${weighted}</div><div class="lbl">加重点</div></div>
    </div>
    <div class="comment-wrap">
      <label>コメント</label>
      <textarea data-role="comment" placeholder="回答の要点・気になった点など">${escapeHtml(sc.comment||'')}</textarea>
    </div>
  </div>`;
}

// ============ Events ============
function bindEvents(){
  document.getElementById('f-name').addEventListener('input', e=>{ state.name = e.target.value; });
  document.getElementById('f-date').addEventListener('input', e=>{ state.date = e.target.value; });
  document.getElementById('f-int1').addEventListener('input', e=>{ state.interviewer1 = e.target.value; });
  document.getElementById('f-int2').addEventListener('input', e=>{ state.interviewer2 = e.target.value; });

  document.getElementById('jobtype-seg').addEventListener('click', e=>{
    const btn = e.target.closest('button[data-job]');
    if(!btn) return;
    state.jobType = btn.dataset.job;
    render();
  });

  document.querySelectorAll('.qcard').forEach(card=>{
    const id = card.dataset.id;
    card.querySelectorAll('.score-buttons').forEach(group=>{
      const role = group.dataset.role;
      group.addEventListener('click', e=>{
        const btn = e.target.closest('button[data-val]');
        if(!btn) return;
        const val = parseInt(btn.dataset.val,10);
        const sc = getScore(id);
        sc[role] = (sc[role]===val) ? null : val; // toggle off if clicked again
        rerenderCard(id);
        updateDashboardOnly();
      });
    });
    const ta = card.querySelector('textarea[data-role="comment"]');
    ta.addEventListener('input', e=>{
      getScore(id).comment = e.target.value;
    });
  });

  document.getElementById('btnNew').addEventListener('click', ()=>{
    if(confirm('現在の入力内容をクリアして新規作成しますか？')) newEvaluation();
  });
  document.getElementById('btnSave').addEventListener('click', saveEvaluation);
  document.getElementById('btnList').addEventListener('click', openDrawer);
  document.getElementById('btnCopy').addEventListener('click', copySummary);
}

function rerenderCard(id){
  const items = currentItems();
  const it = items.find(x=>x.id===id);
  if(!it) return;
  const card = document.querySelector(`.qcard[data-id="${id}"]`);
  if(!card) return;
  card.outerHTML = renderQuestion(it, items);
  const newCard = document.querySelector(`.qcard[data-id="${id}"]`);
  newCard.querySelectorAll('.score-buttons').forEach(group=>{
    const role = group.dataset.role;
    group.addEventListener('click', e=>{
      const btn = e.target.closest('button[data-val]');
      if(!btn) return;
      const val = parseInt(btn.dataset.val,10);
      const sc = getScore(id);
      sc[role] = (sc[role]===val) ? null : val;
      rerenderCard(id);
      updateDashboardOnly();
    });
  });
  newCard.querySelector('textarea[data-role="comment"]').addEventListener('input', e=>{
    getScore(id).comment = e.target.value;
  });
}

function updateDashboardOnly(){
  const summary = computeSummary();
  document.querySelectorAll('.stat .num')[0].textContent = summary.total.toFixed(1);
  document.querySelectorAll('.stat .label')[0].textContent = `総合加重点 / ${summary.max}`;
  document.querySelectorAll('.stat .num')[1].textContent = (summary.rate*100).toFixed(1)+'%';
  document.querySelectorAll('.stat .num.flag')[0].textContent = summary.flags;
  const judgEl = document.querySelector('.judgment');
  judgEl.className = 'judgment '+summary.judgment;
  judgEl.textContent = summary.judgmentLabel;
  document.querySelector('.progress-fill').style.width = Math.min(summary.rate*100,100)+'%';
  const radarBox = document.getElementById('radarBox');
  if(radarBox) radarBox.innerHTML = renderRadarInner();
}

// ============ Drawer ============
async function openDrawer(){
  document.getElementById('drawerOverlay').classList.add('open');
  document.getElementById('drawer').classList.add('open');
  const body = document.getElementById('drawerBody');
  body.innerHTML = '<p class="empty-note">読み込み中…</p>';
  const idx = await loadIndex();
  if(idx.length===0){
    body.innerHTML = '<p class="empty-note">保存された評価はまだありません</p>';
    return;
  }
  const clearAllHtml = `<div style="text-align:right; margin-bottom:10px;">
    <button class="danger" id="btnClearAll" style="font-size:11.5px; padding:5px 10px; border-radius:999px; border:1px solid var(--red-soft); background:#fdfcf9; color:var(--red); cursor:pointer;">すべて削除</button>
  </div>`;
  body.innerHTML = clearAllHtml + idx.map(it=>`
    <div class="saved-item" data-id="${it.id}">
      <div class="name">${escapeHtml(it.name||'（氏名未入力）')}</div>
      <div class="meta">${escapeHtml(jobLabel(it.jobType))} ／ 面接日: ${escapeHtml(it.date||'—')}</div>
      <div class="row">
        <button class="primary" data-action="open">開く</button>
        <button data-action="dup">複製</button>
        <button class="danger" data-action="del">削除</button>
      </div>
    </div>
  `).join('');
  document.getElementById('btnClearAll')?.addEventListener('click', async ()=>{
    if(confirm('保存されているすべての評価を削除しますか？この操作は元に戻せません。')){
      await deleteAllEvaluations();
      openDrawer();
      showToast('すべて削除しました');
    }
  });
  body.querySelectorAll('.saved-item').forEach(el=>{
    const id = el.dataset.id;
    el.querySelector('[data-action="open"]').addEventListener('click', async ()=>{
      const rec = await loadEvaluation(id);
      if(rec){ state = rec; closeDrawer(); render(); showToast('読み込みました'); }
    });
    el.querySelector('[data-action="dup"]').addEventListener('click', async ()=>{
      const rec = await loadEvaluation(id);
      if(rec){
        state = {...rec, id:null, name: rec.name+'（コピー）'};
        closeDrawer(); render(); showToast('複製しました。保存すると新規に登録されます');
      }
    });
    el.querySelector('[data-action="del"]').addEventListener('click', async ()=>{
      if(confirm('この評価を削除しますか？')){
        await deleteEvaluation(id);
        openDrawer();
      }
    });
  });
}
function closeDrawer(){
  document.getElementById('drawerOverlay').classList.remove('open');
  document.getElementById('drawer').classList.remove('open');
}
document.getElementById('drawerOverlay')?.addEventListener('click', closeDrawer);

// ============ Copy summary ============
function copySummary(){
  const summary = computeSummary();
  const items = currentItems();
  const flaggedItems = items.filter(it=>{
    const sc=getScore(it.id); const avg=average(sc.s1,sc.s2); return avg!==null && avg<=2;
  });
  let text = `【採用面接評価サマリー】\n`;
  text += `候補者氏名：${state.name||'—'}\n`;
  text += `面接日：${state.date||'—'}\n`;
  text += `応募職種：${jobLabel(state.jobType)}\n`;
  text += `面接官：${state.interviewer1||'—'} / ${state.interviewer2||'—'}\n\n`;
  text += `総合加重点：${summary.total.toFixed(1)} / ${summary.max}\n`;
  text += `達成率：${(summary.rate*100).toFixed(1)}%\n`;
  text += `採用判定：${summary.judgmentLabel}\n`;
  text += `赤旗件数：${summary.flags}\n`;
  if(flaggedItems.length){
    text += `\n【赤旗項目】\n`;
    flaggedItems.forEach(it=>{ text += `・${it.category.replace(/\n/g,'')} / ${it.sub}\n`; });
  }
  const comments = items.filter(it=>getScore(it.id).comment && getScore(it.id).comment.trim());
  if(comments.length){
    text += `\n【コメント】\n`;
    comments.forEach(it=>{ text += `・${it.sub}：${getScore(it.id).comment.trim()}\n`; });
  }
  navigator.clipboard.writeText(text).then(()=>{
    showToast('サマリーをコピーしました');
  }).catch(()=>{
    showToast('コピーに失敗しました');
  });
}

// ============ Utils ============
function escapeHtml(str){
  if(str===undefined || str===null) return '';
  return String(str).replace(/[&<>"']/g, c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
}
function escapeAttr(str){ return escapeHtml(str); }

// ============ Init ============
render();

</script>
</body>
</html>
