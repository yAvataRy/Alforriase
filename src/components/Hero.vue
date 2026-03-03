<script setup lang="ts">
import { Badge } from "@/components/ui/badge";
import { Button } from "@/components/ui/button";
</script>

<template>
  <section class="container" id="home" style="
      background: linear-gradient(
        180deg,
        #ffffff 0%,
        #f5f0eb 25%,
        #e8ddd4 50%,
        #d1c5ba 75%,
        #c4b5a8 100%
      );
    ">
    <div class="grid place-items-center lg:max-w-screen-xl gap-8 mx-auto py-10 md:py-24">
      <div class="text-center space-y-8">
        <Badge variant="outline" class="text-sm py-2">
          <span class="mr-2 text-primary">
            <Badge>Novo</Badge>
          </span>
          <span> Atendimento 100% online </span>
        </Badge>

        <div class="max-w-screen-md mx-auto text-center text-5xl md:text-6xl font-bold"
          style="font-family: 'Playfair Display', serif">
          <h1>
            Camila Paes
            <br />
            <span class="text-transparent bg-clip-text" style="
                background: linear-gradient(
                  135deg,
                  #722a24 0%,
                  #8b3d35 40%,
                  #a85547 70%,
                  #c97d6f 100%
                );
                -webkit-background-clip: text;
                background-clip: text;
              ">Planejamento Astrológico para sua Carreira</span>
          </h1>
        </div>

        <p class="max-w-screen-sm mx-auto text-xl text-foreground" style="color: #2d1210">
          Astrologia aplicada + acompanhamento estratégico para mulheres que precisam tomar decisões profissionais com
          clareza, direção e no timing certo.
        </p>

        <div class="flex flex-col items-center space-y-4 md:flex-row md:justify-center md:space-y-0 md:space-x-4">
          <Button as-child variant="secondary" class="w-fit px-8 font-bold">
            <a href="https://api.whatsapp.com/send?phone=5511951366861&text=Ol%C3%A1,%20vim%20pelo%20site."
              target="_blank" rel="noopener noreferrer" class="whitespace-nowrap">
              Falar direto comigo
            </a>
          </Button>
        </div>
      </div>

      <div class="relative group mt-14">
        <!-- gradient shadow -->
        <div
          class="absolute -top-6 right-12 w-[90%] h-12 lg:h-[80%] bg-primary/50 blur-3xl rounded-full img-shadow-animation">
        </div>

        <!-- gradient effect img -->
        <div
          class="absolute bottom-0 left-0 w-full h-20 md:h-28 bg-gradient-to-b from-background/0 via-background/50 to-background rounded-lg">
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
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
