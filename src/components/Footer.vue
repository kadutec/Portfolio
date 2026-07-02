<template>
  <footer class="footer" id="footer">
    <div class="footer-contact">
        <span class="footer-subtitle">Contato</span>

        <h3>Vamos conversar?</h3>

        <p>
            Estou sempre aberto a novas oportunidades, colaborações e boas conversas
            sobre desenvolvimento de software, arquitetura e tecnologia. Se você tem
            uma ideia, projeto ou apenas gostaria de trocar experiências, será um
            prazer conversar.
        </p>

        <div class="footer-social">
            <a
            href="https://github.com/kadutec"
            target="_blank"
            aria-label="GitHub"
            >
            <i class="fab fa-github"></i>
            </a>

            <a
            href="https://linkedin.com/in/carlos-eduardo-nogueira-5762a1251/"
            target="_blank"
            aria-label="LinkedIn"
            >
            <i class="fab fa-linkedin"></i>
            </a>

            <a
            href="mailto:kadutec27@gmail.com"
            aria-label="E-mail"
            >
            <i class="fas fa-envelope"></i>
            </a>
        </div>
    </div>

    <div class="footer-bottom">
      © {{ year }} Carlos Nogueira. Todos os direitos reservados.
    </div>
  </footer>
</template>

<script setup>
const year = new Date().getFullYear()
</script>