<script>

  import { slide, scale, fly, fade, blur } from "svelte/transition";
  import { quintOut } from "svelte/easing";

  export let effect;

  let landscapes = [
    "https://i.postimg.cc/15ywXQZP/Dark-Souls-1.jpg",
    "https://i.postimg.cc/Bn6F5B6V/Dark-Souls-2.jpg",
    "https://i.postimg.cc/QxS5WyX7/Dark-Souls-3.jpg"
  ];

  let activeIndex = 0;

  setInterval(() => {
    let next = activeIndex + 1;
    activeIndex = next == 3 ? 0 : next;
  }, 1500);

</script>

<h1>{effect.type}</h1>

<section>

  {#each landscapes as landscape, i}
    {#if activeIndex === i}
      {#if effect.type == 'slide'}
        <img
          transition:slide={effect.params}
          src={landscape}
          alt="dark souls landscape {effect.type}" />
      {:else if effect.type == 'scale'}
        <img
          transition:scale={effect.params}
          src={landscape}
          alt="dark souls landscape" />
      {:else if effect.type == 'fly'}
        <img
          transition:fly={effect.params}
          src={landscape}
          alt="dark souls landscape" />
      {:else if effect.type == 'fade'}
        <img
          transition:fade={effect.params}
          src={landscape}
          alt="dark souls landscape" />
      {:else if effect.type == 'blur'}
        <img
          transition:blur={effect.params}
          src={landscape}
          alt="dark souls landscape" />
      {/if}
    {/if}
  {/each}

</section>

<style>
  
  section {
    display: flex;
    justify-content: center;
    height: 720px;
  }

  section img {
    position: absolute;
    width: 1280px;
    height: 720px;
  }
</style>