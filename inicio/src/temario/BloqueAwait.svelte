<script>
  let promesa = ajax();
  let users = [];
  const url = "https://jsonplaceholder.typicode.com/users";

  async function ajax() {
    const res = await fetch(url);
    users = await res.json();

    if (res.ok) {
      return users;
    } else {
      throw new Error("Error al conectar :(");
    }
  }
</script>

<main>
  <hr />
  <h1>BLOQUE AWAIT.</h1>
  {#await promesa}
    <p>Cargando la API...</p>
  {:then usuarios}
    {#each usuarios as item}
      <li>{item.name}</li>
    {/each}
  {:catch error}
    <p style="color:tomato;">Hubo un error. Vuelve intentar más tarde...</p>
    <p>
      Lo Sentimos mucho, pero hubo un error, porfavor compruebe su conexión a
      internet sí es eso.
    </p>
  {/await}
</main>

<!--Acá estamos haciendo un Bloque Await, que cuando el await sea #await promesa es que se esta cargando la api, cuando es :then usuarios, es porque cargo la API, cuando es :catch error es porque detecto un error. Simplemente cargamos un dato .JSON de otra página con Fetch y Await.-->
