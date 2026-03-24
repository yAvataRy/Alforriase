<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import { Sparkles, Compass, Heart, Zap } from "lucide-vue-next";

interface BenefitsProps {
  icon: string;
  title: string;
  description: string;
}

const benefitList: BenefitsProps[] = [
  {
    icon: "sparkles",
    title: "Astrologia Estratégica",
    description:
      "Não fazemos previsões soltas. Transformamos seu mapa em clareza para decisões profissionais.",
  },
  {
    icon: "compass",
    title: "Planejamento de Ciclos",
    description:
      "Entendemos o seu ano como um todo. Definimos prioridades, movimentos e momentos de ação.",
  },
  {
    icon: "heart",
    title: "Método Direto e Aplicável",
    description:
      "Sem misticismo excessivo. Você sai com plano, direção e próximos passos claros.",
  },
  {
    icon: "zap",
    title: "Clareza para Decidir",
    description:
      "Mais segurança nas escolhas. \nMenos impulso. \nMais estratégia.",
  },
];

const iconMap: Record<
  string,
  typeof Sparkles | typeof Compass | typeof Heart | typeof Zap
> = {
  sparkles: Sparkles,
  compass: Compass,
  heart: Heart,
  zap: Zap,
};
</script>

<template>
  <section id="alforriase" class="container py-12 sm:py-16">
    <div class="grid lg:grid-cols-2 place-items-center lg:gap-24">
      <div>
        <h2
          class="text-lg text-primary mb-2 tracking-wider"
          style="font-family: 'Playfair Display', serif"
        >
          Sobre
        </h2>

        <h2
          class="text-3xl md:text-4xl font-bold mb-4"
          style="font-family: 'Playfair Display', serif"
        >
          Minha História
        </h2>
        <p class="text-xl text-foreground mb-8">
          Meu trabalho nasceu do desejo de ajudar mulheres a saírem do
          automático profissional.
        </p>

        <p class="text-xl text-foreground mb-8">
          Eu <span class="italic">não</span> uso astrologia para prever.<br />
          Eu uso astrologia para
          <span class="font-semibold">organizar decisões</span>.
        </p>

        <p class="text-xl text-foreground mb-4">
          Aqui, o mapa deixa de ser algo abstrato e se transforma em estratégia:
        </p>

        <ul class="text-xl text-foreground space-y-2 mb-8">
          <li>• entender seu momento</li>
          <li>• identificar prioridades</li>
          <li>• agir no tempo certo</li>
          <li>• evitar decisões impulsivas</li>
        </ul>
        <p class="text-lg text-foreground">
          <strong>Método:</strong> Astrologia aplicada + planejamento
          estratégico anual.
        </p>
        <p class="text-lg text-foreground">
          <strong>Foco:</strong> Carreira, trabalho e decisões importantes.
        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-4 w-full">
        <Card
          v-for="{ icon, title, description } in benefitList"
          :key="title"
          class="hover:shadow-lg transition-all delay-75 group/number border-2 border-teal/15 hover:border-wine/60 bg-background/80 backdrop-blur-sm"
        >
          <CardHeader>
            <div class="flex justify-between">
              <component class="size-8 text-primary mr-4" :is="iconMap[icon]" />
              <CardTitle>{{ title }}</CardTitle>
            </div>
          </CardHeader>

          <CardContent class="text-foreground whitespace-pre-line">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>

<style scoped>
p {
  white-space: pre-line;
}
</style>