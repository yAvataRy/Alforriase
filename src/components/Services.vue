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
    link: "https://payfast.greenn.com.br/84569",
  },
  {
    title: "Leitura de Mapa Astral",
    description:
      "Uma análise estratégica do seu mapa natal com foco em carreira, talentos e potencial de crescimento. \n\nIdeal para quem quer: \n* entender sua força profissional \n* reconhecer padrões que travam decisões \n* ganhar direção antes de agir",
    details: "Análise profunda do seu mapa natal",
    pro: 0,
    link: "https://payfast.greenn.com.br/84552",
  },
  {
    title: "Astro Express",
    description:
      "Sessão rápida e objetiva para decisões pontuais. \n\nVocê traz uma questão específica. \nEu te ajudo a enxergar cenário, timing e próximos passos.",
    details: "Clareza em uma conversa focada.",
    pro: 0,
    link: "https://payfast.greenn.com.br/84572/offer/xAcMsw",
  },
  {
    title: "Jornada Solar Pocket",
    description:
      "Panorama estratégico do seu novo ciclo anual. \n\nResumo claro do seu ano profissional: \n* temas centrais \n* prioridades \n* oportunidades \n* pontos de atenção",
    details: "Ideal para quem quer direção sem acompanhamento completo.",
    pro: 0,
    link: "https://payfast.greenn.com.br/116808/offer/Cmw5Od",
  },
];
</script>

<template>
  <section id="experiencias" class="container py-24 sm:py-32" style="
      background: linear-gradient(
        0deg,
        #c4b5a8 0%,
        /* Topo: Bege Escuro */ #ae7d73 40%,
        /* Meio: Terracota suave */ #862d3b 100% /* Base: Seu Vermelho */
      );
    ">
    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4"
      style="color: #2d1210; font-family: 'Playfair Display', serif">
      Experiências Alforriase
    </h2>
    <h3 class="md:w-1/2 mx-auto text-xl text-center textforeground mb-8" style="color: #f5f0eb">
      Escolha o serviço que melhor se adequa ao seu momento e comece sua jornada
      de clareza e liberdade.
    </h3>

    <div class="grid sm:grid-cols-2 lg:grid-cols-2 gap-4 w-full lg:w-[80%] mx-auto">
      <div v-for="{ title, description, details, pro, link } in serviceList" :key="title">
        <Card
          class="h-full relative flex flex-col cursor-pointer hover:shadow-lg transition-shadow border-2 hover:border-[#722a24]"
          style="
            background: linear-gradient(
              135deg,
              #ffffff 0%,
              #f5f0eb 50%,
              #e8ddd4 100%
            );
          " @click="handleCardClick(link)">
          <CardHeader>
            <CardTitle style="color: #000000">{{ title }}</CardTitle>
            <CardDescription style="color: #2d1210">{{
              description
            }}</CardDescription>
            <p class="text-sm text-primary font-semibold whitespace-pre-line mt-2">{{ details }}</p>
          </CardHeader>
          <Badge v-if="pro === ProService.YES" variant="secondary" class="absolute -top-2 -right-3">PRO</Badge>
        </Card>
      </div>
    </div>

    <div class="flex justify-center mt-8">
      <Button class="font-bold" style="
          background: linear-gradient(
            135deg,
            #722a24 0%,
            #8b3d35 40%,
            #a85547 80%,
            #c97d6f 100%
          );
          color: #ffffff;
          border: none;
          box-shadow: 0 4px 15px rgba(114, 42, 36, 0.3);
        " @click="handleServiceClick">
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