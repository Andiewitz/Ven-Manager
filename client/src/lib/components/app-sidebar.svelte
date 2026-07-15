<script lang="ts">
  import * as Sidebar from '$lib/components/ui/sidebar';
  import * as Tooltip from '$lib/components/ui/tooltip';
  import { LayoutDashboard, Users, FolderOpen, MessageSquare, Receipt, Settings } from '@lucide/svelte';

  const navItems = [
    { icon: LayoutDashboard, label: 'Dashboard', href: '/' },
    { icon: Users, label: 'Clients', href: '/clients' },
    { icon: FolderOpen, label: 'Projects', href: '/projects' },
    { icon: MessageSquare, label: 'Messages', href: '/messages' },
    { icon: Receipt, label: 'Invoices', href: '/invoices' },
    { icon: Settings, label: 'Settings', href: '/settings' },
  ];
</script>

<Sidebar.Root collapsible="icon">
  <Sidebar.Header>
    <Sidebar.Menu>
      <Sidebar.MenuItem>
        <Sidebar.MenuButton size="lg" class="bg-transparent hover:bg-sidebar-accent">
          <div class="flex aspect-square size-8 items-center justify-center rounded-lg bg-gold text-ink font-normal" style="font-family: 'Georgia', serif;">
            V
          </div>
          <div class="grid flex-1 text-left text-sm leading-tight">
            <span class="truncate font-semibold" style="font-family: 'Georgia', serif;">Ven-Manager</span>
            <span class="truncate text-[9px] tracking-wider uppercase text-[rgba(245,243,238,0.35)]" style="font-family: 'Courier New', monospace;">
              Admin Workspace
            </span>
          </div>
        </Sidebar.MenuButton>
      </Sidebar.MenuItem>
    </Sidebar.Menu>
  </Sidebar.Header>
  <Sidebar.Content>
    <Sidebar.Group>
      <Sidebar.GroupContent>
        <Sidebar.Menu>
          {#each navItems as item}
            <Sidebar.MenuItem>
              <Tooltip.Provider>
                <Tooltip.Root>
                  <Tooltip.Trigger>
                    <Sidebar.MenuButton
                      href={item.href}
                      class="text-[rgba(245,243,238,0.55)] hover:text-gold hover:bg-sidebar-accent data-[active=true]:text-gold data-[active=true]:bg-sidebar-accent"
                    >
                      <item.icon class="size-4" />
                      <span style="font-family: -apple-system, 'Helvetica Neue', sans-serif; font-size: 12px;">{item.label}</span>
                    </Sidebar.MenuButton>
                  </Tooltip.Trigger>
                  <Tooltip.Content>
                    <p>{item.label}</p>
                  </Tooltip.Content>
                </Tooltip.Root>
              </Tooltip.Provider>
            </Sidebar.MenuItem>
          {/each}
        </Sidebar.Menu>
      </Sidebar.GroupContent>
    </Sidebar.Group>
  </Sidebar.Content>
  <Sidebar.Footer>
    <Sidebar.Menu>
      <Sidebar.MenuItem>
        <Sidebar.MenuButton class="text-[rgba(245,243,238,0.55)] hover:text-gold hover:bg-sidebar-accent">
          <div class="flex size-8 items-center justify-center rounded-full bg-gold text-ink" style="font-family: 'Georgia', serif; font-size: 13px;">
            A
          </div>
          <div class="grid flex-1 text-left text-sm leading-tight">
            <span class="truncate font-semibold text-surface" style="font-family: 'Georgia', serif;">Admin</span>
            <span class="truncate text-[10px] text-[rgba(245,243,238,0.35)]" style="font-family: 'Courier New', monospace;">
              admin@ven-manager.com
            </span>
          </div>
        </Sidebar.MenuButton>
      </Sidebar.MenuItem>
    </Sidebar.Menu>
  </Sidebar.Footer>
  <Sidebar.Rail />
</Sidebar.Root>