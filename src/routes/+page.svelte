<script lang="ts">
  let gifs: string[] = [
    "/bear.gif",
    "/computer.gif",
    "/rainbow-star.gif",
    "/skull.gif",
    "/spin.gif",
    "/star.gif",
    "/tv.gif",
  ]

  let image: string = "/star.gif"

  function onKeyDown(e: KeyboardEvent) {
    if (e.keyCode === 32) {
      image = gifs[Math.floor((Math.random() * gifs.length))]
    }
  }


</script>

<div class="bg-zinc-900 justify-item-center flex flex-col w-1/3 mt-6 p-4 pl-6 pt-4 pb-8 pt-8 ml-6 rounded-lg shadow">
  <h1 class="text-4xl text-slate-100 font-bold rounded-lg"><img class="inline mb-1 rounded-lg" src={image} height="48" width="48"/>&nbsp;starrybomp <h2 class="text-2xl text-slate-300 rounded-lg font-normal inline">he/they</h2></h1>
  <h2 class="text-2xl text-slate-200">Hello, I make, play, and occasionally stream games :)</h2>

  <h1 class="text-3xl mt-6 text-slate-100 font-bold rounded-lg">Contact</h1>
  <div class="mt-2 flex flex-row gap-2 containter grid grid-cols-4">
    <button class="text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-500 shadow">Discord</button>
    <button class="text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-500 shadow">Email</button>
    <button class="text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-500 shadow">Twitter</button>
    <button class="text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-500 shadow">Twitch</button>
    <button class="text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-500 shadow">YouTube</button>
    <button class="text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-500 shadow">GitHub</button>
    <button class="text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-500 shadow">Steam</button>
  </div>
</div>

<svelte:window on:keydown|preventDefault={onKeyDown} />