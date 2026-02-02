---
layout: home

hero:
  name: Yuki Chisaki
  # text: VitePress 主题
  tagline: ✨Welcome!✨
  actions:
    - theme: brand
      text: 我的博客
      link: /archives
    - theme: alt
      text: 关于我
      link: /about
  # image:
  #   src: /teek-logo-large.png
  #   alt: Teek
---

<script setup lang="ts">
import { onMounted } from "vue";
import { useData } from "vitepress";
import { readingIcon } from "vitepress-theme-teek"

const { frontmatter } = useData();
onMounted(() => {
  const heroTextDom = document.querySelector<HTMLElement>(".VPHero .text");
  const textDom = document.querySelector<HTMLElement>("#hero-text");

  if (!heroTextDom || !textDom) return;

  while (heroTextDom.lastChild) heroTextDom.lastChild.remove();
  heroTextDom.append(textDom);
});
</script>
<!--
<span id="hero-text" style="display: inline-block; position: relative">
  {{ frontmatter.hero.text}}
</span> -->

<style>
:root {
  --vp-home-hero-name-color: transparent;
  --vp-home-hero-name-background: -webkit-linear-gradient(120deg, var(--rainbow-prev) 30%, var(--rainbow-next));
  --vp-home-hero-image-background-image: linear-gradient(-45deg, var(--rainbow-prev) 30%, var(--rainbow-next));
  --vp-home-hero-image-filter: blur(44px);
  /* --vp-c-bg:#faf6f1 !important; */
}

/* 彩虹动画 */
:root {
  animation: rainbow 12s linear infinite;
}

.vp-doc #hero-text {
  display: none !important;
}

@media (min-width: 640px) {
  :root {
    --vp-home-hero-image-filter: blur(56px);
  }
}

@media (min-width: 960px) {
  :root {
    --vp-home-hero-image-filter: blur(68px);
  }
}


.VPContent.is-home{
  display: flex;
  justify-content: center;
  align-items: center;
}

/* 首页内容居中 */
.VPHero {
  display: flex !important;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.VPHero .main {
  position: relative;
} 

.VPHero .main::before {
    content:"";
    position: absolute;
    z-index:-999;
    width: 200px;
    height: 200px;
    background-image: var(--vp-home-hero-image-background-image);
    filter: var(--vp-home-hero-image-filter);
    transform: translate(0%, -45%);
    border-radius: 50%;
} 

.VPHero .actions {
  display: flex;
  gap:16px;
  justify-content: center;
}
</style>
