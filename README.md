<!doctype html>
<html lang="uz">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>ITEMS — O‘zing izlagan narsa</title>
<style>
:root{--ink:#20223a;--muted:#777b91;--bg:#f7f7ff;--purple:#6c4cff;--pink:#ff5fa2;--yellow:#ffd75e}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);font-family:system-ui,sans-serif;color:var(--ink)}
button,input,select,textarea{font:inherit}
button{cursor:pointer;border:0}
.top{background:linear-gradient(120deg,#6c4cff,#9b58ed 52%,#ff65a9);color:white;padding:18px 16px 28px;border-radius:0 0 28px 28px}
.nav{max-width:1050px;margin:auto;display:flex;align-items:center;justify-content:space-between;gap:10px}
.logo{font-size:26px;font-weight:900;letter-spacing:1px}
.logo span{color:var(--yellow)}
.pill{background:#ffffff25;color:white;border:1px solid #ffffff55;border-radius:30px;padding:9px 13px}
.hero{max-width:1050px;margin:28px auto 0}
.hero h1{font-size:clamp(28px,6vw,46px);line-height:1.08;margin:0 0 10px}
.hero p{margin:0 0 18px;color:#f4edff}
.search{display:flex;gap:8px;background:white;padding:7px;border-radius:17px;max-width:700px}
.search input{min-width:0;flex:1;border:0;outline:0;padding:10px}
.primary{background:var(--yellow);color:#33244e;font-weight:800;border-radius:12px;padding:11px 14px}
.wrap{max-width:1050px;margin:22px auto;padding:0 14px}
.categories{display:flex;gap:9px;overflow-x:auto;padding:2px 0 12px}
.cat{white-space:nowrap;border:1px solid #e7e4f6;background:white;border-radius:30px;padding:10px 14px;color:var(--ink)}
.cat.active{background:var(--ink);color:white}
.sectionhead{display:flex;justify-content:space-between;align-items:center;gap:10px;margin:12px 0}
.sectionhead h2{margin:0;font-size:22px}
.sub{color:var(--muted);font-size:13px}
.grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:12px}
.card{background:white;border:1px solid #eeecf8;border-radius:18px;overflow:hidden;box-shadow:0 5px 18px #29205c08}
.photo{height:135px;display:flex;align-items:center;justify-content:center;font-size:56px;background:linear-gradient(135deg,#fff0f7,#e9e7ff)}
.cardbody{padding:12px}
.badge{display:inline-block;font-size:11px;background:#e6fff4;color:#087c58;padding:4px 8px;border-radius:20px;font-weight:800}
.title{font-weight:750;margin:8px 0 5px;overflow-wrap:anywhere}
.price{font-weight:900;color:var(--purple);font-size:18px}
.location{font-size:12px;color:var(--muted);margin-top:6px}
.cardactions{display:flex;gap:8px;margin-top:10px}
.smallbtn{background:#f0edff;color:#5a43d7;border-radius:10px;padding:8px 10px;flex:1;font-weight:700;font-size:13px}
.smallbtn.fav{flex:0 0 auto;background:#fff0f5;color:#d43f7f}
.empty{background:white;border:1px dashed #d9d4f2;border-radius:16px;padding:24px;text-align:center;color:var(--muted);grid-column:1/-1}
.notice{background:#fff8db;border:1px solid #ffe8a0;border-radius:14px;padding:12px 14px;margin:18px 0;font-size:13px;color:#68521b}
.modalback{position:fixed;inset:0;background:#17142c99;display:none;align-items:flex-end;justify-content:center;padding:12px;z-index:5}
.modalback.show{display:flex}
.modal{background:white;width:min(560px,100%);border-radius:24px;padding:20px;max-height:90vh;overflow:auto}
.modalhead{display:flex;justify-content:space-between;align-items:center}
.modal h2{margin:0 0 14px}
.close{background:#f0eef8;border-radius:50%;width:36px;height:36px;font-size:20px}
.field{display:block;margin:12px 0;font-size:13px;font-weight:750}
.field input,.field select,.field textarea{display:block;width:100%;margin-top:6px;padding:12px;border:1px solid #e1deef;border-radius:12px;background:white}
.submit{width:100%;background:linear-gradient(100deg,var(--purple),var(--pink));color:white;font-weight:850;padding:14px;border-radius:13px;margin-top:8px}
.footer{text-align:center;color:var(--muted);font-size:12px;padding:28px 12px}
.toast{position:fixed;bottom:18px;left:50%;transform:translateX(-50%);background:#25213c;color:white;border-radius:12px;padding:12px 16px;display:none;z-index:10;max-width:90%;text-align:center}
.toast.show{display:block}
@media(min-width:650px){.grid{grid-template-columns:repeat(3,minmax(0,1fr))}.photo{height:175px}.wrap{padding:0 20px}.top{padding-left:24px;padding-right:24px}}
</style>
</head>
<body>
<header class="top">
  <div class="nav">
    <div class="logo">ITEM<span>S</span> ✦</div>
    <button class="pill" id="loginBtn">👤 Google orqali kirish</button>
  </div>
  <div class="hero">
    <h1>Kerakli narsangni <span style="color:#ffe17b">top.</span><br>Keraksizini sot.</h1>
    <p>Buyumlar, xizmatlar va yaxshi imkoniyatlar — barchasi bir joyda.</p>
    <div class="search">
      <input id="searchInput" placeholder="Nima qidiryapsan? Masalan, telefon…" aria-label="E'lon qidirish">
      <button class="primary" id="searchBtn">Qidirish</button>
    </div>
  </div>
</header>

<main class="wrap">
  <div class="categories" id="categories">
    <button class="cat active" data-cat="Hammasi">✨ Hammasi</button>
    <button class="cat" data-cat="Elektronika">📱 Elektronika</button>
    <button class="cat" data-cat="Kiyim">👕 Kiyim</button>
    <button class="cat" data-cat="Uy-ro‘zg‘or">🏠 Uy-ro‘zg‘or</button>
    <button class="cat" data-cat="Transport">🚗 Transport</button>
    <button class="cat" data-cat="Xizmatlar">🛠️ Xizmatlar</button>
    <button class="cat" data-cat="Bepul">🎁 Bepul</button>
  </div>

  <div class="sectionhead">
    <div>
      <h2>🔥 Yangi e’lonlar</h2>
      <div class="sub" id="countText">E’lonlar yuklanmoqda...</div>
    </div>
    <button class="primary" id="addBtn">＋ E’lon berish</button>
  </div>

  <div class="notice">
    ℹ️ Demo versiya: yangi e’lonlar ushbu brauzerda saqlanadi.
    Google orqali kirish va umumiy e’lonlar uchun Supabase ulanishi kerak.
  </div>

  <div class="grid" id="listingGrid"></div>
  <div class="footer">ITEMS © 2026 · Odamlar uchun qulay bozor 💜</div>
</main>

<div class="modalback" id="modalBack">
  <div class="modal">
    <div class="modalhead">
      <h2>➕ Yangi e’lon</h2>
      <button class="close" id="closeModal" type="button" aria-label="Yopish">×</button>
    </div>

    <form id="listingForm">
      <label class="field">E’lon nomi
        <input required maxlength="70" name="title" placeholder="Masalan, Samsung telefon">
      </label>

      <label class="field">Narxi (so‘m)
        <input required type="number" min="0" step="1" name="price" placeholder="1500000">
      </label>

      <label class="field">Kategoriya
        <select name="category">
          <option>Elektronika</option>
          <option>Kiyim</option>
          <option>Uy-ro‘zg‘or</option>
          <option>Transport</option>
          <option>Xizmatlar</option>
          <option>Bepul</option>
        </select>
      </label>

      <label class="field">Viloyat
        <select name="region" required>
          <option value="">Viloyatni tanlang</option>
          <option>Toshkent shahri</option>
          <option>Toshkent viloyati</option>
          <option>Samarqand</option>
          <option>Andijon</option>
          <option>Farg‘ona</option>
          <option>Namangan</option>
          <option>Buxoro</option>
          <option>Xorazm</option>
          <option>Navoiy</option>
          <option>Qashqadaryo</option>
          <option>Surxondaryo</option>
          <option>Jizzax</option>
          <option>Sirdaryo</option>
          <option>Qoraqalpog‘iston</option>
        </select>
      </label>

      <label class="field">Shahar yoki tuman
        <input required maxlength="60" name="location" placeholder="Masalan, Chilonzor yoki Urgut">
      </label>

      <label class="field">Emoji (rasm o‘rniga)
        <select name="emoji">
          <option>📱</option><option>👟</option><option>👕</option>
          <option>🛋️</option><option>🚗</option><option>🎧</option>
          <option>📚</option><option>🛠️</option><option>🎁</option><option>💻</option>
        </select>
      </label>

      <label class="field">Qisqacha ma’lumot
        <textarea name="description" maxlength="240" rows="3" placeholder="Holati, yetkazib berish…"></textarea>
      </label>

      <button class="submit" type="submit">E’lonni joylash</button>
    </form>
  </div>
</div>

<div class="toast" id="toast" role="status"></div>

<script>
'use strict';

const sample = [
  {id:'s1',title:'Samsung Galaxy — yaxshi holatda',price:1850000,category:'Elektronika',region:'Toshkent shahri',location:'Toshkent',emoji:'📱',description:'Ishlashi yaxshi, kelishamiz.'},
  {id:'s2',title:'Yangi krossovka',price:220000,category:'Kiyim',region:'Samarqand',location:'Samarqand shahri',emoji:'👟',description:'Qulay va zamonaviy.'},
  {id:'s3',title:'Kompyuter stoli',price:450000,category:'Uy-ro‘zg‘or',region:'Toshkent shahri',location:'Toshkent',emoji:'🛋️',description:'Uy yoki ofis uchun.'},
  {id:'s4',title:'Velosiped',price:780000,category:'Transport',region:'Andijon',location:'Andijon shahri',emoji:'🚲',description:'Yaxshi holatda.'},
  {id:'s5',title:'Matematika darslari',price:0,category:'Xizmatlar',region:'Onlayn',location:'Onlayn',emoji:'📚',description:'Birinchi maslahat bepul.'},
  {id:'s6',title:'Bepul kitoblar',price:0,category:'Bepul',region:'Buxoro',location:'Buxoro shahri',emoji:'🎁',description:'O‘qib bo‘lingan kitoblar.'}
];

const $ = selector => document.querySelector(selector);
let activeCat = 'Hammasi';
let userItems = [];

try {
  const saved = JSON.parse(localStorage.getItem('itemsListings') || '[]');
  if (Array.isArray(saved)) userItems = saved;
} catch (error) {
  userItems = [];
}

function esc(value) {
  return String(value ?? '').replace(/[&<>"']/g, char => ({
    '&':'&amp;', '<':'&lt;', '>':'&gt;', '"':'&quot;', "'":'&#39;'
  })[char]);
}

function money(value) {
  const number = Number(value) || 0;
  return number === 0 ? 'Bepul' : number.toLocaleString('uz-UZ') + ' so‘m';
}

function toast(message) {
  const box = $('#toast');
  box.textContent = message;
  box.classList.add('show');
  clearTimeout(toast.timer);
  toast.timer = setTimeout(() => box.classList.remove('show'), 2800);
}

function render() {
  const query = $('#searchInput').value.trim().toLocaleLowerCase('uz-UZ');
  const all = [...userItems, ...sample];

  const items = all.filter(item => {
    const categoryMatch = activeCat === 'Hammasi' || item.category === activeCat;
    const searchable = [
      item.title, item.location, item.region, item.category, item.description
    ].join(' ').toLocaleLowerCase('uz-UZ');
    return categoryMatch && searchable.includes(query);
  });

  $('#countText').textContent = items.length + ' ta e’lon';

  $('#listingGrid').innerHTML = items.map(item => `
    <article class="card">
      <div class="photo">${esc(item.emoji || '📦')}</div>
      <div class="cardbody">
        <span class="badge">${esc(item.category === 'Bepul' ? 'BEPUL' : item.category)}</span>
        <div class="title">${esc(item.title)}</div>
        <div class="price">${money(item.price)}</div>
        <div class="location">📍 ${esc(item.region ? item.region + ', ' : '')}${esc(item.location || '')}</div>
        <div class="cardactions">
          <button class="smallbtn contactBtn" data-id="${esc(item.id)}">☎ Bog‘lanish</button>
          <button class="smallbtn fav" type="button" aria-label="Tanlanganlarga qo‘shish">♡</button>
        </div>
      </div>
    </article>
  `).join('') || '<div class="empty">😕 E’lon topilmadi. Boshqa so‘z bilan qidirib ko‘r.</div>';
}

function saveItems() {
  try {
    localStorage.setItem('itemsListings', JSON.stringify(userItems));
    return true;
  } catch (error) {
    toast('Telefon xotirasiga saqlab bo‘lmadi. Xotirani tekshiring.');
    return false;
  }
}

$('#categories').addEventListener('click', event => {
  const button = event.target.closest('[data-cat]');
  if (!button) return;

  activeCat = button.dataset.cat;
  document.querySelectorAll('.cat').forEach(element => {
    element.classList.toggle('active', element === button);
  });
  render();
});

$('#searchBtn').addEventListener('click', render);
$('#searchInput').addEventListener('input', render);

$('#addBtn').addEventListener('click', () => {
  $('#modalBack').classList.add('show');
});

function closeModal() {
  $('#modalBack').classList.remove('show');
}

$('#closeModal').addEventListener('click', closeModal);

$('#modalBack').addEventListener('click', event => {
  if (event.target === $('#modalBack')) closeModal();
});

document.addEventListener('keydown', event => {
  if (event.key === 'Escape') closeModal();
});

$('#loginBtn').addEventListener('click', () => {
  toast('Google kirishi hali ulanmagan. Buning uchun Supabase OAuth sozlamalari kerak.');
});

$('#listingGrid').addEventListener('click', event => {
  const contactButton = event.target.closest('.contactBtn');

  if (contactButton) {
    const id = contactButton.dataset.id;
    const item = [...userItems, ...sample].find(x => String(x.id) === id);
    if (item) toast('E’lon: ' + item.title + '. Sotuvchi kontakti hali ulanmagan.');
    return;
  }

  const favButton = event.target.closest('.fav');
  if (favButton) {
    favButton.textContent = favButton.textContent === '♡' ? '♥' : '♡';
    toast(favButton.textContent === '♥' ? 'Tanlanganlarga qo‘shildi!' : 'Tanlanganlardan olindi.');
  }
});

$('#listingForm').addEventListener('submit', event => {
  event.preventDefault();

  const form = new FormData(event.target);
  const item = {
    id: String(Date.now()),
    title: String(form.get('title') || '').trim(),
    price: Number(form.get('price')),
    category: String(form.get('category') || 'Bepul'),
    region: String(form.get('region') || ''),
    location: String(form.get('location') || '').trim(),
    emoji: String(form.get('emoji') || '📦'),
    description: String(form.get('description') || '').trim()
  };

  if (!item.title || !item.location || !item.region ||
      !Number.isFinite(item.price) || item.price < 0) {
    toast('Iltimos, barcha kerakli maydonlarni to‘g‘ri to‘ldir.');
    return;
  }

  userItems.unshift(item);

  if (!saveItems()) {
    userItems.shift();
    return;
  }

  event.target.reset();
  closeModal();
  activeCat = 'Hammasi';

  document.querySelectorAll('.cat').forEach(button => {
    button.classList.toggle('active', button.dataset.cat === 'Hammasi');
  });

  render();
  toast('E’lon saqlandi!');
});

render();
</script>
</body>
</html>


