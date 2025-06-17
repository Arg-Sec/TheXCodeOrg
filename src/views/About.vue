<template>
  <div class="about-page">
    <section class="hero">
      <div class="container">
        <h1>About Us</h1>
        <p class="subtitle">We are a collective of innovators pushing the boundaries of technology</p>
      </div>
    </section>

    <section class="content">
      <div class="container">
        <div class="mission">
          <h2>Our Mission</h2>
          <p>TheXCode.org is an organization dedicated to exploring the boundaries of technology and software development. We consider ourselves a club of innovators, where creativity and technical excellence meet.</p>
        </div>

        <div class="values">
          <div class="value-card">
            <h3>Innovation</h3>
            <p>Pushing the boundaries of what's possible in technology</p>
          </div>
          <div class="value-card">
            <h3>Community</h3>
            <p>A space to share knowledge and experiences</p>
          </div>
          <div class="value-card">
            <h3>Excellence</h3>
            <p>Commitment to quality and best practices</p>
          </div>
        </div>

        <div class="team">
          <h2>Our Team</h2>
          <p>We are a diverse group of technologists, researchers, and innovators working together to create the future of technology.</p>
        </div>
      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped>
.about-page {
  padding-top: 80px;
}

.hero {
  min-height: 50vh;
  display: flex;
  align-items: center;
  background: var(--color-bg);
  text-align: center;
  padding: 4rem 0;
}

h1 {
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
}

.subtitle {
  font-size: 1.5rem;
  color: var(--color-text-secondary);
  max-width: 600px;
  margin: 0 auto;
}

.content {
  padding: 6rem 0;
}

.mission {
  max-width: 800px;
  margin: 0 auto 6rem;
  text-align: center;
}

.values {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 6rem;
}

.value-card {
  padding: 2rem;
  background: var(--color-accent);
  border-radius: 8px;
  text-align: center;

  h3 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
  }

  p {
    color: var(--color-text-secondary);
  }
}

.team {
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
}

h2 {
  font-size: 2.5rem;
  margin-bottom: 2rem;
}

p {
  font-size: 1.1rem;
  line-height: 1.8;
  color: var(--color-text-secondary);
}

@media (max-width: 768px) {
  h1 {
    font-size: 2.5rem;
  }

  .subtitle {
    font-size: 1.2rem;
  }

  .values {
    grid-template-columns: 1fr;
  }
}
</style> 