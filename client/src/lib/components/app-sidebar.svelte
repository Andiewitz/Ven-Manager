<script lang="ts">
  import LayoutDashboard from '@lucide/svelte/icons/layout-dashboard';
  import Users from '@lucide/svelte/icons/users';
  import FolderOpen from '@lucide/svelte/icons/folder-open';
  import MessageSquare from '@lucide/svelte/icons/message-square';
  import Receipt from '@lucide/svelte/icons/receipt';
  import Settings from '@lucide/svelte/icons/settings';
  import PanelLeftClose from '@lucide/svelte/icons/panel-left-close';
  import PanelLeftOpen from '@lucide/svelte/icons/panel-left-open';
  import { sidebarCollapsed, toggleSidebar } from '$lib/stores/sidebar';

  let { currentPath = '/' } = $props();

  let collapsed = $state(false);

  $effect(() => {
    const unsub = sidebarCollapsed.subscribe(v => collapsed = v);
    return unsub;
  });

  const navItems = [
    { icon: LayoutDashboard, label: 'Dashboard', href: '/' },
    { icon: Users, label: 'Clients', href: '/clients' },
    { icon: FolderOpen, label: 'Projects', href: '/projects' },
    { icon: MessageSquare, label: 'Messages', href: '/messages' },
    { icon: Receipt, label: 'Invoices', href: '/invoices' },
    { icon: Settings, label: 'Settings', href: '/settings' },
  ];
</script>

<aside class="sidebar" class:collapsed>
  <div class="sidebar-brand wave-in" style="animation-delay: 0ms;">
    {#if collapsed}
      <button onclick={toggleSidebar} class="toggle-btn" title="Expand sidebar">
        <PanelLeftOpen class="size-5" />
      </button>
    {:else}
      <div class="brand-icon">V</div>
      <div class="brand-text">
        <span class="brand-name">Ven-Manager</span>
        <span class="brand-label">Admin Workspace</span>
      </div>
      <button onclick={toggleSidebar} class="toggle-btn toggle-btn-side" title="Collapse sidebar">
        <PanelLeftClose class="size-5" />
      </button>
    {/if}
  </div>

  <nav class="sidebar-nav">
    {#each navItems as item, i}
      <a
        href={item.href}
        class="nav-item wave-in"
        class:active={currentPath === item.href}
        title={collapsed ? item.label : undefined}
        style="animation-delay: {i * 50}ms;"
      >
        <span class="nav-dot"></span>
        <item.icon class="nav-icon" />
        {#if !collapsed}
          <span class="nav-label">{item.label}</span>
        {/if}
      </a>
    {/each}
  </nav>

  <div class="sidebar-footer wave-in" style="animation-delay: 300ms;">
    <div class="user-avatar">A</div>
    {#if !collapsed}
      <div class="user-info">
        <span class="user-name">Admin</span>
        <span class="user-email">admin@ven-manager.com</span>
      </div>
    {/if}
  </div>
</aside>

<style>
  .sidebar {
    width: 220px;
    height: 100vh;
    background: var(--v-ink);
    display: flex;
    flex-direction: column;
    padding: 14px 16px;
    gap: 2px;
    box-shadow: var(--v-shadow-raised);
    flex-shrink: 0;
    transition: width 0.18s ease-out;
    overflow: hidden;
  }

  .sidebar.collapsed {
    width: 64px;
    padding: 14px 12px;
  }

  .sidebar-brand {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 8px 10px 14px;
    border-bottom: 0.5px solid rgba(255, 255, 255, 0.06);
    margin-bottom: 8px;
    min-height: 48px;
  }

  .collapsed .sidebar-brand {
    padding: 8px 0 14px;
    justify-content: center;
    border-bottom: none;
    margin-bottom: 4px;
  }

  .brand-icon {
    width: 32px;
    height: 32px;
    border-radius: 8px;
    background: var(--v-gold);
    color: var(--v-ink);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Libre Baskerville', serif;
    font-size: 14px;
    flex-shrink: 0;
  }

  .brand-text {
    display: flex;
    flex-direction: column;
    min-width: 0;
    flex: 1;
  }

  .brand-name {
    font-family: 'Libre Baskerville', serif;
    font-weight: 700;
    font-size: 13px;
    color: var(--v-surface);
    white-space: nowrap;
  }

  .brand-label {
    font-family: 'Courier New', monospace;
    font-size: 9px;
    color: rgba(245, 243, 238, 0.35);
    letter-spacing: 0.04em;
    white-space: nowrap;
  }

  .toggle-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 32px;
    height: 32px;
    border-radius: 6px;
    border: none;
    background: transparent;
    color: rgba(245, 243, 238, 0.55);
    cursor: pointer;
    transition: all 0.18s ease-out;
    flex-shrink: 0;
  }

  .toggle-btn:hover {
    background: rgba(200, 168, 90, 0.15);
    color: var(--v-gold);
  }

  .toggle-btn-side {
    margin-left: auto;
  }

  .sidebar-nav {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 2px;
  }

  .nav-item {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 7px 10px;
    border-radius: 6px;
    font-family: -apple-system, 'Helvetica Neue', sans-serif;
    font-size: 12px;
    color: rgba(245, 243, 238, 0.55);
    text-decoration: none;
    transition: all 0.18s ease-out;
    cursor: pointer;
    position: relative;
  }

  .collapsed .nav-item {
    padding: 7px;
    justify-content: center;
  }

  .nav-item:hover {
    background: rgba(200, 168, 90, 0.15);
    color: var(--v-gold);
  }

  .nav-item.active {
    background: rgba(200, 168, 90, 0.15);
    color: var(--v-gold);
  }

  .nav-dot {
    width: 5px;
    height: 5px;
    border-radius: 50%;
    background: var(--v-gold);
    opacity: 0;
    transition: opacity 0.18s ease-out;
    position: absolute;
    left: 2px;
  }

  .collapsed .nav-dot {
    left: 50%;
    transform: translateX(-50%);
    bottom: 2px;
  }

  .nav-item.active .nav-dot {
    opacity: 1;
  }

  .nav-icon {
    width: 16px;
    height: 16px;
    flex-shrink: 0;
  }

  .nav-label {
    flex: 1;
    white-space: nowrap;
  }

  .sidebar-footer {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px;
    border-top: 0.5px solid rgba(255, 255, 255, 0.06);
    margin-top: 8px;
  }

  .collapsed .sidebar-footer {
    padding: 10px 0;
    justify-content: center;
    border-top: none;
    margin-top: 4px;
  }

  .user-avatar {
    width: 32px;
    height: 32px;
    border-radius: 50%;
    background: var(--v-gold);
    color: var(--v-ink);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Libre Baskerville', serif;
    font-size: 13px;
    flex-shrink: 0;
  }

  .user-info {
    display: flex;
    flex-direction: column;
    min-width: 0;
  }

  .user-name {
    font-family: 'Libre Baskerville', serif;
    font-weight: 700;
    font-size: 13px;
    color: var(--v-surface);
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  .user-email {
    font-family: 'Courier New', monospace;
    font-size: 10px;
    color: rgba(245, 243, 238, 0.35);
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  .wave-in {
    opacity: 0;
    animation: waveIn 0.4s ease-out forwards;
  }

  @keyframes waveIn {
    from {
      opacity: 0;
      transform: translateX(-8px);
    }
    to {
      opacity: 1;
      transform: translateX(0);
    }
  }
</style>