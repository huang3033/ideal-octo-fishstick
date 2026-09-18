<template>
  <section class="scene">
    <!-- 暗角晕染 -->
    <div class="vignette"></div>

    <!-- 朱砂落日 -->
    <div class="sun"></div>

    <!-- 层叠水墨远山 -->
    <div class="mountains">
      <div class="mtn far-l"></div>
      <div class="mtn far-r"></div>
      <div class="mist"></div>
      <div class="mtn mid-l"></div>
      <div class="mtn mid-r"></div>
      <div class="mtn near-l"></div>
      <div class="mtn near-r"></div>
    </div>

    <!-- 飞鸟 -->
    <svg class="bird bird-1" viewBox="0 0 60 24" fill="none">
      <path d="M2,18 q14,-16 28,0 q14,-16 28,0" stroke="#2B2926" stroke-width="3" fill="none" stroke-linecap="round" />
    </svg>
    <svg class="bird bird-2" viewBox="0 0 44 18" fill="none">
      <path d="M2,14 q10,-12 20,0 q10,-12 20,0" stroke="#2B2926" stroke-width="2.5" fill="none" stroke-linecap="round" />
    </svg>

    <!-- 文案 -->
    <p class="brand-top">墨境 · 东方美学平台</p>
    <h1 class="brand-title">墨境</h1>
    <div class="seal">墨</div>
    <p class="brand-en">M O J I N G</p>
    <p class="tagline">落笔成境 · 水墨为门</p>

    <p class="copyright">版权所有 2026 墨境 MOJING · 水墨之间，遇见东方</p>
  </section>
</template>

<script setup></script>

<style scoped>
.scene {
  position: relative;
  width: 835px;
  height: 900px;
  flex: 0 0 835px;
  background: var(--paper);
  overflow: hidden;
  transition: background 0.4s ease;
}

/* 暗角：中心透明 → 四周淡墨晕染 */
.vignette {
  position: absolute;
  inset: -60px;
  background: radial-gradient(
    circle at 50% 45%,
    transparent 38%,
    var(--vignette) 100%
  );
  pointer-events: none;
}

/* 朱砂落日 */
.sun {
  position: absolute;
  left: 560px;
  top: 235px;
  width: 180px;
  height: 180px;
  border-radius: 50%;
  background: radial-gradient(circle at 50% 50%, #ff7366 0%, #e03d2b 100%);
  box-shadow: 0 0 50px rgba(224, 61, 43, 0.35);
}

/* 远山容器 */
.mountains {
  position: absolute;
  left: 0;
  bottom: 0;
  width: 835px;
  height: 500px;
  overflow: hidden;
}
.mtn {
  position: absolute;
  border-radius: 50%;
  filter: blur(0);
}
/* 远山：淡墨，大模糊 */
.far-l {
  left: -150px;
  top: 90px;
  width: 560px;
  height: 280px;
  background: var(--mtn-far);
  filter: blur(28px);
}
.far-r {
  left: 280px;
  top: 60px;
  width: 640px;
  height: 320px;
  background: var(--mtn-far);
  filter: blur(28px);
}
/* 云雾留白 */
.mist {
  left: -60px;
  top: 240px;
  width: 960px;
  height: 130px;
  background: var(--mist);
  filter: blur(36px);
}
/* 中景：次浓墨 */
.mid-l {
  left: -130px;
  top: 210px;
  width: 620px;
  height: 300px;
  background: var(--mtn-mid);
  filter: blur(18px);
}
.mid-r {
  left: 330px;
  top: 190px;
  width: 660px;
  height: 320px;
  background: var(--mtn-mid);
  filter: blur(18px);
}
/* 近景：浓墨 */
.near-l {
  left: -90px;
  top: 330px;
  width: 560px;
  height: 280px;
  background: var(--mtn-near);
  filter: blur(10px);
}
.near-r {
  left: 290px;
  top: 310px;
  width: 700px;
  height: 320px;
  background: var(--mtn-near);
  filter: blur(10px);
}

/* 飞鸟 */
.bird {
  position: absolute;
  fill: none;
}
.bird-1 {
  left: 210px;
  top: 560px;
  width: 60px;
  height: 24px;
}
.bird-2 {
  left: 300px;
  top: 520px;
  width: 44px;
  height: 18px;
}

/* 文案 */
.brand-top {
  position: absolute;
  left: 128px;
  top: 64px;
  font-size: 16px;
  color: var(--ink-soft);
  letter-spacing: 1px;
}
.brand-title {
  position: absolute;
  left: 110px;
  top: 183px;
  font-family: 'Ma Shan Zheng', 'Noto Serif SC', serif;
  font-size: 104px;
  font-weight: 400;
  line-height: 1;
  color: var(--ink);
}
.seal {
  position: absolute;
  left: 336px;
  top: 236px;
  width: 64px;
  height: 64px;
  border-radius: 12px;
  background: var(--cinnabar);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Noto Serif SC', serif;
  font-weight: 700;
  font-size: 36px;
  color: #fff;
}
.brand-en {
  position: absolute;
  left: 132px;
  top: 424px;
  font-size: 18px;
  font-weight: 500;
  letter-spacing: 8px;
  color: var(--ink-soft);
}
.tagline {
  position: absolute;
  left: 132px;
  top: 462px;
  font-family: 'LXGW WenKai', 'Noto Serif SC', serif;
  font-size: 26px;
  color: var(--ink-soft);
}
.copyright {
  position: absolute;
  left: 128px;
  top: 846px;
  font-size: 12px;
  color: #c9c2b2;
}

@media (max-width: 960px) {
  .scene {
    width: 100%;
    flex: none;
    height: 420px;
  }
  .sun {
    left: 60%;
  }
  .brand-title {
    font-size: 72px;
    top: 120px;
  }
  .seal {
    left: 300px;
    top: 150px;
  }
  .copyright {
    display: none;
  }
}
</style>
