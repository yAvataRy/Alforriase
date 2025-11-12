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
}

const handleServiceClick = () => {
  const element = document.getElementById('contato');
  if (element) element.scrollIntoView({ behavior: 'smooth' });
};

const serviceList: ServiceProps[] = [
  {
    title: "Jornada Solar",
    description:
      "4 encontros ao longo do ano para transformar seus objetivos em um plano prático, alinhado à sua Revolução Solar.",
    details: "Planejamento estratégico anual baseado em astrologia",
    pro: 0,
  },
  {
    title: "Leitura de Mapa Astral",
    description:
      "Mergulho para compreender talentos, desafios e potenciais; plano de ação prático.",
    details: "Análise profunda do seu mapa natal",
    pro: 0,
  },
  {
    title: "Astro Express",
    description: "Atendimento rápido para dúvidas pontuais; clareza imediata para agir.",
    details: "Sessão rápida e focada",
    pro: 0,
  },
  {
    title: "Jornada Solar Pocket",
    description:
      "Resumo do novo ciclo com prioridades principais (formato rápido).",
    details: "Versão compacta da Jornada Solar",
    pro: 0,
  },
];
</script>

<template>
  <section
    id="experiencias"
    class="container py-24 sm:py-32"
  >
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider" style="font-family: 'Playfair Display', serif;">
      Nossas Experiências
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4" style="font-family: 'Playfair Display', serif;">
      Serviços da Alforriase
    </h2>
    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Escolha o serviço que melhor se adequa ao seu momento e comece sua jornada de clareza e liberdade.
    </h3>

    <div
      class="grid sm:grid-cols-2 lg:grid-cols-2 gap-4 w-full lg:w-[80%] mx-auto"
    >
      <div
        v-for="{ title, description, details, pro } in serviceList"
        :key="title"
      >
        <Card class="bg-muted/60 dark:bg-card h-full relative flex flex-col">
          <CardHeader>
            <CardTitle>{{ title }}</CardTitle>
            <CardDescription>{{ description }}</CardDescription>
            <p class="text-sm text-primary font-semibold mt-2">{{ details }}</p>
          </CardHeader>
          <div class="px-6 pb-6 mt-auto">
            <Button 
              variant="outline" 
              class="w-full"
              @click="handleServiceClick"
            >
              Quero saber mais
            </Button>
          </div>
          <Badge
            v-if="pro === ProService.YES"
            variant="secondary"
            class="absolute -top-2 -right-3"
            >PRO</Badge
          >
        </Card>
      </div>
    </div>
  </section>
</template>
