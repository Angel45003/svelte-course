<script>
  let promesa = ajax();
  let movies = [];
  const url = "https://dummyapi.online/api/pokemon";

  async function ajax() {
    const res = await fetch(url);
    movies = await res.json();

    if (res.ok) {
      return movies;
    } else {
      throw new Error("Error al conectar :(");
    }
  }
</script>

<main>
  <div class="banner_list">
    <h1>Pokemon.</h1>
    <p>Ve las mejores Pokemons. ¡Acá!</p>
  </div>
  <div class="main-app">
    {#await promesa}
      <p>Cargando la API...</p>
    {:then movies}
      {#each movies as item}
        <article class="article-card">
          <img src={item.image_url} alt={item.pokemon} />
          <h1>{item.pokemon}</h1>
          <div class="grid-main">
            <div>
              <h3>Habilidad: {item.abilities}</h3>
            </div>
            <div>
              <h2>Tipo: {item.type}</h2>
            </div>
          </div>
        </article>
      {/each}
    {:catch error}
      <p style="color:tomato;">Hubo un error. Vuelve intentar más tarde...</p>
      <p>
        Lo Sentimos mucho, pero hubo un error, porfavor compruebe su conexión a
        internet sí es eso.
      </p>
    {/await}
  </div>
</main>

<!--Acá estamos haciendo un Bloque Await, que cuando el await sea #await promesa es que se esta cargando la api, cuando es :then usuarios, es porque cargo la API, cuando es :catch error es porque detecto un error. Simplemente cargamos un dato .JSON de otra página con Fetch y Await.-->

<style>
  .banner_list {
    max-width: 600px;
    margin: 0 auto;
    text-align: center;
  }

  .main-app {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    width: 90%;
    margin: 0 auto;
  }
  .article-card {
    width: 300px;
    background-color: #f5f5f5b3;
    border-radius: 20px;
    margin-top: 60px;
    text-align: center;
    padding: 10px;
    cursor: pointer;
  }

  .article-card h1 {
    font-size: 40px;
  }

  .grid-main {
    align-items: center;
    display: flex;
    gap: 20px;
    opacity: 80%;
  }

  .grid-main > * {
    font-weight: 200;
    font-size: 12px;
  }

  @media screen and (max-width: 900px) {
    .main-app {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }

  @media screen and (max-width: 700px) {
    .main-app {
      grid-template-columns: repeat(1, minmax(0, 1fr));
    }

    .article-card {
      width: 100%;
    }

    .grid-main {
      justify-content: center;
    }
  }
</style>
