<script>
  import { onMount } from 'svelte'

  let canvas;

  const Node = ({
    append
  }) => {
    const no = document.createElement('div');
    no.setAttribute('class', 'w-full h-12 rounded-md border flex items-center p-2 cursor-pointer');
    no.textContent = 'Node';
    if (append) append.appendChild(no);
    else document.appendChild(no);
  }

  onMount(() => {
    Node({ append: canvas });
    Node({ append: canvas });
    Node({ append: canvas });
    Node({ append: canvas });
    Node({ append: canvas });
    Node({ append: canvas });
  });
</script>

<main class="relative">
  <header class="w-full h-16 bg-slate-800 mb-4"></header>
  <div bind:this={canvas} class="relative w-full flex items-center flex-col gap-2 px-96"></div>
</main>

<style>
  main {
    width: 100vw;
    height: 100vh;
  }
</style>
