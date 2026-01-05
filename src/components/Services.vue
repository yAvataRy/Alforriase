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
      "4 encontros ao longo do ano pra transformar seus objetivos em um plano prático. Baseada na sua Revolução Solar, a Jornada te ajuda a definir prioridades, alinhar decisões e construir uma rotina coerente com o que você quer viver.",
    details: "Planejamento estratégico anual baseado em astrologia",
    pro: 0,
    link: "https://payfast.greenn.com.br/84569",
  },
  {
    title: "Leitura de Mapa Astral",
    description:
      "Um mergulho pra entender seus talentos, desafios e potenciais. Ideal pra quem quer se reconectar com sua essência e compreender quem é e o que precisa pra viver de forma mais alinhada.",
    details: "Análise profunda do seu mapa natal",
    pro: 0,
    link: "https://payfast.greenn.com.br/84552",
  },
  {
    title: "Astro Express",
    description:
      "Um atendimento rápido e certeiro pra momentos de dúvida. Você traz uma questão específica, e eu te ajudo a enxergar o cenário com clareza e confiança pra agir",
    details: "Sessão rápida e focada",
    pro: 0,
    link: "https://payfast.greenn.com.br/84572/offer/xAcMsw",
  },
  {
    title: "Jornada Solar Pocket",
    description:
      "Um resumo do seu novo ciclo, mostrando os temas e prioridades principais. Perfeita pra quem quer começar o ano com direção, mas ainda sem acompanhamento completo.",
    details: "Versão compacta da Jornada Solar",
    pro: 0,
    link: "https://payfast.greenn.com.br/116808/offer/Cmw5Od",
  },
];
</script>

<template>
  <section
    id="experiencias"
    class="container py-24 sm:py-32"
    style="
      background: linear-gradient(
        180deg,
        #d1c5ba 0%,
        #ffffff 50%,
        #f5f0eb 100%
      );
    "
  >
    <h2
      class="text-lg text-primary text-center mb-2 tracking-wider"
      style="font-family: 'Playfair Display', serif"
    >
      Nossas Experiências
    </h2>

    <h2
      class="text-3xl md:text-4xl text-center font-bold mb-4"
      style="
        background: linear-gradient(135deg, #722a24 0%, #8b3d35 100%);
        -webkit-background-clip: text;
        background-clip: text;
        -webkit-text-fill-color: transparent;
        color: transparent;
        font-family: 'Playfair Display', serif;
      "
    >
      Experiências Alforriase
    </h2>
    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Escolha o serviço que melhor se adequa ao seu momento e comece sua jornada
      de clareza e liberdade.
    </h3>

    <div
      class="grid sm:grid-cols-2 lg:grid-cols-2 gap-4 w-full lg:w-[80%] mx-auto"
    >
      <div
        v-for="{ title, description, details, pro, link } in serviceList"
        :key="title"
      >
        <Card
          class="h-full relative flex flex-col cursor-pointer hover:shadow-lg transition-shadow border-2 hover:border-[#722a24]"
          style="background: linear-gradient(135deg, #ffffff 0%, #f5f0eb 100%)"
          @click="handleCardClick(link)"
        >
          <CardHeader>
            <CardTitle>{{ title }}</CardTitle>
            <CardDescription>{{ description }}</CardDescription>
            <p class="text-sm text-primary font-semibold mt-2">{{ details }}</p>
          </CardHeader>
          <Badge
            v-if="pro === ProService.YES"
            variant="secondary"
            class="absolute -top-2 -right-3"
            >PRO</Badge
          >
        </Card>
      </div>
    </div>

    <div class="flex justify-center mt-8">
      <Button
        class="font-bold"
        style="
          background: linear-gradient(135deg, #722a24 0%, #8b3d35 100%);
          color: #d1c5ba;
          border: none;
        "
        @click="handleServiceClick"
      >
        Quero sanar minhas dúvidas
      </Button>
    </div>
  </section>
</template>
