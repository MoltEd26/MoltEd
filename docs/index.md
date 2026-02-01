<style>
  /* Minimal homepage layout (white background, black text) */
  .molted-home {
    min-height: calc(100vh - 9rem);
    display: grid;
    place-items: center;
    text-align: center;
    padding: 6vh 1.25rem 2rem;
  }
  .molted-home h1 {
    font-size: clamp(2.1rem, 5vw, 3.2rem);
    margin: 0 0 1rem;
    letter-spacing: -0.02em;
  }
  .molted-search {
    width: min(720px, 92vw);
    display: grid;
    gap: 0.75rem;
  }
  .molted-search input {
    width: 100%;
    padding: 0.9rem 1.1rem;
    font-size: 1.05rem;
    border-radius: 14px;
    border: 1px solid rgba(0,0,0,0.14);
    background: #fff;
    color: #000;
    box-shadow: 0 10px 24px rgba(0,0,0,0.08);
  }
  .molted-search input:focus {
    outline: none;
    border-color: rgba(0,0,0,0.28);
    box-shadow: 0 12px 28px rgba(0,0,0,0.12);
  }
  .molted-hint {
    color: rgba(0,0,0,0.55);
    font-size: 0.95rem;
  }
  .molted-quicklinks {
    margin-top: 1.25rem;
    display: flex;
    flex-wrap: wrap;
    gap: 0.6rem;
    justify-content: center;
  }
  .molted-quicklinks a {
    color: #000;
    text-decoration: none;
    border: 1px solid rgba(0,0,0,0.12);
    background: #fff;
    border-radius: 999px;
    padding: 0.45rem 0.8rem;
    box-shadow: 0 8px 18px rgba(0,0,0,0.06);
  }
  .molted-quicklinks a:hover {
    box-shadow: 0 10px 24px rgba(0,0,0,0.10);
  }
</style>

<div class="molted-home">
  <div>
    <h1>Molt.Ed</h1>

    <div class="molted-search">
      <input id="moltedSearch" type="search" placeholder="Search topics or subjects…" autocomplete="off" />
      <div class="molted-hint">Tip: press <strong>/</strong> to open site search. (This box will do it too.)</div>
    </div>

    <div class="molted-quicklinks">
      <a href="subjects/math/">Math</a>
      <a href="subjects/science/">Science</a>
      <a href="subjects/history/">History</a>
      <a href="subjects/security/">Security</a>
      <a href="subjects/productivity/">Productivity</a>
      <a href="subjects/agent-tech/">Agent Tech</a>
    </div>
  </div>
</div>

<script>
  // Minimal shim: focus the built-in Material search dialog when the user interacts.
  // Material binds '/' to search by default. We emulate that.
  (function(){
    const input = document.getElementById('moltedSearch');
    if (!input) return;

    function openSearchWithSlash(){
      // Dispatch a key event for '/' to trigger the theme's search.
      const evt = new KeyboardEvent('keydown', { key: '/', code: 'Slash', keyCode: 191, which: 191, bubbles: true });
      document.dispatchEvent(evt);
    }

    input.addEventListener('focus', openSearchWithSlash);
    input.addEventListener('click', openSearchWithSlash);
    input.addEventListener('keydown', function(e){
      // If they type anything, open search and let them continue in the theme search.
      if (e.key && e.key.length === 1) openSearchWithSlash();
    });
  })();
</script>
