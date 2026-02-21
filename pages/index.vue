<template>
  <main class="container">
    <header class="profile">
      <h1 class="name">Lee Cloete</h1>
      <p class="tagline">Designer &amp; Creator</p>
    </header>

    <nav class="links">
      <a
        v-for="link in links"
        :key="link.label"
        class="link-row"
        :href="link.href"
        v-bind="link.external ? { target: '_blank', rel: 'noopener noreferrer' } : {}"
      >
        <span class="link-label">{{ link.label }}</span>
        <span class="link-meta">{{ link.meta }} <span class="arrow">&#8594;</span></span>
      </a>
    </nav>
  </main>
</template>

<script setup lang="ts">
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
  background: #f9f8f6;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>

<style scoped>
.container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 3rem 1.5rem;
  font-family: 'DM Sans', system-ui, -apple-system, sans-serif;
  color: #111;
}

.container > * {
  width: 100%;
  max-width: 440px;
}

/* Profile */
.profile {
  display: flex;
  flex-direction: column;
  gap: 0.45rem;
  margin-bottom: 3.5rem;
}

.name {
  font-family: 'DM Serif Display', Georgia, serif;
  font-size: 2.5rem;
  font-weight: 400;
  line-height: 1.05;
  letter-spacing: -0.02em;
  color: #111;
}

.tagline {
  font-size: 0.85rem;
  font-style: italic;
  font-weight: 300;
  color: #999;
  letter-spacing: 0.01em;
}

/* Links */
.links {
  display: flex;
  flex-direction: column;
  border-top: 1px solid #dedad4;
}

.link-row {
  display: flex;
  align-items: baseline;
  justify-content: space-between;
  gap: 1rem;
  padding: 1.05rem 0;
  border-bottom: 1px solid #dedad4;
  text-decoration: none;
  color: #111;
  transition: color 0.2s ease;
}

.link-row:hover {
  color: #555;
}

.link-label {
  font-size: 0.9rem;
  font-weight: 400;
  color: inherit;
  white-space: nowrap;
}

.link-meta {
  font-size: 0.78rem;
  color: #aaa;
  display: flex;
  align-items: center;
  gap: 0.35rem;
  transition: color 0.2s ease;
  white-space: nowrap;
}

.link-row:hover .link-meta {
  color: #888;
}

.arrow {
  display: inline-block;
  transition: transform 0.2s ease;
}

.link-row:hover .arrow {
  transform: translateX(3px);
}
</style>
