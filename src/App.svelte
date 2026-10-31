<script>
  const username = 'wix';
</script>

<main>
  <h1>ATTENTION, Philly</h1>

  <p class="description">
    An events bulletin for Philadelphians looking to connect, exchange, and
    create in spaces that exercise our attention and leave big-tech behind.
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

<style>
  :global(*) { box-sizing: border-box; }

  :global(body) {
    margin: 0;
    background: #f4f1ea;
    color: #141414;
    font-family: system-ui, -apple-system, sans-serif;
  }

   main {
    min-height: 100vh;
    max-width: 72rem;
    margin: 0 auto;
    padding: clamp(2rem, 6vw, 5rem) 1.25rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    gap: clamp(1.5rem, 4vw, 2.5rem);
  }

  h1 {
    margin: 0;
    font-family: 'Instrument Serif', Georgia, serif;
    font-weight: 400;
    font-size: clamp(4rem, 16vw, 13rem);
    line-height: 0.9;
    letter-spacing: -0.02em;
    color: black;
  }

  .description {
    margin: 0 auto;
    max-width: 36rem;
    font-size: clamp(1.1rem, 2.2vw, 1.4rem);
    line-height: 1.5;
  }

  form {
    display: flex;
    justify-content: center;
    gap: 0.5rem;
    width: 100%;
    max-width: 32rem;
    flex-wrap: wrap;
  }

  input[type='email'] {
    flex: 1 1 16rem;
    padding: 0.85rem 1rem;
    font: inherit;
    font-size: 1rem;
    border: 2px solid #141414;
    border-radius: 0;
    background: transparent;
  }

  input[type='email']:focus {
    outline: none;
    background: #fff;
  }

  button {
    padding: 0.85rem 1.5rem;
    font: inherit;
    font-size: 1rem;
    font-weight: 600;
    color: #f4f1ea;
    background: #141414;
    border: 2px solid #141414;
    border-radius: 0;
    cursor: pointer;
  }

  button:hover { background: #333; }

  .visually-hidden {
    position: absolute;
    width: 1px;
    height: 1px;
    overflow: hidden;
    clip: rect(0 0 0 0);
    white-space: nowrap;
  }
</style>