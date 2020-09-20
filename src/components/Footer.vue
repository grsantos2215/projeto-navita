<template>
  <footer class="page-footer">
    <div class="footer-bar-container">
      <p>Copyright © Navita 2020</p>
    </div>
  </footer>
</template>

<style>
.page-footer {
  display: flex;
  flex-direction: column;
  background: var(--color-header-footer);
  box-shadow: 3px 3px 7px var(--color-shadow);
}

.page-footer .footer-bar-container {
  width: 90%;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  color: var(--color-text);
  padding: 2rem 0;
}

.page-footer .footer-bar-container p {
  font: 500 1.4rem Poppins;
}

@media (min-width: 700px) {
  .page-footer {
    height: 60px;
  }

  .page-footer .footer-bar-container {
    max-width: 1100px;
  }
}
</style>
