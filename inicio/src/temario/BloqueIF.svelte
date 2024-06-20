<script>
  let login = false;
  const cambio = () => (login = !login);
</script>

<main>
  <hr />
  <h1>Bloque IF</h1>
  {#if login}
    <h2>Veo, que estas Logeado.</h2>
  {:else}
    <h2>Ohh no, no estas logeado.</h2>
  {/if}
  <button on:click={cambio}>Login</button>
  <!--
    Lo que se hace acá es que cambias cuando le das al botón, si le das al botón se cambia a True, si le vuelves a dar se cambia a False, y así seguido

  -->
</main>
