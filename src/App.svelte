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
      <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAAwCAQAAAAFxwi+AAAP/UlEQVR42t1bCbhVxZHmrew7EsDEZYKCBBCQQQNoMmBIUFkkKBKDZmRzBFQwLgwJMBERGSCKLCFgIC4gGAWMTjQqLsGAKAFkiySgjIDAKIo48Hjv1f+nb3XT3R4uvMf9Lt8X36nv3Hdfd1V31X/qVNepPrcScyqV42Auc0/UU6mcRzxTtmWYx5xM5wlyzNO/ddmdo2Sa/FYel0dlBkezF+vbWTK1JmDFPlgq07GUP7NNffEsVqSlFwzjTA5lizC1DjAaq/ESXpVpbHBK8F+L5XgVK8qkl7CW1xr+fHN2xzMnlHlRFsl4XskaAQ7VrxdexxZsxgfsGkPm+6/CB6Z3qzl3yiNW0km3kbnYBQETtEfmsFlK2vHl6CzLymXNy3iLgwx/oTm74k3+iIPZXRZzbCUOA8ukIixlczVDTyz1PatZuWwvcJK3gOUn6xnsUy7uD3h78F1eEXrcJUxq8u+R7MoAqdzrW0tRglJHJa7tKIeprXaM68Hyk/zSSBik8BT7yBxZgP9hR2yohH0gSiBKpYhJEE/+BS/X29t4jjyRUsX0FIHsocqUGTxYBTtAFEPKJh33rpQk1uhMkXZJDVV3gvKk+rQ58UcnUwyyT1rwB1ib1bKXj4Evc0BtB5DqUypGKfRQXvLuYyEOG90sZdNRUO63euD3bGWgX4GnWRPrK4EAqIQvm6aTi+spBnGAZ5shCswQSyLfGlxO8OvhMwWkxFNpGEWNC3QY5J1Gpir+DkI8jyA+gk8q0DJZ56qpsIh6L/nDtODfEDjwirWJg0FnL/QzptLwyS5ulvcV/PJYUwTKROv5MpNjOYaXyL0cgjcqRdDzeAqm6/V72Coqj4A4iC8MnOD1x0dV5qfuEEN5qW8O/DPAJJ1sbhmv4G+LNEhP8J/FGhprYdOpga+t1bHd/u/Ge0cm8zYO489lMT7zOpSAWKX8tfH5yTRKkkx3Mb8RVsoMtjIarDeRJBLYx7t5B+/kT5XuMhM/iI2IzdvJKjp1PquwsqGarJM0Lc3yq+azKsfKRJngaCJ/hqecUQCxW+4zreZU+oX8kpemfAV/Czwcy2t4A3/saABvlUWA7XNQjzUydTICv3ekCzkilmBjLLG8To8uas2dMknudfrex3HyOOi1OaCWODJcU/i9YxkjG8h4mWtaWpmhI//ekC45koWRWkVsrctabTZhYzZxISWZqjVlX/5Upsg0Gc8b2e5EiRkvU1+yZr2WNvUrcODryXPT8PTAURBwozyvPrn51MGX+4Iu8iudO9+R2oSXbITXEDIhXYbHliDgxt2UPvQGOfs9Bn8zqzKXBTqlkt4o50eeD35XVZ2Dw/gIn2AtL9FBwuCd8DwOghEV420O0L7KzGeBoyrqbQH8P+vMMRmjE+C3Ny2FzPOUryHwAR3Fcq0zctWxJQPwHw1Bhz1iGbcifAvFoKMV9uIEXTXj+04E/takNQF0lcy1ESIGf5NOk5NYKOtgPwhY72LnVLsGDEt72TDKfsclErUSvyQuYw29THEguioC/01VKzF3AvyLFbpkOPt+4MB7rMGqmYCvFpW6efqpo+QkZC7Fs1iNP2OrPJb24alTDH6lchxJ8KvodVG/8p5/Lko9+Id4lvrJQpeSHQXZ3yegE0HXTohL0+izktfdpc0c/A4KQxLIfwN9hvIuK7NaRp7/SAAfG9jQ+2heCBfxkX3wN6Trl7mRom9a5WWR/q+nPngU+iVLQlKmBMDnSg+pdBbB19u9b9AFL2Ya8znG6uLaP+QwnhFnb+YMlJNt8KFT9mVP9jbUy3zrx/4ciT/FIPJqBfp48HNZqCaHVG2b/Fqm4A9gtFyDbVXRDMHX9SWCwen/ghuhxC2FdTMBX6EjECXXB7Cco/htFoZ0grlZ9/wyyEHnntJy03m+ae8f+zvH2ZRU6x9fgIADZ64anyn4Fx5XTGspC0M/SthC8/xTBV/b1M2Kvc1qi3LskAW8gc1DAe90gR8OUSrxvlzMG62S6cGXhQFImWHhZYF/lIc797C+wnrK4Cttw1qs97QOW1HkxxZQ7lO5mhmAn68LKhV+gGBYqxwdwiqO4pkW6tMDviQIHrYiWcCz/NIagz9cvW278iknm3r/zklx483gnbbKmAn46SkEOpmtYpmBn6ut1+GIz9XgE2yJLsIBmcCCAP/pDzth8dzP9mli/i2mrSnEh6hVClxs6p0hE+ddmYN/fOHPu8bH7Gkvdabgu7OZPBbKBgo6Ql3JXYKXWUW1yzL4RdiEd7HR0bvYgr1Rb7EuyZqExeBrpbqLV5cyR5WJTb3Kc6t/Mj9T8GNKQPMaW+tsGYPv79azOVgWYHscfvx3W6GcpRJZTjU3sxrzWBBRDbaVx8AoXXxAwX8yAn+wpplhUb3fmRE/ntAXZZ/KGPz0JD5L2cVGLuxsygz8eL+OldmOI2Uxdge38jOB7VQmq+BvZH5aDi0r+WfIqmnA7xuBP+k48Dv6MiuxPEPwAcpUDuMdHGlolDlHy3x86uF3NfPMY76nfEMeWNZhd3kcR/w8wcHys/2EW6gQRKQt3cGw8PIbBvzFCfB7RODPSoYdDUriehdnBL6ePCepOy/UrSD4+lB+op5/sp2sAH7ycKlCuAhshmVx9RQvWJ7sgl+QdilphaNRdaetBz/E/Euim/PZ4xbcfgFkmZk5+GyjhTVXa2S+bk78lxsDID5iA90xe9vJFIMcmhb8u3RWDyRr8vu8gt0NXcXLFPKoUmvlZX50/69l4ekFP6h6MaQM8M/EYV9f2c6CL8vL/UFtjtS2zMBvlYi0+f6eg7WBZ6tFK8IzbyhpBClfw9QzVSbjOXF2xyZJFBSX5jjqbfzLaQBfS8r5nvLsVefdUT59hF9PgD9Qd5zWgRDlANs7b3NwYn0E4KWqalbA13Fau8tOUDnUR6Mi85bUqIkwWB07QiDkGNX/ff3P7vsOSlvVbKGRH6rtq6pdzmkvrPFK3UZDqHwmFtyb1ODZAUiZZz3MXbpBAT7sZB1VOivgK8dZ+DSsSOyk7T+x/E7qZgtfqAdpqCr1/ZcnS8r4gF93AceRzjRaOaIySXYLa3s4lAM5yNEQDuc4rPC9dtoHjUga8NkjTgk5xqt1NYqixXiGVTqL4DfCxxH43bS9cXxBUMKRrO1lmshkUMnBxCoK3Y2Iq5rb2SuRyQ+Jd8w4IKvZjhNMT/BKlbobe1EMvs2PsT5a+ohN8pCMx/OIS3NHeYEqmk3w62F/BH5Pt8H/IIjiSPfdeFnmy6P4Ew74VuXgSKdLNZ3J3w8gNstvOIa3cbTMw2Yr5e/fmjp7tsD3mXixOWMSn2CV2heZWJgE37bxe44v+eqFuJHJsdbvswp+Ifb4OXxWzwb4MIK/NF25RHvXMM+/atUz9FqrPYUWUYt/Yu3IBvgnPeLHeJnqFFXwtbXEgZ+n6g8HtV2snBIsFyiPWsAS4Be7/pUnAH+bAqIABvDjA+9FHAO8Lh1xxOqSqAqJr9oQe0IJUOEb5fWnt8BLeTsetLqlBV+sHtiSjcJaoE3seyzvjfdwXW6Q518C3R0VoiR4kEzy0Afwe4KeVp8A/PcDD1sH8AMPVgQOmawjW33aYWMoiXlSIJVW8pvKGQP4I3wMeuhjGReoeI/ypgO/M+hpW3nB34f96Ujb92ALXpRp/IGFlzlWXfmVvr2w35z/z/6x97A+/xNrIaCn3fJbXpxUmXkaqI5ijx0Fz6UFPx+r8Tn2Yr85D/oV48ujjEIR9lgOrGG96G3KyhyJd8E0tJoDnXwSwsYy0V3wJO2SWWwRaZmU7IBPsc/QXqPxynJBr3A1MOdxpO31WD0YGsnUYAPPU9k3+0yG57Enb+YIXs+LWOdEO0AsiEapfQLt6gaeWIN4Tp7htW3EKqHdzfGvHCHTZSGWYIk8LlM5iC2Tm+IJmRrszNuNzBNG5ml5TKZzJL9DZ8cJccwPmipvdg67h19O3pxkcc5tVWT1yFyXYJOzqPy66rNC1lUsi8qSOb43VAk1VJVr7ow49CiHLvmBytApIeP/eplyWvNVP6wJp8sQ/wxroHZBqKIc4f0W/Zt92HKjbxkdFcA7yzYwaegprB4NWYV55rMw27A5tziX3diFLdlGXeVCs1h/9Q9N9W6XmaynpYjx7G0X7RBtWU0joy7jttylfRoCfC21Pj7nQP4LStjNFg2Uy3K3k1+7TcNrZKJyuxXGBhM3is4VvmuPWzRZ3ZzdsBt/5XCQvdkL5AUVIPikDMVboExLGYOPZVbcy0Ks4w/L9mI2BHkbzwPZw3GG2voAkG3dO5aHQzqcTAXjpS+GFb+TCSp9v0xgLRzGOqzFAbZR+a/24Z4796GIF5lv78t/m7YeMl0mq2/dCuI5XsbzOEQLzN30zujHCziUHdhMJskMdnHgD1fwe7On+z3YdezqftVIfkPhm4yPWM20dJAHOJbnporM7M/zDai32DDCLjKbI5SnPu8xY7djNwDrOcBIz5KZbIo18huZjdf53YoC/lqZg1WpogF2ymTz+bxMx2v4nF+TeSD28R4OtC8A4lVsM5//i/8DebWMl8UyH+TlrOrB74JlOKi/FCBHWvDddvrNeAsfalmAeA4bcZTnaIFvG94B9UeeN+OQTDWjP61342ZZxFs4GjSzLWEO2/Ni1mRPDYrd2bACLMMK/gYDzrdTcGKNPKxe20kmg+yjoA7VTWwtlRnQtmh57CO7RrA1R4Ayk1UU/KYgL2XHFC9vAtjQgU/sxS4DKrCVdbETr+h+VInMZxv7Fh2WYw9rYbcsTK1AIC/DF1hmNcQOmZfSqQJmQAr+X2SB+XwFf8UGeYD52IS/y5Mgb2Rt+5abev63FCTr+Uv1R0iL8FnqVQ2Zy+oe/CtM/ycyCb/DH91r4f3sXaNVpp1sjiKOVlDX4Q22tpsqMgW7eCEOYic24j3sYAteg2KUsl9qNr0rcpV04U99VgDoHfhvyxO6w3oE5B0cArIGa4H8sX7ebt9rZkfDuRXrU76I32shmOyt4MzTO2SYgt9Tf/xzAAfZR8G3Mf8CBf8h7GLd1GaJvrdQIrPZEuSVpmcqdrMxPkk5QdhCxGumtQA75IkK4ecnAH8bnnE/NCPHaa37D3jDwo4tIH/OM3EIh7EKpdhq2g5ghb5FcASbsByUhayhl60ZqJB/E8BOVg3ZjvP8eSg2/9+k42/FITZhJ3sBZRbAXN1jeAUvyCx+De8Y7k+xxMz2jM5QWAEvgObUV7Kzfq/FwfqTiD7yMLvyaq3Jt5ApWohuL1N5Hduxp2Y7lyt/B3nItP2AXZjHoWzOmhzEszTrp/ziWEGM5/Am1rb8vFbLx51lGscqZyMO1Jc/LuJ1+gTQVSab+bqzkP8hszhU857Ghve2Cgd8gD/OspP7nelrKScpr7XFLmxnDR1Jz3jc5BtycUtyxApWxTlZ+TX8mCZUOTUCh7/6NOr5XZuXyXEx/lb8jefHkGpfVAL2Ur4v9Fiy30LfP0NG/w/SdvkENeTFLgAAAABJRU5ErkJggg==" class="logo" alt="BioTrust" />
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
