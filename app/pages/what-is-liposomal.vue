<script setup lang="ts">
// Route data
const route = useRoute();
const pageName = computed(() => route.name as string);

// Stores
const shopStore = useShopStore();

// Shopify
const shopify = useShopify();

// Fetch data
const pageVars = computed(() => ({
  handle: pageName.value,
  country: shopStore.buyerCountryCode,
  language: shopStore.buyerLanguageCode
}));

const { data: pageData } = await useAsyncData(
  `page-${pageName.value}`,
  () => shopify.page.get(pageVars.value),
  { watch: [pageVars] }
);

// Computed data
const page = computed(() => pageData.value);

// SEO
useHead({
  title: 'What is Liposomal?'
});

const timeline = [
  {
    name: 'From Women\'s Wellness to Inclusive Health',
    description:
      'We started with a focus on women\'s health, inspired by the unique challenges women face daily—from hormonal shifts and immunity challenges to stress and skin health. Our goal was to create products that truly catered to these needs, with natural, effective ingredients that you can trust.',
    date: 'Founded in 2019'
  },
  {
    name: 'Science-Driven, Quality-Assured',
    description:
      'At ME I VITA, quality is not just a promise—it\'s a priority. Every product is developed with the latest research in immune system health, cellular regeneration, and nutritional science. We collaborate with leading experts to create supplements that are clean, potent, and effective. Our flagship product, Liposomal Glutathione, is a testament to this dedication, offering superior absorption and cutting-edge health benefits.',
    date: 'Rigorous quality standards'
  },
  {
    name: 'Sustainability at the Heart of What We Do',
    description:
      'Being based in Cambridge, a town known for its deep connection to nature and innovation, sustainability is a part of our DNA. From responsibly sourcing our ingredients to using eco-friendly packaging, every decision we make is guided by a commitment to protect the planet while promoting health.',
    date: 'Sustainability in focus'
  }
];


</script>

<template>
  <div>
    <div class="relative bg-[#D7E8C3]">

      <!-- Hero Header -->
      <!-- <div aria-hidden="true" class="absolute inset-0 bg-meivita-green/30" /> -->
      <div class="relative mx-auto flex max-w-4xl flex-col items-center px-6 py-20 text-center sm:py-64 lg:px-0">
        <div class="mx-auto max-w-2xl text-center">
          <span class="text-base/7 font-semibold text-meivita-green-dark ">
            You might be wondering
          </span>
        </div>
        <h1 class="text-6xl font-bold tracking-tight text-meivita-green-dark lg:text-8xl relative mb-6 md:mb-12">
          <span class="relative z-10">What <span class="text-meivita-green">liposomal</span> <span
              class="italic">is</span>?</span>
          <!-- <span class="absolute left-0 right-0 bottom-2 h-3 w-full"
            style="background-image: url('data:image/svg+xml;charset=utf8,<svg width=\'48\' height=\'12\' viewBox=\'0 0 48 12\' fill=\'none\' xmlns=\'http://www.w3.org/2000/svg\'><path d=\'M0 3C8 3 8 9 16 9C24 9 24 3 32 3C40 3 40 9 48 3\' stroke=\'%23365314\' stroke-width=\'3\' style=\'stroke-linecap:round;stroke-linejoin:round\'/></svg>'); background-repeat: repeat-x;">
          </span> -->
        </h1>
        <p class="mt-4 text-xl text-meivita-green-dark text-center tracking-wide leading-relaxed mb-24 md:mb-12">
          Liposomal supplements use <span class="inline-block bubble-text2 relative">
            <span class="bubble-text bubble-text2 relative inline-block">tiny</span> <span
              class="bubble-text bubble-delay relative inline-block">bubbles</span>
          </span> called
          "liposomes" to protect nutrients from stomach acids, enhancing
          their journey through the digestive system. This method improves absorption, ensuring maximum benefits from
          each dose.
        </p>

      </div>
      <HeroWave />
    </div>

    <!-- First Section -->
    <div class=" ">
      <div class="mx-auto w-[85%] px-6 lg:px-8">
        <div class="mx-auto max-w-2xl lg:mx-0 lg:max-w-none">
          <div
            class="mt-10 grid max-w-xl grid-cols-1 gap-8 text-base/7 text-meivita-green-dark lg:max-w-none lg:grid-cols-2 lg:p-12">
            <div class="flex flex-col">
              <h2
                class="text-center lg:text-pretty text-4xl lg:text-6xl mb-6 lg:mb-0 font-semibold tracking-tight text-meivita-green-dark">
                <span class="uppercase text-meivita-green italic">Effective</span> <span
                  class="underline underline-offset-4 decoration-wavy">delivery</span>
              </h2>
              <div class="flex flex-col justify-center items-center flex-1 lg:flex-grow gap-4">
                <p class="text-lg lg:text-xl text-pretty leading-loose">
                  Not all supplements are created equal.
                </p>
                <p class="text-lg lg:text-xl text-pretty leading-loose">
                  Traditional supplements often struggle to make it past the harsh digestive process, meaning
                  your body absorbs only a small fraction of the nutrients. That's where <span
                    class="font-semibold">liposomal technology</span>
                  makes a difference.
                </p>

                <p class="text-lg lg:text-xl text-pretty leading-loose">
                  Through extensive research and clinical trials, we've found that liposomal encapsulation
                  <span class="font-semibold">improves nutrient absorption by up to 4x</span> compared to regular
                  supplements.
                </p>
                <p class="text-lg lg:text-xl text-pretty leading-loose">
                  By protecting the nutrients inside tiny liposomes, they
                  reach your bloodstream more efficiently — so your body gets more of what it needs to thrive.
                </p>
              </div>
            </div>
            <div class="flex justify-center items-center">
              <NuxtImg src="/img/liposome-diagram.jpeg" alt="Liposome diagram"
                class="w-full object-contain aspect-square" />
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Second Section -->
    <div class="">
      <div class="mx-auto sm:w-[85%] px-6 lg:px-8">
        <div class="mx-auto max-w-2xl lg:mx-0 lg:max-w-none">
          <div
            class="mt-10 grid max-w-xl grid-cols-1 gap-8 text-base/7 text-meivita-green-dark lg:max-w-none lg:grid-cols-2">
            <div>
              <NuxtImg src="/img/liposome-absorption-diagram.jpeg" alt="Liposome absorption diagram"
                class="w-full object-contain aspect-square" />
            </div>
            <div class="flex flex-col">
              <h2
                class="text-center lg:text-pretty text-4xl lg:text-6xl mb-6 lg:mb-0 font-semibold tracking-tight text-meivita-green-dark">
                <span class="uppercase text-meivita-green italic">Higher</span> <span
                  class="underline underline-offset-4 decoration-wavy">absorption</span>
                <span
                  class="text-meivita-green block text-base text-right mt-4 sm:text-center md:text-right lg:text-lg">than
                  regular supplements</span>
              </h2>
              <div class="flex flex-col justify-center items-center flex-1 lg:flex-grow gap-4">
                <p class="text-lg lg:text-xl text-pretty leading-loose">
                  Liposomal supplements use <span class="font-semibold">tiny protective
                    bubbles</span> called "liposomes" to deliver nutrients
                  more effectively. These liposomes shield the nutrients from stomach acids, helping them stay
                  intact as they travel through your digestive system.
                </p>
                <p class="text-lg lg:text-xl text-pretty leading-loose">
                  This advanced delivery method allows for <span class="font-semibold">better
                    absorption</span>, ensuring your body gets the
                  maximum benefits from each dose.
                </p>
              </div>
            </div>

          </div>
        </div>
      </div>
    </div>

    <!-- Third Section -->
    <div class="py-16">
      <div class="mx-auto w-[85%] px-6 lg:px-8">
        <div class="mx-auto max-w-2xl lg:mx-0 lg:max-w-none">
          <div
            class="mt-10 grid max-w-xl grid-cols-1 gap-8 text-base/7 text-meivita-green-dark lg:max-w-none lg:grid-cols-2">
            <div class="flex flex-col">
              <h2 class="mt-2 mb-8 text-pretty text-base font-semibold tracking-tight text-meivita-green-dark w-3/4">
                Why regular supplements <span
                  class="text-meivita-green block text-right italic uppercase sm:text-6xl text-4xl">don't work?</span>
              </h2>
              <div class="flex flex-col justify-center items-center flex-1 lg:flex-grow gap-4">
                <p class="text-lg lg:text-xl text-pretty leading-loose">
                  Did you know that a large portion of traditional supplements never actually make it to your cells
                  where they're needed?
                </p>
                <p class="text-lg lg:text-xl text-pretty leading-loose">
                  This means you might not be getting the full benefits, even if you're
                  taking them regularly.
                </p>
                <p class="text-lg lg:text-xl text-pretty leading-loose">
                  The problem lies in <span class="font-semibold">two main factors:</span>
                </p>

                <ul class="list-disc list-inside text-lg lg:text-xl text-pretty leading-loose space-y-4">
                  <li>First, the <span class="font-semibold">harsh environment of your stomach</span> breaks down many
                    nutrients before they can
                    be absorbed.</li>

                  <li>Second, the absorption process in the <span class="font-semibold">small intestine is often
                      inefficient</span>, meaning only a
                    small amount of nutrients actually make it into your bloodstream.</li>
                </ul>
              </div>

            </div>
            <div>
              <NuxtImg src="/img/liposomal-graph.jpeg"
                alt="Chart showing absorption of regular and liposomal supplements"
                class="w-full object-cover aspect-square" />
            </div>
          </div>
        </div>
      </div>
    </div>


    <!-- Fourth Section -->
    <div class="py-16">
      <div class="mx-auto w-[85%] px-6 lg:px-8">
        <div class="mx-auto max-w-2xl lg:mx-0 lg:max-w-none">
          <div
            class="mt-10 grid max-w-xl grid-cols-1 gap-8 text-base/7 text-meivita-green-dark lg:max-w-none lg:grid-cols-2">
            <div class="flex flex-col">
              <h2
                class="mt-2 mb-8 text-4xl font-semibold tracking-tight text-meivita-green-dark sm:text-6xl max-w-[70%] mx-auto">
                <span class=" lowercase italic text-2xl ">Reduce</span> <span
                  class=" text-left uppercase italic text-meivita-green ">waste</span>
              </h2>
              <div class="flex flex-col justify-center items-center flex-1 lg:flex-grow gap-4">
                <p class="text-lg lg:text-xl text-pretty leading-loose">
                  Because of this, studies suggest that up to <span class="font-semibold">80% of conventional
                    supplements are lost</span> before
                  they ever reach your cells.
                </p>
                <p class="text-lg lg:text-xl text-pretty leading-loose">
                  That's not just wasted nutrients - it's wasted money and missed health benefits.
                </p>
                <p class="text-lg lg:text-xl text-pretty leading-loose">
                  This is why
                  advanced delivery methods, like liposomal technology, are transforming the way we absorb
                  essential nutrients, ensuring more of what you take actually gets used by your body.
                </p>
              </div>
            </div>
            <div>
              <NuxtImg src="/img/blood-cells-3d.jpeg" alt="3D blood cells" class="w-full object-cover aspect-square" />
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Fourth Section -->
    <div class="py-16">
      <div class="mx-auto w-[85%] px-6 lg:px-8">
        <div class="mx-auto max-w-2xl lg:mx-0 lg:max-w-none">
          <div class="flex flex-col gap-y-24">
            <h2 class="mt-2 mb-8 text-center text-2xl  text-meivita-green-dark tracking-tight font-semibold">
              How do we <span class="underline text-4xl sm:text-6xl font-semibold uppercase italic">stop</span> all this
              <span
                class="text-meivita-green underline text-4xl sm:text-6xl font-semibold uppercase italic">waste?</span>
            </h2>
            <div
              class="grid grid-cols-1 gap-8 lg:gap-12 text-base/7 text-meivita-green-dark lg:max-w-none lg:grid-cols-3">
              <div class="flex flex-col gap-4">
                <NuxtImg src="/img/supplement-tablets-with-water.jpeg" alt="Supplement tablets with water"
                  class="w-full object-cover aspect-square" />
                <p class="text-lg lg:text-xl leading-relaxed text-center">
                  The key to getting the most out of your supplements is improving absorption-and that's
                  exactly what liposomal technology does.
                </p>
              </div>
              <div class="flex flex-col gap-4">
                <NuxtImg src="/img/liposome-3d.jpeg" alt="Liposome 3D graphic"
                  class="w-full object-cover aspect-square" />
                <p class="text-lg lg:text-xl leading-relaxed text-center">
                  Instead of letting nutrients get destroyed in the
                  digestive process, liposomal supplements use tiny protective bubbles (liposomes) to shield
                  them from stomach acid and enhance their delivery into the bloodstream.
                </p>
              </div>
              <div class="flex flex-col gap-4">
                <NuxtImg src="/img/dna-diagram.jpeg" alt="DNA diagram" class="w-full object-contain aspect-square" />
                <p class="text-lg lg:text-xl leading-relaxed text-center">
                  This advanced method ensures that more nutrients reach your cells, meaning your body
                  absorbs and uses them far more effectively. With liposomal supplements, you get better results,
                  waste less, and maximize the benefits of every dose.
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Fifth Section -->
    <div class="relative mt-[var(--hero-wave-height)] bg-[#D7E8C3]">
      <HeroWave top fill="#D7E8C3" />
      <div class="mx-auto w-[85%] px-6 lg:px-8 py-16 pb-32">
        <div class="mx-auto max-w-2xl lg:mx-0 lg:max-w-none">
          <div
            class="mt-10 grid max-w-xl grid-cols-1 gap-8 text-base/7 text-meivita-green-dark lg:max-w-none lg:grid-cols-2">
            <div>
              <NuxtImg src="/img/supplements-with-hands.jpeg" alt="Liposomal supplement"
                class="w-full object-cover aspect-square" />
            </div>
            <div>
              <h2
                class="mt-2 mb-8 text-pretty text-4xl font-semibold tracking-tight text-meivita-green-dark sm:text-6xl">
                The <span class="text-meivita-green">results?</span>
              </h2>
              <div>
                <h3 class="text-2xl font-semibold tracking-tight text-meivita-green-dark ">
                  10x greater nutrient protection
                </h3>
                <div class="flex flex-col gap-4">
                  <p class="text-lg lg:text-xl leading-relaxed">
                    The digestive system is tough on nutrients, breaking them down before they can be fully
                    absorbed. However, liposomal encapsulation acts as a shield, protecting nutrients up to 10
                    times more effectively than conventional supplements.
                  </p>
                  <p class="text-lg lg:text-xl leading-relaxed">
                    This ensures they remain intact as they pass through the stomach and into the bloodstream, so
                    your body can utilize them where they're needed most.
                  </p>
                </div>
                <h3 class="mt-2 lg:mt-4 text-2xl font-semibold tracking-tight text-meivita-green-dark">
                  4x higher absorption into the bloodstream
                </h3>
                <div class="flex flex-col gap-4">
                  <p class="text-lg lg:text-xl leading-relaxed"> Even when nutrients survive digestion, they
                    still need to be absorbed efficiently. Clinical trials
                    have shown that liposomal supplements improve absorption by up to four times compared to
                    regular supplements.
                  </p>
                  <p class="text-lg lg:text-xl leading-relaxed">
                    By wrapping nutrients in tiny, fat-based liposomes, this advanced delivery system allows them
                    to pass through cell membranes more easily, ensuring your body gets the full benefits of each
                    dose.
                  </p>
                  <p class="text-lg lg:text-xl leading-relaxed">
                    With liposomal technology, you're not just taking supplements-you're making sure your
                    body absorbs and uses them effectively, leading to better health outcomes and less wasted
                    nutrition.
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Sixth Section w Hero -->


    <!-- Seventh Section -->
    <!-- <div class="lg:py-16 bg-[#D7E8C3] relative">
      <div class="mx-auto w-[85%] px-6 lg:px-8">
        <div class="mx-auto max-w-2xl lg:mx-0 lg:max-w-none">
          <div
            class="lg:mt-10 grid max-w-xl grid-cols-1 gap-8 gap-y-16 lg:gap-y-36 text-base/7 text-meivita-green-dark lg:max-w-none lg:grid-cols-2">
            <div>
              <img src="https://placehold.co/600x600/374151/FFF?text=another+image" alt="Liposomal supplement"
                class="w-full h-full object-cover">
            </div>

            <div class="flex justify-center items-center">
              <h3 class="text-3xl font-bold tracking-tight text-meivita-green-dark lg:text-5xl text-center">
                Liposomal <span class="text-meivita-green">Shields</span>
              </h3>
            </div>

            <div class="flex justify-center items-center">
              <h3 class="text-3xl font-bold tracking-tight text-meivita-green-dark lg:text-5xl text-center">
                10x greater <span class="text-meivita-green">nutrient protection</span>
              </h3>
            </div>

            <div>
              <img src="https://placehold.co/600x600/374151/FFF?text=another+image" alt="Liposomal supplement"
                class="w-full h-full object-cover">
            </div>

            <div class="lg:col-span-2 flex justify-center items-center h-full">
              <h3 class="text-3xl font-bold tracking-tight text-meivita-green-dark lg:text-5xl text-center">
                How liposomes <span class="text-meivita-green">increase absorption</span>
              </h3>
            </div>

            <div class="flex flex-col gap-y-4">
              <h3 class="text-3xl/6 font-bold tracking-tight text-meivita-green-dark lg:text-5xl">
                Why regular supplements have <span class="text-meivita-green">low absorption</span>
              </h3>
              <p class="text-lg lg:text-xl tracking-wide">
                A lot of supplements are absorbed into the bloodstream through "active transport" - your body expends
                energy to absorb nutrients into the bloodstream through "protein channels" that are embedded in the gut
                wall.
              </p>
              <p class="text-lg lg:text-xl tracking-wide">
                The body doesn't have enough of these protein channels in the gut wall to absorb the high concentrations
                of nutrients found in supplements, which can lead to nutrients in regular supplements passing straight
                through the body without making it into the bloodstream.
              </p>
            </div>
            <div>
              <img src="https://placehold.co/600x600/374151/FFF?text=another+image" alt="Liposomal supplement"
                class="w-full h-full object-cover">
            </div>

            <div>
              <img src="https://placehold.co/600x600/374151/FFF?text=another+image" alt="Liposomal supplement"
                class="w-full h-full object-cover">
            </div>
            <div class="flex flex-col gap-y-4 justify-center items-center">
              <h3 class="text-3xl/6 font-bold tracking-tight text-meivita-green-dark lg:text-5xl">
                Liposomes get absorbed <span class="text-meivita-green">differently</span>
              </h3>
              <p class="text-lg lg:text-xl tracking-wide">
                By encapsulating nutrients in Liposomes, nutrients in Zooki products are absorbed directly into the
                bloodstream through a different kind of cell in the gut wall known as an "M-cell"; by-passing the need
                for the protein channels that get saturated and act as bottlenecks for nutrient absorption.
              </p>
            </div>

            <div class="lg:col-span-2 py-16 lg:py-32">
              <img src="https://placehold.co/600x600/374151/FFF?text=another+image" alt="Liposomal supplement"
                class="w-full h-full object-cover">
            </div>
          </div>
        </div>
      </div>
    </div> -->
  </div>
</template>

<style scoped>
.bubble-text::before,
.bubble-text::after,
.bubble-text2::before,
.bubble-text2::after {
  content: "○";
  position: absolute;
  color: #16320A;
  opacity: 0;
  animation: float 3s infinite;
}

.bubble-text::before {
  left: 40%;
  animation-delay: 0.5s;
}

.bubble-text::after {
  right: 40%;
  animation-delay: 1.5s;
}

.bubble-text2::before {
  left: 20%;
}

.bubble-text2::after {
  right: 20%;
}




@keyframes float {
  0% {
    transform: translateY(0);
    opacity: 0;
  }

  20% {
    opacity: 0.8;
  }

  100% {
    transform: translateY(-20px);
    opacity: 0;
  }
}

.bubble-delay::before,
.bubble-delay::after {
  animation-duration: 4s !important;
}

.bubble-text2::before,
.bubble-text2::after {
  animation-duration: 2.2s !important;
}
</style>
