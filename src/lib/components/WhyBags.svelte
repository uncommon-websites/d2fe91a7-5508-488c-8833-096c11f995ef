<script>
  import SectionLabel from './SectionLabel.svelte';
</script>

<section class="bg-[#f5f5f5] px-6 py-24">
  <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-12 gap-12">
    <div class="lg:col-span-3">
      <SectionLabel label="Why Bags" />
    </div>
    
    <div class="lg:col-span-9 grid grid-cols-1 md:grid-cols-2 gap-16">
      <div>
        <h2 class="font-serif text-3xl md:text-4xl leading-tight text-gray-900 mb-6">
          Bags empowers creators to monetize their influence and build engaged communities
        </h2>
        <p class="text-gray-500 leading-relaxed">
          Launch tokens with custom fee sharing, earn ongoing royalties from trading activity, and distribute revenue to up to 100 accounts — all on Solana.
        </p>
      </div>
      
      <div class="flex gap-12 items-end pb-2">
        <div class="flex flex-col gap-1">
            <span class="text-5xl font-bold text-gray-900">$21M+</span>
            <span class="text-xs text-gray-400">paid to creators</span>
        </div>
        <div class="flex flex-col gap-1">
            <span class="text-5xl font-bold text-gray-900">100+</span>
            <span class="text-xs text-gray-400">active tokens</span>
        </div>
      </div>
    </div>
  </div>
</section>
