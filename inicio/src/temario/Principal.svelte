<script>
  /*let nombre = "Mundo";*/
  let nombre = "Pedro";
  let v1 = 0;
  let v2 = 0;
  let check = false;
</script>

<main>
  <!--<h1>Hola, {nombre}!</h1> <-- Acá estoy diciendo un "Hola, mundo!" -->

  <h1>DATABINGING</h1>
  <h2>{nombre}</h2>
  <input type="text" bind:value={nombre} />
  <hr />
  Valor 1<input type="range" bind:value={v1} />
  Valor 2<input type="range" bind:value={v2} />
  <p>{v1} + {v2} = {v1 + v2}</p>
  <hr />
  Habilitar botón.<input type="checkbox" bind:checked={check} />
  <button disabled={!check}>Probar.</button>

  <!--

		Acá lo que se hace es usar DATABINGING. Por ejemplo, si el valor del Input se modifica, también se modifica el H2, Algo muy raro, ¿No?, Claro, ay que tener en cuenta que no se modifica la variable, SI NO. El H2 o lo que haga referencia a esa variable, NO A LA VARIABLE.

		Acá es un buen uso de DATABINGING, con sus diferencias y demás..

	-->
</main>

<style>
  main {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
    flex-direction: column;
  }
</style>
