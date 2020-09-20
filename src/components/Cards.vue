<template>
  <div id="cards">
    <!-- CARD DE MARCAS -->
    <div class="card-brands">
      <div class="card-header">
        <header class="header-content">
          <h2 class="card-title">Marcas</h2>
        </header>
      </div>
      <hr />
      <div class="card-content">
        <h3>Marca</h3>
        <hr />
        <!-- MOSTRANDO TODAS AS MARCAS COM OS SEUS RESPECTIVOS BOTÕES E CHAMANDO A FUNÇÃO DE MOSTRAR OS MODELOS COM O CLICK DO BOTÃO -->
        <div class="item" v-for="brand in brands" :key="brand.codigo">
          <p>{{ brand.nome.toLowerCase() }}</p>
          <hr />
          <button v-on:click="getModels(brand.codigo)">Ver modelos</button>
        </div>
      </div>
    </div>

    <!-- CARD DE MODELOS -->
    <div class="card-models">
      <div class="card-models-header">
        <header class="header-models-content">
          <h2 class="card-models-title">Modelos</h2>
        </header>
      </div>
      <hr />
      <div class="card-models-content">
        <h3>Modelo</h3>
        <hr />
        <!-- FAZENDO UM FOR PARA CONSEGUIR MOSTRAR TODOS OS MODELOS COM O CLICK DO BOTÃO -->
        <div class="item-models" v-for="model in models" :key="model.codigo">
          <p>{{ model.nome.toLowerCase() }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    // CRIANDO OS DOIS ARRAYS QUE SERÃO USADOS
    return {
      brands: null,
      models: null,
    };
  },
  methods: {
    // CRIANDO O MÉTODO PARA PEGAR E MOSTRAR AS MARCAS
    getBrands() {
      fetch("https://parallelum.com.br/fipe/api/v1/carros/marcas")
        .then((response) => response.json())
        .then((response) => {
          this.brands = response;
        });
    },
    // CRIANDO O MÉTODO QUE IRÁ RECEBER O ID DA MARCA E MOSTRARÁ OS MODELOS DA RESPECTIVA MARCA
    getModels(id) {
      fetch(`https://parallelum.com.br/fipe/api/v1/carros/marcas/${id}/modelos`)
        .then((response) => response.json())
        .then((response) => {
          this.models = response.modelos;
        });
    },
  },
  created() {
    // AO CRIAR A TELA, O MÉTODO DE MOSTRAR AS MARCAS SERÁ IMEDIATAMENTE INICIADO
    this.getBrands();
  },
};
</script>

<style>
/* CSS DAS MARCAS */
#cards .card-brands {
  background: var(--color-header-footer);
  margin-top: 2.4rem;
  overflow: hidden;
  border-radius: 0.8rem;
  border: 1px solid var(--color-table-border);
  box-shadow: 3px 3px 7px var(--color-shadow);
}
#cards .card-brands .card-header {
  color: var(--color-button);
  padding: 2.2rem 2rem;
  background: var(--color-header-card);
  border-bottom: 1px solid var(--color-table-border);
}

#cards .card-brands hr {
  margin: 2.4rem 1.8rem;
  border: 1px solid var(--color-table-border);
}

#cards .card-brands .card-content h3 {
  margin-left: 3.2rem;
}

#cards .card-brands .card-content .item hr {
  border: none;
}

#cards .card-brands .card-content .item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 2rem 3.2rem;
  border-bottom: 2px solid var(--color-table-border);
}

#cards .card-brands .card-content .item p {
  text-transform: capitalize;
}

#cards .card-brands .card-content .item + .item {
  border-bottom: 2px solid var(--color-table-border);
}

#cards .card-brands .card-content .item:last-child {
  border: 0;
}

#cards .card-brands .card-content .item button {
  border: 0;
  background: none;
  font: 700 1.6rem Poppins;
  color: var(--color-button);
  transition: 0.2s;
  cursor: pointer;
}

#cards .card-brands .card-content .item button:hover,
#cards .card-brands .card-content .item button:focus {
  color: var(--color-activate-button);
}

/* CSS dos Modelos */
.card-models {
  background: var(--color-header-footer);
  margin-top: 2.4rem;
  overflow: hidden;
  border-radius: 0.8rem;
  border: 1px solid var(--color-table-border);
  box-shadow: 3px 3px 7px var(--color-shadow);
}
.card-models .card-models-header {
  color: var(--color-button);
  padding: 2.2rem 2rem;
  background: var(--color-header-card);
  border-bottom: 1px solid var(--color-table-border);
}

.card-models hr {
  margin: 2.4rem 1.8rem;
  border: 1px solid var(--color-table-border);
}

.card-models .card-models-content h3 {
  margin-left: 3.2rem;
}

.card-models .card-models-content .item-models {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 2rem 3.2rem;
  border-bottom: 2px solid var(--color-table-border);
}

.card-models .card-models-content .item-models button {
  border: 0;
  background: none;
  font: 700 1.6rem Poppins;
  color: var(--color-button);
  transition: 0.2s;
  cursor: pointer;
}

.card-models .card-models-content .item-models p {
  text-transform: capitalize;
  padding: 1.6rem 0;
  margin-top: -1.2rem;
}

.card-models .card-models-content .item-models + .item-models {
  border-bottom: 2px solid var(--color-table-border);
}

.card-models .card-models-content .item-models:last-child {
  border: 0;
}

.card-models .card-models-content .item-models button:hover,
.card-models .card-models-content .item-models button:focus {
  color: var(--color-activate-button);
}

@media (min-width: 700px) {
  .card-brands .card-content .item {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .card-models .card-models-content .item-models {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}

@media (min-width: 1800px) {
  .card-brands .card-content .item {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .card-brands .card-content .item button {
    margin-right: 90.4rem;
  }

  .card-models .card-models-content .item-models {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .card-models .card-models-content .item-models button {
    margin-right: 90.4rem;
  }
}
</style>
