<template>
  <header class="page-header">
    <div class="top-bar-container">
      <p>Navita</p>
    </div>
  </header>
</template>

<style>
.page-header {
  display: flex;
  flex-direction: column;
  background: var(--color-header-footer);
  box-shadow: 3px 3px 7px var(--color-shadow);
}

.page-header .top-bar-container {
  width: 90%;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  margin-left: 3.3rem;
  align-items: center;
  color: var(--color-activate-button);
  padding: 1.6rem 0;
}

.page-header .top-bar-container p {
  font: 700 2.4rem Archivo;
}

@media (min-width: 700px) {
  .page-header {
    height: 60px;
  }

  .page-header .top-bar-container {
    max-width: 1100px;
  }
}
</style>
