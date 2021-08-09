<script>
  export let classes = "";
  export let icon = "https://media.istockphoto.com/vectors/flat-icon-check-vector-id496603666?k=6&m=496603666&s=170667a&w=0&h=CdaZL0kvQieOEjq0Vt8gLzlZvVQDKtiqZEx32WDDEYs=";
  export let iconAlt = "corresponding list item icon";
  export let items = [];
</script>

{#if items}
  <div class="list-block {classes}">
    <ul>
      {#each items as item}

          <li class="icon-list-item">
            {#if item.icon}
              <figure class="list-icon">
                <img src="{item.icon}" alt={item.iconAlt} />
              </figure>
            {:else}
            <figure class="list-icon">
                <img src="{icon}" alt={iconAlt} />
            </figure>

            {/if}
            <span class="list-text">
              {item.text}
            </span>
          </li>

      {/each}
    </ul>
  </div>
{/if}

<style>
  .list-block ul {
    display: inline-block;
    text-align: left;
    width: 100%;
    margin: 0;
    padding: 0;
  }

  .icon-list-item {
    display: flex;
    align-items: center;
  }

  .list-icon {
    width: 15px;
    height: 15px;
    margin-right: 5px;
    display: inline-flex;
    flex: 0 0 15px;
    align-items: center;
  }

  img,
  svg {
    max-height: 20px;
    object-fit: contain;
  }
</style>
