<script setup lang="ts">
import type { ProductFragment } from '@@/types/shopify';

// Props
const props = defineProps<{
  product: ProductFragment;
}>();

// Helpers
const { getColorOption } = useShopifyHelpers();

// Computed
const colorOption = computed(() => getColorOption(props.product.options));
const colorOptionName = computed(() => colorOption.value?.optionValues[0]?.name);

// Flatten connection objects
const mediaItems = computed(() => flattenConnection(props.product.media));
const formattedTitle = computed(() => {
  const [title, ...rest] = props.product.title.split(",");
  return {
    title: title.trim(),
    subtitle: rest.join(",").trim() || null
  };
});
</script>

<template>
  <NuxtLink :to="`/products/${product.handle}`" class="relative flex flex-col gap-5 w-full md:w-1/4">
    <ProductCardTags :product="product" />
    <ProductCardMedia :media-items="mediaItems" />
    <div class="flex flex-col gap-2">
      <div>
        <div class="productName">
          <h2 v-if="product.title" class="text-lg font-semibold text-gray-900">{{ formattedTitle.title }}</h2>
          <h3 v-if="formattedTitle.subtitle" class="text-md text-gray-500">{{ formattedTitle.subtitle }}</h3>
        </div>
        <h3 v-if="colorOption" class="normal-case">
          {{ colorOptionName }}
        </h3>
      </div>
      <div class="text-meivita-green font-medium text-lg">
        <PriceDisplay :price="product.priceRange.minVariantPrice"
          :compare-at-price-range="product.compareAtPriceRange.minVariantPrice" />
      </div>
    </div>
  </NuxtLink>
</template>
