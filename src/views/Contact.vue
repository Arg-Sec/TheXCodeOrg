<template>
  <div class="contact-page">
    <section class="hero">
      <div class="container">
        <h1>Contact Us</h1>
        <p class="subtitle">Get in touch with our team</p>
      </div>
    </section>

    <section class="contact">
      <div class="container">
        <div class="contact-content">
          <div class="contact-info">
            <h2>Let's Connect</h2>
            <p>Interested in joining our community or learning more about our work? We'd love to hear from you.</p>
            <div class="contact-methods">
              <div class="contact-method">
                <h3>Email</h3>
                <a href="mailto:contact@thexcode.org">contact@thexcode.org</a>
              </div>
              <div class="contact-method">
                <h3>Location</h3>
                <p>San Francisco, CA</p>
              </div>
            </div>
          </div>

          <form class="contact-form" @submit.prevent="handleSubmit">
            <div class="form-group">
              <label for="name">Name</label>
              <input type="text" id="name" v-model="form.name" required>
            </div>
            <div class="form-group">
              <label for="email">Email</label>
              <input type="email" id="email" v-model="form.email" required>
            </div>
            <div class="form-group">
              <label for="message">Message</label>
              <textarea id="message" v-model="form.message" required></textarea>
            </div>
            <button type="submit" class="btn">Send Message</button>
          </form>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const form = ref({
  name: '',
  email: '',
  message: ''
})

const handleSubmit = () => {
  // Handle form submission
  console.log('Form submitted:', form.value)
}
</script>

<style lang="scss" scoped>
.contact-page {
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

.contact {
  padding: 6rem 0;
  background: var(--color-accent);
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  max-width: 1000px;
  margin: 0 auto;
}

.contact-info {
  h2 {
    font-size: 2.5rem;
    margin-bottom: 1.5rem;
  }

  p {
    font-size: 1.1rem;
    line-height: 1.8;
    color: var(--color-text-secondary);
    margin-bottom: 3rem;
  }
}

.contact-methods {
  display: grid;
  gap: 2rem;
}

.contact-method {
  h3 {
    font-size: 1.2rem;
    margin-bottom: 0.5rem;
  }

  a, p {
    color: var(--color-text);
    font-size: 1.1rem;
  }
}

.contact-form {
  background: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
}

.form-group {
  margin-bottom: 1.5rem;

  label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 500;
  }

  input, textarea {
    width: 100%;
    padding: 0.75rem;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-size: 1rem;
    font-family: inherit;

    &:focus {
      outline: none;
      border-color: var(--color-text);
    }
  }

  textarea {
    height: 150px;
    resize: vertical;
  }
}

.btn {
  width: 100%;
  padding: 1rem;
  background: var(--color-text);
  color: white;
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

  .contact-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
}
</style> 