<script setup lang="ts">
import { ref, reactive } from "vue";
import { Button } from "./ui/button";
import { Card, CardHeader, CardContent, CardFooter } from "./ui/card";
import { Label } from "./ui/label";
import { Input } from "./ui/input";
import {
  Select,
  SelectContent,
  SelectGroup,
  SelectItem,
  SelectTrigger,
  SelectValue,
} from "./ui/select";
import { Textarea } from "./ui/textarea";
import { Alert, AlertDescription, AlertTitle } from "@/components/ui/alert";

import { AlertCircle, Mail, MessageCircle, Clock } from "lucide-vue-next";

interface ContactFormeProps {
  name: string;
  email: string;
  subject: string;
  message: string;
}

const contactForm = reactive<ContactFormeProps>({
  name: "",
  email: "",
  subject: "Jornada Solar",
  message: "",
});

const invalidInputForm = ref<boolean>(false);
const successMessage = ref<boolean>(false);

const handleSubmit = async () => {
  const { name, email, subject, message } = contactForm;

  if (!name || !email || !message) {
    invalidInputForm.value = true;
    return;
  }

  try {
    // Usar FormSubmit.co para enviar o formulário
    const formData = new FormData();
    formData.append("name", name);
    formData.append("email", email);
    formData.append("subject", subject);
    formData.append("message", message);
    formData.append("_captcha", "false");

    const response = await fetch(
      "https://formsubmit.co/ajax/seu_email@alforriase.com",
      {
        method: "POST",
        body: formData,
      }
    );

    if (response.ok) {
      successMessage.value = true;
      contactForm.name = "";
      contactForm.email = "";
      contactForm.subject = "Jornada Solar";
      contactForm.message = "";

      setTimeout(() => {
        successMessage.value = false;
      }, 5000);
    }
  } catch (error) {
    console.error("Erro ao enviar formulário:", error);
    invalidInputForm.value = true;
  }
};
</script>

<template>
  <section
    id="contato"
    class="container py-24 sm:py-32"
    style="
      background: linear-gradient(
        135deg,
        #c4b5a8 0%,
        #d1c5ba 25%,
        #f5f0eb 50%,
        #ffffff 75%,
        #f5f0eb 100%
      );
    "
  >
    <section class="grid grid-cols-1 md:grid-cols-2 gap-8">
      <div>
        <div class="mb-4">
          <h2
            class="text-3xl md:text-4xl font-bold"
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
            Vamos conversar?
          </h2>
        </div>
        <p class="mb-8 text-muted-foreground lg:w-5/6">
          Pronta para transformar seu ciclo? Agende um diagnóstico rápido e
          descubra o próximo passo da sua jornada.
        </p>

        <div class="flex flex-col gap-4">
          <div>
            <div class="flex gap-2 mb-1">
              <Mail />
              <div class="font-bold">Email</div>
            </div>

            <div>
              <a
                href="mailto:alforriase@outlook.com"
                class="text-primary hover:underline"
              >
                alforriase@outlook.com
              </a>
            </div>
          </div>

          <div>
            <div class="flex gap-2 mb-1">
              <MessageCircle />
              <div class="font-bold">WhatsApp</div>
            </div>

            <div>
              <a
                href="https://api.whatsapp.com/send?phone=5511951366861&text=Ol%C3%A1,%20vim%20pelo%20site."
                target="_blank"
                rel="noopener noreferrer"
                class="text-primary hover:underline"
              >
                +55 (11) 95136-6861
              </a>
            </div>
          </div>

          <div>
            <div class="flex gap-2">
              <Clock />
              <div class="font-bold">Atendimento</div>
            </div>

            <div>
              <div>100% Online</div>
              <div>Agendamento por WhatsApp ou formulário</div>
            </div>
          </div>

          <div class="mt-6">
            <p class="text-sm text-muted-foreground mb-3">
              Siga-nos nas redes:
            </p>
            <a
              href="https://instagram.com/camisdaalforriase"
              target="_blank"
              rel="noopener noreferrer"
              class="text-primary hover:underline"
            >
              @camisdaalforriase
            </a>
          </div>
        </div>
      </div>

      <!-- form -->
      <Card
        class="border-2"
        style="
          background: linear-gradient(
            135deg,
            #ffffff 0%,
            #f5f0eb 50%,
            #e8ddd4 100%
          );
        "
      >
        <CardHeader class="text-primary text-2xl">
          Formulário de Contato
        </CardHeader>
        <CardContent>
          <form @submit.prevent="handleSubmit" class="grid gap-4">
            <div class="flex flex-col gap-1.5">
              <Label for="name">Nome *</Label>
              <Input
                id="name"
                type="text"
                placeholder="Seu nome"
                v-model="contactForm.name"
                required
              />
            </div>

            <div class="flex flex-col gap-1.5">
              <Label for="email">Email *</Label>
              <Input
                id="email"
                type="email"
                placeholder="seu@email.com"
                v-model="contactForm.email"
                required
              />
            </div>

            <div class="flex flex-col gap-1.5">
              <Label for="subject">Serviço de Interesse</Label>

              <Select v-model="contactForm.subject">
                <SelectTrigger>
                  <SelectValue placeholder="Selecione um serviço" />
                </SelectTrigger>
                <SelectContent>
                  <SelectGroup>
                    <SelectItem value="Jornada Solar">
                      Jornada Solar
                    </SelectItem>
                    <SelectItem value="Leitura de Mapa Astral">
                      Leitura de Mapa Astral
                    </SelectItem>
                    <SelectItem value="Astro Express">
                      Astro Express
                    </SelectItem>
                    <SelectItem value="Jornada Solar Pocket">
                      Jornada Solar Pocket
                    </SelectItem>
                    <SelectItem value="Dúvida geral"> Dúvida geral </SelectItem>
                  </SelectGroup>
                </SelectContent>
              </Select>
            </div>

            <div class="flex flex-col gap-1.5">
              <Label for="message">Mensagem *</Label>
              <Textarea
                id="message"
                placeholder="Conte-nos mais sobre você e o que você busca..."
                rows="5"
                v-model="contactForm.message"
                required
              />
            </div>

            <Alert v-if="invalidInputForm" variant="destructive">
              <AlertCircle class="w-4 h-4" />
              <AlertTitle>Erro</AlertTitle>
              <AlertDescription>
                Por favor, preencha todos os campos obrigatórios.
              </AlertDescription>
            </Alert>

            <Alert v-if="successMessage" class="bg-green-50 border-green-200">
              <AlertTitle class="text-green-800">Sucesso!</AlertTitle>
              <AlertDescription class="text-green-700">
                Sua mensagem foi enviada com sucesso. Camila entrará em contato
                em breve!
              </AlertDescription>
            </Alert>

            <Button class="mt-4">Enviar mensagem</Button>
          </form>
        </CardContent>

        <CardFooter></CardFooter>
      </Card>
    </section>
  </section>
</template>
