<script>
  import "../app.postcss";
</script>

<header
  class="flex justify-between xl:max-w-7xl max-w-6xl mx-auto my-6 items-center relative z-10"
>
  <ul>
    <li class="flex gap-10">
      <a href="/">Главная</a>
      <a href="/">О нас</a>
    </li>
  </ul>
  <a class="w-fit" href="/">
    <img src="logotype.svg" class="w-16" alt="logotype" />
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

<footer
  class="flex justify-between gap-4 xl:max-w-7xl max-w-6xl mx-auto my-24 items-center relative z-10"
>
  <a class="w-fit" href="/">
    <img src="logotype.svg" class="w-16" alt="logotype" />
  </a>

  <ul>
    <li class="flex gap-10">
      <a href="/">Главная</a>
      <a href="/">О нас</a>
      <a href="/">Кейсы</a>
      <a href="/">Контакты</a>
    </li>
  </ul>
</footer>
