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

<div class="bg-zinc-900 flex md:w-1/2 lg:w-1/3 mt-6 p-4 pl-8 pr-12 pt-4 pb-10 pt-8 ml-6 mr-6 rounded-lg shadow justify-items-center mx-auto flex-col">
  <h1 class="text-4xl text-slate-100 font-bold rounded-lg"><img alt="fun little icon" class="inline mb-1 rounded-lg" src={image} height="48" width="48"/>&nbsp;starrybomp <h2 class="text-2xl text-slate-300 rounded-lg font-normal inline">he/they</h2></h1>
  <h2 class="text-2xl text-slate-200">Hello, I make, play, and occasionally stream games :)</h2>

  <h1 class="text-3xl mt-6 text-slate-100 font-bold rounded-lg">Contact</h1>
  <div class="mt-2 flex flex-row gap-2 containter grid xl:grid-cols-3 sm:grid-cols-3">
    <a href="https://discord.com/users/904100404332204102" target="_blank" class="text-center sm:text-lg xl:text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">Discord</a>
    <a href="mailto:starry@bomp.dev" target="_blank" class="text-center sm:text-lg xl:text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">Email</a>
    <a href="https://twitter.com/starrybomp" target="_blank" class="text-center sm:text-lg xl:text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">Twitter</a>
    <a href="https://twitch.tv/starrybomp" target="_blank" class="text-center sm:text-lg xl:text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">Twitch</a>
    <a href="https://youtube.com/@starrybomp" target="_blank" class="text-center sm:text-lg xl:text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">YouTube</a>
    <a href="https://github.com/starrybomp" target="_blank" class="text-center sm:text-lg xl:text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">GitHub</a>
    <a href="https://steamcommunity.com/id/starrybomp/" target="_blank" class="text-center sm:text-lg xl:text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">Steam</a>
  </div>
</div>

<svelte:window on:keydown|preventDefault={onKeyDown}/>