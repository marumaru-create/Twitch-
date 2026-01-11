<template>
  <div class="min-h-screen flex flex-col">
    <!-- Header -->
    <UHeader>
      <template #logo>
        <span class="font-bold text-xl">Twitch収益チェッカー</span>
      </template>
      <template #right>
        <UButton color="primary" variant="ghost" label="設定" />
      </template>
    </UHeader>

    <!-- Main Content -->
    <main class="flex-1 container mx-auto px-4 py-8">
      <slot />
    </main>

    <!-- Footer -->
    <UFooter>
      <template #left>
        <p class="text-sm text-gray-500">© 2026 Twitch収益チェッカー</p>
      </template>
    </UFooter>
  </div>
</template>
