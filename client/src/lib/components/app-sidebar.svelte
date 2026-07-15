<script lang="ts">
  import { LayoutDashboard, Users, FolderOpen, MessageSquare, Receipt, Settings } from '@lucide/svelte';

  let { currentPath = '/' } = $props();

  const navItems = [
    { icon: LayoutDashboard, label: 'Dashboard', href: '/' },
    { icon: Users, label: 'Clients', href: '/clients' },
    { icon: FolderOpen, label: 'Projects', href: '/projects' },
    { icon: MessageSquare, label: 'Messages', href: '/messages' },
    { icon: Receipt, label: 'Invoices', href: '/invoices' },
    { icon: Settings, label: 'Settings', href: '/settings' },
  ];
</script>

<aside class="sidebar">
  <div class="sidebar-brand">
    <div class="brand-icon">V</div>
    <div class="brand-text">
      <span class="brand-name">Ven-Manager</span>
      <span class="brand-label">Admin Workspace</span>
    </div>
  </div>

  <nav class="sidebar-nav">
    {#each navItems as item}
      <a
        href={item.href}
        class="nav-item"
        class:active={currentPath === item.href}
      >
        <span class="nav-dot"></span>
        <item.icon class="nav-icon" />
        <span class="nav-label">{item.label}</span>
      </a>
    {/each}
  </nav>

  <div class="sidebar-footer">
    <div class="user-avatar">A</div>
    <div class="user-info">
      <span class="user-name">Admin</span>
      <span class="user-email">admin@ven-manager.com</span>
    </div>
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
  }

  .sidebar-brand {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 8px 10px 14px;
    border-bottom: 0.5px solid rgba(255, 255, 255, 0.06);
    margin-bottom: 8px;
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
    font-family: 'Georgia', serif;
    font-size: 14px;
  }

  .brand-text {
    display: flex;
    flex-direction: column;
  }

  .brand-name {
    font-family: 'Georgia', serif;
    font-size: 13px;
    color: var(--v-surface);
  }

  .brand-label {
    font-family: 'Courier New', monospace;
    font-size: 9px;
    color: rgba(245, 243, 238, 0.35);
    letter-spacing: 0.04em;
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
  }

  .nav-item.active .nav-dot {
    opacity: 1;
  }

  .nav-label {
    flex: 1;
  }

  .sidebar-footer {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px;
    border-top: 0.5px solid rgba(255, 255, 255, 0.06);
    margin-top: 8px;
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
    font-family: 'Georgia', serif;
    font-size: 13px;
    flex-shrink: 0;
  }

  .user-info {
    display: flex;
    flex-direction: column;
    min-width: 0;
  }

  .user-name {
    font-family: 'Georgia', serif;
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
</style>