
<script>
    export let kicker = "";
    export let title = "";
    export let subTitle = "";
    export let text = "";
    export let finePrint = "";
    export let classes = "";
    export let id = "";
</script>

<div class="title-block {classes}" id="{id}">
    {#if kicker}
        <h6 >{kicker}</h6>
    {/if}
    {#if title }
        <h2>{title}</h2>
    {/if}
    {#if subTitle }
        <h3>{subTitle}</h3>
    {/if}
    {#if text }
        <p class="lead">{text}</p>
    {/if}
    {#if finePrint }
        <small >{finePrint}</small>
    {/if}

</div>

<style>
    p.lead { 
  font-size: 1.5rem;
}

small, 
.small { 
  display: block;
  font-size:.8rem;
  font-family: sans-serif;
}



</style>