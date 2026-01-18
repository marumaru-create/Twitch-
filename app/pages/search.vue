<template>
  <div class="search-page">
    <header class="search-hero">
      <div class="search-hero__content">
        <p class="search-hero__eyebrow">Search</p>
        <h1>検索結果</h1>
        <p class="search-hero__subtitle">
          「ゲーム実況」で 128 件の検索結果
        </p>
        <div class="search-hero__bar">
          <input
            type="text"
            class="search-hero__input"
            placeholder="キーワードを入力"
            value="ゲーム実況"
          />
          <button class="search-hero__button">検索</button>
        </div>
      </div>
      <div class="search-hero__stats">
        <div>
          <p class="search-hero__label">並び替え</p>
          <select>
            <option>関連度順</option>
            <option>新着順</option>
            <option>視聴者数順</option>
          </select>
        </div>
        <div>
          <p class="search-hero__label">フィルター</p>
          <div class="search-hero__chips">
            <button class="chip chip--active">すべて</button>
            <button class="chip">ライブ</button>
            <button class="chip">アーカイブ</button>
            <button class="chip">クリップ</button>
          </div>
        </div>
      </div>
    </header>

    <section class="search-grid">
      <article v-for="result in results" :key="result.id" class="result-card">
        <div class="result-card__thumb">
          <span class="result-card__badge">{{ result.type }}</span>
          <span class="result-card__viewers">{{ result.viewers }} viewers</span>
        </div>
        <div class="result-card__body">
          <div class="result-card__meta">
            <span class="result-card__category">{{ result.category }}</span>
            <span>•</span>
            <span>{{ result.duration }}</span>
          </div>
          <h3>{{ result.title }}</h3>
          <p class="result-card__channel">{{ result.channel }}</p>
          <p class="result-card__summary">{{ result.summary }}</p>
          <div class="result-card__tags">
            <span v-for="tag in result.tags" :key="tag" class="tag">{{ tag }}</span>
          </div>
        </div>
      </article>
    </section>

    <footer class="search-footer">
      <button class="search-footer__button">さらに読み込む</button>
      <p class="search-footer__note">表示中: 1-12 / 128 件</p>
    </footer>
  </div>
</template>

<script setup>
const results = [
  {
    id: 1,
    type: "LIVE",
    viewers: "24.1K",
    category: "Valorant",
    duration: "2:31:10",
    title: "深夜のランク戦を本気で駆け上がる",
    channel: "Noa_Studio",
    summary: "今日は新しい戦術を試しながらフルパで挑戦。",
    tags: ["日本語", "プロ", "FPS"],
  },
  {
    id: 2,
    type: "CLIP",
    viewers: "8.2K",
    category: "Just Chatting",
    duration: "00:45",
    title: "リスナーからの面白い質問まとめ",
    channel: "MimiTalk",
    summary: "雑談配信で盛り上がったシーンをピックアップ。",
    tags: ["雑談", "切り抜き"],
  },
  {
    id: 3,
    type: "LIVE",
    viewers: "15.9K",
    category: "Apex Legends",
    duration: "1:12:54",
    title: "新シーズンのランクを調査！",
    channel: "AoiGaming",
    summary: "パッチ内容を確認しながらマップを探索。",
    tags: ["日本語", "ランク", "解説"],
  },
  {
    id: 4,
    type: "VOD",
    viewers: "3.4K",
    category: "Minecraft",
    duration: "4:05:12",
    title: "巨大都市建築プロジェクト Day 12",
    channel: "BuildWithNao",
    summary: "街の中心部に新しい広場を作ります。",
    tags: ["建築", "サバイバル"],
  },
  {
    id: 5,
    type: "LIVE",
    viewers: "19.6K",
    category: "Fortnite",
    duration: "3:44:21",
    title: "トーナメント直前練習！",
    channel: "RikuPlay",
    summary: "チームの連携を確認しながら試合を回します。",
    tags: ["日本語", "大会"],
  },
  {
    id: 6,
    type: "CLIP",
    viewers: "5.8K",
    category: "Overwatch 2",
    duration: "01:12",
    title: "神グレで試合を決めた瞬間",
    channel: "LunaOW",
    summary: "オーバータイムの逆転劇がこちら。",
    tags: ["ハイライト", "短編"],
  },
  {
    id: 7,
    type: "VOD",
    viewers: "2.2K",
    category: "League of Legends",
    duration: "5:40:03",
    title: "初心者向けビルド講座",
    channel: "CoachHana",
    summary: "ロールごとの立ち回りを丁寧に解説します。",
    tags: ["解説", "初心者"],
  },
  {
    id: 8,
    type: "LIVE",
    viewers: "12.7K",
    category: "Street Fighter 6",
    duration: "2:05:41",
    title: "ランク配信: マスター帯へ挑戦",
    channel: "KenBox",
    summary: "課題をメモしながら成長配信。",
    tags: ["格闘ゲーム", "日本語"],
  },
  {
    id: 9,
    type: "VOD",
    viewers: "4.9K",
    category: "Splatoon 3",
    duration: "3:15:00",
    title: "チーム練習と作戦会議",
    channel: "InkWave",
    summary: "大会に向けて戦略を練り直します。",
    tags: ["チーム", "戦略"],
  },
  {
    id: 10,
    type: "LIVE",
    viewers: "21.3K",
    category: "GTA V",
    duration: "2:54:06",
    title: "カジノ強盗で大混乱！？",
    channel: "NightCrew",
    summary: "新メンバーとミッションに挑戦。",
    tags: ["RP", "コメディ"],
  },
  {
    id: 11,
    type: "CLIP",
    viewers: "9.1K",
    category: "Horror",
    duration: "00:38",
    title: "叫び声注意！ホラーゲームの絶叫シーン",
    channel: "SoraPlay",
    summary: "驚きの瞬間をまとめました。",
    tags: ["ホラー", "切り抜き"],
  },
  {
    id: 12,
    type: "LIVE",
    viewers: "13.0K",
    category: "Sports",
    duration: "1:50:30",
    title: "eスポーツ大会実況",
    channel: "ArenaVision",
    summary: "実況解説付きで試合の熱さを伝えます。",
    tags: ["実況", "大会"],
  },
];
</script>

<style scoped>
:global(body) {
  margin: 0;
  font-family: "Inter", "Noto Sans JP", system-ui, sans-serif;
  background: #0f0f14;
  color: #f7f7fb;
}

.search-page {
  min-height: 100vh;
  padding: 48px clamp(24px, 6vw, 96px) 64px;
  background: radial-gradient(circle at top, rgba(145, 71, 255, 0.2), transparent 50%),
    #0f0f14;
}

.search-hero {
  display: grid;
  grid-template-columns: minmax(240px, 1fr) minmax(220px, 320px);
  gap: 32px;
  margin-bottom: 40px;
  background: rgba(24, 24, 32, 0.85);
  border-radius: 24px;
  padding: 32px;
  border: 1px solid rgba(145, 71, 255, 0.2);
}

.search-hero__content h1 {
  font-size: clamp(28px, 3vw, 40px);
  margin: 8px 0 8px;
}

.search-hero__eyebrow {
  text-transform: uppercase;
  font-size: 12px;
  letter-spacing: 0.24em;
  color: rgba(255, 255, 255, 0.6);
}

.search-hero__subtitle {
  color: rgba(255, 255, 255, 0.7);
  margin-bottom: 20px;
}

.search-hero__bar {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}

.search-hero__input {
  flex: 1 1 220px;
  padding: 12px 16px;
  border-radius: 12px;
  border: 1px solid rgba(255, 255, 255, 0.12);
  background: rgba(10, 10, 16, 0.9);
  color: #fff;
}

.search-hero__button {
  padding: 12px 20px;
  border-radius: 12px;
  border: none;
  background: #9147ff;
  color: #fff;
  font-weight: 600;
  cursor: pointer;
}

.search-hero__stats {
  display: grid;
  gap: 16px;
}

.search-hero__label {
  font-size: 12px;
  text-transform: uppercase;
  letter-spacing: 0.2em;
  color: rgba(255, 255, 255, 0.5);
  margin-bottom: 8px;
}

.search-hero__stats select {
  width: 100%;
  padding: 10px 12px;
  border-radius: 12px;
  border: 1px solid rgba(255, 255, 255, 0.12);
  background: rgba(10, 10, 16, 0.8);
  color: #fff;
}

.search-hero__chips {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}

.chip {
  padding: 6px 12px;
  border-radius: 999px;
  border: 1px solid rgba(255, 255, 255, 0.12);
  background: transparent;
  color: rgba(255, 255, 255, 0.8);
  cursor: pointer;
}

.chip--active {
  background: rgba(145, 71, 255, 0.2);
  border-color: rgba(145, 71, 255, 0.6);
  color: #fff;
}

.search-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 24px;
}

.result-card {
  background: rgba(24, 24, 32, 0.9);
  border-radius: 18px;
  border: 1px solid rgba(255, 255, 255, 0.08);
  overflow: hidden;
  display: flex;
  flex-direction: column;
  min-height: 320px;
}

.result-card__thumb {
  position: relative;
  background: linear-gradient(135deg, rgba(145, 71, 255, 0.3), rgba(51, 170, 255, 0.25));
  padding: 16px;
  min-height: 140px;
}

.result-card__badge {
  display: inline-block;
  background: rgba(145, 71, 255, 0.85);
  color: #fff;
  font-size: 12px;
  padding: 4px 8px;
  border-radius: 6px;
  text-transform: uppercase;
}

.result-card__viewers {
  position: absolute;
  bottom: 12px;
  left: 12px;
  font-size: 12px;
  background: rgba(0, 0, 0, 0.6);
  padding: 4px 8px;
  border-radius: 999px;
}

.result-card__body {
  padding: 16px;
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.result-card__meta {
  display: flex;
  gap: 6px;
  color: rgba(255, 255, 255, 0.6);
  font-size: 12px;
}

.result-card h3 {
  font-size: 18px;
  margin: 0;
}

.result-card__channel {
  font-weight: 600;
  margin: 0;
}

.result-card__summary {
  color: rgba(255, 255, 255, 0.7);
  font-size: 14px;
  margin: 0;
}

.result-card__tags {
  display: flex;
  gap: 6px;
  flex-wrap: wrap;
}

.tag {
  font-size: 12px;
  padding: 4px 10px;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.08);
}

.search-footer {
  margin-top: 40px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
}

.search-footer__button {
  padding: 12px 24px;
  border-radius: 12px;
  border: 1px solid rgba(145, 71, 255, 0.6);
  background: rgba(145, 71, 255, 0.15);
  color: #fff;
  font-weight: 600;
  cursor: pointer;
}

.search-footer__note {
  color: rgba(255, 255, 255, 0.6);
}

@media (max-width: 900px) {
  .search-hero {
    grid-template-columns: 1fr;
  }
}
</style>
