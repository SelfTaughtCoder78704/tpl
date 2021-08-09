<script>
  import IntersectionObserver from "svelte-intersection-observer";
  
  import IsCarousel from './IsCarousel.svelte';
  
  export let slideType;
  export let isCarousel;
  export let arrows = false;
  export let bullets = false;
  export let mediaItems = [];
  let element;
  let intersecting;

 
</script>

{#if isCarousel }
 <IsCarousel mediaItems={mediaItems} arrows={arrows} bullets={bullets} slideType={slideType}/>
{:else}
    {#if mediaItems.length > 0 }
    {#each mediaItems as {item, type, src, caption, poster, credit, imgRel, imgLink, imgAlt, imgLazy, videoOptions}}
      {#if type == 'image'}
      <header class:intersecting>
        {intersecting ? "Element is in view" : "Element is not in view"}
      </header>
        
        <IntersectionObserver {element} bind:intersecting>
          <img bind:this={element} alt="{imgAlt}" src="{src}" />
         </IntersectionObserver>
      {/if}
      {#if type == 'video'}
        <IntersectionObserver {element} bind:intersecting>
          <!-- svelte-ignore a11y-media-has-caption -->
          <video controls {videoOptions} poster="{poster ? poster : ""}" src="{src}" type="video/mp4"  ></video>
        </IntersectionObserver>
      {/if}
    {/each}
    {/if}
{/if}


<style>
    img{
        width: 100%;
    }
</style>