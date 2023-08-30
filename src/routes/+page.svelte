<script>
    import Calculadora from "../lib/Calculadora.svelte";
	import Historico from "../lib/Historico.svelte";
	import Resultado from "../lib/Resultado.svelte";
</script>

<h1 class="titulo">REGRA DE 3 SIMPLES</h1>

<div>
    <Calculadora/>
    <Resultado/>
</div>

<Historico/>

<style>
    .titulo { color: greenyellow; }

    div {
        display: flex;
        flex-wrap: wrap;
        gap: 8px;
    }

    h1 {
        font-size: calc(24 / 16 * 1rem);
    }
</style>
