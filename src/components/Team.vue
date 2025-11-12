<script setup lang="ts">
import {
  Card,
  CardContent,
  CardHeader,
  CardTitle,
  CardFooter,
} from "@/components/ui/card";

import InstagramIcon from "@/icons/XIcon.vue";

interface TeamProps {
  imageUrl: string;
  name: string;
  title: string;
  description: string;
  socialNetworks: SocialNetworkProps[];
}

interface SocialNetworkProps {
  name: string;
  url: string;
}

const teamList: TeamProps[] = [
  {
    imageUrl:
      "https://images.unsplash.com/photo-1494783367193-149034c05e41?q=80&w=1200&auto=format&fit=crop",
    name: "Camila",
    title: "Fundadora da Alforriase",
    description:
      "Há 3 anos trabalhando com astrologia prática, Camila desenvolveu um método que une mapa astral e planejamento estratégico para transformar descobertas em passos concretos. Comunicadora clara e prática, ajuda mulheres a priorizarem a si mesmas com leveza e responsabilidade.",
    socialNetworks: [
      {
        name: "Instagram",
        url: "https://instagram.com/camisdaalforriase",
      },
    ],
  },
];

const socialIcon = (socialName: string) => {
  switch (socialName) {
    case "Instagram":
      return InstagramIcon;
    default:
      return InstagramIcon;
  }
};
</script>

<template>
  <section
    id="camila"
    class="container lg:w-[75%] py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider" style="font-family: 'Playfair Display', serif;">Fundadora</h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold" style="font-family: 'Playfair Display', serif;">
        Conheça Camila
      </h2>
    </div>

    <div
      class="grid grid-cols-1 gap-8 max-w-2xl mx-auto"
    >
      <Card
        v-for="{
          imageUrl,
          name,
          title,
          description,
          socialNetworks,
        } in teamList"
        :key="imageUrl"
        class="bg-muted/60 dark:bg-card flex flex-col h-full overflow-hidden group/hoverimg"
      >
        <CardHeader class="p-0 gap-0">
          <div class="h-full overflow-hidden">
            <img
              :src="imageUrl"
              :alt="name"
              class="w-full aspect-square object-cover saturate-0 transition-all duration-200 ease-linear size-full group-hover/hoverimg:saturate-100 group-hover/hoverimg:scale-[1.01]"
            />
          </div>
          <CardTitle class="py-6 pb-4 px-6"
            >{{ name }}
            <span class="text-primary">{{ title }}</span>
          </CardTitle>
        </CardHeader>

        <CardContent class="text-muted-foreground pb-4">
          {{ description }}
        </CardContent>

        <CardFooter class="space-x-4 mt-auto">
          <a
            v-for="{ name: socialName, url } in socialNetworks"
            :key="socialName"
            :href="url"
            target="_blank"
            rel="noopener noreferrer"
            class="hover:opacity-80 transition-all"
            :aria-label="`Visite nosso ${socialName}`"
          >
            <component :is="socialIcon(socialName)" />
          </a>
        </CardFooter>
      </Card>
    </div>
  </section>
</template>
