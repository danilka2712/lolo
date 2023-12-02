<script lang="ts">
  import { afterUpdate, onMount } from "svelte";
  import { gsap } from "gsap/dist/gsap";
  import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
  import { slide } from "svelte/transition";
  import { quintOut } from "svelte/easing";

  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);

    gsap.to(".box", {
      scrollTrigger: {
        trigger: ".trigger",
        start: "top 90%",
        scrub: true,
      },
      y: -100,
    });

    gsap.to(".text", {
      scrollTrigger: {
        trigger: ".trigger",
        start: "top 70%",
        scrub: true,
      },
      opacity: 0,
    });
  });

  let m = { x: 0, y: 0 };

  function handleMousemove(event) {
    m.x = event.offsetX;
    m.y = event.offsetY;
    setTimeout(() => {
      imageHide = true;
    }, 100);
  }
  let imageHide = false;
</script>

<div class=" sm:mx-auto xl:max-w-7xl sm:max-w-6xl mx-4">
  <div
    class=" absolute hidden sm:flex -top-36 -rotate-12 items-center justify-center ml-auto mr-auto left-0 right-80 z-0"
  >
    <img class="w-72 box rounded-xl" src="preview-7-p-1080.png" alt="" />
  </div>
  <div class=" absolute hidden sm:flex bottom-4 -right-44 -rotate-12 z-0">
    <img class="w-72 box rounded-xl" src="preview-3-p-1080.png" alt="" />
  </div>
  <div class=" absolute hidden sm:flex bottom-56 -left-44 -rotate-12 z-0">
    <img
      class="w-72 box rounded-xl"
      src="https://assets.website-files.com/64d1a3f882efd7fa3c726596/64dd44d77f953bd5852e5c53_Brand-007.webp"
      alt=""
    />
  </div>
  <div class="flex flex-col sm:mt-32 mt-20 relative z-10">
    <h1
      class="lg:text-9xl sm:text-7xl text-4xl sm:-ml-2 font-extrabold uppercase"
    >
      Из беспорядка <br /> в гармонию
    </h1>
    <p
      class=" sm:text-3xl text-xl sm:w-3/5 my-8 text-white/90 whitespace-normal"
    >
      Мы занимаемся разработкой, проектированием, дизайном и продвижением
      уникальных цифровых продуктов, веб-сайтов, брендов и опыта.
    </p>
    <button class="border text p-2 px-6 w-fit rounded-full border-white/25"
      >Оставить заявку</button
    >
  </div>
  <div
    class="trigger flex justify-between mt-28 border-t py-16 border-white/10 w-full"
  >
    <div class="flex w-full justify-between sm:gap-20">
      <img
        class="sm:w-72 hidden w-32"
        src="https://toproi.ru/wp-content/uploads/2020/05/mcedelvise-1.svg
        "
        alt=""
      />
      <img
        class="sm:w-72 hidden w-32"
        src="https://toproi.ru/wp-content/uploads/2019/08/inrosko-logo.svg"
        alt=""
      />
      <img
        class="sm:w-72 sm:flex w-36"
        src="https://toproi.ru/wp-content/uploads/2019/08/inrosko-logo.svg"
        alt=""
      />
      <img
        class="sm:w-72 sm:flex w-36"
        src="https://toproi.ru/wp-content/uploads/2019/08/inrosko-logo.svg"
        alt=""
      />
    </div>
  </div>
  <div
    role="button"
    tabindex="0"
    on:mouseleave={() => (imageHide = false)}
    class="flex .scroll-trigger-ready__worm-wrap flex-col sm:justify-center sm:items-center relative sm:my-20 my-10 sm:h-96"
  >
    {#if imageHide}
      <img
        on:mouseleave={() => (imageHide = false)}
        transition:slide|local={{
          delay: 0,
          duration: 200,
          easing: quintOut,
          axis: "x",
        }}
        class="w-72 absolute rounded-xl"
        src="https://assets.website-files.com/64d293054a05b986902db3e3/64e53bb70695f0b7c417621f_packaging-box-tape-mockup-v4-isometric-1-2420x1615-p-800.jpeg"
        style="left: {m.x}px; top: {m.y - 36}px;"
        alt=""
      />
    {/if}
    <p
      on:mousemove={handleMousemove}
      class="sm:text-center sm:w-5/6 tracking-wide leading-tight sm:text-5xl text-xl cursor-default"
    >
      С момента начала своей карьеры фрилансера в 2014 году я сотрудничал с
      самыми разными клиентами, от процветающих стартапов до солидных
      корпораций.
    </p>
    <button
      class="border sm:flex p-2 px-6 w-fit rounded-full border-white/25 mt-10"
      >Оставить заявку</button
    >
  </div>
  <div class="mt-32 mb-20 relative">
    <p>Кейсы</p>

    <hr class="border-white/10 my-4" />

    <div class="my-14 flex sm:flex-row flex-col justify-between">
      <div class="sm:w-2/6 flex flex-col gap-6">
        <p class="sm:text-3xl text-xl">
          Создали удобный сайт для компании по демонтажу сооружений.
        </p>
        <div class="flex flex-wrap gap-4 pb-6 sm:pb-0">
          <span
            class=" border border-white/40 p-2 px-4 rounded-full w-fit text-sm"
            >Популярные фреймворки</span
          >
          <span
            class=" border border-white/40 p-2 px-4 rounded-full w-fit text-sm"
            >Front-End</span
          >

          <span
            class=" border border-white/40 p-2 px-4 rounded-full w-fit text-sm"
          >
            Back-End</span
          >
        </div>
      </div>

      <div class="sm:w-1/2">
        <img
          class=" rounded-xl sm:h-96 w-full object-cover"
          src="Group.png"
          alt=""
        />
      </div>
    </div>
    <hr class="border-white/10 my-4" />

    <div class="my-14 flex sm:flex-row flex-col justify-between">
      <div class="sm:w-2/6 flex flex-col gap-6 pb-6 sm:pb-0">
        <p class="sm:text-3xl text-xl">
          SEO продвижение интернет-магазина лодок и моторов
        </p>
        <div class="flex flex-wrap gap-4">
          <span
            class=" border border-white/40 p-2 px-4 rounded-full w-fit text-sm"
            >Увеличение трафика</span
          >
          <span
            class=" border border-white/40 p-2 px-4 rounded-full w-fit text-sm"
            >Снижение затрат</span
          >
        </div>
      </div>
      <div class="sm:w-1/2">
        <img
          class=" rounded-xl sm:h-96 h-60 w-full object-cover"
          src="pres-device-mockups-_image1-9.webp"
          alt=""
        />
      </div>
    </div>
    <hr class="border-white/10 my-4" />

    <div class="my-14 flex sm:flex-row flex-col justify-between">
      <div class="sm:w-2/6 flex flex-col gap-6 pb-6 sm:pb-0">
        <p class="sm:text-3xl text-xl">
          Оптимизировали серверную часть для министерства здравоохранения
        </p>
        <div class="flex flex-wrap gap-4">
          <span
            class=" border border-white/40 p-2 px-4 rounded-full w-fit text-sm"
            >Увеличили производительность</span
          >
          <span
            class=" border border-white/40 p-2 px-4 rounded-full w-fit text-sm"
            >Защита от DDoS</span
          >
        </div>
      </div>
      <div class="sm:w-1/2">
        <img
          class=" rounded-xl sm:h-96 w-full object-cover"
          src="preview-8-v1.webp"
          alt=""
        />
      </div>
    </div>
    <hr class="border-white/10 my-4" />
  </div>

  <div class="flex my-12 hidden">
    <p class="">Соцсети <br /> и новости</p>
    <div class="ml-20 flex gap-12">
      <a class="text-5xl font-black" href="/">VK</a>

      <a class="text-5xl font-black" href="/">INSTAGRAM</a>

      <a class="text-5xl font-black" href="/">FACEBOOK</a>
    </div>
  </div>

  <div class="  grid sm:grid-cols-4 grid-cols-2 sm:gap-10 gap-4 my-24 mb-44">
    <div class="flex flex-col gap-4">
      <img
        class=" rounded-xl h-80 object-cover"
        src="https://assets.website-files.com/64d293054a05b986902db3e3/64e53bb70695f0b7c417621f_packaging-box-tape-mockup-v4-isometric-1-2420x1615-p-800.jpeg"
        alt=""
      />
      <p class="text-lg">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Inventore, iste
        porro ea cumque incidunt earum harum dolores enim, eveniet est.
      </p>
    </div>
    <div class="flex flex-col gap-4">
      <img
        class=" rounded-xl h-80 object-cover"
        src="https://assets.website-files.com/64d293054a05b986902db3e3/64e53bb70695f0b7c417621f_packaging-box-tape-mockup-v4-isometric-1-2420x1615-p-800.jpeg"
        alt=""
      />
      <p class="text-lg">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Inventore, iste
        porro ea cumque incidunt earum harum dolores enim
      </p>
    </div>
    <div class="flex flex-col gap-4">
      <img
        class=" rounded-xl h-80 object-cover"
        src="https://assets.website-files.com/64d293054a05b986902db3e3/64e53bb70695f0b7c417621f_packaging-box-tape-mockup-v4-isometric-1-2420x1615-p-800.jpeg"
        alt=""
      />
      <p class="text-lg">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Inventore, iste
        porro ea cumque incidunt earum harum dolores enim,
      </p>
    </div>
    <div class="flex flex-col gap-4">
      <img
        class=" rounded-xl h-80 object-cover"
        src="https://assets.website-files.com/64d293054a05b986902db3e3/64e53bb70695f0b7c417621f_packaging-box-tape-mockup-v4-isometric-1-2420x1615-p-800.jpeg"
        alt=""
      />
      <p class="text-lg">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Inventore, iste
        porro ea cumque incidunt earum harum dolores enim
      </p>
    </div>
  </div>
  <div class="my-12 flex flex-col">
    <p class="">Контакты</p>
    <hr class="border-white/10 my-4" />

    <div class="flex my-20 flex-col gap-10 sm:justify-center sm:items-center">
      <span
        class=" tracking-wide font-bold leading-tight text-2xl sm:text-5xl sm:text-center"
        >Оставьте заявку <br /> или свяжитесь с нами <br /> по указанным контактам</span
      >
      <div
        class="flex flex-col sm:justify-center gap-2 text-xl sm:items-center"
      >
        <span class=" font-light text-white/75">telegram</span>
        <a href="/" class="font-bold">@pitcher_dev</a>
      </div>
      <div
        class="flex flex-col text-xl sm:justify-center gap-2 sm:items-center"
      >
        <span class=" font-light text-white/75">e-mail</span>
        <a href="/" class="font-bold">pitcher_dev@yandex.ru</a>
      </div>
      <button class=" border border-white/40 rounded-full p-2 px-4"
        >Заполнить форму</button
      >
    </div>
  </div>
  <hr class="border-white/10 my-4" />
</div>
