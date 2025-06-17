<template>
  <div class="projects-page">
    <section class="hero">
      <div class="container">
        <h1>Our Projects</h1>
        <p class="subtitle">Exploring new frontiers in technology and innovation</p>
      </div>
    </section>

    <section class="projects">
      <div class="container">
        <div class="projects-grid">
          <div v-for="project in projects" :key="project.id" class="project-card">
            <div class="project-image" :style="{ backgroundImage: `url(${project.image})` }">
              <div class="project-overlay">
                <h3>{{ project.title }}</h3>
                <p>{{ project.description }}</p>
                <a :href="project.link" class="btn">Learn More</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
const projects = [
  {
    id: 1,
    title: 'Project Alpha',
    description: 'Exploring new frontiers in web development',
    image: 'https://images.unsplash.com/photo-1635070041078-e363dbe005cb?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80',
    link: '#'
  },
  {
    id: 2,
    title: 'Project Beta',
    description: 'Innovation in distributed systems',
    image: 'https://images.unsplash.com/photo-1620712943543-bcc4688e7485?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80',
    link: '#'
  },
  {
    id: 3,
    title: 'Project Gamma',
    description: 'Applied artificial intelligence',
    image: 'https://images.unsplash.com/photo-1639762681057-408e52192e55?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80',
    link: '#'
  }
]
</script>

<style lang="scss" scoped>
.projects-page {
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

.projects {
  padding: 6rem 0;
  background: var(--color-accent);
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.project-card {
  position: relative;
  height: 400px;
  border-radius: 8px;
  overflow: hidden;
  background: var(--color-bg);
}

.project-image {
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  transition: transform 0.5s ease;
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 2rem;
  opacity: 0;
  transition: opacity 0.3s ease;
  color: white;
  text-align: center;
}

.project-card:hover {
  .project-image {
    transform: scale(1.05);
  }
  
  .project-overlay {
    opacity: 1;
  }
}

h3 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

p {
  font-size: 1.1rem;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.btn {
  padding: 0.75rem 1.5rem;
  background: white;
  color: black;
  border-radius: 4px;
  font-weight: 500;
  transition: all 0.3s ease;

  &:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  }
}

@media (max-width: 768px) {
  h1 {
    font-size: 2.5rem;
  }

  .subtitle {
    font-size: 1.2rem;
  }

  .project-card {
    height: 300px;
  }
}
</style> 