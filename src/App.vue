<template>
  <div id="home-page" class="container">
    <PageHeader />
    <h2 class="title">Veículos</h2>
    <div class="cards" id="page-content">
      <Cards />
    </div>
    <Footer />
  </div>
</template>

<script>
import PageHeader from "@/components/PageHeader.vue";
import Cards from "@/components/Cards.vue";
import Footer from "@/components/Footer.vue";
export default {
  components: {
    PageHeader,
    Cards,
    Footer,
  },
};
</script>

<style>
#home-page {
  width: 100vw;
  height: 100vh;
}

.cards {
  padding: 1.4rem 2.4rem;
}

#page-content {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.title {
  font: 500 3.4rem Poppins;
  margin-top: 3.4rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

@media (min-width: 700px) {
  #home-page {
    max-width: 2000px;
  }

  .cards {
    padding: 1.4rem 4.4rem;
  }

  .title {
    font: 500 4.4rem Poppins;
    display: flex;
    align-items: flex-start;
    justify-content: flex-start;
    margin-left: 2.4rem;
    margin-top: 1.8rem;
  }
}
</style>
