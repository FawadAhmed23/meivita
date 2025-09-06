<script setup lang="ts">
// Links
const footerLinks1 = [
  { label: 'About', path: '/about' }
  // { label: 'Contact', path: '/contact' }
];

const footerLinks2 = [
  // { label: 'FAQ', path: '/collections/latest' },
  { label: 'Shipping & Returns', path: '/#' },
  { label: 'Privacy Policy', path: '/#' },
];

const socialLinks = [{ label: 'Tiktok', path: '/#', icon: 'iconoir:tiktok' }, { label: 'Instagram', path: '/#', icon: 'iconoir:instagram' }, { label: 'Facebook', path: '/#', icon: 'iconoir:facebook' }];

const paymentMethods = [{ label: 'Visa', path: '/#', icon: 'logos:visa' }, { label: 'Mastercard', path: '/#', icon: 'logos:mastercard' }, { label: 'Paypal', path: '/#', icon: 'logos:paypal' }, { label: 'Apple Pay', path: '/#', icon: 'logos:apple-pay' }, { label: 'Shopify Pay', path: '/#', icon: 'logos:shopify' }];
</script>

<template>
  <footer class="w-full bg-meivita-green text-white relative mt-10">
    <HeroWave fill="#7AB02A" top />
    <nav class=" flex-col px-6 py-6 gap-20 lg:flex">
      <div class="grid grid-cols-1 justify-items-center sm:justify-items-start sm:grid-cols-4 gap-10">
        <div class="flex flex-col max-w-fit">
          <h3 class="mb-4 font-bold text-center sm:text-left">Follow Us</h3>
          <div class="flex gap-2">
            <a v-for="link in socialLinks" :key="link.label" :to="link.path"
              class="normal-case hover:text-[#344816] transition duration-200 ease-in-out">
              <Icon :name="link.icon" class="h-10 w-10 shrink-0 hover:cursor-pointer" />
            </a>
          </div>
        </div>
        <div class="flex flex-col max-w-fit">
          <h3 class="mb-4 font-bold text-center sm:text-left">Company</h3>
          <NuxtLink v-for="link in footerLinks1" :key="link.label" :to="link.path"
            class="normal-case hover:text-[#344816] transition duration-200 ease-in-out text-center sm:text-left">
            {{ link.label }}
          </NuxtLink>
        </div>
        <div class="flex flex-col max-w-fit">
          <h3 class="mb-4 font-bold text-center sm:text-left">Support</h3>
          <p class="text-center sm:text-left">
            info@meivita.co.uk
          </p>
          <!-- <NuxtLink v-for="link in footerLinks2" :key="link.label" :to="link.path"
            class="normal-case hover:text-[#344816] transition duration-200 ease-in-out text-center sm:text-left">
            {{ link.label }}
          </NuxtLink> -->
        </div>
        <div class="flex flex-col max-w-fit">
          <h3 class="mb-4 font-bold text-center sm:text-left">Payment Methods</h3>
          <div class="flex gap-2">
            <div v-for="link in paymentMethods" :key="link.label"
              class="bg-white rounded px-2 py-1 flex items-center justify-center border border-[#5e8621]">
              <Icon :name="link.icon" class="h-6 w-6 shrink-0 " />
            </div>
          </div>
        </div>
        <div class="flex flex-col max-w-fit">
          <!-- <div class="flex bg-white rounded p-2 text-center justify-center items-center text-meivita-green-dark text-2xl">
            Trustpilot goes here
          </div> -->
          <!-- TrustBox widget - Review Collector -->
          <div class="trustpilot-widget" data-locale="en-GB" data-template-id="56278e9abfbbba0bdcd568bc"
            data-businessunit-id="6786f2b3372187073c2a6fb2" data-style-height="52px" data-style-width="100%">
            <a href="https://uk.trustpilot.com/review/meivita.co.uk" target="_blank" rel="noopener">Trustpilot</a>
          </div>
          <!-- End TrustBox widget -->
        </div>
      </div>
      <div class="flex justify-between">
        <span class="text-sm">© Meivita 2025</span>
      </div>
    </nav>
  </footer>
</template>
