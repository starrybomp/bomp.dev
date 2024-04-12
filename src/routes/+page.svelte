<script lang="ts">
  import { onMount } from 'svelte';

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

  export async function isChannelLive(channel: string): Promise<boolean> {
    try {
      const url = `https://static-cdn.jtvnw.net/previews-ttv/live_user_${channel}-1x1.jpg`;
      const response = await fetch(url, { redirect: 'manual' });
      if (response.status === 200) {
        return true; // Channel is live
      } else if (response.status === 404) {
        return false; // Channel is offline
      } else {
        throw new Error('Unexpected status code: ' + response.status);
      }
    } catch (error) {
      return false; // Error occurred, assume channel is offline
    }
  }

  let hostName: string
  onMount(() => hostName = window.location.hostname);

  let channel: string = 'starrybomp';
  let streaming: boolean = false;
  isChannelLive(channel).then((meow) => { streaming = meow });

  setInterval(async () => {
    streaming = await isChannelLive(channel)
  }, 15000)
</script>
<div class="h-screen flex items-center justify-center flex-col min-h-screen h-fit">
  {#if streaming == true}
    <div class="md:w-1/2 lg:w-1/3 aspect-video ml-4 mr-4 mt-2 mb-4 justify-items-center mx-auto flex-col">
      <iframe
        title="starrybomp's stream"
        src="https://player.twitch.tv/?channel={channel}&parent={hostName}"
        height="100%"
        width="100%"
        class="rounded-lg shadow"
        allowfullscreen>
      </iframe>
    </div>
  {/if}
  <div class="bg-zinc-900 md:w-1/2 lg:w-1/3 mb-2 mr-4 ml-4 pl-8 pr-8 pt-8 pb-10 rounded-lg shadow justify-items-center mx-auto flex-col">
    <h1 class="text-4xl text-slate-100 font-bold rounded-lg"><img alt="fun little icon" class="inline mb-1 rounded-lg" src={image} height="48" width="48"/>&nbsp;starrybomp <h2 class="text-2xl text-slate-300 rounded-lg font-normal inline whitespace-nowrap">he/they</h2></h1>
    <h2 class="text-2xl text-slate-200">Hello, I make, play, and occasionally stream games :)</h2>

    <h1 class="text-3xl mt-6 text-slate-100 font-bold rounded-lg">Contact</h1>
    <div class="mt-2 flex flex-row gap-2 containter grid xl:grid-cols-3 sm:grid-cols-3">
      <a href="https://discord.gg/rTA3yNytK9" target="_blank" class="text-center text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">Discord</a>
      <a href="mailto:starry@bomp.dev" target="_blank" class="text-center text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">Email</a>
      <a href="https://twitter.com/starrybomp" target="_blank" class="text-center text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">Twitter</a>
      <a href="https://twitch.tv/starrybomp" target="_blank" class="text-center text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">Twitch</a>
      <a href="https://youtube.com/@starrybomp" target="_blank" class="text-center text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">YouTube</a>
      <a href="https://github.com/starrybomp" target="_blank" class="text-center text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">GitHub</a>
      <a href="https://steamcommunity.com/id/starrybomp/" target="_blank" class="text-center text-2xl mt-2 text-slate-300 rounded-lg pl-4 pr-4 pt-2 pb-2 bg-zinc-950 justify-items-center font-normal hover:bg-zinc-800 duration-300 shadow">Steam</a>
    </div>
  </div>
</div>

<svelte:window on:keydown|preventDefault={onKeyDown}/>