<template>
  <main class="page-shell">
    <section class="container">
      <header class="profile">
        <div class="avatar-wrap">
          <img :src="profileImage" alt="Lee Cloete" class="avatar" />
        </div>
        <h1 class="name">Lee Cloete</h1>
        <p class="handle">@leelulz</p>
      </header>

      <nav class="links">
        <a
          v-for="link in links"
          :key="link.label"
          class="link-row"
          :href="link.href"
          v-bind="link.external ? { target: '_blank', rel: 'noopener noreferrer' } : {}"
        >
          <span class="link-copy">
            <span class="link-label">{{ link.label }}</span>
            <span class="link-meta">{{ link.meta }}</span>
          </span>
          <span class="arrow" aria-hidden="true">&#8599;</span>
        </a>
      </nav>
    </section>
  </main>
</template>

<script setup lang="ts">
import profileImage from '~/1708707756892.jpg'

const links = [
  {
    label: 'Website',
    meta: 'leecloete.com',
    href: 'https://leecloete.com',
    external: true
  },
  {
    label: 'LinkedIn',
    meta: 'in/leecloete',
    href: 'https://www.linkedin.com/in/leecloete/',
    external: true
  },
  {
    label: 'Work with me',
    meta: 'hello@leecloete.com',
    href: 'mailto:hello@leecloete.com',
    external: false
  },
  {
    label: 'Drone Audio Tool',
    meta: 'drone.leecloete.com',
    href: 'https://drone.leecloete.com',
    external: true
  }
]
</script>

<style>
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  min-height: 100vh;
  background: #f5f5f5;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>

<style scoped>
.page-shell {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem 1rem;
}

.container {
  width: 100%;
  max-width: 430px;
  background: #fff;
  border: 1px solid #e7e7e7;
  border-radius: 1.5rem;
  padding: 1.5rem 1rem 1rem;
  font-family: 'DM Sans', system-ui, -apple-system, sans-serif;
  color: #111;
}

/* Profile */
.profile {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 0.4rem;
  margin-bottom: 1.4rem;
}

.avatar-wrap {
  width: 5.5rem;
  height: 5.5rem;
  overflow: hidden;
  border-radius: 50%;
  border: 1px solid #d8d8d8;
}

.avatar {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.name {
  margin-top: 0.35rem;
  font-family: 'DM Sans', system-ui, -apple-system, sans-serif;
  font-size: 1.5rem;
  font-weight: 700;
  line-height: 1.15;
  color: #111;
}

.handle {
  font-size: 0.95rem;
  font-weight: 400;
  color: #666;
}

/* Links */
.links {
  display: flex;
  flex-direction: column;
  gap: 0.7rem;
}

.link-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.75rem;
  padding: 0.95rem 1rem;
  border: 1px solid #e2e2e2;
  border-radius: 0.95rem;
  background: #fff;
  text-decoration: none;
  color: #111;
  transition: transform 0.18s ease, box-shadow 0.2s ease, border-color 0.2s ease, background-color 0.2s ease;
}

.link-row:hover {
  transform: translateY(-1px);
  border-color: #d2d2d2;
  background: #fcfcfc;
  box-shadow: 0 6px 14px rgba(0, 0, 0, 0.05);
}

.link-copy {
  min-width: 0;
  display: flex;
  flex-direction: column;
  gap: 0.18rem;
}

.link-label {
  font-size: 0.98rem;
  font-weight: 600;
  color: inherit;
}

.link-meta {
  font-size: 0.79rem;
  color: #737373;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.arrow {
  flex-shrink: 0;
  font-size: 1.05rem;
  color: #7a7a7a;
  transition: transform 0.18s ease;
}

.link-row:hover .arrow {
  transform: translate(2px, -2px);
}

@media (max-width: 430px) {
  .container {
    border-radius: 1.35rem;
  }
}
</style>
