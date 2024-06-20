<script>
  let contador = 0;
  let texto = "";
  $: resultado = contador * 10; // Acá se hace una variable Reactiva. llamada "resultado" que va hacer igual a el contador multiplicado por 10. y despues se muestra.
  $: if (resultado >= 30) {
    texto = "Sí.";
  } else {
    texto = "No";
  }
</script>

<main>
  <h1>Variables Reactivas</h1>
  <button on:click={() => (contador += 1)}>Contador {contador}</button>
  <p>Has hecho clicks {contador} veces.</p>
  <hr />
  <p>Resultado x 10 {resultado}</p>
  <p>{texto}</p>

  <!--Esto es un contador sencillo de clicks.-->
</main>
