<template>
  <div class="app">
    <NuxtRouteAnnouncer />
    <nav class="navbar">
      <div class="nav-container">
        <NuxtLink to="/" class="nav-logo">
          <span class="logo-icon">JD</span>
          Portfolio
        </NuxtLink>
        <ul class="nav-menu">
          <li><NuxtLink to="/" class="nav-link">Home</NuxtLink></li>
          <li><NuxtLink to="/about" class="nav-link">About</NuxtLink></li>
          <li><NuxtLink to="/projects" class="nav-link">Projects</NuxtLink></li>
          <li><NuxtLink to="/contact" class="nav-link">Contact</NuxtLink></li>
        </ul>
      </div>
    </nav>

    <main class="main-content">
      <NuxtPage />
    </main>

    <footer class="footer">
      <div class="footer-content">
        <p>&copy; 2026 Janina Dorobantu. All rights reserved.</p>
        <div class="footer-links">
          <a href="https://github.com" target="_blank" rel="noopener">GitHub</a>
          <a href="https://linkedin.com" target="_blank" rel="noopener">LinkedIn</a>
          <a href="https://twitter.com" target="_blank" rel="noopener">Twitter</a>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
// Global navigation setup
</script>

<style lang="scss">
@import './assets/scss/main.scss';

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  background: var(--c-bg-primary);
  color: var(--c-text-primary);
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen', 'Ubuntu',
    'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue', sans-serif;
  line-height: 1.6;
}

.app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

// Navigation Styles
.navbar {
  background: var(--c-panel-bg);
  border-bottom: 1px solid var(--c-border);
  position: sticky;
  top: 0;
  z-index: 100;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-logo {
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--c-text-primary);
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  transition: color 0.3s ease;

  &:hover {
    color: var(--c-accent);
  }

  .logo-icon {
    width: 36px;
    height: 36px;
    background: var(--c-accent);
    color: white;
    border-radius: 6px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.875rem;
    font-weight: 600;
  }
}

.nav-menu {
  list-style: none;
  display: flex;
  gap: 2rem;

  .nav-link {
    text-decoration: none;
    color: var(--c-text-secondary);
    font-weight: 500;
    transition: color 0.3s ease;
    position: relative;

    &:hover {
      color: var(--c-accent);
    }

    &.router-link-active {
      color: var(--c-accent);

      &::after {
        content: '';
        position: absolute;
        bottom: -0.5rem;
        left: 0;
        right: 0;
        height: 2px;
        background: var(--c-accent);
      }
    }
  }
}

// Main Content
.main-content {
  flex: 1;
  padding: 0;
}

// Footer Styles
.footer {
  background: var(--c-panel-bg);
  border-top: 1px solid var(--c-border);
  margin-top: 4rem;
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;

  p {
    color: var(--c-text-secondary);
    font-size: 0.875rem;
  }
}

.footer-links {
  display: flex;
  gap: 1.5rem;

  a {
    color: var(--c-text-secondary);
    text-decoration: none;
    font-size: 0.875rem;
    transition: color 0.3s ease;

    &:hover {
      color: var(--c-accent);
    }
  }
}

// Responsive
@media (max-width: 768px) {
  .nav-container {
    padding: 1rem;
  }

  .nav-menu {
    gap: 1rem;
    font-size: 0.9rem;
  }

  .nav-logo {
    font-size: 1.25rem;
  }

  .footer-content {
    flex-direction: column;
    text-align: center;
    gap: 1rem;
  }
}

// Link styles for NuxtLink
a {
  color: var(--c-accent);
  text-decoration: none;

  &:hover {
    text-decoration: underline;
  }
}
</style>
