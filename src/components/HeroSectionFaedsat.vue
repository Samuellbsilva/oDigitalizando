<template>
  <main class="flex flex-col min-h-screen created fade-in">
    <!-- Hero Section -->
    <section class="hero-section fadeElement">
      <CarouselInit class="w-full max-w-screen-xl mx-auto fadeInAnimation" />
    </section>

    <!-- Intro Section -->
    <section class="back fadeElement flex flex-col sm:justify-center pt-0 lg:text-center">
      <div class="w-full flex flex-col items-center gap-8 py-10 px-6 sm:px-20">
        <div class="w-full flex flex-col lg:flex-row justify-between items-center gap-8">
          <div class="flex-1 text-left">
            <h1 class="colortext2 text-4xl sm:text-6xl font-bold leading-tight mb-4">
              Prepare-se para explorar o universo digital
            </h1>
            <h3 class="colortext2 text-lg sm:text-2xl">
              Sua presença online começa aqui.
            </h3>
          </div>
          <div class="flex-1">
            <img src="/Imgs/Astronauta.png" alt="Astronauta" class="w-full h-auto object-contain" />
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section class="created2 colortext2 py-16 px-6 sm:px-20 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 fadeElement">
      <ServiceCard icon="code" title="Criação de Sites" text="Criamos sites modernos e funcionais, adaptados às necessidades do seu negócio. De landing pages a plataformas completas, ajudamos a sua marca a ter presença online com soluções personalizadas." />
      <ServiceCard icon="smart_toy" title="Assistentes de IA" text="Integre assistentes virtuais inteligentes em sua plataforma. Automatize processos, melhore a experiência do usuário e forneça respostas rápidas e eficientes com soluções baseadas em inteligência artificial." />
      <ServiceCard icon="bar_chart" title="Gestão de Tráfego" text="Gerencie e otimize o tráfego do seu site. Oferecemos estratégias de marketing digital e campanhas pagas para aumentar sua visibilidade online e atrair mais clientes para o seu negócio." />
      <ServiceCard icon="group" title="Consultoria Digital" text="Nossos especialistas em tecnologia e marketing digital estão prontos para ajudar sua empresa a se destacar no mercado online. Oferecemos consultoria personalizada para transformar seus processos e otimizar resultados." />
    </section>

    <!-- Benefits Section -->
    <section class="flex flex-col sm:flex-row items-center justify-between py-16 px-6 sm:px-20 fadeElement">
      <div class="flex-1 mb-10 sm:mb-0">
        <h1 class="colortext2 text-3xl sm:text-5xl font-bold mb-6">
          Transformamos ideias em<br />presença digital
        </h1>
        <ul class="space-y-4">
          <BenefitItem text="Sites otimizados com SEO para atrair e converter leads." />
          <BenefitItem text="Aumente a visibilidade do seu site com estratégias de tráfego." />
          <BenefitItem text="Estruturamos sua marca no digital com e-mails profissionais." />
          <BenefitItem text="Automatize processos com assistentes virtuais." />
        </ul>
      </div>
      <div class="flex-1">
        <img src="/Imgs/PrintCliente.png" class="w-full sm:w-3/4 rounded-lg shadow-lg" alt="Print do Cliente" />
      </div>
    </section>

    <!-- Contact Section -->
    <section class="created2 py-10 fadeElement">
      <EmailJS />
    </section>
  </main>
</template>

<script setup>
import CarouselInit from "./CarouselInit.vue";
import EmailJS from "./EmailJS.vue";

// Subcomponents
const ServiceCard = defineComponent({
  props: ['icon', 'title', 'text'],
  template: `
    <div class="flex flex-col items-start gap-4 p-4 border border-gray-700 rounded-lg shadow-md hover:shadow-xl transition-all duration-300">
      <span class="material-symbols-outlined text-4xl text-primary">{{ icon }}</span>
      <h3 class="text-xl font-semibold">{{ title }}</h3>
      <p class="text-base text-justify">{{ text }}</p>
    </div>
  `
});

const BenefitItem = defineComponent({
  props: ['text'],
  template: `
    <li class="flex items-start gap-3">
      <span class="material-symbols-outlined text-2xl text-green-500">check</span>
      <span class="text-base sm:text-lg colortext2">{{ text }}</span>
    </li>
  `
});
</script>

<style lang="scss" scoped>
@import "../styles/_mixins.scss";

main {
  animation: fadeInUp 1s ease forwards;
}

.back {
  background-image: url("/Imgs/Textura.png");
  background-size: cover;
  background-position: center;
  background-blend-mode: multiply;
}

.created {
  background: linear-gradient(to bottom, #172243, #000000);
}

.created2 {
  background: linear-gradient(to bottom, #000000, #172243);
}

.colortext2 {
  color: #cfc8bc;
}

.fadeElement {
  opacity: 0;
  transition: opacity 1.5s ease, transform 1.5s ease;
  transform: translateY(20px);
}

.fade-in {
  opacity: 1 !important;
  transform: translateY(0) !important;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.material-symbols-outlined {
  font-variation-settings: 'FILL' 1;
}
</style>
