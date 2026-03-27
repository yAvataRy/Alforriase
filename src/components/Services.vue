<script setup lang="ts">
import {
  Card,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import { Badge } from "@/components/ui/badge";
import { Button } from "@/components/ui/button";

enum ProService {
  YES = 1,
  NO = 0,
}

interface ServiceProps {
  title: string;
  pro: ProService;
  description: string;
  details: string;
  link: string;
  buttonText: string;
}

const handleServiceClick = () => {
  const element = document.getElementById("contato");
  if (element) element.scrollIntoView({ behavior: "smooth" });
};

const handleCardClick = (link: string) => {
  window.open(link, "_blank");
};

const serviceList: ServiceProps[] = [
  {
    title: "Jornada Solar",
    description:
      "Acompanhamento estratégico anual para mulheres que querem organizar o ano profissional com clareza e direção. \n\n4 encontros ao longo do ano para: \n* definir prioridades \n* alinhar decisões \n* entender o timing certo \n* evitar retrabalho e desgaste",
    details: "Planejamento anual baseado na sua Revolução Solar.",
    pro: 0,
    link: "https://link.infinitepay.io/alforriase/VC1D-7WlT9vwzjv-1500,00",
    buttonText: "Compre aqui - Jornada Solar",
  },
  {
    title: "Leitura de Mapa Astral",
    description:
      "Uma análise estratégica do seu mapa natal com foco em carreira, talentos e potencial de crescimento. \n\nIdeal para quem quer: \n* entender sua força profissional \n* reconhecer padrões que travam decisões \n* ganhar direção antes de agir",
    details: "Análise profunda do seu mapa natal",
    pro: 0,
    link: "https://link.infinitepay.io/alforriase/VC1D-2Z92IavQp-404,00",
    buttonText: "Compre aqui - Leitura de Mapa Astral",
  },
  {
    title: "Astro Express",
    description:
      "Sessão rápida e objetiva para decisões pontuais. \n\nVocê traz uma questão específica. \nEu te ajudo a enxergar cenário, timing e próximos passos.",
    details: "Clareza em uma conversa focada.",
    pro: 0,
    link: "https://link.infinitepay.io/alforriase/VC1DLTAtUg-7U79M8hv2l-206,00",
    buttonText: "Compre aqui - Astro Express",
  },
  {
    title: "Jornada Solar Pocket",
    description:
      "Panorama estratégico do seu novo ciclo anual. \n\nResumo claro do seu ano profissional: \n* temas centrais \n* prioridades \n* oportunidades \n* pontos de atenção",
    details: "Ideal para quem quer direção sem acompanhamento completo.",
    pro: 0,
    link: "https://link.infinitepay.io/alforriase/VC1D-7S2J1WFmtp-701,00",
    buttonText: "Compre aqui - Jornada Solar Pocket",
  },
];
</script>

<template>
  <section id="experiencias" class="container py-12 sm:py-16">
    <h2
      class="text-3xl md:text-4xl text-center font-bold mb-4"
      style="font-family: 'Playfair Display', serif"
    >
      Experiências com sua astróloga
    </h2>
    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Escolha o serviço que melhor se adequa ao seu momento e comece sua jornada
      de clareza e liberdade.
    </h3>

    <div
      class="grid sm:grid-cols-2 lg:grid-cols-2 gap-4 w-full lg:w-[80%] mx-auto"
    >
      <div
        v-for="{
          title,
          description,
          details,
          pro,
          link,
          buttonText,
        } in serviceList"
        :key="title"
      >
        <Card
          class="h-full relative flex flex-col hover:shadow-lg transition-shadow border-2 border-teal/15 hover:border-wine/60 bg-background/80 backdrop-blur-sm"
        >
          <CardHeader>
            <CardTitle>{{ title }}</CardTitle>
            <CardDescription>{{ description }}</CardDescription>
            <p
              class="text-sm text-primary font-semibold whitespace-pre-line mt-2"
            >
              {{ details }}
            </p>
          </CardHeader>
          <Badge
            v-if="pro === ProService.YES"
            variant="secondary"
            class="absolute -top-2 -right-3"
            >PRO</Badge
          >
          <div class="mt-auto w-full flex justify-center p-2">
            <Button
              class="font-bold w-full max-w-[300px]"
              @click="handleCardClick(link)"
            >
              {{ buttonText }}
            </Button>
          </div>
        </Card>
      </div>
    </div>

    <div class="flex justify-center mt-8">
      <Button class="font-bold" @click="handleServiceClick">
        Quero sanar minhas dúvidas
      </Button>
    </div>
  </section>
</template>

<style scoped>
p {
  white-space: pre-line;
}
</style>