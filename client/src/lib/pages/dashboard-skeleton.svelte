<script lang="ts">
</script>

<!-- Stats Grid Skeleton -->
<div class="grid gap-4 md:grid-cols-2 lg:grid-cols-4 mb-6">
  {#each Array(4) as _, i}
    <div class="skeleton-card" class:dark={i % 2 === 1}>
      <div class="skeleton-line skeleton-label"></div>
      <div class="skeleton-line skeleton-value"></div>
      <div class="skeleton-line skeleton-delta"></div>
    </div>
  {/each}
</div>

<!-- Project Cards Skeleton -->
<div class="grid gap-4 md:grid-cols-2 mb-6">
  {#each Array(2) as _}
    <div class="skeleton-card">
      <div class="skeleton-header">
        <div>
          <div class="skeleton-line skeleton-title"></div>
          <div class="skeleton-line skeleton-subtitle"></div>
        </div>
        <div class="skeleton-badge"></div>
      </div>
      <div class="skeleton-progress">
        <div class="skeleton-progress-fill"></div>
      </div>
      <div class="skeleton-footer">
        <div class="skeleton-avatars">
          <div class="skeleton-avatar"></div>
          <div class="skeleton-avatar"></div>
        </div>
        <div class="skeleton-line skeleton-meta"></div>
      </div>
    </div>
  {/each}
</div>

<!-- Activity Skeleton -->
<div class="skeleton-card">
  <div class="skeleton-line skeleton-section-title"></div>
  <div class="skeleton-activity">
    {#each Array(3) as _}
      <div class="skeleton-activity-item">
        <div class="skeleton-dot"></div>
        <div class="skeleton-activity-content">
          <div class="skeleton-line skeleton-activity-title"></div>
          <div class="skeleton-line skeleton-activity-time"></div>
        </div>
      </div>
    {/each}
  </div>
</div>

<style>
  @keyframes shimmer {
    0% { background-position: -200% 0; }
    100% { background-position: 200% 0; }
  }

  .skeleton-card {
    background: var(--v-surface-card);
    border: 0.5px solid var(--v-border);
    border-radius: 12px;
    padding: 16px;
    box-shadow: var(--v-shadow-card);
  }

  .skeleton-card.dark {
    background: var(--v-ink-2);
    border: 0.5px solid rgba(255, 255, 255, 0.06);
    box-shadow: var(--v-shadow-raised);
  }

  .skeleton-line {
    background: linear-gradient(90deg, var(--v-surface-2) 25%, var(--v-surface) 50%, var(--v-surface-2) 75%);
    background-size: 200% 100%;
    animation: shimmer 1.5s infinite;
    border-radius: 4px;
  }

  .dark .skeleton-line {
    background: linear-gradient(90deg, rgba(255,255,255,0.04) 25%, rgba(255,255,255,0.08) 50%, rgba(255,255,255,0.04) 75%);
    background-size: 200% 100%;
  }

  .skeleton-label {
    width: 60%;
    height: 10px;
    margin-bottom: 8px;
  }

  .skeleton-value {
    width: 40%;
    height: 26px;
    margin-bottom: 8px;
  }

  .skeleton-delta {
    width: 50%;
    height: 10px;
  }

  .skeleton-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 12px;
  }

  .skeleton-title {
    width: 70%;
    height: 13px;
    margin-bottom: 6px;
  }

  .skeleton-subtitle {
    width: 50%;
    height: 10px;
  }

  .skeleton-badge {
    width: 70px;
    height: 22px;
    border-radius: 4px;
    background: linear-gradient(90deg, var(--v-surface-2) 25%, var(--v-surface) 50%, var(--v-surface-2) 75%);
    background-size: 200% 100%;
    animation: shimmer 1.5s infinite;
  }

  .skeleton-progress {
    height: 3px;
    background: var(--v-surface-2);
    border-radius: 2px;
    margin-bottom: 12px;
  }

  .dark .skeleton-progress {
    background: rgba(255, 255, 255, 0.04);
  }

  .skeleton-progress-fill {
    width: 45%;
    height: 100%;
    border-radius: 2px;
    background: linear-gradient(90deg, var(--v-surface-2) 25%, var(--v-surface) 50%, var(--v-surface-2) 75%);
    background-size: 200% 100%;
    animation: shimmer 1.5s infinite;
  }

  .dark .skeleton-progress-fill {
    background: linear-gradient(90deg, rgba(255,255,255,0.04) 25%, rgba(255,255,255,0.08) 50%, rgba(255,255,255,0.04) 75%);
    background-size: 200% 100%;
  }

  .skeleton-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .skeleton-avatars {
    display: flex;
    gap: 6px;
  }

  .skeleton-avatar {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background: linear-gradient(90deg, var(--v-surface-2) 25%, var(--v-surface) 50%, var(--v-surface-2) 75%);
    background-size: 200% 100%;
    animation: shimmer 1.5s infinite;
  }

  .dark .skeleton-avatar {
    background: linear-gradient(90deg, rgba(255,255,255,0.04) 25%, rgba(255,255,255,0.08) 50%, rgba(255,255,255,0.04) 75%);
    background-size: 200% 100%;
  }

  .skeleton-meta {
    width: 80px;
    height: 10px;
  }

  .skeleton-section-title {
    width: 100px;
    height: 10px;
    margin-bottom: 16px;
  }

  .skeleton-activity {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .skeleton-activity-item {
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .skeleton-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: linear-gradient(90deg, var(--v-surface-2) 25%, var(--v-surface) 50%, var(--v-surface-2) 75%);
    background-size: 200% 100%;
    animation: shimmer 1.5s infinite;
    flex-shrink: 0;
  }

  .skeleton-activity-content {
    flex: 1;
  }

  .skeleton-activity-title {
    width: 80%;
    height: 13px;
    margin-bottom: 6px;
  }

  .skeleton-activity-time {
    width: 40%;
    height: 10px;
  }
</style>