<script setup lang="ts">
defineProps<{
  title: string
  icon: string
  description: string
  link: string
  external?: boolean
}>()
</script>
<template>
  <UCard
    :ui="{
      rounded: 'rounded',
      base: 'cursor-pointer relative focus-within:ring-2 focus-within:ring-gray-500 hover:ring-2 hover:ring-gray-500 transition-colors',
      body: {
        base: 'w-[325px] h-full',
        padding: 'sm:px-0 sm:py-0 p-0'
      },
    }"
  >
    <div class="flex flex-col items-center justify-center gap-6 p-4 sm:px-10 sm:py-8">
      <h2 class="text-lg font-semibold uppercase text-bcGovColor-darkGray dark:text-white">
        <NuxtLink :to="link" :target="external ? '_blank' : '_self'" class="focus:outline-none">
          {{ title }}
        </NuxtLink>
      </h2>
      <div class="flex size-16 items-center justify-center rounded-full bg-bcGovColor-nonClickable">
        <UIcon :name="icon" class="size-8 shrink-0 self-center text-white " />
      </div>
      <p class="text-sm text-bcGovColor-midGray dark:text-gray-400">
        {{ description }}
      </p>
      <span class="font-semibold tracking-wide text-bcGovBlue-500 underline dark:text-white">
        {{ $t('SbcMainCard.learnMore') }}
      </span>
    </div>
  </UCard>
</template>
<style scoped>
/* Set link to whole card while keeping link label the same as the card title */
a::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}
</style>
