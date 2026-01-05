# 📸 Guia de Configuração do Feed do Instagram

Este guia explica como configurar o feed do Instagram para aparecer automaticamente no site.

## 🎯 Opção 1: Elfsight (Recomendado - Gratuito e Fácil)

### Passo a Passo:

1. **Acesse o Elfsight**
   - Vá para: https://elfsight.com/pt/instagram-feed-instashow/
   - Clique em "Criar Widget Gratuito"

2. **Crie uma conta**
   - Use seu email ou faça login com Google/Facebook
   - É gratuito para uso básico

3. **Conecte sua conta do Instagram**
   - Clique em "Conectar Instagram"
   - Faça login com a conta @camisdaalforriase
   - Autorize o acesso

4. **Personalize o Widget**
   - Escolha o layout (grid, carousel, etc)
   - Ajuste as cores para combinar com o site (#722a24 e #d1c5ba)
   - Defina quantos posts mostrar (recomendado: 6-9)
   - Configure o tamanho das imagens

5. **Copie o código do widget**
   - O código terá este formato:
   ```html
   <div class="elfsight-app-XXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX"></div>
   ```

6. **Cole no componente**
   - Abra: `src/components/InstagramFeed.vue`
   - Substitua a div com classe `elfsight-app-placeholder` pelo código do widget
   - O script do Elfsight já está carregado automaticamente

### Exemplo do código final:

```vue
<template>
  <section class="container py-24 sm:py-32" style="background: linear-gradient(135deg, #d1c5ba 0%, #f5f0eb 50%, #d1c5ba 100%);">
    <!-- ... título ... -->
    
    <div class="flex justify-center">
      <div class="w-full max-w-5xl">
        <!-- Cole aqui o código do Elfsight -->
        <div class="elfsight-app-XXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX"></div>
      </div>
    </div>
  </section>
</template>
```

---

## 🎯 Opção 2: SnapWidget (Alternativa)

### Passo a Passo:

1. **Acesse o SnapWidget**
   - Vá para: https://snapwidget.com/
   - Clique em "Get Started Free"

2. **Conecte sua conta do Instagram**
   - Faça login com @camisdaalforriase
   - Autorize o acesso

3. **Configure o widget**
   - Escolha o layout e personalização
   - Copie o código iframe gerado

4. **Cole no componente**
   - Substitua o conteúdo da seção pelo iframe do SnapWidget

---

## 🎯 Opção 3: API do Instagram (Avançado)

Se você quiser mais controle, pode usar a API oficial do Instagram:

1. **Criar App no Facebook Developer**
   - Acesse: https://developers.facebook.com/
   - Crie um novo app
   - Configure o Instagram Basic Display API

2. **Obter Token de Acesso**
   - Siga o processo de autenticação OAuth
   - Obtenha o token de acesso

3. **Implementar no componente**
   - Use fetch para buscar posts da API
   - Renderize os posts no componente

**Nota:** Esta opção é mais complexa e requer conhecimento técnico avançado.

---

## ✅ Verificação

Após configurar, verifique:

1. O feed aparece no site?
2. As imagens carregam corretamente?
3. Os links direcionam para o Instagram?
4. O design combina com o site?

---

## 🆘 Problemas Comuns

### Feed não aparece
- Verifique se o código do widget está correto
- Confirme que o script do Elfsight está carregando (verifique o console do navegador)
- Certifique-se de que a conta do Instagram está conectada

### Imagens não carregam
- Verifique a conexão com o Instagram
- Confirme que a conta não está privada
- Tente desconectar e reconectar a conta

### Erro 404
- O widget pode ter expirado, recrie-o
- Verifique se a conta do Instagram ainda está ativa

---

## 📝 Notas Importantes

- **Gratuito vs Pago**: A maioria dos serviços oferece planos gratuitos com limitações (número de posts, atualizações, etc)
- **Atualização**: O feed pode demorar alguns minutos para atualizar após um novo post
- **Privacidade**: Se a conta do Instagram for privada, o feed pode não funcionar

---

## 🎨 Personalização de Cores

Para combinar com o design do site, use estas cores no widget:

- **Cor Principal**: `#722a24` (vermelho escuro)
- **Cor Secundária**: `#d1c5ba` (bege claro)
- **Cor de Fundo**: `#f5f0eb` (bege suave)

---

## 📞 Suporte

Se tiver problemas:
- Elfsight: https://elfsight.com/support/
- SnapWidget: https://snapwidget.com/support
- Ou consulte a documentação oficial de cada serviço

