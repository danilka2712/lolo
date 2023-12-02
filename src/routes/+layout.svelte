<script>
  import "../app.postcss";
</script>

<header
  class="flex justify-between xl:max-w-7xl max-w-6xl sm:mx-auto my-6 mx-4 items-center relative z-10"
>
  <ul class="hidden lg:flex">
    <li class="flex gap-10">
      <a href="/">Главная</a>
      <a href="/">О нас</a>
    </li>
  </ul>
  <a class="w-fit" href="/">
    <img src="logotype.svg" class="w-16" alt="logotype" />
  </a>
  <ul class="hidden lg:flex">
    <li class="flex gap-10">
      <a href="/">Кейсы</a>
      <a href="/">Контакты</a>
    </li>
  </ul>
</header>

<main class="">
  <slot />
</main>

<footer
  class="flex justify-between xl:max-w-7xl max-w-6xl sm:mx-auto my-6 mx-4 items-center relative z-10"
>
  <a class="w-fit" href="/">
    <img src="logotype.svg" class="w-16" alt="logotype" />
  </a>

  <ul class="hidden">
    <li class="flex gap-10">
      <a href="/">Главная</a>
      <a href="/">О нас</a>
      <a href="/">Кейсы</a>
      <a href="/">Контакты</a>
    </li>
  </ul>
</footer>
