<script setup lang="ts">
import {
  Card,
  CardContent,
  CardHeader,
  CardTitle,
  // CardFooter,
} from "@/components/ui/card";

// import InstagramIcon from "@/icons/XIcon.vue";

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
    imageUrl: "/Camila1.jpg",
    name: "Camila",
    title: "Fundadora da Alforriase",
    description:
      "Eu sou Camila Paes, astróloga e criadora do Método Alforriase, uma abordagem que une astrologia prática e planejamento pra mulheres voltarem a se priorizar e realizar seus objetivos. Já ajudei mais de 200 mulheres a retomarem seus projetos, conquistarem clareza sobre seus caminhos e viverem seus ciclos com mais confiança e leveza. Acredito que liberdade vem quando você aprende a se planejar a partir de quem você é e não do que esperam de você.",
    socialNetworks: [
      {
        name: "Instagram",
        url: "https://instagram.com/camila.suaastrologa",
      },
    ],
  },
];

// const socialIcon = (socialName: string) => {
//   switch (socialName) {
//     case "Instagram":
//       return InstagramIcon;
//     default:
//       return InstagramIcon;
//   }
//};
</script>

<template>
  <!-- <section id="camila" class="container py-12 sm:py-16" style="
      background: linear-gradient(
        0deg,
        #ffffff 0%,
        #f5f0eb 25%,
        #e8ddd4 50%,
        #d1c5ba 75%,
        #c4b5a8 100%
      );
    "> QUANDO VOLTAR O INSTAGRAM FEED USAR ESSE BACKGROUND  ACIMA-->
  <section id="camila" class="container py-12 sm:py-16">
    <div class="text-center mb-8">
      <!-- <h2
        class="text-lg text-primary text-center mb-2 tracking-wider"
        style="font-family: 'Playfair Display', serif"
      >
        Fundadora
      </h2> -->

      <h2
        class="text-3xl md:text-4xl text-center font-bold"
        style="font-family: 'Playfair Display', serif"
      >
        Conheça Camila
      </h2>
    </div>

    <div class="grid grid-cols-1 gap-8 max-w-2xl mx-auto lg:w-[75%]">
      <Card
        v-for="{
          imageUrl,
          name,
          title,
          description,
          // socialNetworks,
        } in teamList"
        :key="imageUrl"
        class="flex flex-col h-full overflow-hidden group/hoverimg border-2 border-teal/15 hover:border-wine/60 transition-all bg-background/80 backdrop-blur-sm"
      >
        <CardHeader class="p-0 gap-0">
          <div class="h-full overflow-hidden">
            <img
              :src="imageUrl"
              :alt="name"
              class="w-full aspect-square object-cover transition-all duration-200 ease-linear size-full group-hover/hoverimg:saturate-100 group-hover/hoverimg:scale-[1.01]"
            />
          </div>
          <CardTitle class="py-6 pb-4 px-6"
            >{{ name }}
            <span class="text-primary">{{ title }}</span>
          </CardTitle>
        </CardHeader>

        <CardContent class="text-foreground pb-4">
          {{ description }}
        </CardContent>

        <!-- <CardFooter class="space-x-4 mt-auto">
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
        </CardFooter> -->
      </Card>
    </div>
  </section>
</template>
