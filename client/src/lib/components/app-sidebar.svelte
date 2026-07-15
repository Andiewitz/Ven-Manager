<script lang="ts">
  import * as Sidebar from '$lib/components/ui/sidebar';
  import * as Tooltip from '$lib/components/ui/tooltip';
  import { LayoutDashboard, Users, Settings, BarChart3, Bell } from '@lucide/svelte';

  const navItems = [
    { icon: LayoutDashboard, label: 'Dashboard', href: '/' },
    { icon: Users, label: 'Users', href: '/users' },
    { icon: BarChart3, label: 'Analytics', href: '/analytics' },
    { icon: Bell, label: 'Notifications', href: '/notifications' },
    { icon: Settings, label: 'Settings', href: '/settings' },
  ];
</script>

<Sidebar.Root collapsible="icon">
  <Sidebar.Header>
    <Sidebar.Menu>
      <Sidebar.MenuItem>
        <Sidebar.MenuButton size="lg">
          <div class="flex aspect-square size-8 items-center justify-center rounded-lg bg-primary text-primary-foreground">
            <span class="font-bold">V</span>
          </div>
          <div class="grid flex-1 text-left text-sm leading-tight">
            <span class="truncate font-semibold">Ven-Manager</span>
            <span class="truncate text-xs">Dashboard</span>
          </div>
        </Sidebar.MenuButton>
      </Sidebar.MenuItem>
    </Sidebar.Menu>
  </Sidebar.Header>
  <Sidebar.Content>
    <Sidebar.Group>
      <Sidebar.GroupLabel>Navigation</Sidebar.GroupLabel>
      <Sidebar.GroupContent>
        <Sidebar.Menu>
          {#each navItems as item}
            <Sidebar.MenuItem>
              <Tooltip.Provider>
                <Tooltip.Root>
                  <Tooltip.Trigger>
                    <Sidebar.MenuButton href={item.href}>
                      <item.icon class="size-4" />
                      <span>{item.label}</span>
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
        <Sidebar.MenuButton>
          <div class="flex size-8 items-center justify-center rounded-full bg-muted">
            <span class="text-sm font-medium">A</span>
          </div>
          <div class="grid flex-1 text-left text-sm leading-tight">
            <span class="truncate font-semibold">Admin</span>
            <span class="truncate text-xs">admin@ven-manager.com</span>
          </div>
        </Sidebar.MenuButton>
      </Sidebar.MenuItem>
    </Sidebar.Menu>
  </Sidebar.Footer>
  <Sidebar.Rail />
</Sidebar.Root>