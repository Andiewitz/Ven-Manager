<script lang="ts">
  import AppSidebar from '$lib/components/app-sidebar.svelte';
  import Dashboard from '$lib/pages/dashboard.svelte';
  import { page } from '$app/stores';
  import { PanelLeftClose, PanelLeftOpen } from '@lucide/svelte';
  import { sidebarCollapsed, toggleSidebar } from '$lib/stores/sidebar';

  let collapsed = $state(false);

  $effect(() => {
    const unsub = sidebarCollapsed.subscribe(v => collapsed = v);
    return unsub;
  });
</script>

<div class="flex h-screen">
  <AppSidebar currentPath={$page.url.pathname} />
  <main class="flex-1 overflow-auto" style="background: var(--v-surface);">
    <header class="h-16 shrink-0 flex items-center gap-3 border-b px-6" style="border-color: var(--v-border); background: var(--v-surface-card);">
      <button onclick={toggleSidebar} class="toggle-btn" title="Toggle sidebar">
        {#if collapsed}
          <PanelLeftOpen class="size-5" />
        {:else}
          <PanelLeftClose class="size-5" />
        {/if}
      </button>
      <h1 class="text-[18px] font-normal tracking-[-0.3px]" style="font-family: 'Georgia', serif; color: var(--v-ink);">Dashboard</h1>
    </header>
    <div class="p-6">
      <Dashboard />
    </div>
  </main>
</div>

<style>
  .toggle-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 32px;
    height: 32px;
    border-radius: 6px;
    border: none;
    background: transparent;
    color: var(--v-muted);
    cursor: pointer;
    transition: all 0.18s ease-out;
  }

  .toggle-btn:hover {
    background: var(--v-surface-2);
    color: var(--v-ink);
  }
</style>