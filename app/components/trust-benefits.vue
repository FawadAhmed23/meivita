<template>
        <div 
          v-for="benefit in benefits" 
          :key="benefit.id"
          class="flex flex-col items-center text-center text-white group"
        >
          <div class="mb-4 transition-transform duration-300 group-hover:scale-110">
            <Icon 
              :name="benefit.iconName" 
              class="w-12 h-12 md:w-16 md:h-16 text-white"
            />
          </div>

          <h3 class="font-semibold text-sm md:text-base leading-tight">
            {{ benefit.title }}
          </h3>

          <p class="text-xs md:text-sm opacity-90 mt-1 leading-tight">
            {{ benefit.subtitle }}
          </p>
        </div>
</template>

<script setup>
import { Icon } from '#components'

// Props for customization
const props = defineProps({
  benefits: {
    type: Array,
    default: () => [
      {
        id: 1,
        title: '3rd Party ',
        subtitle: 'Tested',
        iconName: 'mdi:handshake'
      },
      {
        id: 2,
        title: 'cGMP',
        subtitle: 'Certified',
        iconName: 'mdi:factory'
      },
      {
        id: 3,
        title: 'GMO',
        subtitle: 'Free',
        iconName: 'mdi:leaf'
      },
      {
        id: 4,
        title: 'Complete',
        subtitle: 'Transparency',
        iconName: 'mdi:file-document-outline' 
      },
      {
        id: 5,
        title: 'Additive',
        subtitle: 'Free',
        iconName: 'mdi:noodles' 
      },
      {
        id: 6,
        title: 'Global Standard',
        subtitle: 'Certificated',
        iconName: 'mdi:certificate'
      }
    ]
  }
})
</script>
