<script lang="ts">
  import * as Sidebar from '$lib/components/ui/sidebar';
  import * as Card from '$lib/components/ui/card';
  import AppSidebar from '$lib/components/app-sidebar.svelte';
  import { Users, BarChart3, Bell, Activity } from '@lucide/svelte';
</script>

<Sidebar.Provider>
  <AppSidebar />
  <Sidebar.Inset>
    <header class="flex h-16 shrink-0 items-center gap-2 border-b px-4">
      <Sidebar.Trigger />
      <h1 class="text-lg font-semibold">Dashboard</h1>
    </header>
    <main class="flex-1 overflow-auto p-6">
      <div class="grid gap-4 md:grid-cols-2 lg:grid-cols-4">
        <Card.Root>
          <Card.Header class="flex flex-row items-center justify-between space-y-0 pb-2">
            <Card.Title class="text-sm font-medium">Total Users</Card.Title>
            <Users class="size-4 text-muted-foreground" />
          </Card.Header>
          <Card.Content>
            <div class="text-2xl font-bold">1,234</div>
            <p class="text-xs text-muted-foreground">+20.1% from last month</p>
          </Card.Content>
        </Card.Root>
        <Card.Root>
          <Card.Header class="flex flex-row items-center justify-between space-y-0 pb-2">
            <Card.Title class="text-sm font-medium">Active Sessions</Card.Title>
            <Activity class="size-4 text-muted-foreground" />
          </Card.Header>
          <Card.Content>
            <div class="text-2xl font-bold">456</div>
            <p class="text-xs text-muted-foreground">+12.5% from last hour</p>
          </Card.Content>
        </Card.Root>
        <Card.Root>
          <Card.Header class="flex flex-row items-center justify-between space-y-0 pb-2">
            <Card.Title class="text-sm font-medium">Analytics</Card.Title>
            <BarChart3 class="size-4 text-muted-foreground" />
          </Card.Header>
          <Card.Content>
            <div class="text-2xl font-bold">78.2%</div>
            <p class="text-xs text-muted-foreground">+5.2% from yesterday</p>
          </Card.Content>
        </Card.Root>
        <Card.Root>
          <Card.Header class="flex flex-row items-center justify-between space-y-0 pb-2">
            <Card.Title class="text-sm font-medium">Notifications</Card.Title>
            <Bell class="size-4 text-muted-foreground" />
          </Card.Header>
          <Card.Content>
            <div class="text-2xl font-bold">12</div>
            <p class="text-xs text-muted-foreground">3 unread</p>
          </Card.Content>
        </Card.Root>
      </div>
      <div class="mt-6">
        <Card.Root>
          <Card.Header>
            <Card.Title>Recent Activity</Card.Title>
            <Card.Description>Your recent actions and updates.</Card.Description>
          </Card.Header>
          <Card.Content>
            <div class="space-y-4">
              <div class="flex items-center gap-4">
                <div class="size-2 rounded-full bg-green-500"></div>
                <div class="flex-1">
                  <p class="text-sm">New user registered</p>
                  <p class="text-xs text-muted-foreground">2 minutes ago</p>
                </div>
              </div>
              <div class="flex items-center gap-4">
                <div class="size-2 rounded-full bg-blue-500"></div>
                <div class="flex-1">
                  <p class="text-sm">System update completed</p>
                  <p class="text-xs text-muted-foreground">1 hour ago</p>
                </div>
              </div>
              <div class="flex items-center gap-4">
                <div class="size-2 rounded-full bg-yellow-500"></div>
                <div class="flex-1">
                  <p class="text-sm">Database backup scheduled</p>
                  <p class="text-xs text-muted-foreground">3 hours ago</p>
                </div>
              </div>
            </div>
          </Card.Content>
        </Card.Root>
      </div>
    </main>
  </Sidebar.Inset>
</Sidebar.Provider>