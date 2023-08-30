<script>
    import { resultados } from '$lib/stores';
</script>

{ #if $resultados.length }

<section>
  <ul class="resultados">
    {#each $resultados as item }
        <li>{ item }</li>
    {/each}
  </ul>
</section>

{ /if }    

<style>
  section {
    display: grid;
    max-width: 940px;
    margin-top: 32px;
  }

  .resultados {
    border: 1px solid var(--bg-2);
    max-height: 402px;
    overflow-y: auto;
  }

  li {
    font-size: calc(14 / 16 * 1rem);
    height: 40px;
    background-color: var(--bg);
    display: flex;
    align-items: center;
    padding: 16px;
    white-space: nowrap;
  }

  li:first-child {
    margin-top: -1px;
  }

  li + li {
    border-top: 1px solid var(--bg-2);
  }
</style>