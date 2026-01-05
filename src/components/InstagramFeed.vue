<script setup lang="ts">
import { onMounted } from "vue";

onMounted(() => {
  // Carregar script do Elfsight Instagram Feed
  // Para configurar: https://elfsight.com/pt/instagram-feed-instashow/
  // 1. Acesse https://elfsight.com/pt/instagram-feed-instashow/
  // 2. Crie uma conta gratuita
  // 3. Conecte sua conta do Instagram (@camisdaalforriase)
  // 4. Personalize o widget (cores, layout, etc)
  // 5. Copie o código do widget e substitua o ID abaixo

  if (!document.querySelector('script[src*="elfsight"]')) {
    const script = document.createElement("script");
    script.src = "https://static.elfsight.com/platform/platform.js";
    script.async = true;
    script.defer = true;
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
        <!-- Widget do Elfsight Instagram Feed -->
        <!-- 
          INSTRUÇÕES PARA CONFIGURAR:
          
          1. Acesse: https://elfsight.com/pt/instagram-feed-instashow/
          2. Clique em "Criar Widget Gratuito"
          3. Conecte sua conta do Instagram (@camisdaalforriase)
          4. Personalize o widget (cores, número de posts, layout)
          5. Copie o código do widget gerado
          6. Substitua a div abaixo pelo código do Elfsight
          
          O código do Elfsight geralmente tem este formato:
          <div class="elfsight-app-XXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX"></div>
        -->

        <!-- Substitua este div pelo código do seu widget Elfsight -->
        <!-- <div class="elfsight-app-placeholder w-full rounded-lg shadow-lg overflow-hidden" style="background: rgba(255, 255, 255, 0.95); min-height: 500px; padding: 2rem; display: flex; align-items: center; justify-content: center;">
          <div class="text-center">
            <p class="text-lg mb-4" style="color: #722a24; font-family: 'Playfair Display', serif;">
              Configure o feed do Instagram
            </p>
            <p class="text-sm mb-6 text-muted-foreground">
              Siga as instruções nos comentários do código para configurar o widget do Elfsight
            </p>
            <a 
              href="https://elfsight.com/pt/instagram-feed-instashow/" 
              target="_blank" 
              rel="noopener noreferrer"
              class="inline-block px-6 py-3 rounded-lg font-semibold transition-all hover:scale-105"
              style="background: linear-gradient(135deg, #722a24 0%, #8b3d35 100%); color: #d1c5ba;"
            >
              Configurar Widget do Instagram →
            </a>
          </div>
        </div> -->
        <!-- Elfsight Instagram Feed | Camíla | Astrologia pra sua carreira -->
        <div
          class="elfsight-app-72a9f93d-5292-4c8d-ba69-8880fcd152cd"
          data-elfsight-app-lazy
        ></div>

        <!-- 
          ALTERNATIVA: Se preferir usar outro serviço, você pode usar:
          
          - SnapWidget: https://snapwidget.com/
          - Juicer.io: https://www.juicer.io/
          - EmbedSocial: https://embedsocial.com/
          
          Todos funcionam de forma similar: criar conta, conectar Instagram, copiar código.
        -->
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
/* Estilos para o widget do Instagram */
.elfsight-app-placeholder {
  min-height: 500px;
}
</style>
