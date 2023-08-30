<script>
  import { calculadora } from '$lib/stores';
</script>

<section>
  <p>
    {#if $calculadora.a}
    <span>{$calculadora.a}</span>
    {/if}
 
    {#if $calculadora.b}
    <span>está para {$calculadora.b}.</span>
    {/if}
  </p>

  <p>
    {#if $calculadora.c}
    <span>Assim como {$calculadora.c}</span>
    {/if}
 
    {#if $calculadora.x}
    <span>está para {$calculadora.x}.</span>
    {/if}
  </p>
</section>

<style>
  section {
    margin-top: 8px;
    margin-left: 24px;
  }

  p { background-color: rgb(38, 110, 4); color: rgb(241, 241, 235); padding: 15px; margin: 8px; border-radius: 15px; transition: 2s; }

  p:hover { transition: 2s; padding: 10px; }
</style>