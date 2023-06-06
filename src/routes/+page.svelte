<script>
  import { onMount } from 'svelte'
  import form from './data.js';

  let canvas;
  let data = [1, 2, 3, 4, 5, 6];
  let isRoot = true;
  let currentObj = form;

  const setLevel = (key) => {
      currentObj = currentObj[key];
      isRoot = false;
      console.log(currentObj);
  }

  onMount(() => {
  });
</script>

<main class="relative">
  <header class="w-full h-16 bg-slate-800 mb-4"></header>
  <h1 class="mx-4 mb-4 text-md font-semibold text-gray-400">
     <span class="font-semibold mr-2 text-gray-800">Location:</span>
     MMT > Stakeholder > beneficiaries >
     <span class="text-semibold text-gray-800">name</span>
    </h1>
  <div bind:this={canvas} class="relative w-full flex gap-2 px-4">
    <div class="flex flex-col w-6/12 gap-2">
        {#each Object.keys(currentObj) as key}
            <div class="w-full h-12 rounded-md border flex items-center p-2 cursor-pointer" on:click={() => setLevel(key)}>
                <h1 class="font-semibold">{key}</h1>
            </div>
        {/each}
    </div>
    <div class="w-6/12 rounded-md border flex flex-col p-2">
        <h1 class="font-semibold text-md">Properties:</h1>
        {#if !isRoot}
            <ul>
                {#each Object.keys(currentObj) as prop} 
                    <li>{prop}</li>
                {/each}
            </ul>
        {/if}
    </div>
  </div>
</main>

<style>
  main {
    width: 100vw;
    height: 100vh;
  }
</style>
