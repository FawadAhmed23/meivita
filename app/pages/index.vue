<!-- eslint-disable vue/html-self-closing -->
<template>
  <div>
    <nav aria-label="Benefits" class="">
      <div class="mx-auto">
        <ul role="list" class="grid divide-gray-200 grid-cols-3 divide-x divide-y-0">
          <li v-for="offer in offers" :key="offer.name" class="flex flex-col">
            <div class="relative flex flex-1 flex-col justify-center bg-white px-4 py-6 text-center focus:z-10">
              <p class="text-sm text-gray-500">{{ offer.name }}</p>
              <p class="font-semibold text-meivita-green-dark">{{ offer.description }}</p>
            </div>
          </li>
        </ul>
      </div>
    </nav>

    <div class="bg-[#F3F1E4] md:pt-0 pt-12 overflow-hidden">
      <div
        class="flex items-center md:justify-between gap-8 relative w-[90%] mx-auto md:h-[70vh] h-auto md:flex-row flex-col">
        <div class="flex flex-col  gap-2 items-start text-left px-6 lg:px-0">
          <span class="text-left font-semibold leading-loose text-meivita-green-dark text-3xl">Now In Stock: </span>
          <h1 class="text-5xl md:text-8xl font-bold tracking-tight text-meivita-green-dark">
            Liposomal Glutathione
          </h1>
          <p class="mt-4 text-2xl text-meivita-green-dark">
            Superior absorption meets one of nature's most powerful antioxidants
          </p>
          <NuxtLink to="/products/liposomal-glutathione"
            class="mt-4 inline-block w-full text-center text-white text-2xl md:text-left md:w-fit py-4 md:px-8 md:py-4 rounded-sm md:rounded bg-meivita-green hover:bg-meivita-green-dark">
            Shop Now</NuxtLink>
        </div>
        <div class="md:w-1/2 w-full h-full">
          <NuxtImg src="/img/glutathione-img.png" preload alt="Background top"
            class="w-full h-full object-contain block rotate-[25deg]" />
        </div>
      </div>
    </div>

    <MarqueeSlider />


    <section aria-labelledby="glutathione-products" class="w-[90%] mx-auto py-24">
      <div class="text-5xl md:text-6xl tracking-tight mb-12 flex flex-col gap-2">
        <span
          class="text-lg text-white px-3 py-1 bg-meivita-green rounded-full capitalize w-fit drop-shadow-md letter-spacing-wide">
          best sellers
        </span>
        <h2 id="glutathione-products" class="text-meivita-green-dark font-bold">Elevate your Wellbeing Routine</h2>
      </div>
      <div class="flex flex-wrap gap-6 items-stretch">
        <ProductCard v-for="p in products" :key="p.id" :product="p" />
      </div>
    </section>


    <section class="bg-meivita-green-dark py-24">
      <div class="w-[90%] mx-auto">
        <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-8 lg:gap-6">
          <div class="col-span-2 md:col-span-6 text-center flex flex-col gap-6 text-white">
            <h2 class="text-4xl font-bold uppercase mb-12">we bare all. so you can relax</h2>
          </div>
          <TrustBenefits />
        </div>
      </div>
    </section>

    <section aria-labelledby="why-liposomal" class="py-24">
      <div
        class="mx-auto max-w-7xl text-center px-4 sm:px-6 lg:max-w-8xl lg:px-8 py-24 px-32 rounded-lg shadow-lg bg-[linear-gradient(121deg,rgba(120,171,43,1)_0%,rgba(99,138,40,1)_28%,rgba(122,177,42,1)_54%,rgba(82,115,32,1)_93%)]">
        <h2 class="text-4xl md:text-5xl tracking-tight mb-10 text-white px-3 py-1 uppercase font-bold">
          why "me i vita"?
        </h2>

        <div class="text-center mx-auto max-w-3xl text-white flex flex-col gap-2 text-xl">
          <p>Life starts with me. That’s the heart of ME I VITA
            Real health begins inside—and it doesn’t have to be complicated.

            ME I VITA makes caring for your body feel effortless with clean, no-nonsense supplements for everyday life.
          </p>
          <p><b>They’re Saying:</b></p>
          <p>
            “Easy to take, easy to trust—and I actually feel the difference.”</p>
          <p>
            “Finally, supplements that don’t overcomplicate things.”</p>
        </div>
      </div>
    </section>

    <section aria-labelledby="glutathione-explanation" class="mt-4">
      <div class="relative overflow-hidden pb-[var(--hero-wave-height)] max-w-4xl lg:pb-0 lg:max-w-7xl lg:px-8 mx-auto">
        <div aria-hidden="true" class="absolute hidden h-full w-1/2 lg:block"></div>
        <div class="relative bg-transparent">
          <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:grid lg:grid-cols-2 lg:px-8">
            <div class="mx-auto max-w-2xl py-8 lg:max-w-none ">
              <div class="lg:pr-16">
                <h1 class="text-4xl font-bold tracking-tight text-meivita-green-dark sm:text-5xl lg:text-6xl">
                  What is <span class="text-meivita-green">Glutathione</span>?
                </h1>
                <p class="mt-4 text-xl text-gray-600">
                  Glutathione is a powerful antioxidant found naturally in
                  nearly every cell in the body. Composed of three amino
                  acids—glutamine, cysteine, and glycine—it plays a critical
                  role in protecting cells from oxidative damage, detoxifying
                  harmful substances, supporting immune function, and aiding in
                  cellular repair.
                </p>
                <div class="mt-6 text-center lg:text-left">
                  <a href="/products/liposomal-glutathione"
                    class="inline-block rounded-md border transition duration-200 border-transparent bg-meivita-green px-8 py-3 font-medium text-white hover:bg-[#5e8621]">Shop
                    Now</a>
                </div>
              </div>
            </div>
            <div class="w-full">
              <img src="/img/glutathione-img.png" alt="Gluathione bottle"
                class="h-[300px] w-full object-contain lg:h-full lg:object-cover" />
            </div>
          </div>
        </div>
      </div>
    </section>


    <section aria-labelledby="benefits-heading" class="mx-auto max-w-4xl px-4 pt-24 sm:px-6 lg:max-w-7xl lg:px-8 mb-12">
      <EightBenefits />
    </section>

    <div class="py-32 mx-auto max-w-4xl px-4 pt-24 sm:px-6 lg:max-w-7xl lg:px-8 mb-12">
      <div class="mx-auto max-w-7xl lg:max-w-screen-2xl lg:mx-12 px-6 lg:px-8">
        <div class="mx-auto max-w-2xl text-center">
          <h2 class="text-base/7 font-semibold text-meivita-green">
            Customer Feedback
          </h2>
          <p class="mt-2 text-balance text-4xl font-semibold tracking-tight text-meivita-green-dark sm:text-5xl">
            Here's what our customers are saying
          </p>
        </div>
        <div>
          <TestimonialCarousel :testimonials="testimonials" />
        </div>
      </div>
    </div>

    <section class="pb-32 px-6 cursor-grab">
      <h2 class="text-4xl md:text-6xl mb-10 text-meivita-green-dark px-3 py-1 uppercase">
        Meivita: The Home of Women's Wellbeing.
      </h2>
      <Feedback />
    </section>

    <div class="relative bg-meivita-green-light mt-[var(--hero-wave-height)]">
      <HeroWave top fill="#D7E8C3" />
      <div class="mx-auto w-[85%] px-6 lg:px-8 py-16 pb-32 bg-meivita-green-light">
        <div class="grid grid-cols-3 gap-4">
          <div class="col-span-1 lg:p-12">
            <NuxtImg src="/img/stamp-BRCGS.jpeg" alt="BRCGS stamp"
              class="w-full object-cover aspect-square mix-blend-darken" />
          </div>
          <div class="col-span-1 lg:p-12">
            <NuxtImg src="/img/stamp-GMP.jpeg" alt="GMP stamp"
              class="w-full object-cover aspect-square mix-blend-darken" />
          </div>
          <div class="col-span-1 lg:p-12">
            <NuxtImg src="/img/stamp-HACCP.jpeg" alt="HACCP stamp"
              class="w-full object-cover aspect-square mix-blend-darken" />
          </div>

          <div class="col-span-3 flex justify-center">
            <p class="text-meivita-green-dark text-lg lg:text-xl font-semibold mx-auto max-w-2xl text-center">
              Our premium product is crafted with the highest
              <span class="text-meivita-green">
                quality standards, certified by GMP, HACCP and
                BRCGS,
              </span> ensuring exceptional safety, consistency,
              and reliability in every batch.
            </p>
          </div>

        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { breakpointsTailwind } from '@vueuse/core';

const { $gsap, $ScrollTrigger } = useNuxtApp()

const shopify = useShopify()

const collectionResponse = await shopify.collection.get({
  handle: "frontpage",
  first: 12
})

// Products are inside collection
const products = collectionResponse?.products?.edges?.map((p: any) => p.node) || []
const breakpoints = useBreakpoints(breakpointsTailwind)
const smAndLarger = breakpoints.greaterOrEqual('sm')

onMounted(() => {
  $gsap.to('[data-speed]', {
    y: (i, el) => (1 - Number.parseFloat(el.getAttribute('data-speed'))) * $ScrollTrigger.maxScroll(window),
    ease: 'none',
    scrollTrigger: {
      start: 0,
      end: 'max',
      invalidateOnRefresh: true,
      scrub: 0,
    },
  })
})

const offers = [
  {
    name: 'Free shipping',
    description: 'On orders over £30'
  },
  {
    name: '30-day returns',
    description: 'Money back guarantee'
  },
  {
    name: '24/7 support',
    description: 'Customer service'
  }
];


const featuredProduct = {
  id: '1',
  name: 'Liposomal Glutathione',
  description: 'Superior absorption meets one of nature\'s most powerful antioxidants',
  image: '/img/glutathione-img.png',
  price: 29.99,
  availableForSale: true,
  createdAt: '2024-01-01T00:00:00Z',
  descriptionHtml: '<p>Superior absorption meets one of nature\'s most powerful antioxidants</p>',
  handle: 'liposomal-glutathione',
  productType: 'Supplement',
  publishedAt: '2024-01-01T00:00:00Z',
  tags: ['antioxidant', 'liposomal', 'glutathione'],
  title: 'Liposomal Glutathione',
  updatedAt: '2024-01-01T00:00:00Z',
  vendor: 'Meivita',
  options: [],
  variants: [],
  images: [
    {
      id: 'img1',
      src: '/img/glutathione-img.png',
      altText: 'Liposomal Glutathione'
    }
  ],
  priceRange: {
    minVariantPrice: { amount: 29.99, currencyCode: 'GBP' },
    maxVariantPrice: { amount: 29.99, currencyCode: 'GBP' }
  },
  featuredImage: {
    id: 'img1',
    src: '/img/glutathione-img.png',
    altText: 'Liposomal Glutathione'
  },
  seo: {
    title: 'Liposomal Glutathione',
    description: 'Superior absorption meets one of nature\'s most powerful antioxidants'
  },
  metafields: [],
  collections: [],
  // Add missing ProductFragment fields
  isGiftCard: false,
  requiresSellingPlan: false,
  compareAtPriceRange: {
    minVariantPrice: { amount: 29.99, currencyCode: 'GBP' },
    maxVariantPrice: { amount: 29.99, currencyCode: 'GBP' }
  },
  media: [],
  sellingPlanGroups: [],
};

const testimonials = [
  {
    body: "Glutathione is an antioxidant produced in cells. It’s comprised largely of three amino acids: glutamine, glycine, and cysteine. That means it helps combat free radicals. These are molecules that can damage your body's cells. Glutathione plays a role in many chemical reactions in your body. The benefits of glutathione are usually seen after at least three weeks.",
    author: {
      name: 'Christina, 32, Surrey',
      handle: 'lesliealexander',
      imageUrl:
        'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'
    }
  },
  {
    body: "I haven't seen the effect yet since it's my first time gonna take it with my glutha supplement. I hope it will work as just my skin whitening. But packaging and delivery was fast. Reading reviews are helpful too to get ideas and knowledge about the product. I'm hoping for effective result and benefit of this product since it's affordable and most requested one",
    author: {
      name: 'Amanda, 28, London',
      handle: 'amanadasmith',
      imageUrl:
        'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?ixlib=rb-1.2.1&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'
    }
  },
  {
    body: 'As a pharmacist, It\'s safe to take it with omega 3. Vitamin C can act as anti-oxidant and so it have a synergistic effect with Glutathione (work together greatly). Taking collagen with vitamin C is a very wise step and it’s recommended in order to get the optimal effect of collagen.',
    author: {
      name: 'Jayne, 35, London',
      handle: 'anon',
      imageUrl:
        'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?ixlib=rb-1.2.1&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'
    }
  },
  {
    body: 'I am taking glutathione is to help lighten my skintone.. which effective im 1 to 2 tone lighter.. i have finished 2 bottle of 60capsules and im about to finish the 3rd.. im taking 2 capsule with 1,000mg vit C (it enhance the effect of glutathione) everyday on empty stomach.. glutathione helps to detoxify our body.. making our liver healthy.. which results to glowy and lighten skin.. i like it and definitely recommend it.',
    author: {
      name: 'Sasha, 30, Berkshire',
      handle: 'anon',
      imageUrl:
        'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?ixlib=rb-1.2.1&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'
    }
  }
];
</script>