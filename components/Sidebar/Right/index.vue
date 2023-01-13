<script setup>
const whatsHappeningItems = ref([
  { title: 'Fender', count: '124k Tweets' },
  { title: '#vue', count: '28k Tweets' },
  { title: '#angular', count: '21k Tweets' },
  { title: '#react', count: '64k Tweets' },
])

const whoToFollowItems = ref([
  {
    name: 'Marcus Miller',
    handle: '@marcusmiller',
    image: 'https://picsum.photos/200/200',
  },
  { name: 'Flea', handle: '@flea', image: 'https://picsum.photos/200/200' },
  {
    name: 'Chick Korea',
    handle: '@chickkorea',
    image: 'https://picsum.photos/200/200',
  },
])
</script>

<template>
  <div class="flex flex-col">
    <!-- Preview Card: What's happening? -->
    <SidebarRightPreviewCard title="What's happening">
      <SidebarRightPreviewCardItem v-for="what in whatsHappeningItems">
        <div>
          <h2 class="font-bold text-gray-800 text-md dark:text-whte">
            {{ what.title }}
          </h2>
          <p class="text-xs text-gray-400">
            {{ what.count }}
          </p>
        </div>
      </SidebarRightPreviewCardItem>
    </SidebarRightPreviewCard>

    <!-- Preview Card: Follow -->
    <SidebarRightPreviewCard title="Who to follow">
      <SidebarRightPreviewCardItem v-for="follow in whoToFollowItems">
        <div class="flex flex-row justify-between items-center p-2">
          <div class="flex flex-row">
            <img
              class="w-10 h-10 rounded-full"
              :src="follow.image"
              :alt="follow.name"
            />

            <div class="flex flex-col ml-2">
              <h1 class="text-sm font-bold text-gray-900 dark:text-white">
                {{ follow.name }}
              </h1>
              <p class="text-xs text-gray-400">{{ follow.handle }}</p>
            </div>
          </div>

          <div class="flex h-full">
            <button
              class="px-4 py-2 rounded-full text-xs font-bold text-white dark:text-black bg-black dark:bg-white"
            >
              Follow
            </button>
          </div>
        </div>
      </SidebarRightPreviewCardItem>
    </SidebarRightPreviewCard>
  </div>
</template>
