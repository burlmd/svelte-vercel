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
    background: #0056b8;
    padding: 2rem;
    grid-column: 1 / 4;
    position: sticky;
    top: 0;

    color: white;
    font-family: poppins, sans-serif;
  }

  .logo {
    max-height: 48px;
  }

  ul {
    list-style: none;
    display: inline-flex;
    align-items: center;
  }

  nav > ul > li > a {
    color: white;
    text-decoration: none;
    /*font-weight: 600;*/
    padding: 0 16px;
    text-transform: uppercase;
    letter-spacing: 0.06em;
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

  .nav-container {
    display: grid;
  }
</style>

<header>
  <div class="nav-container">
    <a href="https://blog.biotrust.com">
      <img src="/BioTRUST-Naturally-Honest-white.png" class="logo" alt="BioTrust" />
    </a>
    <nav>
      <ul>
        <li>
          <a href="https://blog.biotrust.com/category/nutrition/">Nutrition</a>
        </li>
        <li>
          <a href="https://blog.biotrust.com/category/fitness/">Fitness</a>
        </li>
        <li>
          <a href="https://blog.biotrust.com/category/recipes/">Recipes</a>
        </li>
        <li>
          <a href="https://blog.biotrust.com/category/lifestyle/">Lifestyle</a>
        </li>
        <li>
          <a href="https://blog.biotrust.com/category/videos/">Videos</a>
        </li>
        <li>
          <a href="https://blog.biotrust.com/category/podcasts/">Podcast</a>
        </li>
        <li>
          <a target="_blank" href="https://www.biotrust.com/collections/all?utm_source=blog&amp;utm_medium=display&amp;utm_campaign=top_nav&amp;utm_term=navbutton">Products</a>
        </li>
      </ul>
    </nav>
  </div>
</header>

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
</main>
<div class="right-sidebar">Right Sidebar</div>
<footer>Footer Content — Header.com 2020</footer>
