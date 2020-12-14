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
  @import url("https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap");

  header {
    background: #0056b8;
    padding: 2rem;
    grid-column: 1 / 4;
    position: sticky;
    top: 0;

    color: white;
    font-family: poppins, sans-serif;
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

<header>
  <h1>Header.com</h1>

  <div class="nav__flex-parent flex-parent">
    <button
      class="nav-icon-toggle"
      id="nav-icon-toggle"
      aria-label="Open mobile menu">
      <span class="nav-icon-toggle__box">
        <span class="nav-icon-toggle__inner" />
      </span>
    </button>
    <a href="https://blog.biotrust.com" class="logo">
      <noscript><img
          src="https://bioblog.wpengine.com/wp-content/uploads/2020/04/BioTRUST-Naturally-Honest-white.png"
          srcset="https://bioblog.wpengine.com/wp-content/uploads/2020/04/BioTRUST-Naturally-Honest-white.png 1x, https://bioblog.wpengine.com/wp-content/uploads/2020/04/BioTRUST-Naturally-Honest-white.png 2x"
          class="logo__img"
          alt="BioTrust" /></noscript><img
        src="https://bioblog.wpengine.com/wp-content/uploads/2020/04/BioTRUST-Naturally-Honest-white.png"
        data-src="https://bioblog.wpengine.com/wp-content/uploads/2020/04/BioTRUST-Naturally-Honest-white.png"
        data-srcset="https://bioblog.wpengine.com/wp-content/uploads/2020/04/BioTRUST-Naturally-Honest-white.png 1x, https://bioblog.wpengine.com/wp-content/uploads/2020/04/BioTRUST-Naturally-Honest-white.png 2x"
        class="logo__img lazyloaded"
        alt="BioTrust"
        srcset="https://bioblog.wpengine.com/wp-content/uploads/2020/04/BioTRUST-Naturally-Honest-white.png 1x, https://bioblog.wpengine.com/wp-content/uploads/2020/04/BioTRUST-Naturally-Honest-white.png 2x" />
    </a>
    <nav class="flex-child nav__wrap d-none d-lg-block">
      <ul id="menu-menu-2" class="nav__menu">
        <li
          class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-12956">
          <a href="https://blog.biotrust.com/category/nutrition/">Nutrition</a>
        </li>
        <li
          class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-12780">
          <a href="https://blog.biotrust.com/category/fitness/">Fitness</a>
        </li>
        <li
          class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-12786">
          <a href="https://blog.biotrust.com/category/recipes/">Recipes</a>
        </li>
        <li
          class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-12784">
          <a href="https://blog.biotrust.com/category/lifestyle/">Lifestyle</a>
        </li>
        <li
          class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-has-children nav__dropdown menu-item-11887">
          <a
            href="https://blog.biotrust.com/category/videos/"
            class="nav__dropdown-url">Videos</a>
          <ul class="nav__dropdown-menu depth_0">
            <li
              class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-12136">
              <a
                href="https://blog.biotrust.com/category/videos/product-videos/">Product
                Videos</a>
            </li>
            <li
              class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-12137">
              <a
                href="https://blog.biotrust.com/category/videos/recipe-videos/">Recipe
                Videos</a>
            </li>
          </ul>
        </li>
        <li
          class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-7297">
          <a href="https://blog.biotrust.com/category/podcasts/">Podcast</a>
        </li>
        <li
          class="menu-item menu-item-type-custom menu-item-object-custom menu-item-12781">
          <a
            target="_blank"
            href="https://www.biotrust.com/collections/all?utm_source=blog&amp;utm_medium=display&amp;utm_campaign=top_nav&amp;utm_term=navbutton">Products</a>
        </li>
      </ul>
    </nav>
    <div class="nav__right nav--align-right d-none d-lg-flex">
      <div class="nav__right-item socials socials--nobase nav__socials" />
      <div class="nav__right-item nav__search">
        <a class="nav__search-trigger" id="nav__search-trigger">
          <i class="ui-search nav__search-trigger-icon" />
        </a>
        <div
          class="nav__search-box"
          id="nav__search-box"
          style="display: none;">
          <form
            role="search"
            method="get"
            class="nav__search-form"
            action="https://blog.biotrust.com/">
            <input
              type="search"
              id="search-form-5fd693afd6188"
              class="nav__search-input"
              placeholder="Search an article"
              value=""
              name="s" />
            <button
              type="submit"
              class="nav__search-button btn btn-md btn-color btn-button">
              <i class="ui-search nav__search-icon" />
            </button>
          </form>
        </div>
      </div>
    </div>
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
