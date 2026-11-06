<script>
  const username = 'wix';

  function currentPage() {
    return location.hash === '#/about' ? 'about' : 'home';
  }

  let page = $state(currentPage());

  function onHashChange() {
    page = currentPage();
    window.scrollTo(0, 0);
  }
</script>

<svelte:window onhashchange={onHashChange} />

<div class="page">
  <main>
    <nav aria-label="Main">
      <a href="#/" aria-current={page === 'home' ? 'page' : undefined}>Subscribe</a>
      <a href="#/about" aria-current={page === 'about' ? 'page' : undefined}>About</a>
            <a target="_blank" href="https://buttondown.com/wix/archive/attention-philly/">Newest</a>
    </nav>

    <h1>ATTENTION, PHILLY</h1>

    {#if page === 'about'}
      <article class="about">
        <p>
          I started this with the goal of building an offline community
          infrastructure in Philly, free of digital surveillance and addictive
          design. It's a rejection of the idea that big-tech platforms are
          necessary for social prosperity or information sharing (I have an inkling that we may be
          better off without them, anyway).
        </p>

        <h2>But without social media… how do I stay connected?</h2>
        <p>
          The event is the medium, the public is the place (shout out the  <a href="        https://www.404media.co/luddite-events-nyc-off-tech-summer-of-ludd/">NYC
          Luddite community</a> for this language).
        </p>

        <p>
          The event asks that you participate with your ability to trust,
          negotiate, and create with others. It is people opting to
          play, engaging with a topic, accepting (or rejecting) a premise. The
          event is the practice of collective action. It is a reminder of the
          power we still have when we act together. It is a spark to the
          revolutionary engine.
        </p>

        <h2>How can I help?</h2>
        <p>
          Get out there. Participate. Learn the marks of others,
          make your own. See an event you are excited about, share it with me!
          Hosting an event, share it with me! There is no community without you.
        </p>
        <p>
          Email me at <a href="mailto:attentionphl@proton.me">attentionphl@proton.me</a>
        </p>
      </article>
    {:else}
      <p class="description">
        A biweekly bulletin of events for Philadelphians looking to connect,
        create, and exercise our attention in off-tech spaces, leaving big tech
        behind.
      </p>

      <form
        action="https://buttondown.com/api/emails/embed-subscribe/{username}"
        method="post"
      >
        <label for="email" class="visually-hidden">Email address</label>
        <input
          type="email"
          name="email"
          id="email"
          placeholder="you@example.com"
          autocomplete="email"
          required
        />
        <input type="hidden" name="embed" value="1" />
        <button type="submit">Sign up</button>
      </form>
    {/if}
  </main>
</div>

<style>
  @font-face {
    font-family: 'CC Red Alert INET';
    src: url('/fonts/cc-red-alert-inet.ttf') format('truetype');
    font-display: swap;
  }

  :global(*) { box-sizing: border-box; }

  :global(html),
  :global(body) {
    margin: 0;
    padding: 0;
    min-height: 100%;
  }

  :global(body) {
    display: block;
    background: #d9c88a;
    color: #1a1a1a;
    font-family: system-ui, -apple-system, sans-serif;
  }

  :global(#app) {
    width: 100%;
    max-width: none;
    margin: 0;
    padding: 0;
    border: none;
    text-align: left;
  }

  .page {
    width: 100%;
    min-height: 100vh;
    max-width: 70rem;
    margin: 0 auto;
    background: #e8dcae;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 3rem 1.25rem;
  }

  /* Column width is set by the headline; everything else matches it */
  main {
    width: fit-content;
    max-width: 100%;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  nav,
  .description,
  .about,
  form {
    width: 0;
    min-width: 100%;
  }

  nav {
    display: flex;
    gap: 1.5rem;
    font-family: ui-monospace, 'SF Mono', Menlo, monospace;
    font-size: 0.95rem;
  }

 a {
    color: #6d1a8a;
    text-decoration: none;
    text-underline-offset: 0.3em;
  }

  nav a:hover,
  nav a[aria-current='page'] {
    text-decoration: underline;
  }

  h1 {
    margin: 0;
    font-family: 'CC Red Alert INET', monospace;
    font-weight: 400;
    font-size: clamp(1.75rem, 8.5vw, 4.5rem);
    line-height: 1;
    white-space: nowrap;
    color: #6d1a8a;
  }

  .description {
    margin: 0;
    font-family: ui-monospace, 'SF Mono', Menlo, monospace;
    font-size: 1rem;
    line-height: 2.35;
    text-align: justify;
  }

  .about {
    font-family: ui-monospace, 'SF Mono', Menlo, monospace;
    font-size: 1rem;
    line-height: 1.8;
  }

  .about p {
    margin: 0 0 1.25rem;
  }

  .about p:last-child {
    margin-bottom: 0;
  }

  .about h2 {
    margin: 2rem 0 0.5rem;
    font-size: 1rem;
    font-weight: 700;
    color: #6d1a8a;
  }

  form {
    display: flex;
    gap: 0.5rem;
    flex-wrap: wrap;
  }

  input[type='email'] {
    flex: 1 1 10rem;
    min-width: 0;
    padding: 1rem 1.1rem;
    font: inherit;
    font-size: 1.1rem;
    color: #1a1a1a;
    border: 2px solid #6d1a8a;
    border-radius: 0;
    background: transparent;
  }

  input[type='email']::placeholder { color: #7a7a7a; }

  input[type='email']:focus {
    outline: none;
    background: #f3ead0;
  }

  button {
    padding: 1rem 1.75rem;
    font: inherit;
    font-size: 1.1rem;
    font-weight: 600;
    color: #fff;
    background: #6d1a8a;
    border: 2px solid #6d1a8a;
    border-radius: 0;
    cursor: pointer;
  }

  button:hover { background: #561470; }

  .visually-hidden {
    position: absolute;
    width: 1px;
    height: 1px;
    overflow: hidden;
    clip: rect(0 0 0 0);
    white-space: nowrap;
  }

  @media (max-width: 600px) {
    .page {
      padding: 2rem 1rem;
      min-height: 100svh;
    }

    main {
      gap: 1rem;
    }

    h1 {
      font-size: 14.5vw;
    }

    .description {
      text-align: left;
      line-height: 1.7;
    }

    .about {
      line-height: 1.7;
    }

    form {
      gap: 0.4rem;
    }

    input[type='email'],
    button {
      flex: 1 1 100%;
      padding: 0.8rem 1rem;
    }
  }
</style>