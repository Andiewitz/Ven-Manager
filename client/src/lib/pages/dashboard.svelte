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
  <!-- Stats Grid -->
  <div class="grid gap-3 md:grid-cols-2 lg:grid-cols-4 mb-5">
    <div class="wave-in" style="animation-delay: 0ms;">
      <div class="rounded-lg border border-border p-3" style="background: var(--v-surface-card); box-shadow: var(--v-shadow-card);">
        <p class="text-[9px] tracking-wider uppercase text-dusk mb-0.5" style="font-family: 'JetBrains Mono', monospace;">Total clients</p>
        <p class="text-[20px] tracking-[-0.5px] text-ink leading-tight" style="font-family: 'Fraunces', serif; font-weight: 700;">24</p>
        <p class="text-[9px] text-sage mt-0.5" style="font-family: 'JetBrains Mono', monospace;">↑ +3 this month</p>
      </div>
    </div>
    <div class="wave-in" style="animation-delay: 60ms;">
      <div class="rounded-lg border border-[rgba(255,255,255,0.06)] p-3" style="background: var(--v-ink-2); box-shadow: var(--v-shadow-raised);">
        <p class="text-[9px] tracking-wider uppercase text-[rgba(245,243,238,0.45)] mb-0.5" style="font-family: 'JetBrains Mono', monospace;">Revenue · July</p>
        <p class="text-[20px] tracking-[-0.5px] text-surface leading-tight" style="font-family: 'Fraunces', serif; font-weight: 700;">₱142,000</p>
        <p class="text-[9px] text-gold mt-0.5" style="font-family: 'JetBrains Mono', monospace;">2 invoices pending</p>
      </div>
    </div>
    <div class="wave-in" style="animation-delay: 120ms;">
      <div class="rounded-lg border border-border p-3" style="background: var(--v-surface-card); box-shadow: var(--v-shadow-card);">
        <p class="text-[9px] tracking-wider uppercase text-dusk mb-0.5" style="font-family: 'JetBrains Mono', monospace;">Active projects</p>
        <p class="text-[20px] tracking-[-0.5px] text-ink leading-tight" style="font-family: 'Fraunces', serif; font-weight: 700;">8</p>
        <p class="text-[9px] text-sage mt-0.5" style="font-family: 'JetBrains Mono', monospace;">↑ +2 this week</p>
      </div>
    </div>
    <div class="wave-in" style="animation-delay: 180ms;">
      <div class="rounded-lg border border-[rgba(255,255,255,0.06)] p-3" style="background: var(--v-ink-2); box-shadow: var(--v-shadow-raised);">
        <p class="text-[9px] tracking-wider uppercase text-[rgba(245,243,238,0.45)] mb-0.5" style="font-family: 'JetBrains Mono', monospace;">Pending tasks</p>
        <p class="text-[20px] tracking-[-0.5px] text-surface leading-tight" style="font-family: 'Fraunces', serif; font-weight: 700;">12</p>
        <p class="text-[9px] text-gold mt-0.5" style="font-family: 'JetBrains Mono', monospace;">3 due today</p>
      </div>
    </div>
  </div>

  <!-- Project Cards -->
  <div class="grid gap-3 md:grid-cols-2 mb-5">
    <div class="wave-in" style="animation-delay: 240ms;">
      <div class="rounded-lg border border-border p-3" style="background: var(--v-surface-card); box-shadow: var(--v-shadow-card);">
        <div class="flex justify-between items-start mb-2">
          <div>
            <p class="text-[11px] text-ink mb-0.5" style="font-family: 'Fraunces', serif; font-weight: 700;">Dragon Lore — Brand Identity</p>
            <p class="text-[9px] text-dusk" style="font-family: 'JetBrains Mono', monospace;">Started Jun 12 · Est. delivery Jul 28</p>
          </div>
          <span class="inline-block text-[8px] tracking-wider px-2 py-0.5 rounded" style="font-family: 'JetBrains Mono', monospace; background: #D6DCF5; color: #2D3A7A;">In revision</span>
        </div>
        <div class="h-[2px] rounded-sm mb-1.5" style="background: var(--v-surface-2);">
          <div class="h-full rounded-sm" style="width: 68%; background: var(--v-sage);"></div>
        </div>
        <div class="flex justify-between items-center mt-2">
          <div class="flex gap-1">
            <div class="w-6 h-6 rounded-full flex items-center justify-center text-[9px]" style="background: var(--v-ink); color: var(--v-gold); font-family: 'Fraunces', serif; font-weight: 700;">A</div>
            <div class="w-6 h-6 rounded-full flex items-center justify-center text-[9px]" style="background: var(--v-gold-light); color: var(--v-gold-dark); font-family: 'Fraunces', serif; font-weight: 700;">DL</div>
          </div>
          <p class="text-[9px] text-dusk" style="font-family: 'JetBrains Mono', monospace;">68% complete</p>
        </div>
      </div>
    </div>

    <div class="wave-in" style="animation-delay: 300ms;">
      <div class="rounded-lg border border-border p-3" style="background: var(--v-surface-card); box-shadow: var(--v-shadow-card);">
        <div class="flex justify-between items-start mb-2">
          <div>
            <p class="text-[11px] text-ink mb-0.5" style="font-family: 'Fraunces', serif; font-weight: 700;">Meridian — Web Redesign</p>
            <p class="text-[9px] text-dusk" style="font-family: 'JetBrains Mono', monospace;">Started Jul 01 · Est. delivery Aug 15</p>
          </div>
          <span class="inline-block text-[8px] tracking-wider px-2 py-0.5 rounded" style="font-family: 'JetBrains Mono', monospace; background: var(--v-sage-light); color: var(--v-sage-dark);">Active</span>
        </div>
        <div class="h-[2px] rounded-sm mb-1.5" style="background: var(--v-surface-2);">
          <div class="h-full rounded-sm" style="width: 42%; background: var(--v-sage);"></div>
        </div>
        <div class="flex justify-between items-center mt-2">
          <div class="flex gap-1">
            <div class="w-6 h-6 rounded-full flex items-center justify-center text-[9px]" style="background: var(--v-ink); color: var(--v-gold); font-family: 'Fraunces', serif; font-weight: 700;">M</div>
          </div>
          <p class="text-[9px] text-dusk" style="font-family: 'JetBrains Mono', monospace;">42% complete</p>
        </div>
      </div>
    </div>
  </div>

  <!-- Recent Activity -->
  <div class="wave-in" style="animation-delay: 360ms;">
    <div class="rounded-lg border border-border p-3" style="background: var(--v-surface-card); box-shadow: var(--v-shadow-card);">
      <p class="text-[9px] tracking-wider uppercase text-dusk mb-3" style="font-family: 'JetBrains Mono', monospace;">Recent Activity</p>
      <div class="space-y-2.5">
        <div class="flex items-center gap-2.5">
          <div class="w-1 h-1 rounded-full" style="background: var(--v-sage);"></div>
          <div class="flex-1">
            <p class="text-[11px] text-ink" style="font-family: 'Inter', sans-serif;">New client registered — Acme Corp</p>
            <p class="text-[9px] text-dusk" style="font-family: 'JetBrains Mono', monospace;">2 minutes ago</p>
          </div>
        </div>
        <div class="flex items-center gap-2.5">
          <div class="w-1 h-1 rounded-full" style="background: var(--v-gold);"></div>
          <div class="flex-1">
            <p class="text-[11px] text-ink" style="font-family: 'Inter', sans-serif;">Invoice #00142 — ₱28,000 pending</p>
            <p class="text-[9px] text-dusk" style="font-family: 'JetBrains Mono', monospace;">1 hour ago</p>
          </div>
        </div>
        <div class="flex items-center gap-2.5">
          <div class="w-1 h-1 rounded-full" style="background: var(--v-navy);"></div>
          <div class="flex-1">
            <p class="text-[11px] text-ink" style="font-family: 'Inter', sans-serif;">Project milestone completed — Dragon Lore</p>
            <p class="text-[9px] text-dusk" style="font-family: 'JetBrains Mono', monospace;">3 hours ago</p>
          </div>
        </div>
      </div>
    </div>
  </div>
{/if}

<style>
  .wave-in {
    opacity: 0;
    animation: waveIn 0.5s ease-out forwards;
  }

  @keyframes waveIn {
    from {
      opacity: 0;
      transform: translateY(12px) scale(0.98);
    }
    to {
      opacity: 1;
      transform: translateY(0) scale(1);
    }
  }
</style>