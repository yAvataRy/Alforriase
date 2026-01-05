<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Sparkles,
  Compass,
  Heart,
  Zap,
} from "lucide-vue-next";

interface BenefitsProps {
  icon: string;
  title: string;
  description: string;
}

const benefitList: BenefitsProps[] = [
  {
    icon: "sparkles",
    title: "Astrologia Prática",
    description:
      "Não fazemos previsões, construímos planos de ação. A astrologia é uma ferramenta para compreender seus talentos, desafios e potenciais.",
  },
  {
    icon: "compass",
    title: "Planejamento Estratégico",
    description:
      "Transformamos descobertas astrológicas em passos concretos e alcançáveis para sua vida.",
  },
  {
    icon: "heart",
    title: "Método Humanizado",
    description:
      "Camila ajuda mulheres a priorizarem a si mesmas com leveza e responsabilidade.",
  },
  {
    icon: "zap",
    title: "Liberdade e Clareza",
    description:
      "Alforriase nasceu do desejo de ajudar mulheres a saírem do automático e viverem com liberdade.",
  },
];

const iconMap: Record<
  string,
  | typeof Sparkles
  | typeof Compass
  | typeof Heart
  | typeof Zap
> = {
  sparkles: Sparkles,
  compass: Compass,
  heart: Heart,
  zap: Zap,
};
</script>

<template>
  <section
    id="alforriase"
    class="container py-24 sm:py-32"
    style="background: linear-gradient(135deg, #f5f0eb 0%, #d1c5ba 50%, #f5f0eb 100%);"
  >
    <div class="grid lg:grid-cols-2 place-items-center lg:gap-24">
      <div>
        <h2 class="text-lg text-primary mb-2 tracking-wider" style="font-family: 'Playfair Display', serif;">Sobre</h2>

        <h2 class="text-3xl md:text-4xl font-bold mb-4" style="font-family: 'Playfair Display', serif;">
          A História da Alforriase
        </h2>
        <p class="text-xl text-muted-foreground mb-8">
          Alforriase nasceu do desejo de ajudar mulheres a saírem do automático e viverem com liberdade. 
          Aqui a astrologia é ferramenta prática: não fazemos previsões, construímos planos de ação.
        </p>
        <p class="text-lg text-muted-foreground">
          <strong>Nome:</strong> Alforriase — dar-se liberdade.
        </p>
        <p class="text-lg text-muted-foreground">
          <strong>Método:</strong> Astrologia aplicada + acompanhamento estratégico.
        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-4 w-full">
        <Card
          v-for="({ icon, title, description }, index) in benefitList"
          :key="title"
          class="hover:shadow-lg transition-all delay-75 group/number border-2 hover:border-[#722a24]"
          style="background: linear-gradient(135deg, #ffffff 0%, #f5f0eb 100%);"
        >
          <CardHeader>
            <div class="flex justify-between">
              <component
                class="size-8 mb-6 text-primary"
                :is="iconMap[icon]"
              />

              <span
                class="text-5xl text-muted-foreground/15 font-medium transition-all delay-75 group-hover/number:text-muted-foreground/30"
                >0{{ index + 1 }}</span
              >
            </div>

            <CardTitle>{{ title }}</CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>
