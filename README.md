<!DOCTYPE html>

<html lang="bn">

<head>

  <meta charset="UTF-8" />

  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>পারিশা ফিলিং স্টেশন — ডিজিটাল ক্যাশ মেমো সিস্টেম</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">

  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

  <link href="https://fonts.googleapis.com/css2?family=Hind+Siliguri:wght@400;500;600;700&family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">

  <style>

    :root {

      --primary: #0f766e;

      --primary-dark: #115e59;

      --accent: #16a34a;

      --due: #dc2626;

      --bg: #f1f5f9;

      --card: #ffffff;

      --text: #0f172a;

      --muted: #475569;

      --border: #cbd5e1;

      --print-width: 80mm;

      --print-font-size: 12px;

    }


    * {

      box-sizing: border-box;

      margin: 0;

      padding: 0;

    }


    body {

      font-family: 'Hind Siliguri', 'Inter', sans-serif;

      background: var(--bg);

      color: var(--text);

      line-height: 1.45;

    }


    .topbar {

      background: var(--card);

      border-bottom: 1px solid var(--border);

      padding: 12px 20px;

      display: flex;

      flex-wrap: wrap;

      gap: 12px;

      align-items: center;

      justify-content: space-between;

      position: sticky;

      top: 0;

      z-index: 30;

    }


    .brand-title {

      font-size: 18px;

      font-weight: 700;

      color: var(--primary-dark);

      display: flex;

      align-items: center;

      gap: 8px;

    }


    .badge-role {

      font-size: 12px;

      padding: 3px 10px;

      border-radius: 999px;

      background: #e2e8f0;

      color: #0f172a;

      font-weight: 600;

    }


    .controls {

      display: flex;

      flex-wrap: wrap;

      gap: 8px;

      align-items: center;

    }


    select, input, button, textarea {

      font-family: 'Hind Siliguri', 'Inter', sans-serif;

      font-size: 14px;

    }


    select, input[type="text"], input[type="number"], input[type="password"], textarea {

      border: 1px solid var(--border);

      border-radius: 8px;

      padding: 8px 10px;

      background: #fff;

      color: var(--text);

    }


    button {

      border: none;

      border-radius: 8px;

      padding: 8px 14px;

      font-weight: 600;

      cursor: pointer;

      transition: 0.15s ease;

    }


    button:hover {

      opacity: 0.92;

    }


    .btn-primary {

      background: var(--primary);

      color: #fff;

    }


    .btn-success {

      background: var(--accent);

      color: #fff;

    }


    .btn-danger {

      background: var(--due);

      color: #fff;

    }


    .btn-secondary {

      background: #e2e8f0;

      color: #0f172a;

    }


    .btn-sm {

      padding: 5px 10px;

      font-size: 12px;

    }


    .login-overlay {

      position: fixed;

      inset: 0;

      background: rgba(15, 23, 42, 0.72);

      display: flex;

      align-items: center;

      justify-content: center;

      z-index: 100;

      padding: 16px;

    }


    .login-card {

      background: #fff;

      width: 100%;

      max-width: 440px;

      border-radius: 14px;

      padding: 24px;

      box-shadow: 0 20px 40px rgba(0,0,0,0.2);

    }


    .login-card h2 {

      margin-bottom: 6px;

      color: var(--primary-dark);

    }


    .login-card p {

      font-size: 13px;

      color: var(--muted);

      margin-bottom: 16px;

    }


    .field-group {

      margin-bottom: 12px;

    }


    .field-group label {

      display: block;

      font-size: 13px;

      font-weight: 600;

      margin-bottom: 4px;

    }


    .field-group input, .field-group select, .field-group textarea {

      width: 100%;

    }


    .app-container {

      max-width: 1380px;

      margin: 18px auto;

      padding: 0 16px 40px;

    }


    .nav-tabs {

      display: flex;

      flex-wrap: wrap;

      gap: 8px;

      margin-bottom: 16px;

    }


    .nav-tab {

      background: #fff;

      color: var(--text);

      border: 1px solid var(--border);

      padding: 9px 16px;

      border-radius: 10px;

      font-weight: 600;

    }


    .nav-tab.active {

      background: var(--primary);

      color: #fff;

      border-color: var(--primary);

    }


    .tab-panel {

      display: none;

    }


    .tab-panel.active {

      display: block;

    }


    .grid-2 {

      display: grid;

      grid-template-columns: 1.1fr 0.9fr;

      gap: 18px;

      align-items: start;

    }


    @media (max-width: 960px) {

      .grid-2 {

        grid-template-columns: 1fr;

      }

    }


    .card {

      background: var(--card);

      border: 1px solid var(--border);

      border-radius: 12px;

      padding: 18px;

      box-shadow: 0 2px 8px rgba(15, 23, 42, 0.04);

      margin-bottom: 16px;

    }


    .card-title {

      font-size: 16px;

      font-weight: 700;

      margin-bottom: 12px;

      padding-bottom: 8px;

      border-bottom: 1px solid #e2e8f0;

      display: flex;

      align-items: center;

      justify-content: space-between;

    }


    .form-row {

      display: grid;

      grid-template-columns: repeat(2, 1fr);

      gap: 10px;

    }


    @media (max-width: 600px) {

      .form-row {

        grid-template-columns: 1fr;

      }

    }


    .items-box {

      border: 1px solid #e2e8f0;

      border-radius: 10px;

      padding: 12px;

      background: #f8fafc;

      margin-bottom: 12px;

    }


    .item-row {

      display: grid;

      grid-template-columns: 2fr 1fr 1fr 1fr auto;

      gap: 8px;

      margin-bottom: 8px;

      align-items: center;

    }


    @media (max-width: 680px) {

      .item-row {

        grid-template-columns: 1fr 1fr;

      }

    }


    .status-pill {

      display: inline-block;

      padding: 2px 9px;

      border-radius: 999px;

      font-size: 12px;

      font-weight: 700;

    }


    .status-paid {

      background: #dcfce7;

      color: #166534;

      border: 1px solid #86efac;

    }


    .status-due {

      background: #fee2e2;

      color: #991b1b;

      border: 1px solid #fca5a5;

    }


    .memo-preview-wrap {

      display: flex;

      justify-content: center;

      background: #e2e8f0;

      padding: 16px;

      border-radius: 12px;

      overflow-x: auto;

    }


    .memo-sheet {

      width: 100%;

      max-width: 440px;

      background: #ffffff;

      color: #0f172a;

      padding: 18px 18px 20px;

      border: 1px solid #cbd5e1;

      box-shadow: 0 8px 24px rgba(0,0,0,0.08);

    }


    .memo-sheet.theme-bw {

      filter: grayscale(100%);

      contrast: 120%;

    }


    .memo-sheet.theme-classic {

      border-top: 4px solid #16a34a;

    }


    .memo-sheet.theme-royal {

      border-top: 4px solid #1d4ed8;

    }


    .memo-header {

      text-align: center;

      border-bottom: 2px solid #16a34a;

      padding-bottom: 10px;

      margin-bottom: 10px;

    }


    .memo-sheet.theme-bw .memo-header {

      border-bottom-color: #000000;

    }


    .memo-sheet.theme-royal .memo-header {

      border-bottom-color: #1d4ed8;

    }


    .memo-station-name {

      font-size: 20px;

      font-weight: 700;

      color: #0f172a;

    }


    .memo-dealer-line {

      font-size: 13px;

      font-weight: 600;

      color: #334155;

      margin-top: 2px;

    }


    .memo-type-pill {

      display: inline-block;

      margin: 7px 0 5px;

      padding: 2px 14px;

      border: 1.5px solid #0f172a;

      border-radius: 999px;

      font-size: 12px;

      font-weight: 700;

    }


    .memo-contact-line {

      font-size: 12px;

      font-weight: 600;

      color: #1e293b;

    }


    .memo-slogan {

      font-size: 12px;

      font-weight: 700;

      color: #0f172a;

      margin-top: 4px;

    }


    .memo-meta-box {

      background: #f8fafc;

      border: 1px solid #cbd5e1;

      border-radius: 8px;

      padding: 8px 10px;

      font-size: 12.5px;

      display: grid;

      grid-template-columns: 1fr 1fr;

      gap: 6px 10px;

      margin-bottom: 10px;

    }


    .memo-meta-right {

      text-align: right;

    }


    table.memo-table {

      width: 100%;

      border-collapse: collapse;

      font-size: 12.5px;

      margin-bottom: 10px;

    }


    table.memo-table th {

      background: #f1f5f9;

      border-top: 1.5px solid #0f172a;

      border-bottom: 1.5px solid #0f172a;

      padding: 6px 4px;

      font-weight: 700;

      text-align: left;

    }


    table.memo-table td {

      padding: 6px 4px;

      border-bottom: 1px solid #e2e8f0;

      font-weight: 600;

    }


    .num-right {

      text-align: right !important;

    }


    .memo-payment-section {

      display: flex;

      justify-content: space-between;

      align-items: flex-start;

      gap: 8px;

      margin-bottom: 8px;

      font-size: 12.5px;

    }


    .memo-badge-box {

      display: flex;

      flex-direction: column;

      gap: 4px;

      margin-top: 4px;

    }


    .memo-method-tag {

      display: inline-block;

      border: 1.5px solid #16a34a;

      color: #15803d;

      border-radius: 6px;

      padding: 2px 8px;

      font-weight: 700;

      font-size: 12px;

      width: fit-content;

    }


    .memo-status-tag {

      display: inline-block;

      border: 1.5px solid #16a34a;

      color: #15803d;

      border-radius: 6px;

      padding: 2px 8px;

      font-weight: 700;

      font-size: 12px;

      width: fit-content;

    }


    .memo-status-tag.due {

      border-color: #dc2626;

      color: #b91c1c;

    }


    .memo-totals-right {

      text-align: right;

      font-size: 13px;

    }


    .memo-grand-total {

      font-size: 16px;

      font-weight: 800;

      border-top: 1.5px solid #0f172a;

      border-bottom: 2px double #0f172a;

      padding: 4px 0;

      margin-top: 4px;

    }


    .memo-words-box {

      border: 1.5px solid #334155;

      background: #f8fafc;

      padding: 7px 10px;

      border-radius: 4px;

      font-size: 12px;

      margin: 10px 0;

    }


    .memo-words-bn {

      font-weight: 700;

      color: #0f172a;

    }


    .memo-words-en {

      font-weight: 600;

      color: #1e293b;

      margin-top: 2px;

    }


    .memo-footer {

      border-top: 1.5px dashed #475569;

      padding-top: 8px;

      display: flex;

      justify-content: space-between;

      align-items: flex-end;

      gap: 10px;

      font-size: 11.5px;

    }


    .memo-note {

      font-weight: 700;

      max-width: 66%;

    }


    .memo-sign {

      text-align: center;

      min-width: 90px;

      border-top: 1px solid #0f172a;

      padding-top: 3px;

      font-weight: 700;

    }


    .data-table {

      width: 100%;

      border-collapse: collapse;

      font-size: 13px;

    }


    .data-table th, .data-table td {

      border-bottom: 1px solid #e2e8f0;

      padding: 9px 8px;

      text-align: left;

    }


    .data-table th {

      background: #f8fafc;

      font-weight: 700;

    }


    .summary-strip {

      display: grid;

      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));

      gap: 10px;

      margin-bottom: 14px;

    }


    .stat-box {

      background: #f8fafc;

      border: 1px solid var(--border);

      border-radius: 10px;

      padding: 12px;

    }


    .stat-label {

      font-size: 12px;

      color: var(--muted);

      font-weight: 600;

    }


    .stat-val {

      font-size: 18px;

      font-weight: 800;

      margin-top: 2px;

      color: var(--primary-dark);

    }


    .help-note {

      font-size: 12px;

      color: var(--muted);

      margin-top: 6px;

    }


    @media print {

      body {

        background: #fff !important;

      }

      .topbar, .nav-tabs, .no-print, .login-overlay {

        display: none !important;

      }

      .app-container {

        margin: 0 !important;

        padding: 0 !important;

        max-width: 100% !important;

      }

      .grid-2 {

        display: block !important;

      }

      .memo-preview-wrap {

        background: #fff !important;

        padding: 0 !important;

      }

      .memo-sheet {

        width: var(--print-width) !important;

        max-width: var(--print-width) !important;

        font-size: var(--print-font-size) !important;

        border: none !important;

        box-shadow: none !important;

        padding: 4px !important;

      }

    }

  </style>

</head>

<body>


  <div id="loginModal" class="login-overlay">

    <div class="login-card">

      <h2>ফিলিং স্টেশন লগইন</h2>

      <p>মোবাইল নম্বর অথবা Gmail দিয়ে লগইন করুন। শুধুমাত্র এডমিনের অনুমোদিত ইউজার/এডমিন লগইন করতে পারবেন।</p>

      <div class="field-group">

        <label>মোবাইল নম্বর বা Gmail</label>

        <input type="text" id="loginIdentifier" placeholder="যেমন: 01711000001 বা admin@parisha.com" />

      </div>

      <div class="field-group">

        <label>পাসওয়ার্ড / পিন</label>

        <input type="password" id="loginPassword" placeholder="পাসওয়ার্ড দিন" />

      </div>

      <button class="btn-primary" style="width:100%" onclick="handleLogin()">লগইন করুন</button>

      <div class="help-note">

        <strong>ডেমো ক্রেডেনশিয়াল:</strong><br/>

        এডমিন ১: <code>admin@parisha.com</code> / <code>1234</code><br/>

        এডমিন ২: <code>01711000002</code> / <code>1234</code><br/>

        নজেল ম্যান ১: <code>01811000001</code> / <code>1234</code><br/>

        নজেল ম্যান ২: <code>nozzle2@parisha.com</code> / <code>1234</code>

      </div>

      <div id="loginError" style="color:#dc2626; font-size:13px; margin-top:8px; font-weight:600;"></div>

    </div>

  </div>


  <header class="topbar no-print">

    <div class="brand-title">

      <span id="uiBrandName">পারিশা ফিলিং স্টেশন</span>

      <span id="uiUserBadge" class="badge-role">অতিথি</span>

    </div>

    <div class="controls">

      <select id="langSelect" onchange="changeLanguage(this.value)" title="ভাষা নির্বাচন">

        <option value="bn_en">বাংলা + ইংরেজি (Bilingual)</option>

        <option value="bn">শুধুমাত্র বাংলা (Only Bangla)</option>

        <option value="en">শুধুমাত্র ইংরেজি (Only English)</option>

      </select>


      <select id="themeSelect" onchange="changeTheme(this.value)" title="ডিজাইন থিম">

        <option value="classic">ক্লাসিক সবুজ (Classic Green)</option>

        <option value="bw">হাই-কনট্রাস্ট সাদা-কালো (Pure B&W)</option>

        <option value="royal">রয়্যাল ব্লু (Royal Blue)</option>

      </select>


      <select id="printerSizeSelect" onchange="changePrinterSize(this.value)" title="প্রিন্টার সাইজ">

        <option value="80mm">80mm Thermal / Standard</option>

        <option value="58mm">58mm Mini Bluetooth</option>

      </select>


      <label style="font-size:12px; font-weight:600; display:flex; align-items:center; gap:4px;">

        <input type="checkbox" id="autoPrintToggle" onchange="toggleAutoPrint(this.checked)" />

        অটো প্রিন্ট

      </label>


      <button class="btn-secondary btn-sm" onclick="openLoginModal()">লগইন / পরিবর্তন</button>

    </div>

  </header>


  <main class="app-container">

    <div class="nav-tabs no-print">

      <button class="nav-tab active" onclick="switchTab('memoTab', this)">নতুন মেমো তৈরি</button>

      <button class="nav-tab" onclick="switchTab('historyTab', this)">ক্লাউড হিস্ট্রি ও বাকি পরিশোধ (৩০ দিন)</button>

      <button class="nav-tab admin-only" onclick="switchTab('adminTab', this)">এডমিন প্যানেল (পণ্য, দাম ও ইউজার)</button>

      <button class="nav-tab admin-only" onclick="switchTab('settingsTab', this)">ডিলার, অঙ্গ প্রতিষ্ঠান ও মেমো সেটিংস</button>

    </div>


    <section id="memoTab" class="tab-panel active">

      <div class="grid-2">

        <div class="card no-print">

          <div class="card-title">

            <span>ক্যাশ মেমো ফর্ম</span>

            <span id="memoNoBadge" style="font-size:13px; color:var(--primary-dark);">#34870</span>

          </div>


          <div class="form-row">

            <div class="field-group">

              <label>কাস্টমারের নাম</label>

              <input type="text" id="custName" placeholder="যেমন: রবিউল ভাই" oninput="renderLiveMemo()" />

            </div>

            <div class="field-group">

              <label>মোবাইল নম্বর</label>

              <input type="text" id="custPhone" placeholder="017XXXXXXXX" oninput="renderLiveMemo()" />

            </div>

          </div>


          <div class="form-row">

            <div class="field-group">

              <label>গাড়ির নম্বর</label>

              <input type="text" id="vehicleNo" placeholder="ঢাকা মেট্রো-ট-১১-xxxx" oninput="renderLiveMemo()" />

            </div>

            <div class="field-group">

              <label>ঠিকানা</label>

              <input type="text" id="custAddress" placeholder="মাঝকান্দি / মধুখালী" oninput="renderLiveMemo()" />

            </div>

          </div>


          <div class="items-box">

            <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:8px;">

              <strong style="font-size:13px;">পণ্যের তালিকা (তেল / লুব্রিকেন্ট / সেবা)</strong>

              <button type="button" class="btn-secondary btn-sm" onclick="addLineItem()">+ আইটেম যোগ করুন</button>

            </div>

            <div id="lineItemsContainer"></div>

          </div>


          <div class="form-row">

            <div class="field-group">

              <label>পেমেন্টের ধরন (পরিশোধ / বাকি)</label>

              <select id="paymentStatus" onchange="renderLiveMemo()">

                <option value="PAID">পরিশোধিত / PAID</option>

                <option value="DUE">বাকি / DUE</option>

              </select>

            </div>

            <div class="field-group">

              <label>পেমেন্ট মাধ্যম</label>

              <select id="paymentMethod" onchange="renderLiveMemo()">

                <option value="CASH">ক্যাশ (Cash)</option>

                <option value="BKASH">বিকাশ (bKash)</option>

                <option value="NAGAD">নগদ (Nagad)</option>

                <option value="CARD">ব্যাংক কার্ড (Bank Card)</option>

              </select>

            </div>

          </div>


          <div style="display:flex; flex-wrap:wrap; gap:10px; margin-top:8px;">

            <button class="btn-success" onclick="saveMemo(false)">ক্লাউডে সেভ করুন</button>

            <button class="btn-primary" onclick="saveMemo(true)">সেভ ও প্রিন্ট করুন</button>

            <button class="btn-secondary" onclick="resetMemoForm()">রিসেট</button>

          </div>

          <div id="memoSaveMsg" style="margin-top:8px; font-size:13px; font-weight:600; color:var(--accent);"></div>

        </div>


        <div class="card">

          <div class="card-title no-print">

            <span>লাইভ মেমো প্রিভিউ</span>

            <button class="btn-primary btn-sm" onclick="window.print()">প্রিন্ট দিন</button>

          </div>

          <div class="memo-preview-wrap">

            <div id="memoSheet" class="memo-sheet theme-classic">

              <div class="memo-header">

                <div id="pvStationName" class="memo-station-name">পারিশা ফিলিং স্টেশন (Parisha Filling Station)</div>

                <div id="pvDealerLine" class="memo-dealer-line">মেঘনা ডিলার | A unit of Hashem & Sons</div>

                <div id="pvMemoType" class="memo-type-pill">ক্যাশ মেমো / CASH MEMO</div>

                <div id="pvContactLine" class="memo-contact-line">📞 ০১৮৪৮-৩২৪১৬০ | 📍 মাঝকান্দি বাজার, মধুখালী, ফরিদপুর</div>

                <div id="pvSlogan" class="memo-slogan">নির্ভরজাল তেল • সঠিক মাপ • ২৪ ঘণ্টা উত্তম সেবা</div>

              </div>


              <div class="memo-meta-box">

                <div>

                  <div><strong id="lblMemoNo">মেমো নং:</strong> <span id="pvMemoNo">#34870</span></div>

                  <div><strong id="lblDate">তারিখ:</strong> <span id="pvDate"></span></div>

                  <div><strong id="lblTime">সময়:</strong> <span id="pvTime"></span></div>

                </div>

                <div class="memo-meta-right">

                  <div><strong id="lblName">নাম:</strong> <span id="pvCustName">-</span></div>

                  <div><strong id="lblVehicle">গাড়ি নং:</strong> <span id="pvVehicle">-</span></div>

                  <div><strong id="lblPhone">মোবাইল:</strong> <span id="pvPhone">-</span></div>

                  <div><strong id="lblAddress">ঠিকানা:</strong> <span id="pvAddress">-</span></div>

                </div>

              </div>


              <table class="memo-table">

                <thead>

                  <tr>

                    <th style="width:30px;">#</th>

                    <th id="thDesc">বিবরণ (Description)</th>

                    <th class="num-right" id="thQty">পরিমাণ (Qty)</th>

                    <th class="num-right" id="thRate">দর (Rate)</th>

                    <th class="num-right" id="thAmount">টাকা (Amount)</th>

                  </tr>

                </thead>

                <tbody id="pvItemsBody"></tbody>

              </table>


              <div class="memo-payment-section">

                <div>

                  <div id="lblPayMode" style="font-weight:700;">পেমেন্ট পদ্ধতি (Payment):</div>

                  <div class="memo-badge-box">

                    <span id="pvMethodBadge" class="memo-method-tag">ক্যাশ (Cash)</span>

                    <span id="pvStatusBadge" class="memo-status-tag">পরিশোধিত / PAID</span>

                  </div>

                </div>

                <div class="memo-totals-right">

                  <div><span id="lblSubtotal">মোট বিল (Subtotal):</span> <strong id="pvSubtotal">৳ 0.00</strong></div>

                  <div class="memo-grand-total"><span id="lblGrandTotal">সর্বমোট (Total):</span> <span id="pvTotal">৳ 0.00</span></div>

                </div>

              </div>


              <div class="memo-words-box">

                <div id="pvWordsBn" class="memo-words-bn">কথায়: শূন্য টাকা মাত্র</div>

                <div id="pvWordsEn" class="memo-words-en">In Words: Zero Taka Only</div>

              </div>


              <div class="memo-footer">

                <div id="pvFooterNote" class="memo-note">পণ্য হাতে পেয়ে দেখে নিন। “আপনাদের পরামর্শ একান্ত কাম্য” - ধন্যবাদ!</div>

                <div id="pvSign" class="memo-sign">স্বাক্ষর / Sign</div>

              </div>

            </div>

          </div>

        </div>

      </div>

    </section>


    <section id="historyTab" class="tab-panel">

      <div class="card">

        <div class="card-title">

          <span>ক্লাউড মেমো হিস্ট্রি (স্বয়ংক্রিয় ৩০ দিন পর পুরোনো ডেটা ডিলিট হয়)</span>

          <button class="btn-secondary btn-sm" onclick="cleanupExpiredMemos(true)">এখনই ৩০ দিনের পুরোনো মেমো ক্লিন করুন</button>

        </div>


        <div class="summary-strip" id="historySummary"></div>

        <div id="receiverBreakdown" style="margin-bottom:14px; font-size:12.5px; background:#f8fafc; border:1px solid var(--border); border-radius:10px; padding:10px 12px;"></div>


        <div class="form-row" style="margin-bottom:12px;">

          <input type="text" id="searchHistory" placeholder="কাস্টমারের নাম, গাড়ির নম্বর বা মেমো নং দিয়ে খুঁজুন..." oninput="renderHistory()" />

          <select id="filterStatus" onchange="renderHistory()">

            <option value="ALL">সব মেমো (All)</option>

            <option value="DUE">শুধুমাত্র বাকি (Due)</option>

            <option value="PAID">শুধুমাত্র পরিশোধিত (Paid)</option>

          </select>

        </div>


        <div style="overflow-x:auto;">

          <table class="data-table">

            <thead>

              <tr>

                <th>মেমো নং</th>

                <th>তারিখ ও সময়</th>

                <th>কাস্টমার ও গাড়ি</th>

                <th>তৈরিকারী (নজেল ম্যান)</th>

                <th>মোট টাকা</th>

                <th>মাধ্যম</th>

                <th>স্ট্যাটাস ও রিসিভার</th>

                <th>অ্যাকশন</th>

              </tr>

            </thead>

            <tbody id="historyTableBody"></tbody>

          </table>

        </div>

      </div>

    </section>


    <section id="adminTab" class="tab-panel">

      <div class="grid-2">

        <div class="card">

          <div class="card-title">পণ্য যোগ ও দাম পরিবর্তন (পার্মানেন্ট ক্লাউড/স্টোরেজ)</div>

          <div class="form-row">

            <div class="field-group">

              <label>পণ্যের নাম (বাংলা/ইংরেজি)</label>

              <input type="text" id="newProdName" placeholder="যেমন: ডিজেল (Diesel) বা মবিল ১ লিটার" />

            </div>

            <div class="field-group">

              <label>একক মূল্য / দাম (টাকা)</label>

              <input type="number" id="newProdPrice" step="0.01" placeholder="105.00" />

            </div>

          </div>

          <div class="form-row">

            <div class="field-group">

              <label>একক (Unit)</label>

              <input type="text" id="newProdUnit" value="লিটার / Unit" placeholder="যেমন: লিটার, পিস, বোতল" />

            </div>

            <div class="field-group">

              <label>নোট / ক্যাটাগরি (ঐচ্ছিক)</label>

              <input type="text" id="newProdNote" placeholder="যেমন: ফুয়েল / লুব্রিকেন্ট / সার্ভিস" />

            </div>

          </div>

          <div style="display:flex; gap:8px; flex-wrap:wrap;">

            <button class="btn-primary" onclick="addOrUpdateProduct()">স্থায়ীভাবে সেভ / দাম আপডেট করুন</button>

            <button type="button" class="btn-secondary" onclick="clearProductForm()">ফর্ম ক্লিয়ার</button>

          </div>


          <table class="data-table" style="margin-top:14px;">

            <thead>

              <tr>

                <th>পণ্যের নাম ও একক</th>

                <th>বর্তমান দাম</th>

                <th>সর্বশেষ আপডেট</th>

                <th>অ্যাকশন</th>

              </tr>

            </thead>

            <tbody id="productsTableBody"></tbody>

          </table>

        </div>


        <div class="card">

          <div class="card-title">অনুমোদিত ইউজার ও এডমিন তালিকা (১–৩ জন এডমিন)</div>

          <div class="form-row">

            <div class="field-group">

              <label>নাম</label>

              <input type="text" id="newUserName" placeholder="যেমন: করিম (নজেল ম্যান)" />

            </div>

            <div class="field-group">

              <label>রোল (Role)</label>

              <select id="newUserRole">

                <option value="USER">ইউজার / নজেল ম্যান (User)</option>

                <option value="ADMIN">এডমিন (Admin - সর্বোচ্চ ৩ জন)</option>

              </select>

            </div>

          </div>

          <div class="form-row">

            <div class="field-group">

              <label>মোবাইল নম্বর</label>

              <input type="text" id="newUserPhone" placeholder="018XXXXXXXX" />

            </div>

            <div class="field-group">

              <label>Gmail</label>

              <input type="text" id="newUserEmail" placeholder="user@parisha.com" />

            </div>

          </div>

          <div class="field-group">

            <label>পাসওয়ার্ড</label>

            <input type="text" id="newUserPass" value="1234" />

          </div>

          <button class="btn-success" onclick="addAllowedUser()">ইউজার অনুমোদন দিন</button>


          <table class="data-table" style="margin-top:14px;">

            <thead>

              <tr>

                <th>নাম ও রোল</th>

                <th>ফোন / Gmail</th>

                <th>অ্যাকশন</th>

              </tr>

            </thead>

            <tbody id="usersTableBody"></tbody>

          </table>

        </div>

      </div>

    </section>


    <section id="settingsTab" class="tab-panel">

      <div class="card" style="max-width:760px;">

        <div class="card-title">ফিলিং স্টেশন, ডিলার, অঙ্গ প্রতিষ্ঠান ও ফুটার সেটিংস</div>

        <div class="form-row">

          <div class="field-group">

            <label>ফিলিং স্টেশনের নাম</label>

            <input type="text" id="cfgStationName" />

          </div>

          <div class="field-group">

            <label>ডিলার ও অঙ্গ প্রতিষ্ঠানের নাম</label>

            <input type="text" id="cfgDealerLine" placeholder="মেঘনা ডিলার | A unit of Hashem & Sons" />

          </div>

        </div>

        <div class="form-row">

          <div class="field-group">

            <label>মোবাইল ও ঠিকানা লাইন</label>

            <input type="text" id="cfgContactLine" />

          </div>

          <div class="field-group">

            <label>স্লোগান / সেবা লাইন</label>

            <input type="text" id="cfgSlogan" />

          </div>

        </div>

        <div class="field-group">

          <label>ফুটার ও একান্ত কাম্য পরামর্শ বার্তা</label>

          <textarea id="cfgFooterNote" rows="2"></textarea>

        </div>

        <button class="btn-primary" onclick="saveStationSettings()">সেটিংস স্থায়ীভাবে সেভ করুন</button>

        <span id="settingsMsg" style="margin-left:10px; font-size:13px; font-weight:600; color:var(--accent);"></span>

      </div>


      <div class="card" style="max-width:760px;">

        <div class="card-title">

          <span>ক্লাউড সিঙ্ক (Firebase Firestore) ও রিসিভার হিসাব</span>

          <span id="cloudStatusBadge" class="badge-role">লোকাল মোড (Local)</span>

        </div>

        <p style="font-size:13px; color:var(--muted); margin-bottom:10px;">

          এডমিন ও নজেল ম্যানদের আলাদা ফোন/ডিভাইসে একই মেমো হিস্ট্রি, বাকি-পরিশোধ এবং পণ্য-দামের লাইভ সিঙ্কের জন্য Firebase Config বসিয়ে সেভ করুন। কনফিগ না বসালে স্বয়ংক্রিয়ভাবে লোকাল স্টোরেজে কাজ করবে।

        </p>

        <div class="field-group">

          <label>Firebase Config JSON (যেমন: {"apiKey":"...","projectId":"..."})</label>

          <textarea id="cfgFirebaseJson" rows="4" placeholder='{"apiKey":"YOUR_API_KEY","authDomain":"YOUR_PROJECT.firebaseapp.com","projectId":"YOUR_PROJECT_ID"}'></textarea>

        </div>

        <div style="display:flex; gap:8px; flex-wrap:wrap;">

          <button class="btn-primary" onclick="saveFirebaseConfig()">ক্লাউড কনফিগ সেভ ও কানেক্ট করুন</button>

          <button class="btn-secondary" onclick="syncFromCloudNow()">এখনই ক্লাউড থেকে সিঙ্ক করুন</button>

          <button class="btn-danger" onclick="clearFirebaseConfig()">ক্লাউড কনফিগ মুছুন</button>

        </div>

        <div id="cloudMsg" style="margin-top:8px; font-size:13px; font-weight:600; color:var(--primary-dark);"></div>

      </div>

    </section>

  </main>


  <script>

    const THIRTY_DAYS_MS = 30 * 24 * 60 * 60 * 1000;


    const DEFAULT_STATE = {

      currentUser: null,

      lang: "bn_en",

      theme: "classic",

      printerSize: "80mm",

      autoPrint: false,

      memoCounter: 34870,

      settings: {

        stationName: "পারিশা ফিলিং স্টেশন (Parisha Filling Station)",

        dealerLine: "মেঘনা ডিলার | A unit of Hashem & Sons",

        contactLine: "📞 ০১৮৪৮-৩২৪১৬০ | 📍 মাঝকান্দি বাজার, মধুখালী, ফরিদপুর",

        slogan: "নির্ভরজাল তেল • সঠিক মাপ • ২৪ ঘণ্টা উত্তম সেবা",

        footerNote: "পণ্য হাতে পেয়ে দেখে নিন। “আপনাদের পরামর্শ একান্ত কাম্য” - ধন্যবাদ!"

      },

      products: [

        { id: "p1", name: "ডিজেল (Diesel)", price: 105.00 },

        { id: "p2", name: "অকটেন (Octane)", price: 125.00 },

        { id: "p3", name: "পেট্রোল (Petrol)", price: 121.00 },

        { id: "p4", name: "গাড়ি ধোয়া (Car Wash)", price: 50.00 }

      ],

      allowedUsers: [

        { id: "u1", name: "প্রধান এডমিন", role: "ADMIN", phone: "01711000001", email: "admin@parisha.com", password: "1234" },

        { id: "u2", name: "সহকারী এডমিন ২", role: "ADMIN", phone: "01711000002", email: "admin2@parisha.com", password: "1234" },

        { id: "u3", name: "নজেল ম্যান ১", role: "USER", phone: "01811000001", email: "nozzle1@parisha.com", password: "1234" },

        { id: "u4", name: "নজেল ম্যান ২", role: "USER", phone: "01811000002", email: "nozzle2@parisha.com", password: "1234" }

      ],

      memos: []

    };


    let state = loadState();


    function loadState() {

      try {

        const raw = localStorage.getItem("parisha_memo_system_v1");

        if (!raw) return structuredClone(DEFAULT_STATE);

        const parsed = JSON.parse(raw);

        return {

          ...structuredClone(DEFAULT_STATE),

          ...parsed,

          settings: { ...DEFAULT_STATE.settings, ...(parsed.settings || {}) }

        };

      } catch (e) {

        return structuredClone(DEFAULT_STATE);

      }

    }


    function saveState() {

      localStorage.setItem("parisha_memo_system_v1", JSON.stringify(state));

      pushStateToCloud();

    }


    function cleanupExpiredMemos(showNotice = false) {

      const now = Date.now();

      const beforeCount = state.memos.length;

      state.memos = state.memos.filter(m => (now - m.createdAt) <= THIRTY_DAYS_MS);

      const removed = beforeCount - state.memos.length;

      if (removed > 0) saveState();

      if (showNotice) {

        alert(removed > 0 ? `${removed}টি ৩০ দিনের পুরোনো মেমো ডিলিট করা হয়েছে।` : "৩০ দিনের পুরোনো কোনো মেমো পাওয়া যায়নি।");

        renderHistory();

      }

    }


    function toBnDigits(str) {

      const map = { "0": "০", "1": "১", "2": "২", "3": "৩", "4": "৪", "5": "৫", "6": "৬", "7": "৭", "8": "৮", "9": "৯" };

      return String(str).replace(/[0-9]/g, d => map[d]);

    }


    function formatNumByLang(num, decimals = 2) {

      const fixed = Number(num || 0).toFixed(decimals);

      return state.lang === "en" ? fixed : toBnDigits(fixed);

    }


    function numberToWordsEn(num) {

      num = Math.floor(Number(num) || 0);

      if (num === 0) return "Zero Taka Only";

      const ones = ["", "One", "Two", "Three", "Four", "Five", "Six", "Seven", "Eight", "Nine", "Ten",

        "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen", "Seventeen", "Eighteen", "Nineteen"];

      const tens = ["", "", "Twenty", "Thirty", "Forty", "Fifty", "Sixty", "Seventy", "Eighty", "Ninety"];


      function twoDigits(n) {

        if (n < 20) return ones[n];

        return tens[Math.floor(n / 10)] + (n % 10 ? " " + ones[n % 10] : "");

      }

      function threeDigits(n) {

        const h = Math.floor(n / 100);

        const r = n % 100;

        return (h ? ones[h] + " Hundred " : "") + twoDigits(r);

      }


      let out = "";

      const crore = Math.floor(num / 10000000);

      num %= 10000000;

      const lakh = Math.floor(num / 100000);

      num %= 100000;

      const thousand = Math.floor(num / 1000);

      num %= 1000;


      if (crore) out += twoDigits(crore) + " Crore ";

      if (lakh) out += twoDigits(lakh) + " Lakh ";

      if (thousand) out += twoDigits(thousand) + " Thousand ";

      if (num) out += threeDigits(num);


      return out.trim() + " Taka Only";

    }


    function numberToWordsBn(num) {

      num = Math.floor(Number(num) || 0);

      if (num === 0) return "শূন্য টাকা মাত্র";

      const units = {

        0: "শূন্য", 1: "এক", 2: "দুই", 3: "তিন", 4: "চার", 5: "পাঁচ",

        6: "ছয়", 7: "সাত", 8: "আট", 9: "নয়", 10: "দশ",

        11: "এগারো", 12: "বারো", 13: "তেরো", 14: "চৌদ্দ", 15: "পনেরো",

        16: "ষোল", 17: "সতেরো", 18: "আঠারো", 19: "উনিশ", 20: "বিশ",

        21: "একুশ", 22: "বাইশ", 23: "তেইশ", 24: "চব্বিশ", 25: "পঁচিশ",

        26: "ছাব্বিশ", 27: "সাতাশ", 28: "আঠাশ", 29: "উনত্রিশ", 30: "ত্রিশ",

        35: "পঁয়ত্রিশ", 40: "চল্লিশ", 45: "পঁয়তাল্লিশ", 50: "পঞ্চাশ",

        55: "পঞ্চান্ন", 60: "ষাট", 70: "সত্তর", 80: "আশি", 90: "নব্বই"

      };

      if (units[num]) return units[num] + " টাকা মাত্র";


      let out = "";

      const crore = Math.floor(num / 10000000);

      num %= 10000000;

      const lakh = Math.floor(num / 100000);

      num %= 100000;

      const thousand = Math.floor(num / 1000);

      num %= 1000;

      const hundred = Math.floor(num / 100);

      const rem = num % 100;


      if (crore) out += (units[crore] || crore) + " কোটি ";

      if (lakh) out += (units[lakh] || lakh) + " লক্ষ ";

      if (thousand) out += (units[thousand] || thousand) + " হাজার ";

      if (hundred) out += (units[hundred] || hundred) + " শত ";

      if (rem) out += (units[rem] || rem) + " ";


      return out.trim() + " টাকা মাত্র";

    }


    function openLoginModal() {

      document.getElementById("loginError").textContent = "";

      document.getElementById("loginModal").style.display = "flex";

    }


    function handleLogin() {

      const idVal = document.getElementById("loginIdentifier").value.trim().toLowerCase();

      const passVal = document.getElementById("loginPassword").value.trim();

      const found = state.allowedUsers.find(u =>

        (u.phone.toLowerCase() === idVal || u.email.toLowerCase() === idVal) && u.password === passVal

      );

      if (!found) {

        document.getElementById("loginError").textContent = "অনুমোদিত ইউজার নয় অথবা নম্বর/Gmail/পাসওয়ার্ড ভুল হয়েছে।";

        return;

      }

      state.currentUser = found;

      saveState();

      document.getElementById("loginModal").style.display = "none";

      applyRoleUI();

      renderAll();

    }


    function applyRoleUI() {

      const u = state.currentUser;

      const badge = document.getElementById("uiUserBadge");

      const adminEls = document.querySelectorAll(".admin-only");


      if (!u) {

        badge.textContent = "লগইন প্রয়োজন";

        adminEls.forEach(el => el.style.display = "none");

        return;

      }


      badge.textContent = `${u.name} (${u.role === "ADMIN" ? "এডমিন" : "নজেল ম্যান"})`;

      adminEls.forEach(el => {

        el.style.display = u.role === "ADMIN" ? "inline-block" : "none";

      });

    }


    function switchTab(tabId, btn) {

      document.querySelectorAll(".tab-panel").forEach(p => p.classList.remove("active"));

      document.querySelectorAll(".nav-tab").forEach(b => b.classList.remove("active"));

      document.getElementById(tabId).classList.add("active");

      if (btn) btn.classList.add("active");

      if (tabId === "historyTab") renderHistory();

      if (tabId === "adminTab") {

        renderProductsTable();

        renderUsersTable();

      }

      if (tabId === "settingsTab") populateSettingsForm();

    }


    function changeLanguage(val) {

      state.lang = val;

      saveState();

      renderLiveMemo();

      renderHistory();

    }


    function changeTheme(val) {

      state.theme = val;

      saveState();

      const sheet = document.getElementById("memoSheet");

      sheet.className = "memo-sheet theme-" + val;

    }


    function changePrinterSize(val) {

      state.printerSize = val;

      saveState();

      const root = document.documentElement;

      if (val === "58mm") {

        root.style.setProperty("--print-width", "58mm");

        root.style.setProperty("--print-font-size", "10.5px");

      } else {

        root.style.setProperty("--print-width", "80mm");

        root.style.setProperty("--print-font-size", "12px");

      }

    }


    function toggleAutoPrint(checked) {

      state.autoPrint = checked;

      saveState();

    }


    function addLineItem(prodName = "", price = 0, qty = 1) {

      const container = document.getElementById("lineItemsContainer");

      const row = document.createElement("div");

      row.className = "item-row";


      const optionsHtml = state.products.map(p =>

        `<option value="${escapeHtml(p.name)}" data-price="${p.price}" ${p.name === prodName ? "selected" : ""}>${escapeHtml(p.name)} (৳${p.price})</option>`

      ).join("");


      row.innerHTML = `

        <select class="item-prod" onchange="onProdSelect(this)">

          ${optionsHtml}

        </select>

        <input type="number" class="item-qty" step="0.01" min="0.01" value="${qty}" placeholder="লিটার / Qty" title="লিটার লিখলে টাকা হিসাব হবে" oninput="onQtyOrRateChange(this)" />

        <input type="number" class="item-rate" step="0.01" min="0" value="${price}" placeholder="দর" title="প্রতি লিটার দর" oninput="onQtyOrRateChange(this)" />

        <input type="number" class="item-amount-input" step="0.01" min="0" value="0.00" placeholder="টাকা / Amount" title="টাকা লিখলে লিটার হিসাব হবে" oninput="onAmountChange(this)" />

        <button type="button" class="btn-danger btn-sm" onclick="this.parentElement.remove(); renderLiveMemo();">✕</button>

      `;

      container.appendChild(row);

      if (!prodName && state.products.length > 0) {

        onProdSelect(row.querySelector(".item-prod"));

      } else {

        renderLiveMemo();

      }

    }


    function onProdSelect(sel) {

      const opt = sel.options[sel.selectedIndex];

      const price = parseFloat(opt.getAttribute("data-price") || "0");

      const row = sel.parentElement;

      row.querySelector(".item-rate").value = price;

      onQtyOrRateChange(row.querySelector(".item-rate"));

    }


    function onQtyOrRateChange(el) {

      const row = el.closest(".item-row");

      if (!row) return;

      const qty = parseFloat(row.querySelector(".item-qty").value || "0");

      const rate = parseFloat(row.querySelector(".item-rate").value || "0");

      const amount = qty * rate;

      row.querySelector(".item-amount-input").value = amount > 0 ? amount.toFixed(2) : "0.00";

      renderLiveMemo();

    }


    function onAmountChange(el) {

      const row = el.closest(".item-row");

      if (!row) return;

      const amount = parseFloat(row.querySelector(".item-amount-input").value || "0");

      const rate = parseFloat(row.querySelector(".item-rate").value || "0");

      if (rate > 0) {

        const liters = amount / rate;

        row.querySelector(".item-qty").value = liters > 0 ? liters.toFixed(2) : "0.00";

      }

      renderLiveMemo();

    }


    function collectItemsFromForm() {

      const rows = document.querySelectorAll("#lineItemsContainer .item-row");

      const items = [];

      rows.forEach(r => {

        const desc = r.querySelector(".item-prod").value;

        const qty = parseFloat(r.querySelector(".item-qty").value || "0");

        const rate = parseFloat(r.querySelector(".item-rate").value || "0");

        const amountInput = r.querySelector(".item-amount-input");

        let amount = parseFloat(amountInput ? amountInput.value : "0") || (qty * rate);

        if (document.activeElement !== amountInput) {

          amount = qty * rate;

          if (amountInput) amountInput.value = amount.toFixed(2);

        }

        if (desc && qty > 0) {

          items.push({ desc, qty, rate, amount });

        }

      });

      return items;

    }


    function renderLiveMemo() {

      const items = collectItemsFromForm();

      const total = items.reduce((sum, it) => sum + it.amount, 0);


      const s = state.settings;

      document.getElementById("uiBrandName").textContent = s.stationName.split("(")[0].trim();

      document.getElementById("pvStationName").textContent = s.stationName;

      document.getElementById("pvDealerLine").textContent = s.dealerLine;

      document.getElementById("pvContactLine").textContent = s.contactLine;

      document.getElementById("pvSlogan").textContent = s.slogan;

      document.getElementById("pvFooterNote").textContent = s.footerNote;


      const memoNoStr = "#" + formatNumByLang(state.memoCounter, 0);

      document.getElementById("memoNoBadge").textContent = memoNoStr;

      document.getElementById("pvMemoNo").textContent = memoNoStr;


      const now = new Date();

      const dStr = `${String(now.getDate()).padStart(2, "0")}/${String(now.getMonth() + 1).padStart(2, "0")}/${now.getFullYear()}`;

      const tStr = now.toLocaleTimeString("en-US", { hour12: true });

      document.getElementById("pvDate").textContent = state.lang === "en" ? dStr : toBnDigits(dStr);

      document.getElementById("pvTime").textContent = state.lang === "en" ? tStr : toBnDigits(tStr);


      document.getElementById("pvCustName").textContent = document.getElementById("custName").value || "-";

      document.getElementById("pvVehicle").textContent = document.getElementById("vehicleNo").value || "-";

      document.getElementById("pvPhone").textContent = document.getElementById("custPhone").value || "-";

      document.getElementById("pvAddress").textContent = document.getElementById("custAddress").value || "-";


      const tbody = document.getElementById("pvItemsBody");

      tbody.innerHTML = items.map((it, idx) => `

        <tr>

          <td>${formatNumByLang(idx + 1, 0)}</td>

          <td>${escapeHtml(it.desc)}</td>

          <td class="num-right">${formatNumByLang(it.qty, 2)}</td>

          <td class="num-right">${formatNumByLang(it.rate, 2)}</td>

          <td class="num-right">${formatNumByLang(it.amount, 2)}</td>

        </tr>

      `).join("");


      const status = document.getElementById("paymentStatus").value;

      const method = document.getElementById("paymentMethod").value;

      const methodMap = {

        CASH: "ক্যাশ (Cash)",

        BKASH: "বিকাশ (bKash)",

        NAGAD: "নগদ (Nagad)",

        CARD: "ব্যাংক কার্ড (Bank Card)"

      };


      const mBadge = document.getElementById("pvMethodBadge");

      mBadge.textContent = state.lang === "en" ? method : methodMap[method];


      const sBadge = document.getElementById("pvStatusBadge");

      if (status === "PAID") {

        sBadge.textContent = state.lang === "en" ? "PAID" : "পরিশোধিত / PAID";

        sBadge.className = "memo-status-tag";

      } else {

        sBadge.textContent = state.lang === "en" ? "DUE (BAKI)" : "বাকি / DUE";

        sBadge.className = "memo-status-tag due";

      }


      const currPrefix = state.lang === "en" ? "BDT " : "৳ ";

      document.getElementById("pvSubtotal").textContent = currPrefix + formatNumByLang(total, 2);

      document.getElementById("pvTotal").textContent = currPrefix + formatNumByLang(total, 2);


      document.getElementById("pvWordsBn").textContent = "কথায়: " + numberToWordsBn(total);

      document.getElementById("pvWordsEn").textContent = "In Words: " + numberToWordsEn(total);

    }


    function saveMemo(shouldPrint) {

      if (!state.currentUser) {

        alert("মেমো সেভ করতে আগে লগইন করুন।");

        openLoginModal();

        return;

      }

      const items = collectItemsFromForm();

      if (items.length === 0) {

        alert("অন্তত একটি পণ্যের পরিমাণ ১ বা তার বেশি দিন।");

        return;

      }


      const total = items.reduce((sum, it) => sum + it.amount, 0);

      const status = document.getElementById("paymentStatus").value;

      const method = document.getElementById("paymentMethod").value;


      const memoObj = {

        id: "m_" + Date.now(),

        memoNo: state.memoCounter,

        createdAt: Date.now(),

        dateLabel: new Date().toLocaleString("bn-BD"),

        custName: document.getElementById("custName").value.trim() || "কাস্টমার",

        custPhone: document.getElementById("custPhone").value.trim() || "-",

        vehicleNo: document.getElementById("vehicleNo").value.trim() || "-",

        custAddress: document.getElementById("custAddress").value.trim() || "-",

        items,

        total,

        status,

        method,

        createdBy: state.currentUser.name,

        createdByRole: state.currentUser.role,

        paidBy: status === "PAID" ? state.currentUser.name : null,

        paidAt: status === "PAID" ? Date.now() : null

      };


      state.memos.unshift(memoObj);

      state.memoCounter += 1;

      saveState();


      document.getElementById("memoSaveMsg").textContent = `মেমো #${memoObj.memoNo} সফলভাবে ক্লাউড হিস্ট্রিতে সেভ হয়েছে!`;

      renderLiveMemo();

      renderHistory();


      if (shouldPrint || state.autoPrint) {

        setTimeout(() => window.print(), 200);

      }

    }


    function resetMemoForm() {

      document.getElementById("custName").value = "";

      document.getElementById("custPhone").value = "";

      document.getElementById("vehicleNo").value = "";

      document.getElementById("custAddress").value = "";

      document.getElementById("paymentStatus").value = "PAID";

      document.getElementById("lineItemsContainer").innerHTML = "";

      addLineItem();

      renderLiveMemo();

    }


    function renderHistory() {

      cleanupExpiredMemos(false);

      const q = (document.getElementById("searchHistory")?.value || "").toLowerCase();

      const filterStatus = document.getElementById("filterStatus")?.value || "ALL";


      const totalSales = state.memos.reduce((s, m) => s + m.total, 0);

      const totalPaid = state.memos.filter(m => m.status === "PAID").reduce((s, m) => s + m.total, 0);

      const totalDue = state.memos.filter(m => m.status === "DUE").reduce((s, m) => s + m.total, 0);


      document.getElementById("historySummary").innerHTML = `

        <div class="stat-box"><div class="stat-label">মোট মেমো (৩০ দিন)</div><div class="stat-val">${formatNumByLang(state.memos.length, 0)}</div></div>

        <div class="stat-box"><div class="stat-label">মোট বিক্রি</div><div class="stat-val">৳ ${formatNumByLang(totalSales, 2)}</div></div>

        <div class="stat-box"><div class="stat-label">পরিশোধিত (Paid)</div><div class="stat-val" style="color:#16a34a;">৳ ${formatNumByLang(totalPaid, 2)}</div></div>

        <div class="stat-box"><div class="stat-label">বাকি (Due)</div><div class="stat-val" style="color:#dc2626;">৳ ${formatNumByLang(totalDue, 2)}</div></div>

      `;


      const byReceiver = {};

      state.memos.filter(m => m.status === "PAID").forEach(m => {

        const rec = m.paidBy || m.createdBy || "অজানা";

        byReceiver[rec] = (byReceiver[rec] || 0) + Number(m.total || 0);

      });

      const recEntries = Object.entries(byReceiver);

      document.getElementById("receiverBreakdown").innerHTML = recEntries.length

        ? `<strong>কার কাছে কত টাকা পরিশোধ জমা হয়েছে (Paid Cash/Collection):</strong> ` +

          recEntries.map(([name, amt]) => `<span style="margin-left:10px; display:inline-block;">• <strong>${escapeHtml(name)}</strong>: ৳ ${formatNumByLang(amt, 2)}</span>`).join("")

        : `<strong>কার কাছে কত টাকা পরিশোধ জমা হয়েছে:</strong> এখনো কোনো পরিশোধিত মেমো নেই।`;


      const filtered = state.memos.filter(m => {

        if (filterStatus !== "ALL" && m.status !== filterStatus) return false;

        const hay = `${m.memoNo} ${m.custName} ${m.vehicleNo} ${m.custPhone} ${m.createdBy}`.toLowerCase();

        return hay.includes(q);

      });


      const tbody = document.getElementById("historyTableBody");

      tbody.innerHTML = filtered.map(m => {

        const statusHtml = m.status === "PAID"

          ? `<span class="status-pill status-paid">পরিশোধিত</span><div style="font-size:11px; color:#475569; margin-top:2px;">রিসিভ: ${escapeHtml(m.paidBy || m.createdBy)}</div>`

          : `<span class="status-pill status-due">বাকি</span>`;


        const settleBtn = m.status === "DUE"

          ? `<button class="btn-success btn-sm" onclick="markMemoPaid('${m.id}')">পরিশোধ করুন</button>`

          : "";


        return `

          <tr>

            <td><strong>#${m.memoNo}</strong></td>

            <td style="font-size:12px;">${escapeHtml(m.dateLabel)}</td>

            <td><strong>${escapeHtml(m.custName)}</strong><br/><span style="font-size:12px; color:#475569;">${escapeHtml(m.vehicleNo)} | ${escapeHtml(m.custPhone)}</span></td>

            <td>${escapeHtml(m.createdBy)}</td>

            <td><strong>৳ ${m.total.toFixed(2)}</strong></td>

            <td>${escapeHtml(m.method)}</td>

            <td>${statusHtml}</td>

            <td style="display:flex; gap:5px; flex-wrap:wrap;">

              ${settleBtn}

              <button class="btn-secondary btn-sm" onclick="loadMemoIntoPreview('${m.id}', true)">প্রিন্ট</button>

            </td>

          </tr>

        `;

      }).join("") || `<tr><td colspan="8" style="text-align:center; color:#64748b;">কোনো মেমো পাওয়া যায়নি</td></tr>`;

    }


    function markMemoPaid(memoId) {

      if (!state.currentUser) {

        alert("টাকা পরিশোধ আপডেট করতে লগইন করুন।");

        return;

      }

      const m = state.memos.find(x => x.id === memoId);

      if (!m) return;

      const chosenMethod = prompt("কোন মাধ্যমে টাকা জমা হয়েছে? (CASH / BKASH / NAGAD / CARD)", m.method || "CASH");

      m.status = "PAID";

      if (chosenMethod) m.method = chosenMethod.toUpperCase();

      m.paidBy = state.currentUser.name;

      m.paidAt = Date.now();

      saveState();

      renderHistory();

      loadMemoIntoPreview(memoId, true);

    }


    function loadMemoIntoPreview(memoId, autoPrintNow = false) {

      const m = state.memos.find(x => x.id === memoId);

      if (!m) return;

      switchTab("memoTab", document.querySelector(".nav-tab"));


      document.getElementById("pvMemoNo").textContent = "#" + formatNumByLang(m.memoNo, 0);

      document.getElementById("pvCustName").textContent = m.custName;

      document.getElementById("pvVehicle").textContent = m.vehicleNo;

      document.getElementById("pvPhone").textContent = m.custPhone;

      document.getElementById("pvAddress").textContent = m.custAddress;


      const tbody = document.getElementById("pvItemsBody");

      tbody.innerHTML = m.items.map((it, idx) => `

        <tr>

          <td>${formatNumByLang(idx + 1, 0)}</td>

          <td>${escapeHtml(it.desc)}</td>

          <td class="num-right">${formatNumByLang(it.qty, 2)}</td>

          <td class="num-right">${formatNumByLang(it.rate, 2)}</td>

          <td class="num-right">${formatNumByLang(it.amount, 2)}</td>

        </tr>

      `).join("");


      const currPrefix = state.lang === "en" ? "BDT " : "৳ ";

      document.getElementById("pvSubtotal").textContent = currPrefix + formatNumByLang(m.total, 2);

      document.getElementById("pvTotal").textContent = currPrefix + formatNumByLang(m.total, 2);

      document.getElementById("pvWordsBn").textContent = "কথায়: " + numberToWordsBn(m.total);

      document.getElementById("pvWordsEn").textContent = "In Words: " + numberToWordsEn(m.total);


      const sBadge = document.getElementById("pvStatusBadge");

      if (m.status === "PAID") {

        sBadge.textContent = state.lang === "en" ? "PAID" : "পরিশোধিত / PAID";

        sBadge.className = "memo-status-tag";

      } else {

        sBadge.textContent = state.lang === "en" ? "DUE (BAKI)" : "বাকি / DUE";

        sBadge.className = "memo-status-tag due";

      }


      if (autoPrintNow) {

        setTimeout(() => window.print(), 200);

      }

    }


    function clearProductForm() {

      document.getElementById("newProdName").value = "";

      document.getElementById("newProdPrice").value = "";

      document.getElementById("newProdUnit").value = "লিটার / Unit";

      document.getElementById("newProdNote").value = "";

    }


    function editProductPriceQuick(id) {

      const p = state.products.find(x => x.id === id);

      if (!p) return;

      const val = prompt(`"${p.name}" এর নতুন দাম লিখুন (বর্তমান: ৳ ${p.price.toFixed(2)}):`, p.price);

      if (val === null) return;

      const newPrice = parseFloat(val);

      if (isNaN(newPrice) || newPrice <= 0) {

        alert("সঠিক দাম লিখুন।");

        return;

      }

      p.price = newPrice;

      p.updatedAt = new Date().toLocaleString("bn-BD");

      p.updatedBy = state.currentUser ? state.currentUser.name : "Admin";

      saveState();

      renderProductsTable();

      refreshProductDropdowns();

      renderLiveMemo();

    }


    function loadProductIntoForm(id) {

      const p = state.products.find(x => x.id === id);

      if (!p) return;

      document.getElementById("newProdName").value = p.name;

      document.getElementById("newProdPrice").value = p.price;

      document.getElementById("newProdUnit").value = p.unit || "লিটার / Unit";

      document.getElementById("newProdNote").value = p.note || "";

    }


    function addOrUpdateProduct() {

      const name = document.getElementById("newProdName").value.trim();

      const price = parseFloat(document.getElementById("newProdPrice").value);

      const unit = document.getElementById("newProdUnit").value.trim() || "লিটার / Unit";

      const note = document.getElementById("newProdNote").value.trim();

      if (!name || isNaN(price) || price <= 0) {

        alert("সঠিক পণ্যের নাম ও দাম দিন।");

        return;

      }

      const nowLabel = new Date().toLocaleString("bn-BD");

      const actor = state.currentUser ? state.currentUser.name : "Admin";

      const existing = state.products.find(p => p.name.toLowerCase() === name.toLowerCase());

      if (existing) {

        existing.price = price;

        existing.unit = unit;

        existing.note = note;

        existing.updatedAt = nowLabel;

        existing.updatedBy = actor;

      } else {

        state.products.push({

          id: "p_" + Date.now(),

          name,

          price,

          unit,

          note,

          updatedAt: nowLabel,

          updatedBy: actor

        });

      }

      saveState();

      clearProductForm();

      renderProductsTable();

      refreshProductDropdowns();

      renderLiveMemo();

    }


    function deleteProduct(id) {

      state.products = state.products.filter(p => p.id !== id);

      saveState();

      renderProductsTable();

      refreshProductDropdowns();

      renderLiveMemo();

    }


    function renderProductsTable() {

      const tbody = document.getElementById("productsTableBody");

      tbody.innerHTML = state.products.map(p => `

        <tr>

          <td>

            <strong>${escapeHtml(p.name)}</strong><br/>

            <span style="font-size:11px; color:#475569;">একক: ${escapeHtml(p.unit || "লিটার / Unit")}${p.note ? " • " + escapeHtml(p.note) : ""}</span>

          </td>

          <td><strong>৳ ${Number(p.price).toFixed(2)}</strong></td>

          <td style="font-size:11px; color:#475569;">${escapeHtml(p.updatedAt || "ডিফল্ট")}<br/>${escapeHtml(p.updatedBy || "System")}</td>

          <td style="display:flex; gap:5px; flex-wrap:wrap;">

            <button class="btn-primary btn-sm" onclick="editProductPriceQuick('${p.id}')">দাম বদলান</button>

            <button class="btn-secondary btn-sm" onclick="loadProductIntoForm('${p.id}')">এডিট</button>

            <button class="btn-danger btn-sm" onclick="deleteProduct('${p.id}')">ডিলিট</button>

          </td>

        </tr>

      `).join("");

    }


    function refreshProductDropdowns() {

      const selects = document.querySelectorAll(".item-prod");

      selects.forEach(sel => {

        const currentVal = sel.value;

        sel.innerHTML = state.products.map(p =>

          `<option value="${escapeHtml(p.name)}" data-price="${p.price}">${escapeHtml(p.name)} (৳${p.price})</option>`

        ).join("");

        if ([...sel.options].some(o => o.value === currentVal)) {

          sel.value = currentVal;

        }

      });

    }


    function addAllowedUser() {

      const name = document.getElementById("newUserName").value.trim();

      const role = document.getElementById("newUserRole").value;

      const phone = document.getElementById("newUserPhone").value.trim();

      const email = document.getElementById("newUserEmail").value.trim();

      const password = document.getElementById("newUserPass").value.trim() || "1234";


      if (!name || (!phone && !email)) {

        alert("নাম এবং অন্তত একটি মোবাইল নম্বর বা Gmail দিন।");

        return;

      }


      const adminCount = state.allowedUsers.filter(u => u.role === "ADMIN").length;

      if (role === "ADMIN" && adminCount >= 3) {

        alert("সর্বোচ্চ ৩ জন এডমিন থাকতে পারবেন।");

        return;

      }


      state.allowedUsers.push({

        id: "u_" + Date.now(),

        name, role, phone, email, password

      });

      saveState();

      document.getElementById("newUserName").value = "";

      document.getElementById("newUserPhone").value = "";

      document.getElementById("newUserEmail").value = "";

      renderUsersTable();

    }


    function deleteUser(id) {

      if (state.currentUser && state.currentUser.id === id) {

        alert("বর্তমানে লগইন থাকা ইউজার ডিলিট করা যাবে না।");

        return;

      }

      state.allowedUsers = state.allowedUsers.filter(u => u.id !== id);

      saveState();

      renderUsersTable();

    }


    function renderUsersTable() {

      const tbody = document.getElementById("usersTableBody");

      tbody.innerHTML = state.allowedUsers.map(u => `

        <tr>

          <td><strong>${escapeHtml(u.name)}</strong><br/><span class="badge-role">${u.role === "ADMIN" ? "এডমিন" : "নজেল ম্যান"}</span></td>

          <td style="font-size:12px;">${escapeHtml(u.phone || "-")}<br/>${escapeHtml(u.email || "-")}</td>

          <td><button class="btn-danger btn-sm" onclick="deleteUser('${u.id}')">রিমুভ</button></td>

        </tr>

      `).join("");

    }


    function populateSettingsForm() {

      document.getElementById("cfgStationName").value = state.settings.stationName;

      document.getElementById("cfgDealerLine").value = state.settings.dealerLine;

      document.getElementById("cfgContactLine").value = state.settings.contactLine;

      document.getElementById("cfgSlogan").value = state.settings.slogan;

      document.getElementById("cfgFooterNote").value = state.settings.footerNote;

      const ta = document.getElementById("cfgFirebaseJson");

      if (ta && firebaseConfigCache) {

        ta.value = JSON.stringify(firebaseConfigCache, null, 2);

      }

      updateCloudBadge(firebaseConfigCache ? "ক্লাউড সংযুক্ত" : "লোকাল মোড (Local)", !!firebaseConfigCache);

    }


    function saveStationSettings() {

      state.settings = {

        stationName: document.getElementById("cfgStationName").value.trim() || DEFAULT_STATE.settings.stationName,

        dealerLine: document.getElementById("cfgDealerLine").value.trim(),

        contactLine: document.getElementById("cfgContactLine").value.trim(),

        slogan: document.getElementById("cfgSlogan").value.trim(),

        footerNote: document.getElementById("cfgFooterNote").value.trim()

      };

      saveState();

      renderLiveMemo();

      document.getElementById("settingsMsg").textContent = "সেটিংস সংরক্ষিত হয়েছে!";

      setTimeout(() => { document.getElementById("settingsMsg").textContent = ""; }, 2500);

    }


    function escapeHtml(str) {

      return String(str || "")

        .replace(/&/g, "&amp;")

        .replace(/</g, "&lt;")

        .replace(/>/g, "&gt;")

        .replace(/"/g, "&quot;");

    }


    function renderAll() {

      document.getElementById("langSelect").value = state.lang;

      document.getElementById("themeSelect").value = state.theme;

      document.getElementById("printerSizeSelect").value = state.printerSize;

      document.getElementById("autoPrintToggle").checked = state.autoPrint;

      changeTheme(state.theme);

      changePrinterSize(state.printerSize);

      renderLiveMemo();

      renderHistory();

      renderProductsTable();

      renderUsersTable();

      populateSettingsForm();

    }


    let firebaseConfigCache = null;

    try {

      const savedFb = localStorage.getItem("parisha_firebase_cfg_v1");

      if (savedFb) firebaseConfigCache = JSON.parse(savedFb);

    } catch (e) {}


    function updateCloudBadge(text, isOnline = false) {

      const el = document.getElementById("cloudStatusBadge");

      if (!el) return;

      el.textContent = text;

      el.style.background = isOnline ? "#dcfce7" : "#e2e8f0";

      el.style.color = isOnline ? "#166534" : "#0f172a";

    }


    function saveFirebaseConfig() {

      const raw = document.getElementById("cfgFirebaseJson").value.trim();

      const msgEl = document.getElementById("cloudMsg");

      if (!raw) {

        alert("Firebase Config JSON দিন।");

        return;

      }

      try {

        const cfg = JSON.parse(raw);

        if (!cfg.projectId || !cfg.apiKey) {

          alert("JSON এ projectId এবং apiKey থাকতে হবে।");

          return;

        }

        firebaseConfigCache = cfg;

        localStorage.setItem("parisha_firebase_cfg_v1", JSON.stringify(cfg));

        updateCloudBadge("ক্লাউড সংযুক্ত (Firestore)", true);

        msgEl.textContent = "Firebase কনফিগ সেভ হয়েছে! সিঙ্ক শুরু হচ্ছে...";

        pushStateToCloud().then(() => syncFromCloudNow());

      } catch (err) {

        alert("সঠিক JSON ফরম্যাট দিন।");

      }

    }


    function clearFirebaseConfig() {

      firebaseConfigCache = null;

      localStorage.removeItem("parisha_firebase_cfg_v1");

      document.getElementById("cfgFirebaseJson").value = "";

      updateCloudBadge("লোকাল মোড (Local)", false);

      document.getElementById("cloudMsg").textContent = "ক্লাউড কনফিগ মুছে ফেলা হয়েছে।";

    }


    function firestoreDocUrl() {

      if (!firebaseConfigCache || !firebaseConfigCache.projectId) return null;

      const pid = encodeURIComponent(firebaseConfigCache.projectId);

      const key = encodeURIComponent(firebaseConfigCache.apiKey || "");

      return `https://firestore.googleapis.com/v1/projects/${pid}/databases/(default)/documents/parisha_station/shared_state?key=${key}`;

    }


    async function pushStateToCloud() {

      const url = firestoreDocUrl();

      if (!url) return;

      try {

        const payload = {

          fields: {

            json_data: { stringValue: JSON.stringify({

              memoCounter: state.memoCounter,

              settings: state.settings,

              products: state.products,

              allowedUsers: state.allowedUsers,

              memos: state.memos

            })},

            updatedAt: { integerValue: String(Date.now()) }

          }

        };

        await fetch(url, {

          method: "PATCH",

          headers: { "Content-Type": "application/json" },

          body: JSON.stringify(payload)

        });

        updateCloudBadge("ক্লাউড সিঙ্কড (Live)", true);

      } catch (e) {

        updateCloudBadge("অফলাইন / লোকাল", false);

      }

    }


    async function syncFromCloudNow() {

      const url = firestoreDocUrl();

      const msgEl = document.getElementById("cloudMsg");

      if (!url) {

        if (msgEl) msgEl.textContent = "আগে Firebase Config JSON সেভ করুন।";

        return;

      }

      try {

        const res = await fetch(url);

        if (!res.ok) throw new Error("Fetch failed");

        const doc = await res.json();

        const rawJson = doc?.fields?.json_data?.stringValue;

        if (rawJson) {

          const remote = JSON.parse(rawJson);

          state.memoCounter = remote.memoCounter || state.memoCounter;

          state.settings = { ...state.settings, ...(remote.settings || {}) };

          if (Array.isArray(remote.products) && remote.products.length) state.products = remote.products;

          if (Array.isArray(remote.allowedUsers) && remote.allowedUsers.length) state.allowedUsers = remote.allowedUsers;

          if (Array.isArray(remote.memos)) state.memos = remote.memos;

          cleanupExpiredMemos(false);

          localStorage.setItem("parisha_memo_system_v1", JSON.stringify(state));

          renderAll();

          updateCloudBadge("ক্লাউড সিঙ্কড (Live)", true);

          if (msgEl) msgEl.textContent = "ক্লাউড থেকে সর্বশেষ ডেটা সিঙ্ক হয়েছে!";

        }

      } catch (e) {

        updateCloudBadge("লোকাল ব্যাকআপ", false);

        if (msgEl) msgEl.textContent = "ক্লাউড সিঙ্ক করা যায়নি; লোকাল ডেটা ব্যবহৃত হচ্ছে।";

      }

    }


    cleanupExpiredMemos(false);

    addLineItem();

    applyRoleUI();

    renderAll();

    if (firebaseConfigCache) {

      updateCloudBadge("ক্লাউড সংযুক্ত", true);

      syncFromCloudNow();

    }

    if (!state.currentUser) {

      openLoginModal();

    } else {

      document.getElementById("loginModal").style.display = "none";

    }

  </script>

</body>

</html>

