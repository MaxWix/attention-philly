<script>
  const username = 'wix';
</script>

<div class="page">
  <main>
    <h1>ATTENTION, PHILLY</h1>

    <p class="description">
      A biweekly bulletin of events for Philadelphians looking to connect,
      create, and exercise attention in offline spaces, leaving big tech
      behind!
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

  /* Column width is set by the headline; description and form match it */
  main {
    width: fit-content;
    max-width: 100%;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
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

  .description,
  form {
    width: 0;
    min-width: 100%;
  }

  .description {
    margin: 0;
    font-family: ui-monospace, 'SF Mono', Menlo, monospace;
    font-size: 1rem;
    line-height: 2.35;
    text-align: justify;
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
      font-size: 15vw;
    }

    .description {
      text-align: left;
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