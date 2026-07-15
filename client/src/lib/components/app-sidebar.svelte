<script lang="ts">
  import { Sidebar, SidebarBrand, SidebarGroup, SidebarItem, SidebarWrapper } from 'flowbite-svelte';
  import { LayoutDashboard, Users, FolderOpen, MessageSquare, Receipt, Settings } from '@lucide/svelte';

  let activeUrl = $state('/');

  const navItems = [
    { icon: LayoutDashboard, label: 'Dashboard', href: '/' },
    { icon: Users, label: 'Clients', href: '/clients' },
    { icon: FolderOpen, label: 'Projects', href: '/projects' },
    { icon: MessageSquare, label: 'Messages', href: '/messages' },
    { icon: Receipt, label: 'Invoices', href: '/invoices' },
    { icon: Settings, label: 'Settings', href: '/settings' },
  ];

  $effect(() => {
    activeUrl = window.location.pathname;
  });
</script>

<Sidebar class="w-56" activeUrl={activeUrl}>
  <SidebarWrapper>
    <SidebarBrand href="/" name="Ven-Manager" img="/favicon.svg">
      <div class="flex items-center gap-2">
        <div class="flex size-8 items-center justify-center rounded-lg" style="background: var(--v-gold); color: var(--v-ink); font-family: 'Georgia', serif;">
          V
        </div>
        <div>
          <p class="text-sm font-semibold" style="font-family: 'Georgia', serif; color: var(--v-surface);">Ven-Manager</p>
          <p class="text-[9px] tracking-wider uppercase" style="font-family: 'Courier New', monospace; color: rgba(245,243,238,0.35);">Admin Workspace</p>
        </div>
      </div>
    </SidebarBrand>

    <SidebarGroup>
      {#each navItems as item}
        <SidebarItem href={item.href} active={activeUrl === item.href}>
          <item.icon class="size-4" />
          <span class="text-xs">{item.label}</span>
        </SidebarItem>
      {/each}
    </SidebarGroup>
  </SidebarWrapper>
</Sidebar>