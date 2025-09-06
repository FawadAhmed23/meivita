<script setup lang="ts">
import { ChevronDownIcon } from '@heroicons/vue/20/solid';
import {
  Bars3Icon,
  MagnifyingGlassIcon,
  ShoppingCartIcon,
  UserIcon,
  XMarkIcon
} from '@heroicons/vue/24/outline';

// Links
const navLinksLeft = [
  { label: 'Shop', path: '/products/liposomal-glutathione' },
  { label: 'What is Liposomal?', path: '/what-is-liposomal' },
  { label: 'About Us', path: '/about' }
];

const navLinksRight = [{ label: 'Account', path: '/account' }];

// Stores
const cartStore = useCartStore();
const shopStore = useShopStore();

// Computed
const countryCode = computed(() => shopStore.buyerCountryCode);
const currencySymbol = computed(() => shopStore.buyerCurrencySymbol);
const cartTotalItems = computed(() => cartStore.lineItemsCount);

// Emits
const emit = defineEmits([
  'toggleLocaleModal',
  'toggleSearchMenu',
  'toggleCartDrawer'
]);
</script>

<template>
  <header class="relative z-10">
    <nav aria-label="Top">
      <!-- Top navigation -->
      <div class="bg-meivita-green">
        <div class="mx-auto flex h-10 items-center justify-between px-4 sm:px-6 lg:px-8">
          <!-- Currency selector -->
          <div class="hidden lg:block lg:flex-1">
            <div class="-ml-2 inline-grid grid-cols-1">
              <button
                class="col-start-1 row-start-1 w-full appearance-none rounded-md bg-meivita-green py-0.5 pl-2 pr-7 text-left text-base font-medium text-white focus:outline focus:outline-2 focus:-outline-offset-1 focus:outline-white sm:text-sm/6"
                @click="emit('toggleLocaleModal')">
                {{ countryCode }} / {{ currencySymbol }}
              </button>
              <ChevronDownIcon
                class="pointer-events-none col-start-1 row-start-1 mr-1 size-5 self-center justify-self-end fill-white"
                aria-hidden="true" />
            </div>
          </div>

          <p class="flex-1 text-center text-sm font-medium text-white lg:flex-none">
            Get free delivery on orders over £30
          </p>

          <div class="hidden lg:flex lg:flex-1 lg:items-center lg:justify-end lg:space-x-6">
            <NuxtLink to="/account"
              class="text-sm font-medium text-white hover:text-meivita-green-dark transition duration-200 ease-in-out ">
              Create an
              account
            </NuxtLink>
            <span class="h-6 w-px bg-meivita-green-dark" aria-hidden="true" />
            <NuxtLink to="/account"
              class="text-sm font-medium text-white hover:text-meivita-green-dark transition duration-200 ease-in-out ">
              Sign in
            </NuxtLink>
          </div>
        </div>
      </div>

      <!-- Secondary navigation -->
      <div class="bg-white hidden lg:block">
        <div class="border-b border-gray-200/20">
          <div class="mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex h-16 items-center justify-between">
              <div class="flex h-16 items-center flex-1">
                <!-- Logo (lg+) -->
                <div class="hidden lg:flex lg:items-center">
                  <NuxtLink to="/">
                    <span class="sr-only">Meivita</span>
                    <NuxtImg class="h-24 w-auto" src="/img/meivita-logo-green.png" alt="Meivita" />
                  </NuxtLink>
                </div>

                <!-- Left links -->
                <div class="hidden h-full lg:flex lg:ml-8">
                  <div class="flex h-full items-center justify-center space-x-8">
                    <NuxtLink v-for="link in navLinksLeft" :key="link.label"
                      class="px-2 py-0.5 text-normalize bg-transparent rounded-md transition duration-200 hover:bg-meivita-green hover:text-white"
                      :to="link.path">
                      {{ link.label }}
                    </NuxtLink>
                  </div>
                </div>
              </div>

              <div class="grid grid-flow-col justify-end items-center flex-1">
                <div class="flex flex-1 items-center justify-end">
                  <div class="flex items-center lg:ml-8">
                    <div class="flex space-x-8">
                      <!-- <div class="hidden lg:flex">
            <button
              class="-m-2 p-2 text-gray-400 hover:text-gray-500"
              @click="emit('toggleSearchMenu')"
            >
              <span class="sr-only">Search</span>
              <MagnifyingGlassIcon
                class="size-6"
                aria-hidden="true"
              />
            </button>
              </div> -->

                      <div class="flex">
                        <NuxtLink to="/account"
                          class="-m-2 p-2 text-gray-400 hover:bg-meivita-green hover:text-white rounded-md transition duration-200">
                          <span class="sr-only">Account</span>
                          <UserIcon class="size-6" aria-hidden="true" />
                        </NuxtLink>
                      </div>
                    </div>

                    <span class="mx-4 h-6 w-px bg-gray-200 lg:mx-6" aria-hidden="true" />

                    <div class="flow-root group">
                      <button to="/cart"
                        class="-m-2 p-2 text-gray-400 hover:bg-meivita-green hover:text-white rounded-md transition duration-200 flex items-center"
                        @click="emit('toggleCartDrawer')">
                        <ShoppingCartIcon class="size-6 shrink-0" aria-hidden="true" />
                        <span class="ml-2 text-sm font-medium text-meivita-green-dark group-hover:text-white">
                          ({{ cartTotalItems }})</span>
                        <span class="sr-only">items in cart, view bag</span>
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>