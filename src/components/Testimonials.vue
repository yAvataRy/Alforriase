<script setup lang="ts">
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";

import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from "@/components/ui/carousel";

import { Star } from "lucide-vue-next";

interface ReviewProps {
  image: string;
  name: string;
  result: string;
  comment: string;
  rating: number;
}

const reviewList: ReviewProps[] = [
  {
    image: "https://images.unsplash.com/photo-1494790108377-be9c29b29330?q=80&w=400&auto=format&fit=crop",
    name: "Juliana M.",
    result: "Planejamento mais focado",
    comment:
      "A Jornada Solar mudou minha forma de planejar o ano — me sinto mais focada e menos ansiosa.",
    rating: 5.0,
  },
  {
    image: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?q=80&w=400&auto=format&fit=crop",
    name: "Marina S.",
    result: "Autoconhecimento profundo",
    comment:
      "A leitura do mapa astral foi reveladora. Camila ajudou a compreender meus talentos e desafios de forma prática.",
    rating: 5.0,
  },

  {
    image: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?q=80&w=400&auto=format&fit=crop",
    name: "Ana P.",
    result: "Clareza para agir",
    comment:
      "O Astro Express foi perfeito para resolver uma dúvida que me travava. Saí da sessão com clareza e ação.",
    rating: 4.9,
  },
  {
    image: "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?q=80&w=400&auto=format&fit=crop",
    name: "Beatriz L.",
    result: "Liberdade e leveza",
    comment:
      "Camila me ajudou a priorizar a mim mesma com responsabilidade. Sinto-me mais livre e leve.",
    rating: 5.0,
  },
  {
    image: "https://images.unsplash.com/photo-1517841905240-1c28a8a0ceb8?q=80&w=400&auto=format&fit=crop",
    name: "Fernanda T.",
    result: "Transformação pessoal",
    comment:
      "Depois de três meses com Camila, minha vida mudou completamente. Estou vivendo com mais propósito.",
    rating: 5.0,
  },
];
</script>

<template>
  <section
    id="depoimentos"
    class="container py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider" style="font-family: 'Playfair Display', serif;">
        Depoimentos
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold mb-4" style="font-family: 'Playfair Display', serif;">
        O que nossas clientes dizem
      </h2>
    </div>

    <Carousel
      :opts="{
        align: 'start',
      }"
      class="relative w-[80%] sm:w-[90%] lg:max-w-screen-xl mx-auto"
    >
      <CarouselContent>
        <CarouselItem
          v-for="review in reviewList"
          :key="review.name"
          class="md:basis-1/2 lg:basis-1/3"
        >
          <Card class="bg-muted/50 dark:bg-card h-full">
            <CardContent class="pt-6 pb-0">
              <div class="flex gap-1 pb-6">
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
              </div>

              <p class="italic">"{{ review.comment }}"</p>
            </CardContent>

            <CardHeader>
              <div class="flex flex-row items-center gap-4">
                <Avatar>
                  <AvatarImage
                    :src="review.image"
                    :alt="review.name"
                  />
                  <AvatarFallback>{{ review.name.charAt(0) }}</AvatarFallback>
                </Avatar>

                <div class="flex flex-col">
                  <CardTitle class="text-lg">{{ review.name }}</CardTitle>
                  <CardDescription>{{ review.result }}</CardDescription>
                </div>
              </div>
            </CardHeader>
          </Card>
        </CarouselItem>
      </CarouselContent>
      <CarouselPrevious />
      <CarouselNext />
    </Carousel>
  </section>
</template>
