<script setup lang="ts">
import { Sparkles } from "lucide-vue-next";
import Separator from "./ui/separator/Separator.vue";
</script>

<template>
  <footer id="footer" class="container py-3 pb-4 sm:py-4 sm:pb-6">
    <div class="p-10 bg-muted/50 dark:bg-card border rounded-2xl">
      <div
        class="grid grid-cols-2 md:grid-cols-4 xl:grid-cols-6 gap-x-12 gap-y-8"
      >
        <div class="col-span-full xl:col-span-2">
          <a href="#home" class="flex font-bold items-center">
            <Sparkles
              class="bg-gradient-to-tr from-primary via-primary/70 to-secondary rounded-lg w-9 h-9 mr-2 border text-white"
            />

            <h3 class="text-2xl" style="font-family: 'Playfair Display', serif">
              Alforriase
            </h3>
          </a>
          <p class="text-sm text-muted-foreground mt-2">
            Astrologia aplicada para mulheres que querem direção e liberdade.
          </p>
        </div>

        <!-- <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Navegação</h3>
          <div>
            <a
              href="#home"
              class="opacity-60 hover:opacity-100"
            >
              Home
            </a>
          </div>

          <div>
            <a
              href="#alforriase"
              class="opacity-60 hover:opacity-100"
            >
              Sobre
            </a>
          </div>

          <div>
            <a
              href="#experiencias"
              class="opacity-60 hover:opacity-100"
            >
              Experiências
            </a>
          </div>
        </div> -->

        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Experiências</h3>
          <div>
            <a
              href="https://payfast.greenn.com.br/84569"
              target="_blank"
              rel="noopener noreferrer"
              class="opacity-60 hover:opacity-100"
            >
              Jornada Solar
            </a>
          </div>

          <div>
            <a
              href="https://payfast.greenn.com.br/84552"
              target="_blank"
              rel="noopener noreferrer"
              class="opacity-60 hover:opacity-100"
            >
              Leitura de Mapa Astral
            </a>
          </div>

          <div>
            <a
              href="https://payfast.greenn.com.br/84572/offer/xAcMsw"
              target="_blank"
              rel="noopener noreferrer"
              class="opacity-60 hover:opacity-100"
            >
              Astro Express
            </a>
          </div>

          <div>
            <a
              href="https://payfast.greenn.com.br/116808/offer/Cmw5Od"
              target="_blank"
              rel="noopener noreferrer"
              class="opacity-60 hover:opacity-100"
            >
              Jornada Solar Pocket
            </a>
          </div>
        </div>

        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Contato</h3>
          <div>
            <a href="#contato" class="opacity-60 hover:opacity-100">
              Formulário
            </a>
          </div>

          <div>
            <a
              href="https://api.whatsapp.com/send?phone=5511951366861&text=Ol%C3%A1,%20vim%20pelo%20site."
              target="_blank"
              rel="noopener noreferrer"
              class="opacity-60 hover:opacity-100"
            >
              WhatsApp
            </a>
          </div>

          <div>
            <a
              href="mailto:alforriase@outlook.com"
              class="opacity-60 hover:opacity-100"
            >
              Email
            </a>
          </div>
        </div>

        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Redes Sociais</h3>
          <div>
            <a
              href="https://instagram.com/camisdaalforriase"
              target="_blank"
              rel="noopener noreferrer"
              class="opacity-60 hover:opacity-100"
            >
              Instagram
            </a>
          </div>

          <!-- <div>
            <a
              href="https://api.whatsapp.com/send?phone=5511951366861&text=Ol%C3%A1,%20vim%20pelo%20site."
              target="_blank"
              rel="noopener noreferrer"
              class="opacity-60 hover:opacity-100"
            >
              WhatsApp
            </a>
          </div> -->
        </div>
      </div>

      <Separator class="my-6" />
      <section class="">
        <div
          class="flex flex-col md:flex-row justify-between items-center gap-4"
        >
          <h3 class="text-sm">&copy; 2026 Alforriase.</h3>
          <p class="text-sm text-muted-foreground">
            Desenvolvido por Bravva Glow - Agência de marketing digital e tech
          </p>
        </div>
      </section>
    </div>
  </footer>
</template>
