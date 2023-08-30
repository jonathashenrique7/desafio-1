<script>
  import { calculadora, resultados } from '$lib/stores';

  let calcularResultado = () => {
    if (!$calculadora.a || !$calculadora.b || !$calculadora.c) return;

    // Multiplicar o valor de 'C' pelo 'B' e dividir pelo valor de 'A'
    $calculadora.x = ($calculadora.b * $calculadora.c) / $calculadora.a;

    // estruturar resultado
    let resultado = `${$calculadora.a} está para ${$calculadora.b}, assim como ${$calculadora.c} está para ${$calculadora.x}`;
    
    // adicionar resultado ao store
    $resultados = [...$resultados, resultado];

    // reiniciar a calculadora 
    $calculadora.travar = true;

    // enviar para o localStorage
    localStorage.setItem('resultados', JSON.stringify($resultados));
  }

  $: console.log($resultados)
</script>

<section>
  <div class="linha linha__1">
    <input bind:value={$calculadora.a} on:blur={ calcularResultado } type="number" placeholder="a" disabled={ $calculadora.travar } />
    <input bind:value={$calculadora.b} on:blur={ calcularResultado } name="b" type="number" placeholder="b" disabled={ $calculadora.travar } />
  </div>
  <div class="linha linha__2">
    <input bind:value={$calculadora.c} on:blur={ calcularResultado } name="c" type="number" placeholder="c" disabled={ $calculadora.travar } />
    <input bind:value={$calculadora.x} on:blur={ calcularResultado } name="x" type="number" placeholder="x" disabled />
  </div>
</section>

<style>
  section {
    background-color: var(--bg-2);
    padding: 24px;
    display: flex;
    flex-direction: column;
    gap: 8px;
    margin-top: 8px;
    width: fit-content;
  }

  .linha {
    display: flex;
    gap: 40px;
    position: relative;
  }

  .linha::after {
    content: '';
    width: 40px;
    height: 8px;
    background-color: var(--bg);
    position: absolute;
    top: 26px;
    right: 120px;
  }

  input {
    width: 120px;
    height: 60px;
    padding: 16px;
    color: var(--principal);
    font-size: calc(18 / 16 * 1rem);
    background-color: var(--bg);
    border: none;
    text-align: end;
  }

  input::placeholder {
    color: var(--principal);
    text-transform: uppercase;
    opacity: .5;
  }

  input:focus-visible {
    outline: 1px solid var(--principal);
    outline-offset: -1px;
  }

  /* Remover setas type="number" */
  /* https://www.w3schools.com/howto/howto_css_hide_arrow_number.asp */
  input::-webkit-outer-spin-button,
  input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
  }
  
  input[type=number] {
    -moz-appearance: textfield;
    appearance: textfield;
  }
</style>