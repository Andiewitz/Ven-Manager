<script lang="ts">
  import { page } from '$app/stores';
</script>

<div class="error-page">
  <div class="error-content">
    <p class="error-code">404</p>
    <h1 class="error-title">Error</h1>
    <p class="error-message">Sorry, we could not find what you were looking for.</p>
    <a href="/" class="error-link">Return to Dashboard</a>
  </div>
</div>

<style>
  .error-page {
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    background: var(--v-surface);
  }

  .error-content {
    text-align: center;
    padding: 3rem;
  }

  .error-code {
    font-family: 'Libre Baskerville', serif;
    font-weight: 700;
    font-size: 6rem;
    color: var(--v-ink);
    line-height: 1;
    margin-bottom: 0.5rem;
  }

  .error-title {
    font-family: 'Libre Baskerville', serif;
    font-weight: 700;
    font-size: 2rem;
    color: var(--v-ink);
    margin-bottom: 1rem;
  }

  .error-message {
    font-family: 'Syne', sans-serif;
    font-size: 1rem;
    color: var(--v-dusk);
    margin-bottom: 2rem;
    max-width: 400px;
  }

  .error-link {
    display: inline-block;
    font-family: 'Syne', sans-serif;
    font-size: 12px;
    font-weight: 500;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    text-decoration: none;
    background: var(--v-ink);
    color: var(--v-surface);
    padding: 10px 24px;
    border-radius: 6px;
    transition: all 0.18s ease-out;
  }

  .error-link:hover {
    background: var(--v-ink-2);
  }
</style>