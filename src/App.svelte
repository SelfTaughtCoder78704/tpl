<script>

  import "../node_modules/@glidejs/glide/dist/css/glide.core.min.css";
  import TitleBlock from "./thesis-pattern-library/TitleBlock.svelte";
  import ListBlock from "./thesis-pattern-library/ListBlock.svelte";
  import Actions from "./thesis-pattern-library/Actions.svelte";
  import myjson from  "./overview_b.json";
import MediaBlock from "./thesis-pattern-library/MediaBlock.svelte";


  
  let secIndex = 0;

  function makeIndex() {
    let indexToReturn = secIndex;
    secIndex++;
    return indexToReturn;
  }

  export let Page = myjson.Page;
  console.log(Page);
</script>

<main>
  {#each Page as data}
    {#if data.block === "Actions"}
      {#if data.titleBlock}
        <Actions
          actionIsCarousel={data.actionIsCarousel}
          focusAt={data.focusAt}
          perView={data.perView}
          actionSlideType={data.actionSlideType}
          titleBlock={data.titleBlock}
          titleBlockTitle={data.titleBlockTitle ? data.titleBlockTitle : ""}
          titleBlockText={data.titleBlockText ? data.titleBlockText : ""}
          actions={data.actions ? data.actions : []}
          id={data.id ? data.id : ""}
          classes={data.classes ? data.classes : ""}
          bullets={data.bullets ? data.bullets : false}
          arrows={data.arrows ? data.arrows : false}
          section_index={makeIndex()}
        />
      {:else}
        <Actions
          actionIsCarousel={data.actionIsCarousel}
          focusAt={data.focusAt}
          perView={data.perView}
          actionSlideType={data.actionSlideType}
          titleBlock={false}
          actions={data.actions ? data.actions : []}
          id={data.id ? data.id : ""}
          classes={data.classes ? data.classes : ""}
          bullets={data.bullets ? data.bullets : false}
          arrows={data.arrows ? data.arrows : false}
          section_index={makeIndex()}
        />
      {/if}
    {/if}
    {#if data.block === "TitleBlock"}
      <TitleBlock
        title={data.title ? data.title : ""}
        text={data.text ? data.text : ""}
        finePrint={data.finePrint ? data.finePrint : ""}
        subTitle={data.subtitle ? data.subtitle : ""}
        kicker={data.kicker ? data.kicker : ""}
      />
    {/if}
    {#if data.block === "ListBlock"}
      <ListBlock items={data.items ? data.items : []} />
    {/if}
    {#if data.block === "MediaBlock"}
      <MediaBlock 
      slideType={data.slideType ? data.slideType : ''} 
      mediaItems={data.mediaItems ? data.mediaItems : []} 
      
      />
    {/if}
  {/each}
</main>

<style>
</style>
