<script lang="ts">
  import AppSidebar from '$lib/components/app-sidebar.svelte';
  import Dashboard from '$lib/pages/dashboard.svelte';
</script>

<div class="flex h-screen">
  <AppSidebar />
  <main class="flex-1 overflow-auto" style="background: var(--v-surface);">
    <header class="h-16 shrink-0 flex items-center gap-2 border-b px-6" style="border-color: var(--v-border); background: var(--v-surface-card);">
      <h1 class="text-[18px] font-normal tracking-[-0.3px]" style="font-family: 'Georgia', serif; color: var(--v-ink);">Dashboard</h1>
    </header>
    <div class="p-6">
      <Dashboard />
    </div>
  </main>
</div>