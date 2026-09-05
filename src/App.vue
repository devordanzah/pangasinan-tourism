<template>
  <div id="app" class="app">
    <a href="#main-content" class="skip-link"> Skip to main content </a>

    <HeaderNavigation />
    <main id="main-content" class="main-content">
      <router-view v-slot="{ Component }">
        <transition name="page" mode="out-in">
          <component :is="Component" />
        </transition>
      </router-view>
    </main>

    <footer class="footer">
      <div class="footer__bottom">
        <div class="footer__bottom-container">
          <span> © 2026 Pangasinan Heritage </span>

          <span> Proudly promoting Pangasinan tourism </span>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import HeaderNavigation from "./components/organisms/HeaderNavigation.vue";

export default {
  name: "App",

  components: {
    HeaderNavigation,
  },
};
</script>

<style>
:root {
  --color-primary: #176b4d;
  --color-primary-dark: #0f5138;
  --color-primary-light: #e7f3ed;

  --color-accent: #d99a32;

  --color-background: #f7f5ef;
  --color-surface: #ffffff;

  --color-text: #1c2923;
  --color-text-muted: #66736d;

  --color-border: #e1e6e3;

  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 40px;
  --space-2xl: 64px;

  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 20px;
  --radius-xl: 28px;

  --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.05);

  --shadow-md: 0 10px 30px rgba(0, 0, 0, 0.08);

  --shadow-lg: 0 20px 50px rgba(0, 0, 0, 0.12);

  --content-width: 1200px;
}

*,
*::before,
*::after {
  box-sizing: border-box;
}

html,
body {
  width: 100%;
  max-width: 100%;
  overflow-x: hidden;
}

html {
  scroll-behavior: smooth;

  scroll-padding-top: 80px;
}

body {
  margin: 0;

  min-width: 320px;

  background: var(--color-background);

  color: var(--color-text);

  font-family: Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Helvetica, Arial, sans-serif;

  line-height: 1.6;

  -webkit-font-smoothing: antialiased;

  -moz-osx-font-smoothing: grayscale;
}

img {
  display: block;

  max-width: 100%;

  height: auto;
}

button,
input,
textarea,
select {
  font: inherit;

  max-width: 100%;
}

button {
  cursor: pointer;
}

a {
  color: inherit;
}

::selection {
  background: var(--color-primary);

  color: white;
}

.app {
  width: 100%;

  min-height: 100vh;

  min-height: 100dvh;

  display: flex;

  flex-direction: column;

  overflow-x: hidden;
}

.main-content {
  width: 100%;

  max-width: 100%;

  flex: 1;

  min-width: 0;

  min-height: calc(100vh - 72px);

  min-height: calc(100dvh - 72px);
}

.skip-link {
  position: fixed;

  top: -100px;

  left: 16px;

  z-index: 9999;

  padding: 12px 18px;

  border-radius: var(--radius-md);

  background: var(--color-primary);

  color: white;

  font-weight: 700;

  text-decoration: none;

  box-shadow: var(--shadow-md);

  transition: top 0.2s ease;
}

.skip-link:focus {
  top: 16px;
}

:focus-visible {
  outline: 3px solid var(--color-accent);

  outline-offset: 3px;
}

.page-enter-active,
.page-leave-active {
  transition: opacity 0.2s ease, transform 0.2s ease;
}

.page-enter-from {
  opacity: 0;

  transform: translateY(8px);
}

.page-leave-to {
  opacity: 0;

  transform: translateY(-8px);
}

.footer {
  width: 100%;

  margin-top: auto;

  background: #12382b;

  color: white;
}
l .footer__bottom {
  width: 100%;

  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.footer__bottom-container {
  width: 100%;

  max-width: var(--content-width);

  margin: 0 auto;

  padding: 18px 24px;

  display: flex;

  align-items: center;

  justify-content: space-between;

  gap: 20px;

  color: rgba(255, 255, 255, 0.6);

  font-size: 0.8rem;
}

@media (min-width: 1200px) {
  .footer__bottom-container {
    padding-left: 0;

    padding-right: 0;
  }
}

@media (max-width: 1024px) {
  :root {
    --space-2xl: 48px;
  }

  html {
    scroll-padding-top: 72px;
  }

  .main-content {
    min-height: calc(100vh - 72px);

    min-height: calc(100dvh - 72px);
  }

  .footer__bottom-container {
    padding: 18px 24px;
  }
}

@media (max-width: 767px) {
  :root {
    --space-xl: 32px;

    --space-2xl: 40px;
  }

  html {
    scroll-padding-top: 68px;
  }

  .main-content {
    min-height: calc(100vh - 68px);

    min-height: calc(100dvh - 68px);
  }

  .footer__bottom-container {
    padding: 16px 20px;

    flex-direction: column;

    align-items: center;

    justify-content: center;

    text-align: center;

    gap: 4px;
  }
}

@media (max-width: 600px) {
  body {
    font-size: 15px;
  }

  html {
    scroll-padding-top: 64px;
  }

  .main-content {
    min-height: calc(100vh - 64px);

    min-height: calc(100dvh - 64px);
  }

  .footer__bottom-container {
    padding: 15px 16px;

    font-size: 0.75rem;
  }
}

@media (max-width: 479px) {
  :root {
    --space-md: 14px;

    --space-lg: 20px;

    --space-xl: 28px;
  }

  body {
    font-size: 14px;
  }

  .footer__bottom-container {
    padding: 14px 12px;
  }
}

@media (max-width: 359px) {
  body {
    font-size: 13px;
  }

  .footer__bottom-container {
    padding: 12px 10px;
  }
}

@media (max-width: 767px) and (orientation: landscape) {
  .main-content {
    min-height: calc(100vh - 60px);

    min-height: calc(100dvh - 60px);
  }
}

@media (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }

  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;

    animation-iteration-count: 1 !important;

    transition-duration: 0.01ms !important;

    scroll-behavior: auto !important;
  }
}
</style>
