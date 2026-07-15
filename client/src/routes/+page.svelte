<script lang="ts">
  import * as Sidebar from '$lib/components/ui/sidebar';
  import AppSidebar from '$lib/components/app-sidebar.svelte';
  import Dashboard from '$lib/pages/dashboard.svelte';
</script>

<Sidebar.Provider>
  <AppSidebar />
  <Sidebar.Inset>
    <header class="flex h-16 shrink-0 items-center gap-2 border-b border-border px-4">
      <Sidebar.Trigger />
      <h1 class="text-[18px] font-normal tracking-[-0.3px]" style="font-family: 'Georgia', serif;">Dashboard</h1>
    </header>
    <main class="flex-1 overflow-auto p-6">
      <Dashboard />
    </main>
  </Sidebar.Inset>
</Sidebar.Provider>