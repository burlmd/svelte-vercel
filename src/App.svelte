<script>
  import { onMount } from "svelte";
  export let date;

  onMount(async () => {
    const res = await fetch("/api/date");
    const newDate = await res.text();
    date = newDate;
  });
</script>

<style>

header {
  background: lightpink;
  padding: 2rem;
  grid-column: 1 / 4;
  position: sticky;
  top: 0;
}

.left-sidebar {
  background: lightblue;
  grid-column: 1 / 2;
}

main {
  background: coral;
  grid-column: 2 / 3;
}

.right-sidebar {
  background: yellow;
  grid-column: 3 / 4;
}

footer {
  background: wheat;
  padding: 2rem;
  text-align: center;
  grid-column: 1 / 4;
}

.left-sidebar,
.right-sidebar {
  padding: 1rem;
}

</style>


<header><h1>Header.com</h1></header>
<div class="left-sidebar">Left Sidebar</div>
<main>
  <h1>Hello Mark</h1>
  <h1>Svelte + Node.js API</h1>
  <h2>
    Deployed with
    <a href="https://vercel.com/docs" target="_blank" rel="noreferrer noopener">
      Vercel
    </a>
    !
  </h2>
  <p>
    <a
      href="https://github.com/vercel/vercel/tree/master/examples/svelte"
      target="_blank"
      rel="noreferrer noopener">
      This project
    </a>
    is a
    <a href="https://svelte.dev/">Svelte</a>
    app with three directories,
    <code>/public</code>
    for static assets,
    <code>/src</code>
    for components and content, and
    <code>/api</code>
    which contains a serverless
    <a href="https://nodejs.org/en/">Node.js</a>
    function. See
    <a href="/api/date">
      <code>api/date</code>
      for the Date API with Node.js
    </a>
    .
  </p>
  <br />
  <h2>The date according to Node.js is:</h2>
  <p>{date ? date : 'Loading date...'}</p>
</main><div class="right-sidebar">Right Sidebar</div>
<footer>Footer Content — Header.com 2020</footer>


