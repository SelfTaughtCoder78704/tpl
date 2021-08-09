<script>
  import { onMount } from "svelte";
  import Glide from "@glidejs/glide";
  import TitleBlock from "./TitleBlock.svelte";
  import ListBlock from "./ListBlock.svelte";
  import CtaBlock from "./CtaBlock.svelte";
  import MediaBlock from  "./MediaBlock.svelte";

  export let id = "";
  export let classes;
  export let section_index;
  export let actions =[];
  export let actionIsCarousel = false;
  export let titleBlock = false;
  export let titleBlockTitle = "";
  export let titleBlockText = "";
  export let actionSlideType = "";
  export let bullets = false;
  export let arrows = false;
  export let titleFinePrint = ''
  export let perView = 1;
  export let focusAt;
 

  if (actionIsCarousel) {
    classes = classes += " is-carousel";
  }
console.log(actions.length)
  onMount(() => {
    var sliders = document.querySelectorAll(".actionGlide");

    for (var i = 0; i < sliders.length; i++) {
      var glide = new Glide(sliders[i], {
        type: actionSlideType,
        focusAt: focusAt,
        perView: perView,
      });

      glide.mount();
    }
  });
</script>

<section
  class="actions-section page-section {classes} {actionIsCarousel ? 'carousel' : ''}"
  data-index={section_index}
  id={id ? id : ""}
>

      
  {#if actionIsCarousel}
    <div class="actionGlide">

      {#if titleBlock}
        <TitleBlock title={titleBlockTitle} text={titleBlockText} finePrint={titleFinePrint}/>
      {/if}

      <div data-glide-el="track" class="glide__track">
        <div class="glide__slides actions-content">
          {#if actions.length > 0}
            {#each actions as {ctaLink, media, mediaBlock,icon, list, listItems, title, finePrint, text, index, classes, clickable=false,ctaText, ctaBlock, slideType, isCarousel }}
              <div class="action cards index-{index}">
                <div class="glide_slide">
                  <div class="mySlide">
                    {#if clickable}
                              {#if mediaBlock}
                                <MediaBlock 
                                bullets={bullets}
                                arrows={arrows}
                                 {isCarousel} 
                                 slideType={slideType} 
                                 mediaItems={media}/>
                              {/if}
                              <a href={ctaLink} class={classes}>
                                {#if title}
                                  <h3>{title}</h3>
                                {/if}
                                {#if text}
                                  <p>{text}</p>
                                {/if}
                                {#if list}
                                  <ListBlock 
                                  classes={classes} 
                                  items={listItems}
                                  icon={icon}
                                 
                                  />
                                {/if}
                              </a>
                    {:else}
                              <div class={classes}>
                                {#if mediaBlock}
                                  <MediaBlock 
                                  bullets={bullets}
                                  arrows={arrows}
                                   {isCarousel} 
                                   slideType={slideType} 
                                   mediaItems={media} />
                                {/if}
                                {#if title}
                                  <h3>{title}</h3>
                                {/if}
                                {#if text}
                                  <p>{text}</p>
                                {/if}
                                {#if list}
                                  <ListBlock 
                                  classes={classes} 
                                  items={listItems}
                                  icon=""
                                 
                                  />
                                {/if}
                              </div>
                    {/if}
                    {#if ctaBlock}
                              <CtaBlock
                                {ctaLink}
                                ctaText="{ctaText}"
                                id="callToAction"
                                ctaFinePrint="{finePrint}"
                                classes="{classes}"
                              />
                    {/if}
                  </div>
                </div>
              </div>
            {/each}
          {/if}
        </div>

        {#if bullets}
          <div class="glide__bullets" data-glide-el="controls[nav]">
            {#each actions as action, i}
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

  {:else}

    <div class="container ">

      {#if titleBlock}
        <TitleBlock title={titleBlockTitle} text={titleBlockText} finePrint={titleFinePrint} />
      {/if}
      
      {#if actions.length > 0}
                <div class="actions-content grid columns-{actions.length}">
                  {#each actions as {ctaLink,media, mediaBlock, icon, list, listItems, title, finePrint, text, index, classes, clickable=false, ctaText, ctaBlock, slideType, isCarousel, isCarousel }}
                    <div class="action cards index-{index}">
                      {#if clickable}
                        {#if mediaBlock}
                          <MediaBlock 
                          bullets={bullets}
                          arrows={arrows}
                           {isCarousel} slideType={slideType} mediaItems={media}/>
                        {/if}
                        <a href={ctaLink} class={classes}>
                          {#if title}
                            <h3>{title}</h3>
                          {/if}
                          {#if text}
                            <p>{text}</p>
                          {/if}
                          {#if list}
                            <ListBlock 
                                  classes={classes} 
                                  items={listItems}
                                  icon={icon}
                                 
                                  />
                          {/if}
                        </a>
                      {:else}
                        <span class={classes}>
                          {#if mediaBlock}
                            <MediaBlock 
                            bullets={bullets}
                            arrows={arrows}
                             {isCarousel} slideType={slideType} mediaItems={media}/>
                          {/if}
                          {#if title}
                            <h3>{title}</h3>
                          {/if}
                          {#if text}
                            <p>{text}</p>
                          {/if}
                          {#if list}
                            <ListBlock 
                                  classes={classes} 
                                  items={listItems}
                                  icon=""
                                 
                                  />
                          {/if}
                        </span>
                      {/if}
                      {#if ctaBlock}
                        <CtaBlock
                          {ctaLink}
                          ctaText="{ctaText}"
                          id="callToAction"
                          ctaFinePrint="{finePrint}"
                          classes="blue big"
                        />
                      {/if}
                    </div>
                  {/each}
                </div>
      {/if}
    </div>
  {/if}
</section>

<style>
  .action {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .action-text {
    flex: 2;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  }

  .cards {
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    border: 1px solid rgb(231, 231, 231);
  }
  .actionGlide {
    width: 100%;
  }

  

  
</style>
