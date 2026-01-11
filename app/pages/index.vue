<template>
  <UContainer class="py-10">
    <UCard>
      <template #header>
        <h2 class="text-xl font-bold text-primary">Twitch 収益チェッカー</h2>
      </template>

      <div class="space-y-4">
        <p>チャンネル名を入力してください</p>
        <div class="flex gap-2">
          <UInput
            icon="i-heroicons-magnifying-glass"
            placeholder="Search channel..."
          />
          <UButton color="primary" variant="solid">検索</UButton>
        </div>
      </div>
    </UCard>
  </UContainer>
</template>
