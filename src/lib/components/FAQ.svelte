<script lang="ts">
  import { slide } from 'svelte/transition';
  
  interface FAQItem {
    question: string;
    answer: string;
  }

  const faqs: FAQItem[] = [
    { question: "How do I launch a token on Bags?", answer: "To launch a token on Bags, you'll need to create an account, upload your token image and details, set up your fee sharing structure (if desired), and make an initial buy. We recommend a minimum 0.5 SOL initial purchase to prevent snipers. The platform guides you through each step of the process." },
    { question: "How does the fee sharing system work?", answer: "Bags allows you to distribute trading fees to up to 100 accounts. You can upload a CSV file with wallet addresses and percentage allocations. As your token is traded, fees are automatically distributed according to your specified percentages. This enables revenue sharing with team members, communities, or causes." },
    { question: "How much can creators earn?", answer: "Creator earnings vary based on token trading volume. Our platform has paid out over $21 million to creators total. Top performing tokens like NYAN have generated over $380K in creator earnings, while BTH has earned $367K. Earnings come from ongoing trading fees, creating a sustainable revenue stream." },
    { question: "What blockchain does Bags use?", answer: "Bags is built on Solana blockchain, offering fast transaction speeds and low fees. We integrate with major Solana DEXs including Jupiter, Photon, and Axiom, and use the Meteora DLMM Program for liquidity management." },
    { question: "Can I use Bags on mobile?", answer: "Yes! Bags is available on iOS, Android, and web. Our mobile-first approach makes it easy to launch and manage your tokens from anywhere. Wallet integration is handled through Privy for seamless onboarding." },
    { question: "What types of tokens can I create?", answer: "Bags supports various token types including meme coins, creator tokens, social cause tokens, and community tokens. Notable examples include celebrity tokens (MrBeast, Drake Bell), charitable tokens (F*CK CANCER), and iconic meme collaborations (Nyan Cat, Pepe by Matt Furie)." },
    { question: "Is there support available?", answer: "Yes, we offer support through our Discord community server and dedicated support portal at support.bags.fm. Our community is active and helpful, and we provide documentation at docs.bags.fm for technical integration questions." }
  ];

  let openIndex: number | null = null;

  function toggle(index: number) {
    openIndex = openIndex === index ? null : index;
  }
</script>

<section class="bg-[#f5f5f5] px-6 py-24">
  <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-12 gap-12">
    <div class="lg:col-span-4">
      <h2 class="font-serif text-4xl text-gray-900 mb-6">
        Frequently asked questions
      </h2>
      <a href="/" class="text-sm text-gray-900 border-b border-gray-300 pb-0.5 hover:border-black transition-colors">See all support</a>
    </div>
    
    <div class="lg:col-span-8">
      <div class="border-t border-gray-200">
        {#each faqs as faq, i}
          <div class="border-b border-gray-200">
            <button 
              class="w-full py-6 flex justify-between items-center text-left hover:bg-gray-50 transition-colors"
              on:click={() => toggle(i)}
            >
              <span class="text-lg text-gray-800">{faq.question}</span>
              <span class="text-2xl font-light text-gray-400 ml-4">
                {openIndex === i ? '−' : '+'}
              </span>
            </button>
            {#if openIndex === i}
              <div transition:slide class="pb-6 text-gray-500 leading-relaxed">
                {faq.answer}
              </div>
            {/if}
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>
