<template>
  <div class="app">
    <nav class="navbar" :class="{ 'scrolled': isScrolled }">
      <div class="container">
        <router-link to="/" class="logo">
          <span class="logo-text">THE</span>
          <span class="logo-accent">X</span>
          <span class="logo-text">CODE</span>
        </router-link>
        <div class="nav-links" :class="{ 'active': isMenuOpen }">
          <router-link to="/" class="nav-link">ENTRY</router-link>
          <router-link to="/" class="nav-link" @click.native="scrollToPrinciples">RULES</router-link>
        </div>
        <button class="menu-toggle" @click="toggleMenu">
          <span></span>
          <span></span>
          <span></span>
        </button>
      </div>
    </nav>

    <main>
      <router-view v-slot="{ Component }">
        <transition name="fade" mode="out-in">
          <component :is="Component" />
        </transition>
      </router-view>
    </main>

    <footer class="footer">
      <div class="container">
        <div class="footer-bottom">
          <p>THE XCODE ORGANIZATION. ALL RIGHTS RESERVED.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { useRouter } from 'vue-router'

const isScrolled = ref(false)
const isMenuOpen = ref(false)
const router = useRouter()

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

function scrollToPrinciples(e) {
  e.preventDefault()
  if (router.currentRoute.value.path !== '/') {
    router.push('/').then(() => {
      setTimeout(() => {
        const el = document.querySelector('.features')
        if (el) el.scrollIntoView({ behavior: 'smooth' })
      }, 300)
    })
  } else {
    const el = document.querySelector('.features')
    if (el) el.scrollIntoView({ behavior: 'smooth' })
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  position: relative;
}

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  background: rgba(0, 0, 0, 0.95);
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
  border-bottom: 1px solid rgba(192, 192, 192, 0.1);
}

.navbar.scrolled {
  background: rgba(0, 0, 0, 0.98);
  box-shadow: 0 0 20px rgba(192, 192, 192, 0.05);
}

.navbar .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;
}

.logo {
  font-size: 1.5rem;
  font-weight: 700;
  text-decoration: none;
  letter-spacing: 0.2em;
  display: flex;
  align-items: center;
  gap: 0.2em;
}

.logo-text {
  color: var(--text);
}

.logo-accent {
  color: var(--accent);
  font-size: 1.2em;
}

.nav-links {
  display: flex;
  gap: 2rem;
  align-items: center;
}

.nav-link {
  color: var(--text);
  text-decoration: none;
  font-size: 0.8rem;
  font-weight: 500;
  transition: all 0.3s ease;
  position: relative;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 1px;
  background: var(--accent);
  transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 100%;
}

.cta-button {
  background: transparent;
  color: var(--text);
  border: 1px solid var(--text);
  padding: 0.75rem 1.5rem;
  font-size: 0.8rem;
  font-weight: 500;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
  letter-spacing: 0.2em;
}

.cta-button::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(192, 192, 192, 0.1), transparent);
  transition: 0.5s;
}

.cta-button:hover::before {
  left: 100%;
}

.cta-button:hover {
  background: var(--text);
  color: var(--background);
  transform: translateY(-2px);
  box-shadow: 0 0 20px rgba(192, 192, 192, 0.1);
}

.menu-toggle {
  display: none;
  flex-direction: column;
  gap: 6px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
}

.menu-toggle span {
  display: block;
  width: 24px;
  height: 2px;
  background: var(--text);
  transition: all 0.3s ease;
}

main {
  flex: 1;
  margin-top: 80px;
  position: relative;
  z-index: 1;
}

.footer {
  background: var(--surface);
  margin-top: auto;
  position: relative;
  z-index: 1;
  border-top: 1px solid rgba(0, 255, 0, 0.1);
}

.footer-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 4rem;
  margin-bottom: 4rem;
}

.footer-section h3 {
  font-size: 0.9rem;
  font-weight: 600;
  margin-bottom: 1.5rem;
  color: var(--accent);
  letter-spacing: 0.2em;
}

.footer-section ul {
  list-style: none;
  padding: 0;
}

.footer-section ul li {
  margin-bottom: 0.75rem;
}

.footer-section ul li a {
  color: var(--text-secondary);
  text-decoration: none;
  font-size: 0.8rem;
  transition: all 0.3s ease;
  opacity: 0.7;
}

.footer-section ul li a:hover {
  color: var(--accent);
  opacity: 1;
}

.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 2rem;
  border-top: 1px solid rgba(0, 255, 0, 0.1);
}

.footer-bottom p {
  font-size: 0.8rem;
  opacity: 0.7;
}

.social-links {
  display: flex;
  gap: 2rem;
}

.social-link {
  color: var(--text-secondary);
  text-decoration: none;
  font-size: 0.8rem;
  transition: all 0.3s ease;
  opacity: 0.7;
}

.social-link:hover {
  color: var(--accent);
  opacity: 1;
}

/* Transiciones */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/* Responsive */
@media (max-width: 768px) {
  .nav-links {
    position: fixed;
    top: 80px;
    left: 0;
    right: 0;
    background: var(--surface);
    padding: 2rem;
    flex-direction: column;
    align-items: flex-start;
    gap: 1.5rem;
    transform: translateY(-100%);
    opacity: 0;
    transition: all 0.3s ease;
    border-bottom: 1px solid rgba(0, 255, 0, 0.1);
  }

  .nav-links.active {
    transform: translateY(0);
    opacity: 1;
  }

  .menu-toggle {
    display: flex;
  }

  .footer-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
  }

  .footer-bottom {
    flex-direction: column;
    gap: 1.5rem;
    text-align: center;
  }
}

@media (max-width: 480px) {
  .footer-grid {
    grid-template-columns: 1fr;
  }
}
</style> 