<script setup lang="ts">
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion";

interface FAQProps {
  question: string;
  answer: string;
  value: string;
}

const FAQList: FAQProps[] = [
  {
    question:
      "Qual é a diferença da Jornada Solar pra uma leitura comum de mapa?",
    answer:
      "A maioria das leituras termina quando o atendimento acaba. Na Jornada Solar, você tem um acompanhamento contínuo ao longo do ano com quatro encontros trimestrais pra revisar metas, alinhar decisões e ajustar a rota.",
    value: "item-1",
  },
  {
    question: "Qual é o momento ideal pra fazer a Jornada Solar?",
    answer:
      "O ideal é o início do seu novo ano pessoal, o período do seu aniversário. Mas se você está num momento de recomeço (mudança de carreira, foco ou propósito), o céu sempre tem um ponto de virada pra você.",
    value: "item-2",
  },
  {
    question: "E se eu não entender nada de astrologia?",
    answer:
      "Eu traduzo todo o conteúdo de forma prática e acessível, pra que você consiga aplicar o que aparece no seu mapa no dia a dia, nas metas, nas relações e nas escolhas que realmente importam.",
    value: "item-3",
  },
];
</script>

<template>
  <section id="faq" class="container md:w-[700px] py-6 sm:py-8">
    <div class="text-center mb-2">
      <!-- <h2 class="text-lg text-primary text-center mb-2 tracking-wider">FAQS</h2> -->

      <h2
        class="text-3xl md:text-4xl text-center font-bold"
        style="
          background: linear-gradient(
            135deg,
            #722a24 0%,
            #8b3d35 40%,
            #a85547 80%,
            #c97d6f 100%
          );

          background-clip: text;
          -webkit-text-fill-color: transparent;
          color: transparent;
          font-family: 'Playfair Display', serif;
        "
      >
        Dúvidas comuns
      </h2>
    </div>

    <Accordion type="single" collapsible class="AccordionRoot">
      <AccordionItem
        v-for="{ question, answer, value } in FAQList"
        :key="value"
        :value="value"
      >
        <AccordionTrigger class="text-left" style="color: #62120a !important">
          {{ question }}
        </AccordionTrigger>

        <AccordionContent class="!text-[#62120a] !text-sm">{{
          answer
        }}</AccordionContent>
      </AccordionItem>
    </Accordion>

    <h3 class="font-medium mt-4">
      Ainda tem dúvidas?
      <a href="#" class="text-muted-foreground">
        <a
          href="https://api.whatsapp.com/send?phone=5511951366861&text=Ol%C3%A1,%20ainda%20tenho%20d%C3%BAvidas."
          target="_blank"
          rel="noopener noreferrer"
          class="underline"
          >Entre em contato</a
        >
      </a>
    </h3>
  </section>
</template>
