<script>

  import { blur } from "svelte/transition";

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


<h1>Blur</h1>

<section>

  {#each landscapes as landscape, i}
    {#if activeIndex === i}
      <img
        transition:blur={{amount: 100}}
        src={landscape}
        width="1280"
        height="720"
        alt="dark souls landscape" />
    {/if}
  {/each}

</section>

<style>
  
  section {
    display: flex;
    justify-content: center;
    height: 720px;
  }

  section img {position: absolute}
</style>