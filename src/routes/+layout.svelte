<script>
  import "../app.postcss";
</script>

<header class="flex justify-between max-w-7xl mx-auto my-6 items-center">
  <ul>
    <li class="flex gap-10">
      <a href="/">Главная</a>
      <a href="/">О нас</a>
    </li>
  </ul>
  <a class="w-fit" href="/">
    <img src="logotype.svg" class="w-16 relative z-10" alt="logotype" />
  </a>
  <ul>
    <li class="flex gap-10">
      <a href="/">Кейсы</a>
      <a href="/">Контакты</a>
    </li>
  </ul>
</header>

<main>
  <slot />
</main>
