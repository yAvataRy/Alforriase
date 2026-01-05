<script setup lang="ts">
import { onMounted } from 'vue';

onMounted(() => {
  // Carregar script do Instagram Embed para posts individuais
  if (!document.querySelector('script[src*="instagram.com/embed"]')) {
    const script = document.createElement('script');
    script.src = 'https://www.instagram.com/embed.js';
    script.async = true;
    document.body.appendChild(script);
  }
});
</script>

<template>
  <section class="container py-24 sm:py-32" style="background: linear-gradient(135deg, #d1c5ba 0%, #f5f0eb 50%, #d1c5ba 100%);">
    <div class="text-center mb-8">
      <h2 class="text-lg text-center mb-2 tracking-wider" style="font-family: 'Playfair Display', serif; color: #722a24;">
        Instagram
      </h2>
      <h2 class="text-3xl md:text-4xl text-center font-bold mb-4" style="font-family: 'Playfair Display', serif; color: #722a24;">
        Siga @camisdaalforriase
      </h2>
    </div>
    
    <div class="flex justify-center">
      <div class="w-full max-w-5xl">
        <!-- Feed do Instagram usando Instagram Embed -->
        <!-- Esta solução funciona sem necessidade de configuração adicional -->
        <div class="w-full rounded-lg shadow-lg overflow-hidden" style="background: rgba(255, 255, 255, 0.95); min-height: 500px; padding: 2rem;">
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 mb-6">
            <!-- Placeholder visual para o feed do Instagram -->
            <div 
              v-for="i in 6" 
              :key="i"
              class="aspect-square rounded-lg overflow-hidden cursor-pointer hover:opacity-90 transition-opacity group"
              style="background: linear-gradient(135deg, #f5f0eb 0%, #d1c5ba 100%); border: 2px solid rgba(114, 42, 36, 0.2);"
              @click="() => window.open('https://www.instagram.com/camisdaalforriase/', '_blank')"
            >
              <div class="w-full h-full flex items-center justify-center">
                <div class="text-center p-4">
                  <svg 
                    class="w-12 h-12 mx-auto mb-2 opacity-50 group-hover:opacity-100 transition-opacity" 
                    style="color: #722a24;"
                    fill="currentColor" 
                    viewBox="0 0 24 24"
                  >
                    <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
                  </svg>
                  <p class="text-sm opacity-70" style="color: #722a24;">
                    @camisdaalforriase
                  </p>
                </div>
              </div>
            </div>
          </div>
          
          <div class="text-center">
            <p class="text-lg mb-4" style="color: #722a24; font-family: 'Playfair Display', serif;">
              Acompanhe nosso conteúdo no Instagram
            </p>
            <a 
              href="https://www.instagram.com/camisdaalforriase/" 
              target="_blank" 
              rel="noopener noreferrer"
              class="inline-block px-8 py-4 rounded-lg font-semibold transition-all hover:scale-105 shadow-md"
              style="background: linear-gradient(135deg, #722a24 0%, #8b3d35 100%); color: #d1c5ba;"
            >
              Ver perfil completo no Instagram →
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

