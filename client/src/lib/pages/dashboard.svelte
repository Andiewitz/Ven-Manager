<script lang="ts">
  import DashboardSkeleton from '$lib/pages/dashboard-skeleton.svelte';

  let loading = $state(true);

  $effect(() => {
    const timer = setTimeout(() => {
      loading = false;
    }, 1500);

    return () => clearTimeout(timer);
  });
</script>

{#if loading}
  <DashboardSkeleton />
{:else}
  <div class="fade-in">
  <!-- Stats Grid -->
  <div class="grid gap-4 md:grid-cols-2 lg:grid-cols-4 mb-6">
    <!-- Light stat card -->
    <div class="rounded-xl border border-border p-4" style="background: var(--v-surface-card); box-shadow: var(--v-shadow-card);">
      <p class="text-[10px] tracking-wider uppercase text-dusk mb-1" style="font-family: 'Courier New', monospace;">Total clients</p>
      <p class="text-[26px] tracking-[-0.5px] text-ink" style="font-family: 'Libre Baskerville', serif; font-weight: 700;">24</p>
      <p class="text-[10px] text-sage mt-1" style="font-family: 'Courier New', monospace;">↑ +3 this month</p>
    </div>
    <!-- Dark stat card -->
    <div class="rounded-xl border border-[rgba(255,255,255,0.06)] p-4" style="background: var(--v-ink-2); box-shadow: var(--v-shadow-raised);">
      <p class="text-[10px] tracking-wider uppercase text-[rgba(245,243,238,0.45)] mb-1" style="font-family: 'Courier New', monospace;">Revenue · July</p>
      <p class="text-[26px] tracking-[-0.5px] text-surface" style="font-family: 'Libre Baskerville', serif; font-weight: 700;">₱142,000</p>
      <p class="text-[10px] text-gold mt-1" style="font-family: 'Courier New', monospace;">2 invoices pending</p>
    </div>
    <!-- Light stat card -->
    <div class="rounded-xl border border-border p-4" style="background: var(--v-surface-card); box-shadow: var(--v-shadow-card);">
      <p class="text-[10px] tracking-wider uppercase text-dusk mb-1" style="font-family: 'Courier New', monospace;">Active projects</p>
      <p class="text-[26px] tracking-[-0.5px] text-ink" style="font-family: 'Libre Baskerville', serif; font-weight: 700;">8</p>
      <p class="text-[10px] text-sage mt-1" style="font-family: 'Courier New', monospace;">↑ +2 this week</p>
    </div>
    <!-- Dark stat card -->
    <div class="rounded-xl border border-[rgba(255,255,255,0.06)] p-4" style="background: var(--v-ink-2); box-shadow: var(--v-shadow-raised);">
      <p class="text-[10px] tracking-wider uppercase text-[rgba(245,243,238,0.45)] mb-1" style="font-family: 'Courier New', monospace;">Pending tasks</p>
      <p class="text-[26px] tracking-[-0.5px] text-surface" style="font-family: 'Libre Baskerville', serif; font-weight: 700;">12</p>
      <p class="text-[10px] text-gold mt-1" style="font-family: 'Courier New', monospace;">3 due today</p>
    </div>
  </div>

  <!-- Project Cards -->
  <div class="grid gap-4 md:grid-cols-2 mb-6">
    <!-- Project 1 -->
    <div class="rounded-xl border border-border p-4" style="background: var(--v-surface-card); box-shadow: var(--v-shadow-card);">
      <div class="flex justify-between items-start mb-3">
        <div>
          <p class="text-[13px] text-ink mb-1" style="font-family: 'Libre Baskerville', serif; font-weight: 700;">Dragon Lore — Brand Identity</p>
          <p class="text-[10px] text-dusk" style="font-family: 'Courier New', monospace;">Started Jun 12 · Est. delivery Jul 28</p>
        </div>
        <span class="inline-block text-[10px] tracking-wider px-2.5 py-1 rounded" style="font-family: 'Courier New', monospace; background: #D6DCF5; color: #2D3A7A;">In revision</span>
      </div>
      <div class="h-[3px] rounded-sm mb-2" style="background: var(--v-surface-2);">
        <div class="h-full rounded-sm" style="width: 68%; background: var(--v-sage);"></div>
      </div>
      <div class="flex justify-between items-center mt-3">
        <div class="flex gap-1.5">
          <div class="w-9 h-9 rounded-full flex items-center justify-center text-[13px]" style="background: var(--v-ink); color: var(--v-gold); font-family: 'Libre Baskerville', serif; font-weight: 700;">A</div>
          <div class="w-9 h-9 rounded-full flex items-center justify-center text-[13px]" style="background: var(--v-gold-light); color: var(--v-gold-dark); font-family: 'Libre Baskerville', serif; font-weight: 700;">DL</div>
        </div>
        <p class="text-[10px] text-dusk" style="font-family: 'Courier New', monospace;">68% complete</p>
      </div>
    </div>

    <!-- Project 2 -->
    <div class="rounded-xl border border-border p-4" style="background: var(--v-surface-card); box-shadow: var(--v-shadow-card);">
      <div class="flex justify-between items-start mb-3">
        <div>
          <p class="text-[13px] text-ink mb-1" style="font-family: 'Libre Baskerville', serif; font-weight: 700;">Meridian — Web Redesign</p>
          <p class="text-[10px] text-dusk" style="font-family: 'Courier New', monospace;">Started Jul 01 · Est. delivery Aug 15</p>
        </div>
        <span class="inline-block text-[10px] tracking-wider px-2.5 py-1 rounded" style="font-family: 'Courier New', monospace; background: var(--v-sage-light); color: var(--v-sage-dark);">Active</span>
      </div>
      <div class="h-[3px] rounded-sm mb-2" style="background: var(--v-surface-2);">
        <div class="h-full rounded-sm" style="width: 42%; background: var(--v-sage);"></div>
      </div>
      <div class="flex justify-between items-center mt-3">
        <div class="flex gap-1.5">
          <div class="w-9 h-9 rounded-full flex items-center justify-center text-[13px]" style="background: var(--v-ink); color: var(--v-gold); font-family: 'Libre Baskerville', serif; font-weight: 700;">M</div>
        </div>
        <p class="text-[10px] text-dusk" style="font-family: 'Courier New', monospace;">42% complete</p>
      </div>
    </div>
  </div>

  <!-- Recent Activity -->
  <div class="rounded-xl border border-border p-4" style="background: var(--v-surface-card); box-shadow: var(--v-shadow-card);">
    <p class="text-[10px] tracking-wider uppercase text-dusk mb-4" style="font-family: 'Courier New', monospace;">Recent Activity</p>
    <div class="space-y-4">
      <div class="flex items-center gap-3">
        <div class="w-1.5 h-1.5 rounded-full" style="background: var(--v-sage);"></div>
        <div class="flex-1">
          <p class="text-[13px] text-ink" style="font-family: 'Syne', sans-serif;">New client registered — Acme Corp</p>
          <p class="text-[10px] text-dusk" style="font-family: 'Courier New', monospace;">2 minutes ago</p>
        </div>
      </div>
      <div class="flex items-center gap-3">
        <div class="w-1.5 h-1.5 rounded-full" style="background: var(--v-gold);"></div>
        <div class="flex-1">
          <p class="text-[13px] text-ink" style="font-family: 'Syne', sans-serif;">Invoice #00142 — ₱28,000 pending</p>
          <p class="text-[10px] text-dusk" style="font-family: 'Courier New', monospace;">1 hour ago</p>
        </div>
      </div>
      <div class="flex items-center gap-3">
        <div class="w-1.5 h-1.5 rounded-full" style="background: var(--v-navy);"></div>
        <div class="flex-1">
          <p class="text-[13px] text-ink" style="font-family: 'Syne', sans-serif;">Project milestone completed — Dragon Lore</p>
          <p class="text-[10px] text-dusk" style="font-family: 'Courier New', monospace;">3 hours ago</p>
        </div>
      </div>
    </div>
  </div>
  </div>
{/if}

<style>
  .fade-in {
    animation: fadeIn 0.4s ease-out;
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(8px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
</style>