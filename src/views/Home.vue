<template>
  <div class="home">
    <!-- Hero Section -->
    <section class="hero">
      <div id="particles-js"></div>
      <div class="container">
        <h1 class="hero-title animate-fade-in">
          <span class="hero-title-top">WELCOME TO</span>
          <span class="hero-title-bottom">THE XCODE ORGANIZATION</span>
        </h1>
        <p class="hero-subtitle animate-fade-in-delayed">WHERE TECHNOLOGY MEETS INNOVATION</p>
        <div class="hero-cta animate-fade-in-delayed2">
          <button class="cta-button">REQUEST MEMBERSHIP</button>
        </div>
      </div>
    </section>

    <!-- Stats Section -->
    <section class="stats">
      <div class="container">
        <div class="stats-grid">
          <div class="stat-item">
            <span class="stat-number glitch" data-text="3">3</span>
            <span class="stat-label">CORE PRINCIPLES</span>
          </div>
          <div class="stat-item">
            <span class="stat-number glitch" data-text="13">13</span>
            <span class="stat-label">SELECT MEMBERS</span>
          </div>
          <div class="stat-item">
            <span class="stat-number glitch" data-text="42">74</span>
            <span class="stat-label">Projects</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Features Section -->
    <section class="features">
      <div class="container">
        <h2 class="section-title glitch" data-text="CORE PRINCIPLES">CORE PRINCIPLES</h2>
        <div class="features-grid">
          <div class="feature-card">
            <div class="feature-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
              </svg>
            </div>
            <h3>DISCIPLINE</h3>
            <p>Master the art of self-control and mental fortitude through rigorous training and practice.</p>
          </div>
          <div class="feature-card">
            <div class="feature-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <circle cx="12" cy="12" r="10"/>
                <path d="M12 6v6l4 2"/>
              </svg>
            </div>
            <h3>PRECISION</h3>
            <p>Develop an unwavering focus and attention to detail in every aspect of your craft.</p>
          </div>
          <div class="feature-card">
            <div class="feature-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>
              </svg>
            </div>
            <h3>LOYALTY</h3>
            <p>Build unbreakable bonds with fellow members through shared experiences, trust and privacy.</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const projects = ref([
  {
    id: 1,
    title: 'MENTAL MASTERY',
    description: 'A comprehensive system for developing mental resilience and focus.',
    image: 'https://images.unsplash.com/photo-1465101046530-73398c7f28ca?auto=format&fit=crop&w=600&q=80',
    link: '#'
  },
  {
    id: 2,
    title: 'PHYSICAL DISCIPLINE',
    description: 'Advanced training methodologies for peak physical performance.',
    image: 'https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=600&q=80',
    link: '#'
  },
  {
    id: 3,
    title: 'SPIRITUAL GROWTH',
    description: 'Ancient wisdom combined with modern techniques for personal evolution.',
    image: 'https://images.unsplash.com/photo-1464983953574-0892a716854b?auto=format&fit=crop&w=600&q=80',
    link: '#'
  }
])

onMounted(() => {
  if (typeof window.particlesJS !== 'undefined') {
    window.particlesJS('particles-js', {
      particles: {
        number: { value: 80, density: { enable: true, value_area: 800 } },
        color: { value: ['#c0c0c0', '#ffd700'] },
        shape: { type: ['circle', 'triangle'], stroke: { width: 0, color: '#000000' } },
        opacity: { value: 0.7, random: true, anim: { enable: true, speed: 1, opacity_min: 0.2, sync: false } },
        size: { value: 4, random: true, anim: { enable: true, speed: 2, size_min: 0.2, sync: false } },
        line_linked: { enable: true, distance: 150, color: '#c0c0c0', opacity: 0.4, width: 1 },
        move: { enable: true, speed: 1.2, direction: 'none', random: true, straight: false, out_mode: 'out', bounce: false, attract: { enable: true, rotateX: 600, rotateY: 1200 } }
      },
      interactivity: {
        detect_on: 'canvas',
        events: { onhover: { enable: true, mode: 'grab' }, onclick: { enable: true, mode: 'push' }, resize: true },
        modes: { grab: { distance: 140, line_linked: { opacity: 0.6 } }, push: { particles_nb: 4 } }
      },
      retina_detect: true
    })
  }
})

onUnmounted(() => {
  // Limpia el canvas de partículas al desmontar
  const el = document.getElementById('particles-js')
  if (el) el.innerHTML = ''
})
</script>

<style scoped>
.home {
  position: relative;
}

/* Hero Section */
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(45deg, rgba(0,0,0,0.95), rgba(0,0,0,0.85));
  z-index: 1;
}

#particles-js {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
  pointer-events: none;
}

.hero .container {
  position: relative;
  z-index: 1;
}

.hero-title {
  display: block;
  font-size: 4rem;
  font-weight: 800;
  margin-bottom: 1rem;
  letter-spacing: 0.2em;
  text-align: left;
}

.hero-title-top,
.hero-title-bottom {
  display: block;
  font-size: inherit;
  line-height: 1.1;
  text-align: left;
}

.hero-subtitle {
  font-size: 1.5rem;
  margin-bottom: 3rem;
  opacity: 0.8;
  letter-spacing: 0.1em;
}

.hero-cta {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.animate-fade-in {
  opacity: 0;
  animation: fadeInUp 1s 0.1s forwards;
}
.animate-fade-in-delayed {
  opacity: 0;
  animation: fadeInUp 1s 0.4s forwards;
}
.animate-fade-in-delayed2 {
  opacity: 0;
  animation: fadeInUp 1s 0.7s forwards;
}
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Stats Section */
.stats {
  padding: 6rem 0;
  background: var(--surface);
  position: relative;
}

.stats::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--accent), transparent);
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 4rem;
  text-align: center;
}

.stat-number {
  font-size: 4rem;
  font-weight: 800;
  color: var(--accent);
  display: block;
  margin-bottom: 1rem;
  letter-spacing: 0.1em;
  animation: countUp 2s ease-out;
}

@keyframes countUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.stat-label {
  font-size: 0.9rem;
  text-transform: uppercase;
  letter-spacing: 0.2em;
  opacity: 0.8;
}

/* Features Section */
.features {
  padding: 6rem 0;
  background: var(--background);
  position: relative;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 800;
  text-align: center;
  margin-bottom: 4rem;
  letter-spacing: 0.2em;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.feature-card {
  background: var(--surface);
  padding: 3rem 2rem;
  border: 1.5px solid rgba(192, 192, 192, 0.15);
  border-radius: 18px;
  transition: all 0.3s cubic-bezier(.4,2,.6,1);
  position: relative;
  overflow: hidden;
  box-shadow: 0 4px 32px 0 rgba(0,0,0,0.12);
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 340px;
}

.feature-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, transparent, rgba(255, 215, 0, 0.08), transparent);
  opacity: 0;
  transition: opacity 0.4s;
  pointer-events: none;
  border-radius: 18px;
}

.feature-card:hover::before {
  opacity: 1;
}

.feature-card:hover {
  transform: translateY(-10px) scale(1.04);
  box-shadow: 0 8px 40px 0 rgba(255,215,0,0.10), 0 2px 8px 0 rgba(0,0,0,0.18);
  border-color: var(--accent);
}

.feature-icon {
  width: 72px;
  height: 72px;
  margin-bottom: 2rem;
  color: var(--accent);
  transition: all 0.3s cubic-bezier(.4,2,.6,1);
}

.feature-card:hover .feature-icon {
  transform: scale(1.15) rotate(6deg);
  filter: drop-shadow(0 0 8px var(--accent));
}

.feature-card h3 {
  font-size: 1.6rem;
  margin-bottom: 1.2rem;
  letter-spacing: 0.12em;
  font-weight: 700;
  text-align: center;
}

.feature-card p {
  font-size: 1.1rem;
  opacity: 0.85;
  line-height: 1.7;
  text-align: center;
}

/* Buttons */
.cta-button {
  padding: 1rem 2rem;
  border-radius: 4px;
  font-weight: 500;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
  position: relative;
  overflow: hidden;
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

.cta-button.primary {
  background: var(--text);
  color: var(--background);
}

.cta-button.primary:hover {
  background: var(--accent);
  transform: translateY(-2px);
}

.cta-button.secondary {
  background: transparent;
  color: var(--text);
  border: 1px solid var(--text);
}

.cta-button.secondary:hover {
  background: var(--text);
  color: var(--background);
  transform: translateY(-2px);
}

/* Glitch Effect */
.glitch {
  position: relative;
  color: var(--text);
  animation: glitch-skew 1s infinite linear alternate-reverse;
}

.glitch::before,
.glitch::after {
  content: attr(data-text);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0.8;
}

.glitch::before {
  left: 2px;
  text-shadow: -2px 0 var(--accent);
  animation: glitch-anim-1 2s infinite linear alternate-reverse;
}

.glitch::after {
  left: -2px;
  text-shadow: 2px 0 var(--accent);
  animation: glitch-anim-2 3s infinite linear alternate-reverse;
}

@keyframes glitch-skew {
  0% {
    transform: skew(0deg);
  }
  20% {
    transform: skew(1deg);
  }
  40% {
    transform: skew(-1deg);
  }
  60% {
    transform: skew(0.5deg);
  }
  80% {
    transform: skew(-0.5deg);
  }
  100% {
    transform: skew(0deg);
  }
}

@keyframes glitch-anim-1 {
  0% {
    clip-path: inset(20% 0 30% 0);
    transform: translate(0);
  }
  20% {
    clip-path: inset(60% 0 10% 0);
    transform: translate(-2px, 2px);
  }
  40% {
    clip-path: inset(40% 0 50% 0);
    transform: translate(-2px, -2px);
  }
  60% {
    clip-path: inset(80% 0 5% 0);
    transform: translate(2px, 2px);
  }
  80% {
    clip-path: inset(10% 0 70% 0);
    transform: translate(2px, -2px);
  }
  100% {
    clip-path: inset(30% 0 20% 0);
    transform: translate(0);
  }
}

@keyframes glitch-anim-2 {
  0% {
    clip-path: inset(15% 0 35% 0);
    transform: translate(0);
  }
  20% {
    clip-path: inset(55% 0 15% 0);
    transform: translate(2px, -2px);
  }
  40% {
    clip-path: inset(45% 0 45% 0);
    transform: translate(2px, 2px);
  }
  60% {
    clip-path: inset(75% 0 10% 0);
    transform: translate(-2px, -2px);
  }
  80% {
    clip-path: inset(15% 0 65% 0);
    transform: translate(-2px, 2px);
  }
  100% {
    clip-path: inset(25% 0 25% 0);
    transform: translate(0);
  }
}

/* Responsive */
@media (max-width: 1024px) {
  .features-grid {
    grid-template-columns: 1fr;
  }
}
@media (max-width: 600px) {
  .features-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 2.5rem;
  }

  .hero-subtitle {
    font-size: 1.2rem;
  }

  .hero-cta {
    flex-direction: column;
  }

  .stats-grid,
  .features-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .section-title {
    font-size: 2rem;
  }
}

@media (max-width: 480px) {
  .hero-title {
    font-size: 1.5rem;
  }

  .hero-subtitle {
    font-size: 1rem;
  }

  .stat-number {
    font-size: 3rem;
  }
}
</style> 