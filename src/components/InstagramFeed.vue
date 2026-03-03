<script setup lang="ts">
import { onMounted } from "vue";

onMounted(() => {
  // Carregar script do Tagembed Instagram Feed
  if (!document.querySelector('script[src*="tagembed.com"]')) {
    const script = document.createElement("script");
    script.src = "https://widget.tagembed.com/embed.min.js";
    script.type = "text/javascript";
    script.async = true;
    document.body.appendChild(script);
  }
});
</script>

<template>
  <section class="container py-24 sm:py-32" style="
      background: linear-gradient(
        180deg,
        #862d3b 0%,
        /* Topo: Seu Vermelho */ #a56a65 35%,
        /* Meio: Marrom rosado */ #b99086 70%,
        /* Meio: Bege rosado */ #c4b5a8 100% /* Base: Bege Escuro */
      );
    ">
    <div class="text-center mb-8">
      <h2 class="text-lg text-center mb-2 tracking-wider"
        style="font-family: 'Playfair Display', serif; color: #f5f0eb">
        Instagram
      </h2>
      <h2 class="text-3xl md:text-4xl text-center font-bold mb-4"
        style="font-family: 'Playfair Display', serif; color: #f5f0eb">
        Siga @camila.suaastrologa
      </h2>
    </div>

    <div class="flex justify-center">
      <div class="w-full max-w-5xl">
        <!-- Tagembed Instagram Feed -->
        <div class="tagembed-widget rounded-lg shadow-lg overflow-hidden" style="
            width: 100%;
            min-height: 500px;
            background: rgba(255, 255, 255, 0.95);
          " data-widget-id="312895" data-website="1"></div>
      </div>
    </div>

    <div class="text-center mt-8">
      <a href="https://www.instagram.com/camila.suaastrologa/" target="_blank" rel="noopener noreferrer"
        class="inline-block px-6 py-3 rounded-lg font-semibold transition-all hover:scale-105" style="
          background: linear-gradient(
            135deg,
            #722a24 0%,
            #8b3d35 40%,
            #a85547 80%,
            #c97d6f 100%
          );
          color: #ffffff;
          box-shadow: 0 4px 15px rgba(114, 42, 36, 0.3);
        ">
        Ver mais no Instagram →
      </a>
    </div>
  </section>
</template>

<style scoped>
/* Estilos para o widget do Instagram Tagembed */
.tagembed-widget {
  min-height: 500px;
}
</style>
