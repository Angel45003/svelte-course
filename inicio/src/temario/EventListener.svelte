<script>
  function Alerta() {
    alert("hola");
  }
</script>

<main>
  <input type="checkbox" on:click={() => alert("Hola")} />
  <button on:click={Alerta()}>Alerta </button>

  <!--
    Esto es un uso que se le da a los eventos. Los Eventos son todo lo que pasa en el DOM, cuando mueves el Mouse, Cuando Precionas algo y demás (Cosa qué lo había visto en JavaScript.)
  -->
</main>
