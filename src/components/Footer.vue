<script setup lang="ts">
import { Sparkles } from "lucide-vue-next";
import Separator from "./ui/separator/Separator.vue";
</script>

<template>
  <footer
    id="footer"
    class="container py-24 pb-16 sm:py-32 sm:pb-24"
  >
    <div class="p-10 bg-muted/50 dark:bg-card border rounded-2xl">
      <div
        class="grid grid-cols-2 md:grid-cols-4 xl:grid-cols-6 gap-x-12 gap-y-8"
      >
        <div class="col-span-full xl:col-span-2">
          <a
            href="#home"
            class="flex font-bold items-center"
          >
            <Sparkles
              class="bg-gradient-to-tr from-primary via-primary/70 to-secondary rounded-lg w-9 h-9 mr-2 border text-white"
            />

            <h3 class="text-2xl" style="font-family: 'Playfair Display', serif;">Alforriase</h3>
          </a>
          <p class="text-sm text-muted-foreground mt-2">
            Astrologia aplicada para mulheres que querem direção e liberdade.
          </p>
        </div>

        <div class="flex flex-col gap-2">
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
              Serviços
            </a>
          </div>
        </div>

        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Serviços</h3>
          <div>
            <a
              href="#experiencias"
              class="opacity-60 hover:opacity-100"
            >
              Jornada Solar
            </a>
          </div>

          <div>
            <a
              href="#experiencias"
              class="opacity-60 hover:opacity-100"
            >
              Mapa Astral
            </a>
          </div>

          <div>
            <a
              href="#experiencias"
              class="opacity-60 hover:opacity-100"
            >
              Astro Express
            </a>
          </div>
        </div>

        <div class="flex flex-col gap-2">
          <h3 class="font-bold text-lg">Contato</h3>
          <div>
            <a
              href="#contato"
              class="opacity-60 hover:opacity-100"
            >
              Formulário
            </a>
          </div>

          <div>
            <a
              href="https://wa.me/5511999999999"
              target="_blank"
              rel="noopener noreferrer"
              class="opacity-60 hover:opacity-100"
            >
              WhatsApp
            </a>
          </div>

          <div>
            <a
              href="mailto:contato@alforriase.com"
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

          <div>
            <a
              href="https://wa.me/5511999999999"
              target="_blank"
              rel="noopener noreferrer"
              class="opacity-60 hover:opacity-100"
            >
              WhatsApp
            </a>
          </div>
        </div>
      </div>

      <Separator class="my-6" />
      <section class="">
        <div class="flex flex-col md:flex-row justify-between items-center gap-4">
          <h3 class="text-sm">
            &copy; 2024 Alforriase. Atendimento 100% online.
          </h3>
          <p class="text-sm text-muted-foreground">
            Desenvolvido com ❤️ para mulheres que buscam clareza e liberdade.
          </p>
        </div>
      </section>
    </div>
  </footer>
</template>
