<script setup lang="ts">
const channelName = ref('');
const errorMessage = ref('');

const validateChannelName = () => {
  if (!channelName.value.trim()) {
    errorMessage.value = 'チャンネル名を入力してください';
    return false;
  }
  errorMessage.value = '';
  return true;
};

const onSearchClick = () => {
  if (!validateChannelName()) return;
  const trimmedName = channelName.value.trim();
  const targetUrl = `https://twitchtracker.com/${encodeURIComponent(trimmedName)}/earnings`;
  if (import.meta.client) {
    window.open(targetUrl, '_blank', 'noopener');
  }
};

watch(channelName, (value) => {
  if (value.trim()) {
    errorMessage.value = '';
  }
});
</script>
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
            v-model="channelName"
            icon="i-heroicons-magnifying-glass"
            placeholder="Search channel..."
          />
          <UButton color="primary" variant="solid" @click="onSearchClick">検索</UButton>
        </div>
        <p v-if="errorMessage" class="text-sm text-red-600">{{ errorMessage }}</p>
      </div>
    </UCard>
  </UContainer>
</template>

