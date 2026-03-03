<script setup lang="ts">
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
  name: string;
  result: string;
  comment: string;
  rating: number;
}

const reviewList: ReviewProps[] = [
  {
    name: "Glaucia Égua",
    result: "Liberdade",
    comment:
      "Meu mapa este ano só reforçou o que tinha dado nos anos anteriores. Tinha a informação mas não havia me posicionado. Foi preciso auxílio da minha astróloga para me dar clareza sobre os pontos que me travaram, com base nessas reflexões, entendi quais eram as crenças que me limitavam e como trabalhar na libertação desses pontos e, com isso planejar com base na astrologia os meus próximos passos.",
    rating: 5.0,
  },
  {
    name: "Anonimo",
    result: "Direcionamento",
    comment:
      "Conhecí a Camis através de uma comunidade de mulheres que fazemos parte. Logo me interessei pelo acompanhamento que ela faz mensalmente, voltado para mulheres. Fizemos nossa primeira sessão dia 30/10 e ela me ajudou a enxergar a astrologia de uma forma diferente. Trouxe todas as questões pelas quais estou passando. Tá tudo lá, no meu mapa solar deste ano. Através do meu mapa, consegui identificar os bloqueios pelos quais estou passando mas tmb me mostrou que os movimentos que tenho feito este ano são exatamente os movimentos que o meu mapa me pede pra fazer. Adorei nosso primeiro encontro e tudo o que me trouxe. Aguardando ansiosa pelo de novembro",
    rating: 5.0,
  },

  {
    name: "Mari Balbino",
    result: "Direcionamento",
    comment:
      "Conheci a Camila na B2mamy no mês do meu aniversário e descobrindo que nosso mapa astral muda todo ano, pasmem, não sabia, ali decidi que queria ela como astrologa, ainda não finalizei a jornada solar, estou no meu 2 mês, mas tantas coisas bateram que chega a assustar(risos), começo a sentir algo e aí lembro que ela falou algo sobre isso e quando vou consultar o notion que ela oferece, está tudo lá. Recomendo para todas",
    rating: 5.0,
  },
];
</script>

<template>
  <section id="depoimentos" class="container py-24 sm:py-32" style="
      background: linear-gradient(
        180deg,
        #c4b5a8 0%,
        /* Bege Escuro (Conexão) */ #b28a82 30%,
        /* Transição suave */ #9c5b5e 60%,
        /* Transição suave */ #862d3b 100% /* Seu Vermelho */
      );
    ">
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider" style="font-family: 'Playfair Display', serif">
        Depoimentos
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold mb-4" style="font-family: 'Playfair Display', serif">
        Mulheres que decidiram com mais clareza
      </h2>
    </div>

    <Carousel :opts="{
      align: 'start',
    }" class="relative w-[80%] sm:w-[90%] lg:max-w-screen-xl mx-auto">
      <CarouselContent>
        <CarouselItem v-for="review in reviewList" :key="review.name" class="md:basis-1/2 lg:basis-1/3">
          <Card class="h-full border-2 hover:border-[#722a24] transition-all" style="
              background: linear-gradient(
                135deg,
                #ffffff 0%,
                #f5f0eb 50%,
                #e8ddd4 100%
              );
            ">
            <CardContent class="pt-6 pb-0">
              <div class="flex gap-1 pb-6">
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
              </div>

              <p class="italic !text-[#62120a]">"{{ review.comment }}"</p>
            </CardContent>

            <CardHeader>
              <div class="flex flex-row items-center gap-4">
                <div class="flex flex-col">
                  <CardTitle class="text-lg">{{ review.name }}</CardTitle>
                  <CardDescription>{{ review.result }}</CardDescription>
                </div>
              </div>
            </CardHeader>
          </Card>
        </CarouselItem>
      </CarouselContent>
      <CarouselPrevious aria-label="Depoimento anterior" />
      <CarouselNext aria-label="Próximo depoimento" />
    </Carousel>
  </section>
</template>
