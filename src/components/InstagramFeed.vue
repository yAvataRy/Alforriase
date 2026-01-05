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
  <section
    class="container py-24 sm:py-32"
    style="
      background: linear-gradient(
        135deg,
        #d1c5ba 0%,
        #f5f0eb 50%,
        #d1c5ba 100%
      );
    "
  >
    <div class="text-center mb-8">
      <h2
        class="text-lg text-center mb-2 tracking-wider"
        style="font-family: 'Playfair Display', serif; color: #722a24"
      >
        Instagram
      </h2>
      <h2
        class="text-3xl md:text-4xl text-center font-bold mb-4"
        style="font-family: 'Playfair Display', serif; color: #722a24"
      >
        Siga @camisdaalforriase
      </h2>
    </div>

    <div class="flex justify-center">
      <div class="w-full max-w-5xl">
        <!-- Tagembed Instagram Feed -->
        <div
          class="tagembed-widget rounded-lg shadow-lg overflow-hidden"
          style="
            width: 100%;
            min-height: 500px;
            background: rgba(255, 255, 255, 0.95);
          "
          data-widget-id="312895"
          data-website="1"
        ></div>
      </div>
    </div>

    <div class="text-center mt-8">
      <a
        href="https://www.instagram.com/camisdaalforriase/"
        target="_blank"
        rel="noopener noreferrer"
        class="inline-block px-6 py-3 rounded-lg font-semibold transition-all hover:scale-105"
        style="
          background: linear-gradient(135deg, #722a24 0%, #8b3d35 100%);
          color: #d1c5ba;
        "
      >
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
