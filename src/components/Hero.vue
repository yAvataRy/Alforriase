<script setup lang="ts">
import { Badge } from "@/components/ui/badge";
import { Button } from "@/components/ui/button";
import { ArrowRight } from "lucide-vue-next";

const handleScroll = () => {
  const element = document.getElementById('contato');
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' });
  }
};
</script>

<template>
  <section class="container" id="home" style="background: linear-gradient(180deg, #ffffff 0%, #f5f0eb 50%, #d1c5ba 100%);">
    <div
      class="grid place-items-center lg:max-w-screen-xl gap-8 mx-auto py-20 md:py-32"
    >
      <div class="text-center space-y-8">
        <Badge
          variant="outline"
          class="text-sm py-2"
        >
          <span class="mr-2 text-primary">
            <Badge>Novo</Badge>
          </span>
          <span> Atendimento 100% online </span>
        </Badge>

        <div
          class="max-w-screen-md mx-auto text-center text-5xl md:text-6xl font-bold"
          style="font-family: 'Playfair Display', serif;"
        >
          <h1>
            Alforriase —
            <span
              class="text-transparent bg-clip-text"
              style="background: linear-gradient(135deg, #722a24 0%, #8b3d35 100%); -webkit-background-clip: text; background-clip: text;"
              >Clareza que liberta</span
            >
          </h1>
        </div>

        <p class="max-w-screen-sm mx-auto text-xl text-muted-foreground">
          Astrologia aplicada + acompanhamento estratégico para mulheres que querem viver com mais direção e liberdade.
        </p>

        <div class="space-y-4 md:space-y-0 md:space-x-4">
          <Button class="w-5/6 md:w-1/4 font-bold group/arrow" @click="handleScroll">
            Agendar conversa
            <ArrowRight
              class="size-5 ml-2 group-hover/arrow:translate-x-1 transition-transform"
            />
          </Button>

          <Button
            as-child
            variant="secondary"
            class="w-5/6 md:w-1/4 font-bold"
          >
            <a
              href="https://wa.me/5511999999999?text=Olá! Gostaria de agendar uma conversa com a Camila."
              target="_blank"
              rel="noopener noreferrer"
              >WhatsApp</a
            >
          </Button>
        </div>
      </div>

      <div class="relative group mt-14">
        <!-- gradient shadow -->
        <div
          class="absolute -top-6 right-12 w-[90%] h-12 lg:h-[80%] bg-primary/50 blur-3xl rounded-full img-shadow-animation"
        ></div>

        <img
          class="w-full md:w-[1200px] mx-auto rounded-lg relative rouded-lg leading-none flex items-center border border-t-2 border-t-primary/30 img-border-animation"
          src="https://images.unsplash.com/photo-1494783367193-149034c05e41?w=1200&h=600&fit=crop"
          alt="Alforriase - Astrologia aplicada para mulheres"
          loading="lazy"
        />

        <!-- gradient effect img -->
        <div
          class="absolute bottom-0 left-0 w-full h-20 md:h-28 bg-gradient-to-b from-background/0 via-background/50 to-background rounded-lg"
        ></div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.img-shadow-animation {
  animation-name: img-shadow-animation;
  animation-iteration-count: infinite;
  animation-duration: 2s;
  animation-timing-function: linear;
  animation-direction: alternate;
}

.img-border-animation {
  animation-name: img-border-animation;
  animation-iteration-count: infinite;
  animation-duration: 2s;
  animation-timing-function: linear;
  animation-direction: alternate;
}

@keyframes img-shadow-animation {
  from {
    opacity: 0.5;
    transform: translateY(30px);
  }

  to {
    opacity: 1;
    transform: translateY(0px);
  }
}
@keyframes img-border-animation {
  from {
    @apply border-t-primary/10;
  }

  to {
    @apply border-t-primary/60;
  }
}
</style>
