<script>
  let nombres = ["Maria", "Juan", "Pedro"];

  let personas = [
    {
      id: 1,
      nombre: "Devan",
      apellido: "Mordey",
      email: "dmordey0@google.com.br",
    },
    { id: 2, nombre: "Tobi", apellido: "Knudsen", email: "tknudsen1@cbc.ca" },
    {
      id: 3,
      nombre: "Thia",
      apellido: "Rosengarten",
      email: "trosengarten2@posterous.com",
    },
    {
      id: 4,
      nombre: "Willy",
      apellido: "Sterling",
      email: "wsterling3@blogspot.com",
    },
    {
      id: 5,
      nombre: "Wes",
      apellido: "Chaffin",
      email: "wchaffin4@myspace.com",
    },
    {
      id: 6,
      nombre: "Martyn",
      apellido: "Nicholson",
      email: "mnicholson5@dmoz.org",
    },
    {
      id: 7,
      nombre: "Lannie",
      apellido: "Gallatly",
      email: "lgallatly6@senate.gov",
    },
    {
      id: 8,
      nombre: "Mirella",
      apellido: "De Ruel",
      email: "mderuel7@facebook.com",
    },
    {
      id: 9,
      nombre: "Sunny",
      apellido: "Stening",
      email: "sstening8@odnoklassniki.ru",
    },
    {
      id: 10,
      nombre: "Newton",
      apellido: "Hatchman",
      email: "nhatchman9@ebay.co.uk",
    },
    { id: 11, nombre: "Karalee", apellido: "Ogle", email: "koglea@ted.com" },
    {
      id: 12,
      nombre: "Tobye",
      apellido: "Hefner",
      email: "thefnerb@goo.ne.jp",
    },
    { id: 13, nombre: "Krissie", apellido: "Pimm", email: "kpimmc@jugem.jp" },
    {
      id: 14,
      nombre: "Hadley",
      apellido: "Bouller",
      email: "hboullerd@elpais.com",
    },
    {
      id: 15,
      nombre: "Elizabet",
      apellido: "Shevlan",
      email: "eshevlane@wufoo.com",
    },
    {
      id: 16,
      nombre: "Gris",
      apellido: "Karpenko",
      email: "gkarpenkof@buzzfeed.com",
    },
    {
      id: 17,
      nombre: "Ermina",
      apellido: "Morecombe",
      email: "emorecombeg@dagondesign.com",
    },
    {
      id: 18,
      nombre: "Florrie",
      apellido: "Roylance",
      email: "froylanceh@yahoo.co.jp",
    },
    {
      id: 19,
      nombre: "Jessi",
      apellido: "Scarrisbrick",
      email: "jscarrisbricki@rambler.ru",
    },
    {
      id: 20,
      nombre: "Lura",
      apellido: "Questier",
      email: "lquestierj@howstuffworks.com",
    },
  ];
</script>

<main>
  <hr />
  <h1>Bloque EACH.</h1>
  <ul>
    {#each nombres as nombre, i}
      <li>{i + 1}{nombre}</li>
    {/each}
  </ul>
  <hr />
  <h1>Ejemplo 1:</h1>
  <table>
    <th>Nombre</th>
    <th>Apellido</th>
    <th>Mail</th>
    {#each personas as item}
      <tr>
        <td>{item.nombre}</td>
        <td>{item.apellido}</td>
        <td>{item.email}</td>
      </tr>
    {:else}
      <tr>
        <td colspan="3">La API no tiene datos.</td>
      </tr>
    {/each}
  </table>

  <!--Acá recorre todo el array de nombres, desde Maria hasta Pedro. Es como Object Map, o algo parecido a For, si pones "," en el Each, te va a mostrar lo que sería el Key.-->
</main>
