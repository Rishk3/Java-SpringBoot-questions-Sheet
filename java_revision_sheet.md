<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Java Interview Revision Sheet</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;700&family=Syne:wght@400;600;700;800&display=swap');

  :root {
    --bg: #0a0e1a;
    --surface: #111827;
    --surface2: #1a2235;
    --accent: #1A4E9E;
    --accent2: #3b82f6;
    --accent3: #60a5fa;
    --green: #10b981;
    --yellow: #f59e0b;
    --red: #ef4444;
    --text: #e2e8f0;
    --muted: #94a3b8;
    --border: #1e3a5f;
    --code-bg: #0d1929;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    padding: 40px 24px;
  }

  .header {
    text-align: center;
    margin-bottom: 48px;
    position: relative;
  }

  .header::before {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 400px;
    height: 400px;
    background: radial-gradient(circle, rgba(26,78,158,0.15) 0%, transparent 70%);
    pointer-events: none;
  }

  .badge {
    display: inline-block;
    background: var(--accent);
    color: #fff;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    padding: 6px 16px;
    border-radius: 2px;
    margin-bottom: 16px;
  }

  h1 {
    font-size: 42px;
    font-weight: 800;
    letter-spacing: -1px;
    background: linear-gradient(135deg, #fff 0%, var(--accent3) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 8px;
  }

  .subtitle {
    color: var(--muted);
    font-size: 14px;
    letter-spacing: 1px;
  }

  .toc {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    justify-content: center;
    margin-bottom: 48px;
  }

  .toc-item {
    background: var(--surface);
    border: 1px solid var(--border);
    color: var(--accent3);
    padding: 6px 14px;
    border-radius: 100px;
    font-size: 12px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s;
    font-family: 'JetBrains Mono', monospace;
  }

  .toc-item:hover {
    background: var(--accent);
    color: #fff;
    border-color: var(--accent);
  }

  .section {
    max-width: 900px;
    margin: 0 auto 40px;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 20px;
    padding-bottom: 12px;
    border-bottom: 1px solid var(--border);
  }

  .section-num {
    background: var(--accent);
    color: #fff;
    width: 32px;
    height: 32px;
    border-radius: 6px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 13px;
    font-weight: 700;
    font-family: 'JetBrains Mono', monospace;
    flex-shrink: 0;
  }

  .section-title {
    font-size: 20px;
    font-weight: 700;
    color: #fff;
  }

  .section-tag {
    margin-left: auto;
    font-size: 11px;
    color: var(--green);
    font-family: 'JetBrains Mono', monospace;
    background: rgba(16,185,129,0.1);
    padding: 3px 10px;
    border-radius: 100px;
    border: 1px solid rgba(16,185,129,0.3);
  }

  .card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px;
    margin-bottom: 12px;
    position: relative;
    overflow: hidden;
  }

  .card::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 3px;
    background: var(--accent2);
    border-radius: 3px 0 0 3px;
  }

  .card.green::before { background: var(--green); }
  .card.yellow::before { background: var(--yellow); }
  .card.red::before { background: var(--red); }

  .card-title {
    font-size: 13px;
    font-weight: 700;
    color: var(--accent3);
    font-family: 'JetBrains Mono', monospace;
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .card-title .icon { font-size: 14px; }

  .card p, .card li {
    font-size: 13.5px;
    color: var(--text);
    line-height: 1.7;
  }

  .card ul { padding-left: 18px; }
  .card li { margin-bottom: 4px; }

  .highlight { color: var(--accent3); font-weight: 600; }
  .green-text { color: var(--green); font-weight: 600; }
  .yellow-text { color: var(--yellow); font-weight: 600; }
  .red-text { color: var(--red); font-weight: 600; }

  code {
    font-family: 'JetBrains Mono', monospace;
    background: var(--code-bg);
    color: var(--accent3);
    padding: 1px 6px;
    border-radius: 4px;
    font-size: 12px;
    border: 1px solid var(--border);
  }

  pre {
    background: var(--code-bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 16px;
    margin-top: 10px;
    overflow-x: auto;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    line-height: 1.7;
    color: #a5d6ff;
  }

  pre .comment { color: #4a6b8a; }
  pre .keyword { color: #ff79c6; }
  pre .string { color: #f1fa8c; }
  pre .good { color: var(--green); }
  pre .bad { color: var(--red); }

  .table-wrap { overflow-x: auto; margin-top: 10px; }

  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 13px;
  }

  th {
    background: var(--surface2);
    color: var(--accent3);
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    letter-spacing: 1px;
    text-transform: uppercase;
    padding: 10px 14px;
    text-align: left;
    border-bottom: 1px solid var(--border);
  }

  td {
    padding: 9px 14px;
    border-bottom: 1px solid rgba(30,58,95,0.5);
    color: var(--text);
    vertical-align: top;
  }

  tr:last-child td { border-bottom: none; }
  tr:hover td { background: rgba(26,78,158,0.08); }

  .gotcha {
    background: rgba(239,68,68,0.08);
    border: 1px solid rgba(239,68,68,0.25);
    border-radius: 8px;
    padding: 14px 16px;
    margin-top: 10px;
    font-size: 13px;
  }

  .gotcha-title {
    color: var(--red);
    font-weight: 700;
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 6px;
    font-family: 'JetBrains Mono', monospace;
  }

  .tip {
    background: rgba(16,185,129,0.08);
    border: 1px solid rgba(16,185,129,0.25);
    border-radius: 8px;
    padding: 14px 16px;
    margin-top: 10px;
    font-size: 13px;
  }

  .tip-title {
    color: var(--green);
    font-weight: 700;
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 6px;
    font-family: 'JetBrains Mono', monospace;
  }

  .grid2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  @media (max-width: 640px) {
    .grid2 { grid-template-columns: 1fr; }
    h1 { font-size: 28px; }
  }

  .progress-bar {
    max-width: 900px;
    margin: 0 auto 40px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 20px;
    display: flex;
    align-items: center;
    gap: 16px;
  }

  .progress-label {
    font-size: 12px;
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
    white-space: nowrap;
  }

  .progress-track {
    flex: 1;
    height: 6px;
    background: var(--surface2);
    border-radius: 100px;
    overflow: hidden;
  }

  .progress-fill {
    height: 100%;
    width: 18%;
    background: linear-gradient(90deg, var(--accent), var(--accent3));
    border-radius: 100px;
    animation: fillAnim 1s ease forwards;
  }

  @keyframes fillAnim {
    from { width: 0; }
    to { width: 18%; }
  }

  .progress-pct {
    font-size: 13px;
    font-weight: 700;
    color: var(--accent3);
    font-family: 'JetBrains Mono', monospace;
  }
</style>
</head>
<body>

<div class="header">
  <div class="badge">JP Morgan Interview Prep</div>
  <h1>Java Revision Sheet</h1>
  <p class="subtitle">Session 1 — Core Java Internals · HashMap · String · Concurrency</p>
</div>

<div class="progress-bar">
  <span class="progress-label">ROADMAP PROGRESS</span>
  <div class="progress-track"><div class="progress-fill"></div></div>
  <span class="progress-pct">~18% Core Java</span>
</div>

<div class="toc">
  <span class="toc-item">01 · HashMap</span>
  <span class="toc-item">02 · ConcurrentHashMap</span>
  <span class="toc-item">03 · equals/hashCode</span>
  <span class="toc-item">04 · String Pool</span>
  <span class="toc-item">05 · Immutability</span>
  <span class="toc-item">06 · StringBuilder</span>
</div>

<!-- SECTION 1 -->
<div class="section" id="hashmap">
  <div class="section-header">
    <div class="section-num">01</div>
    <div class="section-title">HashMap Internals</div>
    <div class="section-tag">✅ Covered</div>
  </div>

  <div class="card">
    <div class="card-title"><span class="icon">🗂</span> Internal Structure</div>
    <ul>
      <li>Backed by <code>Node&lt;K,V&gt;[]</code> array — called <span class="highlight">buckets</span></li>
      <li>Default initial capacity: <span class="highlight">16</span>, load factor: <span class="highlight">0.75</span></li>
      <li>Index = <code>(n-1) & hash</code> where <code>hash = hashCode() ^ (hashCode() >>> 16)</code></li>
      <li>Collision → <span class="highlight">linked list</span> chaining in same bucket</li>
    </ul>
  </div>

  <div class="grid2">
    <div class="card green">
      <div class="card-title"><span class="icon">🌳</span> Treeification Thresholds</div>
      <ul>
        <li>Bucket size <span class="green-text">&gt; 8</span> AND total buckets <span class="green-text">≥ 64</span> → converts to <strong>Red-Black Tree</strong></li>
        <li>If bucket &gt; 8 but total &lt; 64 → <strong>resize instead</strong></li>
        <li>Tree → List again if bucket size drops <span class="green-text">&lt; 6</span></li>
      </ul>
    </div>
    <div class="card yellow">
      <div class="card-title"><span class="icon">📐</span> Resizing</div>
      <ul>
        <li>Triggers at <span class="yellow-text">75%</span> capacity (load factor)</li>
        <li>New array size = <span class="yellow-text">old × 2</span> (always power of 2)</li>
        <li>No full rehash — new index = <span class="yellow-text">same</span> OR <span class="yellow-text">old + old capacity</span></li>
        <li>HashCode NOT recomputed</li>
      </ul>
    </div>
  </div>

  <div class="gotcha">
    <div class="gotcha-title">⚠ Java 7 Infinite Loop Bug</div>
    Concurrent resize by two threads causes <strong>cyclic linked list</strong>: A → B → A. Any <code>get()</code> on that bucket loops forever → <strong>100% CPU spike</strong>. Fixed in Java 8 by maintaining insertion order (head/tail pointers) during rehash.
  </div>

  <div class="tip">
    <div class="tip-title">💡 Perturbation — Why not use hashCode() directly?</div>
    <code>hash = h ^ (h >>> 16)</code> — spreads higher bits into lower bits. Prevents clustering when capacity is small (only lower bits of index matter with small n).
  </div>
</div>

<!-- SECTION 2 -->
<div class="section" id="chm">
  <div class="section-header">
    <div class="section-num">02</div>
    <div class="section-title">ConcurrentHashMap Internals</div>
    <div class="section-tag">✅ Covered</div>
  </div>

  <div class="card">
    <div class="table-wrap">
      <table>
        <tr><th>Operation</th><th>Mechanism</th><th>Lock?</th></tr>
        <tr><td><code>get()</code></td><td><code>volatile</code> read</td><td class="green-text">Lock-free</td></tr>
        <tr><td>Insert into <strong>empty</strong> bucket</td><td>CAS (Compare-And-Swap)</td><td class="green-text">Lock-free</td></tr>
        <tr><td>Insert into <strong>non-empty</strong> bucket</td><td><code>synchronized</code> on first node</td><td class="yellow-text">Fine-grained lock</td></tr>
        <tr><td>Tree conversion</td><td><code>synchronized</code> on bucket head</td><td class="yellow-text">Fine-grained lock</td></tr>
        <tr><td>Size tracking</td><td><code>baseCount</code> + <code>CounterCell[]</code> (LongAdder)</td><td class="green-text">Lock-free</td></tr>
      </table>
    </div>
  </div>

  <div class="card red">
    <div class="card-title"><span class="icon">🔴</span> Check-Then-Act Race Condition</div>
    <pre><span class="comment">// BROKEN — two threads can both pass the if-check</span>
<span class="bad">if (!map.containsKey(key)) {
    map.put(key, expensiveCompute(key)); // computed twice!
}</span>

<span class="comment">// CORRECT — atomic operation</span>
<span class="good">map.computeIfAbsent(key, k -> expensiveCompute(k));</span></pre>
    <div style="margin-top:10px; font-size:13px;">Also remember: <code>putIfAbsent</code>, <code>compute</code>, <code>merge</code> for atomic compound ops.</div>
  </div>

  <div class="card">
    <div class="card-title"><span class="icon">⚖️</span> Thread-Safe Map Options</div>
    <div class="table-wrap">
      <table>
        <tr><th>Option</th><th>Locking</th><th>Use When</th></tr>
        <tr><td><code>Collections.synchronizedMap</code></td><td>Single global lock</td><td>Low concurrency, simple use</td></tr>
        <tr><td><code>ConcurrentHashMap</code></td><td>Fine-grained / CAS</td><td>High concurrency, production</td></tr>
        <tr><td><code>synchronized</code> block</td><td>Manual control</td><td>Custom compound operations</td></tr>
      </table>
    </div>
  </div>
</div>

<!-- SECTION 3 -->
<div class="section" id="equals">
  <div class="section-header">
    <div class="section-num">03</div>
    <div class="section-title">equals() & hashCode() Contract</div>
    <div class="section-tag">✅ Covered</div>
  </div>

  <div class="card">
    <div class="card-title"><span class="icon">📜</span> The Contract</div>
    <ul>
      <li>If <code>a.equals(b)</code> → <code>a.hashCode() == b.hashCode()</code> <span class="red-text">MUST</span> be true</li>
      <li>Reverse not required — same hashCode doesn't mean equal</li>
      <li>Violation = broken behavior in ALL hash-based collections</li>
    </ul>
  </div>

  <div class="card">
    <div class="table-wrap">
      <table>
        <tr><th>Scenario</th><th>Functionally Correct?</th><th>Performance</th></tr>
        <tr><td>Both overridden correctly</td><td class="green-text">✅ Yes</td><td class="green-text">O(1)</td></tr>
        <tr><td>Only <code>equals</code> overridden</td><td class="red-text">❌ No</td><td>—</td></tr>
        <tr><td>Only <code>hashCode</code> (constant 42)</td><td class="yellow-text">✅ Yes</td><td class="red-text">O(N) — all in one bucket</td></tr>
        <tr><td>Neither overridden</td><td class="red-text">❌ No</td><td>—</td></tr>
      </table>
    </div>
  </div>
</div>

<!-- SECTION 4 -->
<div class="section" id="string">
  <div class="section-header">
    <div class="section-num">04</div>
    <div class="section-title">String Pool & Interning</div>
    <div class="section-tag">✅ Covered</div>
  </div>

  <div class="grid2">
    <div class="card">
      <div class="card-title"><span class="icon">🏊</span> String Pool</div>
      <ul>
        <li>Lives in <span class="highlight">Heap</span> (moved from PermGen in Java 8)</li>
        <li><code>"hello"</code> → checks pool → reuses if exists</li>
        <li><code>new String("hello")</code> → always new heap object</li>
        <li><code>==</code> compares references, <code>equals()</code> compares content</li>
      </ul>
    </div>
    <div class="card green">
      <div class="card-title"><span class="icon">♻️</span> intern()</div>
      <ul>
        <li>Moves heap string → pool (or returns existing pool ref)</li>
        <li>Use when processing <span class="green-text">millions of repeated strings</span></li>
        <li>Real case: country codes, currency codes, status codes from Kafka streams</li>
      </ul>
    </div>
  </div>

  <div class="card red">
    <div class="card-title"><span class="icon">🎯</span> Compiler Trick — Must Know</div>
    <pre><span class="keyword">String</span> a = <span class="string">"hello"</span>;
<span class="keyword">String</span> b = <span class="string">"hel"</span> + <span class="string">"lo"</span>;   <span class="comment">// compile-time constant folding → same pool ref</span>
<span class="keyword">String</span> c = <span class="string">"hel"</span>;
<span class="keyword">String</span> d = c + <span class="string">"lo"</span>;      <span class="comment">// runtime StringBuilder → new heap object</span>

a == b  <span class="good">// true  — compiler resolves at compile time</span>
a == d  <span class="bad">// false — c is a variable, resolved at runtime</span></pre>
  </div>
</div>

<!-- SECTION 5 -->
<div class="section" id="immutability">
  <div class="section-header">
    <div class="section-num">05</div>
    <div class="section-title">String Immutability</div>
    <div class="section-tag">✅ Covered</div>
  </div>

  <div class="card">
    <div class="card-title"><span class="icon">🔒</span> Three Reasons</div>
    <ul>
      <li><span class="highlight">Security</span> — DB URLs, file paths, class loading paths can't be changed after validation. Prevents post-validation attacks.</li>
      <li><span class="highlight">String Pool / Performance</span> — Safe reference sharing across threads and variables without copying.</li>
      <li><span class="highlight">HashCode Caching</span> — Cached after first call. Makes String a perfect HashMap key — O(1) hashcode after first computation. <span class="red-text">(Most candidates miss this!)</span></li>
    </ul>
  </div>

  <div class="card yellow">
    <div class="card-title"><span class="icon">📦</span> Object Count — s = s + " world"</div>
    <ul>
      <li><code>"hello"</code> — already in string pool</li>
      <li><code>StringBuilder</code> — created internally for concatenation</li>
      <li><code>"hello world"</code> — new heap object via <code>StringBuilder.toString()</code></li>
    </ul>
    <p style="margin-top:8px; color: var(--muted);">Total: <span class="yellow-text">3 objects</span>. <code>s</code> now points to heap object, not pool.</p>
  </div>
</div>

<!-- SECTION 6 -->
<div class="section" id="sb">
  <div class="section-header">
    <div class="section-num">06</div>
    <div class="section-title">StringBuilder vs StringBuffer</div>
    <div class="section-tag">✅ Covered</div>
  </div>

  <div class="grid2">
    <div class="card">
      <div class="card-title"><span class="icon">⚡</span> StringBuilder</div>
      <ul>
        <li><span class="green-text">Not synchronized</span> — faster</li>
        <li>Use in single-threaded context or method-local scope</li>
        <li>Stack-confined = inherently thread-safe</li>
        <li><span class="highlight">Preferred choice in 2024</span></li>
      </ul>
    </div>
    <div class="card">
      <div class="card-title"><span class="icon">🔒</span> StringBuffer</div>
      <ul>
        <li><span class="yellow-text">Synchronized</span> — thread-safe but slower</li>
        <li>Rarely used in modern code</li>
        <li>Senior answer: <span class="red-text">"Almost never use it"</span> — redesign instead</li>
      </ul>
    </div>
  </div>

  <div class="card red">
    <div class="card-title"><span class="icon">🐌</span> Loop Concatenation — Classic Mistake</div>
    <pre><span class="bad">// O(n²) — new StringBuilder + new String every iteration
String str = "";
for (int i = 0; i < 10000; i++) {
    str = str + newChunk;
}</span>

<span class="good">// O(n) — one StringBuilder, append in place
StringBuilder sb = new StringBuilder();
for (int i = 0; i < 10000; i++) {
    sb.append(newChunk);
}
String result = sb.toString();</span></pre>
  </div>
</div>

<div style="max-width:900px; margin: 0 auto 60px; text-align:center; color: var(--muted); font-size: 12px; font-family: 'JetBrains Mono', monospace; border-top: 1px solid var(--border); padding-top: 24px;">
  SESSION 1 COMPLETE · NEXT → OOP Internals · Abstract Class vs Interface · Polymorphism
</div>

</body>
</html>
