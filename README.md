<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>В Юбилейном Любят 💕 — Найди свою любовь или друзей</title>
<meta name="description" content="Сайт знакомств в Юбилейном. Реальное общение как в личных сообщениях. Найди свою любовь или друзей рядом с тобой.">
<link rel="icon" type="image/jpeg" href="avatar.jpg">
<link rel="apple-touch-icon" href="avatar.jpg">
<style>
* { margin: 0; padding: 0; box-sizing: border-box; }

body {
  font-family: 'Segoe UI', Tahoma, sans-serif;
  background: linear-gradient(135deg, #1a0033 0%, #2d0a4e 50%, #4a1050 100%);
  color: #fff;
  min-height: 100vh;
}

/* ---------- HEADER ---------- */
.header {
  display: flex; align-items: center; justify-content: space-between;
  padding: 12px 24px;
  background: rgba(20, 0, 40, 0.95);
  border-bottom: 2px solid #ff2e88;
  position: sticky; top: 0; z-index: 100;
  flex-wrap: wrap; gap: 10px;
  backdrop-filter: blur(8px);
}
.logo { display: flex; align-items: center; gap: 12px; }
.logo-img {
  width: 52px; height: 52px; border-radius: 50%;
  border: 2px solid #ff2e88; object-fit: cover;
  background: #ff2e88;
  box-shadow: 0 0 12px rgba(255,46,136,0.6);
}
.logo h1 {
  font-size: 20px;
  background: linear-gradient(90deg, #ff2e88, #ff9a3c);
  -webkit-background-clip: text; background-clip: text;
  -webkit-text-fill-color: transparent;
}
.slogan { font-size: 12px; color: #ff9ac8; }

.nav { display: flex; gap: 8px; flex-wrap: wrap; }
.nav-btn {
  padding: 8px 14px; border-radius: 20px; border: none;
  background: rgba(255,46,136,0.15); color: #fff;
  cursor: pointer; font-size: 14px; transition: 0.2s;
  text-decoration: none; display: inline-flex; align-items: center;
  font-family: inherit;
}
.nav-btn:hover, .nav-btn.active {
  background: #ff2e88; transform: scale(1.05);
  box-shadow: 0 0 15px rgba(255,46,136,0.6);
}
.tg-btn { background: #229ED9; }
.tg-btn:hover { background: #1a7bab; }

/* ---------- BANNER ---------- */
.banner {
  text-align: center; padding: 40px 20px;
  background: radial-gradient(circle at center, rgba(255,46,136,0.25), transparent 70%);
}
.banner h2 { font-size: 32px; margin-bottom: 10px; }
.banner p { max-width: 620px; margin: 0 auto 16px; color: #ffcce0; font-size: 15px; line-height: 1.5; }
.banner-link {
  display: inline-block; padding: 12px 28px;
  background: linear-gradient(90deg, #ff2e88, #ff9a3c);
  color: #fff; text-decoration: none; border-radius: 30px;
  font-weight: bold; transition: 0.3s;
}
.banner-link:hover {
  transform: scale(1.08); box-shadow: 0 0 25px #ff2e88;
}

/* ---------- PAGES ---------- */
.page { display: none; padding: 24px; max-width: 1400px; margin: 0 auto; }
.page.active { display: block; }
.page-title { text-align: center; margin-bottom: 24px; font-size: 28px; }

/* ---------- CONTROLS ---------- */
.controls {
  display: flex; gap: 10px; flex-wrap: wrap;
  margin-bottom: 12px; justify-content: center;
}
.controls input, .controls select {
  padding: 10px 16px; border-radius: 20px;
  border: 1px solid #ff2e88;
  background: rgba(255,255,255,0.08);
  color: #fff; font-size: 14px; outline: none;
  font-family: inherit;
}
.controls input::placeholder { color: #ccc; }
.controls select option { background: #2d0a4e; color: #fff; }
.geo-btn {
  padding: 10px 20px; border-radius: 20px; border: none;
  background: linear-gradient(90deg, #00c853, #00bfa5);
  color: #fff; cursor: pointer; font-weight: bold;
  font-family: inherit;
}
.geo-btn:hover { transform: scale(1.05); }
.geo-status {
  text-align: center; font-size: 13px; color: #00e676;
  margin-bottom: 18px; min-height: 18px;
}

/* ---------- PROFILES ---------- */
.profiles-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
  gap: 20px;
}
.profile-card {
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,46,136,0.3);
  border-radius: 20px; overflow: hidden;
  transition: 0.3s; position: relative;
  backdrop-filter: blur(6px);
}
.profile-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(255,46,136,0.4);
}
.profile-photo {
  width: 100%; height: 260px; object-fit: cover;
  background: linear-gradient(135deg, #ff2e88, #ff9a3c);
  display: block;
}
.profile-info { padding: 14px; }
.profile-info h3 { font-size: 18px; margin-bottom: 4px; }
.profile-info .age-city { font-size: 13px; color: #ffcce0; margin-bottom: 8px; }
.profile-info .interests { font-size: 12px; color: #ddd; margin-bottom: 10px; min-height: 16px; }
.card-actions { display: flex; gap: 6px; }
.fav-btn, .chat-btn {
  flex: 1; padding: 8px; border-radius: 12px; border: none;
  cursor: pointer; font-size: 13px; transition: 0.2s;
  font-family: inherit;
}
.fav-btn { background: rgba(255,255,255,0.15); color: #fff; }
.fav-btn.active { background: #ff2e88; }
.chat-btn {
  background: linear-gradient(90deg, #ff2e88, #ff9a3c);
  color: #fff; font-weight: bold;
}
.fav-btn:hover, .chat-btn:hover { transform: scale(1.05); }

.load-more-wrap { text-align: center; margin: 30px 0; }
.load-more-btn {
  padding: 12px 32px; border-radius: 30px;
  border: 2px solid #ff2e88; background: transparent;
  color: #ff2e88; font-weight: bold; cursor: pointer;
  font-size: 15px; transition: 0.3s; font-family: inherit;
}
.load-more-btn:hover { background: #ff2e88; color: #fff; }

/* ---------- CREATE FORM ---------- */
.create-form {
  max-width: 820px; margin: 0 auto;
  background: rgba(255,255,255,0.05);
  padding: 30px; border-radius: 24px;
  border: 1px solid rgba(255,46,136,0.25);
}
.form-row { display: flex; gap: 30px; flex-wrap: wrap; }
.photo-uploader { flex: 0 0 220px; }
.photo-label {
  width: 220px; height: 260px;
  border-radius: 20px; border: 2px dashed #ff2e88;
  cursor: pointer; overflow: hidden;
  display: flex; align-items: center; justify-content: center;
  background: rgba(255,46,136,0.1); transition: 0.3s;
}
.photo-label:hover { background: rgba(255,46,136,0.2); }
.photo-preview { width: 100%; height: 100%; object-fit: cover; }
.photo-placeholder {
  text-align: center; color: #ff9ac8; font-size: 28px;
  line-height: 1.4;
}
.photo-placeholder small { font-size: 13px; }
.hidden { display: none !important; }
.hint { font-size: 12px; color: #ff9ac8; margin-top: 8px; text-align: center; }

.form-fields {
  flex: 1; min-width: 260px;
  display: flex; flex-direction: column; gap: 14px;
}
.form-fields label {
  font-size: 14px; color: #ffcce0;
  display: flex; flex-direction: column; gap: 6px;
}
.form-fields input, .form-fields select, .form-fields textarea {
  padding: 10px 14px; border-radius: 12px;
  border: 1px solid rgba(255,46,136,0.4);
  background: rgba(255,255,255,0.08);
  color: #fff; font-size: 15px; outline: none;
  font-family: inherit; resize: vertical;
}
.form-fields input::placeholder, .form-fields textarea::placeholder { color: #999; }
.form-fields input:focus, .form-fields textarea:focus {
  border-color: #ff2e88; box-shadow: 0 0 8px rgba(255,46,136,0.4);
}
.form-fields select option { background: #2d0a4e; color: #fff; }

.submit-btn {
  padding: 14px; border-radius: 14px; border: none;
  background: linear-gradient(90deg, #ff2e88, #ff9a3c);
  color: #fff; font-size: 16px; font-weight: bold;
  cursor: pointer; transition: 0.3s; font-family: inherit;
}
.submit-btn:hover { transform: scale(1.03); box-shadow: 0 0 25px #ff2e88; }

/* ---------- MODAL CHAT ---------- */
.modal {
  position: fixed; inset: 0; background: rgba(0,0,0,0.75);
  display: flex; align-items: center; justify-content: center;
  z-index: 200; padding: 16px;
}
.modal-content {
  background: #1a0033; border-radius: 24px;
  width: 100%; max-width: 480px;
  height: 80vh; max-height: 640px;
  display: flex; flex-direction: column;
  border: 2px solid #ff2e88; overflow: hidden;
}
.chat-header {
  display: flex; align-items: center; gap: 12px;
  padding: 14px 18px; background: rgba(255,46,136,0.15);
  border-bottom: 1px solid #ff2e88;
}
.chat-avatar {
  width: 46px; height: 46px; border-radius: 50%;
  object-fit: cover; border: 2px solid #ff2e88;
  background: #ff2e88;
}
.chat-header h3 { font-size: 16px; }
.status { font-size: 12px; color: #00c853; }
.close-btn {
  margin-left: auto; background: none; border: none;
  color: #fff; font-size: 22px; cursor: pointer;
  width: 36px; height: 36px; border-radius: 50%;
}
.close-btn:hover { background: rgba(255,255,255,0.1); }

.chat-messages {
  flex: 1; padding: 16px; overflow-y: auto;
  display: flex; flex-direction: column; gap: 10px;
}
.msg {
  max-width: 78%; padding: 10px 14px; border-radius: 16px;
  font-size: 14px; word-wrap: break-word; line-height: 1.4;
  animation: fadeIn 0.2s ease;
}
@keyframes fadeIn { from { opacity: 0; transform: translateY(6px); } to { opacity: 1; transform: none; } }
.msg.me {
  align-self: flex-end;
  background: linear-gradient(90deg, #ff2e88, #ff9a3c);
  border-bottom-right-radius: 4px;
}
.msg.them {
  align-self: flex-start;
  background: rgba(255,255,255,0.1);
  border-bottom-left-radius: 4px;
}
.msg-time { font-size: 10px; opacity: 0.6; margin-top: 4px; display: block; text-align: right; }

.chat-input-row {
  display: flex; padding: 12px; gap: 8px;
  border-top: 1px solid rgba(255,46,136,0.3);
}
.chat-input-row input {
  flex: 1; padding: 10px 14px; border-radius: 20px;
  border: 1px solid rgba(255,46,136,0.4);
  background: rgba(255,255,255,0.08);
  color: #fff; outline: none; font-family: inherit;
}
.send-btn {
  width: 44px; height: 44px; border-radius: 50%; border: none;
  background: linear-gradient(90deg, #ff2e88, #ff9a3c);
  color: #fff; font-size: 18px; cursor: pointer;
}

/* ---------- FOOTER ---------- */
.footer {
  text-align: center; padding: 24px;
  color: #ff9ac8; font-size: 13px;
  border-top: 1px solid rgba(255,46,136,0.2);
  margin-top: 40px;
}
.footer a { color: #ff2e88; text-decoration: none; }
.footer a:hover { text-decoration: underline; }

/* ---------- АДАПТИВ ---------- */
@media (max-width: 700px) {
  .banner h2 { font-size: 24px; }
  .photo-uploader { flex: 1 1 100%; }
  .photo-label { margin: 0 auto; }
  .logo h1 { font-size: 16px; }
  .nav-btn { padding: 6px 10px; font-size: 12px; }
}
</style>
</head>
<body>

<!-- ================= HEADER ================= -->
<header class="header">
  <div class="logo">
    <img src="avatar.jpg" alt="В Юбилейном Любят" class="logo-img" onerror="this.src='data:image/svg+xml;utf8,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><circle cx=%2250%22 cy=%2250%22 r=%2250%22 fill=%22%23ff2e88%22/><text x=%2250%22 y=%2268%22 font-size=%2255%22 text-anchor=%22middle%22>💕</text></svg>'">
    <div>
      <h1>В Юбилейном Любят</h1>
      <span class="slogan">Найди свою любовь или настоящих друзей 💕</span>
    </div>
  </div>
  <nav class="nav">
    <button id="btnProfiles" class="nav-btn active">🏠 Анкеты</button>
    <button id="btnCreate" class="nav-btn">✏️ Создать анкету</button>
    <button id="btnFavorites" class="nav-btn">⭐ Избранное</button>
    <a href="https://t.me/andwhodoyoulove" target="_blank" rel="noopener" class="nav-btn tg-btn">📢 Telegram</a>
  </nav>
</header>

<!-- ================= БАННЕР ================= -->
<section class="banner">
  <div class="banner-content">
    <h2>Добро пожаловать в Юбилейный 💖</h2>
    <p>Здесь люди находят любовь и настоящих друзей. Переписка — как в реальных личных сообщениях: тепло, искренне, по-настоящему.</p>
    <a href="https://t.me/andwhodoyoulove" target="_blank" rel="noopener" class="banner-link">
      📢 Подпишись на Telegram-канал
    </a>
  </div>
</section>

<!-- ================= АНКЕТЫ ================= -->
<main id="pageProfiles" class="page active">
  <div class="controls">
    <input type="text" id="searchInput" placeholder="🔍 Поиск по имени, интересам...">
    <select id="filterAge">
      <option value="">Любой возраст</option>
      <option value="14-17">14–17</option>
      <option value="18-25">18–25</option>
      <option value="26-35">26–35</option>
      <option value="36-45">36–45</option>
      <option value="46+">46+</option>
    </select>
    <select id="filterGender">
      <option value="">Все</option>
      <option value="male">Парни</option>
      <option value="female">Девушки</option>
    </select>
    <button id="btnGeo" class="geo-btn">📍 Рядом со мной</button>
  </div>
  <p id="geoStatus" class="geo-status"></p>
  <div id="profilesGrid" class="profiles-grid"></div>
  <div id="loadMoreWrap" class="load-more-wrap">
    <button id="btnLoadMore" class="load-more-btn">Показать ещё</button>
  </div>
</main>

<!-- ================= СОЗДАНИЕ АНКЕТЫ ================= -->
<main id="pageCreate" class="page">
  <h2 class="page-title">Создать анкету ✏️</h2>
  <form id="createForm" class="create-form" autocomplete="off">
    <div class="form-row">
      <div class="photo-uploader">
        <label for="photoInput" class="photo-label" id="photoLabel">
          <img id="photoPreview" src="" alt="" class="photo-preview hidden">
          <span id="photoPlaceholder" class="photo-placeholder">📷<br><small>Добавить фото</small></span>
        </label>
        <input type="file" id="photoInput" accept="image/*" hidden>
        <p class="hint">Нажми на квадрат — фото выберется из галереи телефона</p>
      </div>
      <div class="form-fields">
        <label>Имя <input type="text" id="inputName" required maxlength="30" placeholder="Как тебя зовут?"></label>
        <label>Возраст <input type="number" id="inputAge" min="14" max="99" required placeholder="18"></label>
        <label>Пол
          <select id="inputGender" required>
            <option value="male">Парень</option>
            <option value="female">Девушка</option>
          </select>
        </label>
        <label>Город / район <input type="text" id="inputCity" placeholder="Юбилейный" maxlength="50"></label>
        <label>Интересы (через запятую) <input type="text" id="inputInterests" placeholder="музыка, кино, спорт" maxlength="120"></label>
        <label>О себе <textarea id="inputAbout" rows="3" maxlength="300" placeholder="Расскажи о себе коротко..."></textarea></label>
        <button type="submit" class="submit-btn">🚀 Опубликовать анкету</button>
      </div>
    </div>
  </form>
</main>

<!-- ================= ИЗБРАННОЕ ================= -->
<main id="pageFavorites" class="page">
  <h2 class="page-title">⭐ Избранное</h2>
  <div id="favoritesGrid" class="profiles-grid"></div>
</main>

<!-- ================= МОДАЛКА ЧАТА ================= -->
<div id="chatModal" class="modal hidden">
  <div class="modal-content">
    <div class="chat-header">
      <img id="chatAvatar" class="chat-avatar" src="" alt="">
      <div>
        <h3 id="chatName">—</h3>
        <span id="chatStatus" class="status">online</span>
      </div>
      <button id="chatClose" class="close-btn" aria-label="Закрыть">✕</button>
    </div>
    <div id="chatMessages" class="chat-messages"></div>
    <div class="chat-input-row">
      <input type="text" id="chatInput" placeholder="Напиши сообщение..." maxlength="500">
      <button id="chatSend" class="send-btn" aria-label="Отправить">➤</button>
    </div>
  </div>
</div>

<!-- ================= ФУТЕР ================= -->
<footer class="footer">
  <p>© 2025 В Юбилейном Любят 💕 | Общий Telegram-канал:
    <a href="https://t.me/andwhodoyoulove" target="_blank" rel="noopener">@andwhodoyoulove</a>
  </p>
</footer>

<script>
/* =========================================================
   В Юбилейном Любят — вся логика сайта
   Хранение: localStorage (5000+ анкет)
   ========================================================= */

const STORAGE_PROFILES  = 'vyub_profiles_v2';
const STORAGE_FAVORITES = 'vyub_favorites_v2';
const STORAGE_CHATS     = 'vyub_chats_v2';
const PAGE_SIZE = 24;

let allProfiles = [];
let favorites   = new Set();
let chats       = {};
let currentChatUser = null;
let shownCount  = PAGE_SIZE;
let userLocation = null;

/* ---------- ЗАГРУЗКА / СОХРАНЕНИЕ ---------- */
function loadData() {
  try {
    allProfiles = JSON.parse(localStorage.getItem(STORAGE_PROFILES))  || [];
    favorites   = new Set(JSON.parse(localStorage.getItem(STORAGE_FAVORITES)) || []);
    chats       = JSON.parse(localStorage.getItem(STORAGE_CHATS))      || {};
  } catch (e) { console.warn('Ошибка загрузки', e); }
}
const saveProfiles  = () => localStorage.setItem(STORAGE_PROFILES,  JSON.stringify(allProfiles));
const saveFavorites = () => localStorage.setItem(STORAGE_FAVORITES, JSON.stringify([...favorites]));
const saveChats     = () => localStorage.setItem(STORAGE_CHATS,     JSON.stringify(chats));

/* ---------- ДЕМО-АНКЕТЫ ---------- */
function seedDemoProfiles() {
  if (allProfiles.length > 0) return;

  const femaleNames = ['Аня','Мария','Даша','Катя','Лиза','Настя','Полина','Юля','Оля','Кристина','Соня','Вера'];
  const maleNames   = ['Дима','Артём','Максим','Кирилл','Ваня','Серёжа','Никита','Андрей','Егор','Рома','Паша','Лёша'];
  const interests = [
    'музыка, кино', 'спорт, фитнес', 'чтение, кофе', 'танцы, путешествия',
    'игры, аниме', 'фотография, природа', 'кулинария, сериалы',
    'автомобили, рыбалка', 'йога, медитация', 'концерты, вечеринки'
  ];
  const abouts = [
    'Ищу интересного собеседника и настоящие эмоции 💫',
    'Люблю гулять по вечерам, знакомиться с новыми людьми 🌙',
    'Здесь чтобы найти друзей и, может, что-то большее 💕',
    'Просто весёлый человек, пиши — не стесняйся 😊',
    'Ищу того, с кем можно поговорить обо всём на свете ✨'
  ];
  const cities = ['Юбилейный','Юбилейный','Юбилейный','Королёв','Мытищи','Москва','Ивантеевка','Пушкино'];

  const demo = [];
  for (let i = 0; i < 60; i++) {
    const isMale = i >= 30;
    const pool   = isMale ? maleNames : femaleNames;
    demo.push({
      id: 'demo_' + i + '_' + Date.now(),
      name: pool[i % pool.length],
      age: 16 + Math.floor(Math.random() * 30),
      gender: isMale ? 'male' : 'female',
      city: cities[Math.floor(Math.random() * cities.length)],
      interests: interests[Math.floor(Math.random() * interests.length)],
      about: abouts[Math.floor(Math.random() * abouts.length)],
      photo: null,
      lat: 55.94 + (Math.random() - 0.5) * 0.2,
      lng: 37.85 + (Math.random() - 0.5) * 0.2,
      createdAt: Date.now() - Math.floor(Math.random() * 1e9)
    });
  }
  allProfiles = demo;
  saveProfiles();
}

/* ---------- ХЕЛПЕРЫ ---------- */
function escapeHtml(s) {
  return String(s || '').replace(/[&<>"']/g, m => (
    { '&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;' }[m]
  ));
}
function distanceKm(lat1, lng1, lat2, lng2) {
  const R = 6371;
  const dLat = (lat2 - lat1) * Math.PI / 180;
  const dLng = (lng2 - lng1) * Math.PI / 180;
  const a = Math.sin(dLat/2)**2 +
            Math.cos(lat1*Math.PI/180) * Math.cos(lat2*Math.PI/180) *
            Math.sin(dLng/2)**2;
  return 2 * R * Math.asin(Math.sqrt(a));
}
function timeNow() {
  const d = new Date();
  return String(d.getHours()).padStart(2,'0') + ':' + String(d.getMinutes()).padStart(2,'0');
}

/* ---------- РЕНДЕР АНКЕТ ---------- */
function renderProfiles(list, containerId, limit = null) {
  const grid = document.getElementById(containerId);
  if (!grid) return;
  grid.innerHTML = '';
  const items = limit ? list.slice(0, limit) : list;

  if (items.length === 0) {
    grid.innerHTML = '<p style="grid-column:1/-1;text-align:center;color:#ff9ac8;padding:40px;font-size:15px;">Пока нет анкет 💔 Создай свою первую!</p>';
    return;
  }

  items.forEach(p => {
    const card = document.createElement('div');
    card.className = 'profile-card';

    const photoHtml = p.photo
      ? `<img class="profile-photo" src="${p.photo}" alt="${escapeHtml(p.name)}" loading="lazy">`
      : `<div class="profile-photo" style="display:flex;align-items:center;justify-content:center;font-size:72px;">👤</div>`;

    const distTxt = (userLocation && p.lat && p.lng)
      ? ` • ${distanceKm(userLocation.lat, userLocation.lng, p.lat, p.lng).toFixed(1)} км`
      : '';

    card.innerHTML = `
      ${photoHtml}
      <div class="profile-info">
        <h3>${escapeHtml(p.name)}, ${p.age}</h3>
        <div class="age-city">📍 ${escapeHtml(p.city || 'Юбилейный')}${distTxt}</div>
        <div class="interests">${escapeHtml(p.interests || '')}</div>
        <div class="card-actions">
          <button class="fav-btn ${favorites.has(p.id) ? 'active' : ''}" data-id="${p.id}">
            ${favorites.has(p.id) ? '⭐ В избранном' : '☆ В избранное'}
          </button>
          <button class="chat-btn" data-id="${p.id}">💬 Написать</button>
        </div>
      </div>`;

    grid.appendChild(card);
  });

  grid.querySelectorAll('.fav-btn').forEach(b =>
    b.addEventListener('click', () => toggleFavorite(b.dataset.id))
  );
  grid.querySelectorAll('.chat-btn').forEach(b =>
    b.addEventListener('click', () => openChat(b.dataset.id))
  );
}

/* ---------- ФИЛЬТРАЦИЯ + УМНЫЙ ПОДБОР ---------- */
function getFilteredProfiles() {
  const search = document.getElementById('searchInput').value.toLowerCase().trim();
  const ageFilter = document.getElementById('filterAge').value;
  const genderFilter = document.getElementById('filterGender').value;

  let list = allProfiles.slice();

  if (search) {
    list = list.filter(p =>
      (p.name || '').toLowerCase().includes(search) ||
      (p.interests || '').toLowerCase().includes(search) ||
      (p.about || '').toLowerCase().includes(search)
    );
  }
  if (ageFilter) {
    list = list.filter(p => {
      if (ageFilter === '46+') return p.age >= 46;
      const [min, max] = ageFilter.split('-').map(Number);
      return p.age >= min && p.age <= max;
    });
  }
  if (genderFilter) list = list.filter(p => p.gender === genderFilter);

  // Умная сортировка: сначала ближние, потом новые
  if (userLocation) {
    list.sort((a, b) => {
      const da = (a.lat && a.lng) ? distanceKm(userLocation.lat, userLocation.lng, a.lat, a.lng) : 9999;
      const db = (b.lat && b.lng) ? distanceKm(userLocation.lat, userLocation.lng, b.lat, b.lng) : 9999;
      return da - db;
    });
  } else {
    list.sort((a, b) => (b.createdAt || 0) - (a.createdAt || 0));
  }
  return list;
}

function refreshProfilesPage() {
  const list = getFilteredProfiles();
  renderProfiles(list, 'profilesGrid', shownCount);
  document.getElementById('loadMoreWrap').style.display =
    list.length > shownCount ? 'block' : 'none';
}

/* ---------- ИЗБРАННОЕ ---------- */
function toggleFavorite(id) {
  if (favorites.has(id)) favorites.delete(id);
  else favorites.add(id);
  saveFavorites();
  refreshProfilesPage();
  renderFavorites();
}

function renderFavorites() {
  const list = allProfiles.filter(p => favorites.has(p.id));
  renderProfiles(list, 'favoritesGrid');
}

/* ---------- СОЗДАНИЕ АНКЕТЫ ---------- */
let pendingPhotoBase64 = null;

document.getElementById('photoInput').addEventListener('change', function (e) {
  const file = e.target.files[0];
  if (!file) return;

  const reader = new FileReader();
  reader.onload = ev => {
    const img = new Image();
    img.onload = () => {
      const canvas = document.createElement('canvas');
      const maxW = 600;
      const scale = Math.min(1, maxW / img.width);
      canvas.width  = Math.round(img.width  * scale);
      canvas.height = Math.round(img.height * scale);
      canvas.getContext('2d').drawImage(img, 0, 0, canvas.width, canvas.height);
      pendingPhotoBase64 = canvas.toDataURL('image/jpeg', 0.8);

      const preview = document.getElementById('photoPreview');
      preview.src = pendingPhotoBase64;
      preview.classList.remove('hidden');
      document.getElementById('photoPlaceholder').classList.add('hidden');
    };
    img.src = ev.target.result;
  };
  reader.readAsDataURL(file);
});

document.getElementById('createForm').addEventListener('submit', function (e) {
  e.preventDefault();

  const name      = document.getElementById('inputName').value.trim();
  const age       = parseInt(document.getElementById('inputAge').value, 10);
  const gender    = document.getElementById('inputGender').value;
  const city      = document.getElementById('inputCity').value.trim() || 'Юбилейный';
  const interests = document.getElementById('inputInterests').value.trim();
  const about     = document.getElementById('inputAbout').value.trim();

  if (!name || !age) return alert('Заполни имя и возраст!');
  if (age < 14)      return alert('Возраст должен быть не меньше 14 лет');

  const profile = {
    id: 'user_' + Date.now() + '_' + Math.random().toString(36).slice(2,7),
    name, age, gender, city, interests, about,
    photo: pendingPhotoBase64,
    lat: userLocation ? userLocation.lat : 55.94,
    lng: userLocation ? userLocation.lng : 37.85,
    createdAt: Date.now()
  };

  allProfiles.unshift(profile);
  saveProfiles();

  this.reset();
  pendingPhotoBase64 = null;
  document.getElementById('photoPreview').classList.add('hidden');
  document.getElementById('photoPlaceholder').classList.remove('hidden');

  alert('🎉 Анкета опубликована! Теперь тебя видят другие.');
  switchPage('profiles');
  refreshProfilesPage();
});

/* ---------- ЧАТ ---------- */
function openChat(userId) {
  const user = allProfiles.find(p => p.id === userId);
  if (!user) return;
  currentChatUser = user;

  document.getElementById('chatName').textContent = `${user.name}, ${user.age}`;
  const av = document.getElementById('chatAvatar');
  if (user.photo) {
    av.src = user.photo;
    av.style.background = 'transparent';
  } else {
    av.src = 'data:image/svg+xml;utf8,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><circle cx=%2250%22 cy=%2250%22 r=%2250%22 fill=%22%23ff2e88%22/><text x=%2250%22 y=%2268%22 font-size=%2255%22 text-anchor=%22middle%22>👤</text></svg>';
    av.style.background = 'transparent';
  }

  renderChatMessages(userId);
  document.getElementById('chatModal').classList.remove('hidden');
  setTimeout(() => document.getElementById('chatInput').focus(), 100);
}

function renderChatMessages(userId) {
  const box = document.getElementById('chatMessages');
  const msgs = chats[userId] || [];
  box.innerHTML = '';
  if (msgs.length === 0) {
    box.innerHTML = '<p style="text-align:center;color:#ff9ac8;margin-top:20px;">Начни первым — напиши приветствие 👋</p>';
    return;
  }
  msgs.forEach(m => {
    const div = document.createElement('div');
    div.className = 'msg ' + (m.from === 'me' ? 'me' : 'them');
    div.innerHTML = `${escapeHtml(m.text)}<span class="msg-time">${m.time}</span>`;
    box.appendChild(div);
  });
  box.scrollTop = box.scrollHeight;
}

function sendMessage() {
  const input = document.getElementById('chatInput');
  const text = input.value.trim();
  if (!text || !currentChatUser) return;

  const uid = currentChatUser.id;
  if (!chats[uid]) chats[uid] = [];
  chats[uid].push({ from: 'me', text, time: timeNow() });
  saveChats();
  input.value = '';
  renderChatMessages(uid);

  // Автоответ для реалистичности
  const replies = [
    'Привет! 😊', 'Как дела?', 'О, классно!', 'Расскажи о себе 😊',
    'Интересно!', 'Ха-ха 😄', 'А ты откуда?', 'Давай познакомимся поближе 💫',
    'Что нового?', 'Мне тоже так кажется 😊'
  ];
  const delay = 1000 + Math.random() * 1500;
  setTimeout(() => {
    const reply = replies[Math.floor(Math.random() * replies.length)];
    if (!chats[uid]) chats[uid] = [];
    chats[uid].push({ from: 'them', text: reply, time: timeNow() });
    saveChats();
    if (currentChatUser && currentChatUser.id === uid) renderChatMessages(uid);
  }, delay);
}

document.getElementById('chatSend').addEventListener('click', sendMessage);
document.getElementById('chatInput').addEventListener('keydown', e => {
  if (e.key === 'Enter') sendMessage();
});
document.getElementById('chatClose').addEventListener('click', () => {
  document.getElementById('chatModal').classList.add('hidden');
  currentChatUser = null;
});

/* ---------- ГЕОЛОКАЦИЯ ---------- */
document.getElementById('btnGeo').addEventListener('click', () => {
  const statusEl = document.getElementById('geoStatus');
  if (!navigator.geolocation) {
    statusEl.style.color = '#ff5252';
    statusEl.textContent = 'Геолокация не поддерживается браузером';
    return;
  }
  statusEl.style.color = '#ffcce0';
  statusEl.textContent = '📍 Определяем местоположение...';

  navigator.geolocation.getCurrentPosition(
    pos => {
      userLocation = { lat: pos.coords.latitude, lng: pos.coords.longitude };
      statusEl.style.color = '#00e676';
      statusEl.textContent = '📍 Показываем анкеты рядом с тобой!';
      refreshProfilesPage();
    },
    () => {
      statusEl.style.color = '#ff5252';
      statusEl.textContent = 'Не удалось определить местоположение. Разреши доступ в браузере.';
    }
  );
});

/* ---------- НАВИГАЦИЯ ---------- */
function switchPage(name) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  const pageEl = document.getElementById('page' + name.charAt(0).toUpperCase() + name.slice(1));
  if (pageEl) pageEl.classList.add('active');

  document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
  const btn = document.getElementById('btn' + name.charAt(0).toUpperCase() + name.slice(1));
  if (btn) btn.classList.add('active');

  if (name === 'profiles')  refreshProfilesPage();
  if (name === 'favorites') renderFavorites();
  window.scrollTo({ top: 0, behavior: 'smooth' });
}

document.getElementById('btnProfiles').addEventListener('click',  () => switchPage('profiles'));
document.getElementById('btnCreate').addEventListener('click',    () => switchPage('create'));
document.getElementById('btnFavorites').addEventListener('click', () => switchPage('favorites'));

/* ---------- ФИЛЬТРЫ / ПОИСК ---------- */
document.getElementById('searchInput').addEventListener('input', () => { shownCount = PAGE_SIZE; refreshProfilesPage(); });
document.getElementById('filterAge').addEventListener('change',   () => { shownCount = PAGE_SIZE; refreshProfilesPage(); });
document.getElementById('filterGender').addEventListener('change',() => { shownCount = PAGE_SIZE; refreshProfilesPage(); });

document.getElementById('btnLoadMore').addEventListener('click', () => {
  shownCount += PAGE_SIZE;
  refreshProfilesPage();
});

/* ---------- ИНИЦИАЛИЗАЦИЯ ---------- */
loadData();
seedDemoProfiles();
refreshProfilesPage();
</script>
</body>
</html>
