<template>
  <div class="w-full overflow-hidden bg-meivita-green-dark text-meivita-green-light z-20 h-12 flex">
    <div
      class="flex w-max animate-scroll"
    >
      <!-- First copy -->
      <ul class="flex list-none px-8 md:px-48 gap-8 md:gap-48">
        <li v-for="(item, index) in announcements" :key="'a-' + index" class="flex items-center font-medium whitespace-nowrap">
          <a
            :href="item.href"
            class="text-xl hover:underline"
            :aria-label="item.label"
          >
            {{ item.text }}
          </a>
        </li>
      </ul>

      <!-- Second copy (for seamless loop) -->
      <ul class="flex list-none gap-8 md:gap-48">
        <li v-for="(item, index) in announcements" :key="'b-' + index" class="flex items-center font-medium whitespace-nowrap">
          <a
            :href="item.href"
            class="text-xl hover:underline"
            :aria-label="item.label"
          >
            {{ item.text }}
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
const announcements = [
  { text: "Clean ingredients", href: "/", label: "Clean ingredients" },
  { text: "Thoughtful formulas", href: "/", label: "Thoughtful formulas" },
  { text: "No fillers or fads", href: "/", label: "No fillers or fads" },
  { text: "Liposomal Technology", href: "/", label: "Liposomal Technology" },
  { text: "Up to 90% Absorption", href: "/", label: "Up to 90% Absorption" },
]
</script>

<style scoped>
@keyframes scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

.animate-scroll {
  animation: scroll 45s linear infinite;
}
</style>
