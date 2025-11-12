<script lang="ts" setup>
import { ref } from "vue";

import { useColorMode } from "@vueuse/core";
const mode = useColorMode();
mode.value = "light";

import {
  NavigationMenu,
  NavigationMenuContent,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  NavigationMenuTrigger,
} from "@/components/ui/navigation-menu";
import {
  Sheet,
  SheetContent,
  SheetFooter,
  SheetHeader,
  SheetTitle,
  SheetTrigger,
} from "@/components/ui/sheet";

import { Button } from "@/components/ui/button";
import { Separator } from "@/components/ui/separator";

import { Sparkles, Menu } from "lucide-vue-next";
import ToggleTheme from "./ToggleTheme.vue";

interface RouteProps {
  href: string;
  label: string;
}

interface FeatureProps {
  title: string;
  description: string;
}

const routeList: RouteProps[] = [
  {
    href: "#alforriase",
    label: "Sobre",
  },
  {
    href: "#camila",
    label: "Camila",
  },
  {
    href: "#experiencias",
    label: "Experiências",
  },
  {
    href: "#depoimentos",
    label: "Depoimentos",
  },
  {
    href: "#contato",
    label: "Contato",
  },
];

const featureList: FeatureProps[] = [
  {
    title: "Jornada Solar",
    description: "4 encontros ao longo do ano para transformar seus objetivos em um plano prático.",
  },
  {
    title: "Leitura de Mapa Astral",
    description:
      "Mergulho para compreender talentos, desafios e potenciais; plano de ação prático.",
  },
  {
    title: "Astro Express",
    description:
      "Atendimento rápido para dúvidas pontuais; clareza imediata para agir.",
  },
];

const isOpen = ref<boolean>(false);
</script>

<template>
  <header
    :class="{
      'shadow-light': mode === 'light',
      'shadow-dark': mode === 'dark',
      'w-[90%] md:w-[70%] lg:w-[75%] lg:max-w-screen-xl top-5 mx-auto sticky border z-40 rounded-2xl flex justify-between items-center p-2 bg-card shadow-md': true,
    }"
  >
    <a
      href="#home"
      class="font-bold text-lg flex items-center"
      style="font-family: 'Playfair Display', serif;"
    >
      <Sparkles
        class="bg-gradient-to-tr from-primary via-primary/70 to-secondary rounded-lg w-9 h-9 mr-2 border text-white"
      />
      Alforriase
    </a>
    <!-- Mobile -->
    <div class="flex items-center lg:hidden">
      <Sheet v-model:open="isOpen">
        <SheetTrigger as-child>
          <Menu
            @click="isOpen = true"
            class="cursor-pointer"
          />
        </SheetTrigger>

        <SheetContent
          side="left"
          class="flex flex-col justify-between rounded-tr-2xl rounded-br-2xl bg-card"
        >
          <div>
            <SheetHeader class="mb-4 ml-4">
              <SheetTitle class="flex items-center" style="font-family: 'Playfair Display', serif;">
                <a
                  href="#home"
                  class="flex items-center"
                >
                  <Sparkles
                    class="bg-gradient-to-tr from-primary/70 via-primary to-secondary/70 rounded-lg size-9 mr-2 border text-white"
                  />
                  Alforriase
                </a>
              </SheetTitle>
            </SheetHeader>

            <div class="flex flex-col gap-2">
              <Button
                v-for="{ href, label } in routeList"
                :key="label"
                as-child
                variant="ghost"
                class="justify-start text-base"
              >
                <a
                  @click="isOpen = false"
                  :href="href"
                >
                  {{ label }}
                </a>
              </Button>
            </div>
          </div>

          <SheetFooter class="flex-col sm:flex-col justify-start items-start">
            <Separator class="mb-2" />

            <ToggleTheme />
          </SheetFooter>
        </SheetContent>
      </Sheet>
    </div>

    <!-- Desktop -->
    <NavigationMenu class="hidden lg:block">
      <NavigationMenuList>
        <NavigationMenuItem>
          <NavigationMenuTrigger class="bg-card text-base">
            Serviços
          </NavigationMenuTrigger>
          <NavigationMenuContent>
            <div class="grid w-[600px] grid-cols-2 gap-5 p-4">
              <img
                src="https://images.unsplash.com/photo-1494783367193-149034c05e41?w=400&h=400&fit=crop"
                alt="Alforriase"
                class="h-full w-full rounded-md object-cover"
              />
              <ul class="flex flex-col gap-2">
                <li
                  v-for="{ title, description } in featureList"
                  :key="title"
                  class="rounded-md p-3 text-sm hover:bg-muted"
                >
                  <p class="mb-1 font-semibold leading-none text-foreground">
                    {{ title }}
                  </p>
                  <p class="line-clamp-2 text-muted-foreground">
                    {{ description }}
                  </p>
                </li>
              </ul>
            </div>
          </NavigationMenuContent>
        </NavigationMenuItem>

        <NavigationMenuItem>
          <NavigationMenuLink asChild>
            <Button
              v-for="{ href, label } in routeList"
              :key="label"
              as-child
              variant="ghost"
              class="justify-start text-base"
            >
              <a :href="href">
                {{ label }}
              </a>
            </Button>
          </NavigationMenuLink>
        </NavigationMenuItem>
      </NavigationMenuList>
    </NavigationMenu>

    <div class="hidden lg:flex gap-2">
      <ToggleTheme />

      <Button
        as-child
        size="sm"
        class="font-bold"
      >
        <a
          href="#contato"
        >
          Agendar conversa
        </a>
      </Button>
    </div>
  </header>
</template>

<style scoped>
.shadow-light {
  box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.085);
}

.shadow-dark {
  box-shadow: inset 0 0 5px rgba(255, 255, 255, 0.141);
}
</style>
