<script>
    import { onMount } from "svelte";
  import Glide from "@glidejs/glide";
  export let slideType;
  export let mediaItems = [];
  export let arrows = false;
  export let bullets = false;
  onMount(() => {
    var sliders = document.querySelectorAll('.myGlide');

    for (var i = 0; i < sliders.length; i++) {
    var glide = new Glide(sliders[i], {
        type: slideType,
    });

    glide.mount()
}
  });
</script>

<div class="glide myGlide media-block">
    <div data-glide-el="track" class="glide__track">
      <ul class="glide__slides">
       {#if mediaItems.length > 0 }
        {#each mediaItems as {item, type, src, caption, poster, credit, imgRel, imgLink, imgAlt, imgLazy, videoOptions}}
          {#if type == 'image'}
          <li class="glide__slide">
            <img alt="{imgAlt}" src="{src}" />
          </li>
          {/if}
          {#if type == 'video'}
          <li class="glide__slide">
            <!-- svelte-ignore a11y-media-has-caption -->
            <video controls {videoOptions} poster="{poster ? poster : ""}" src="{src}" type="video/mp4"  ></video>
            
          </li>
          {/if}
        {/each}
       {/if}
      </ul>
     
      {#if bullets}
          <div class="glide__bullets" data-glide-el="controls[nav]">
            {#each mediaItems as item, i}
              <button class="glide__bullet" data-glide-dir={`=${i}`} />
            {/each}
          </div>
        {/if}

        {#if arrows}
          <div class="glide__bullets" data-glide-el="controls[nav]">
            <button data-glide-dir="<">Back</button>
            <button data-glide-dir=">">Continue</button>
          </div>
        {/if}
      
    </div>
  </div>