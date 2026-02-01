---
hide:
  - navigation
  - toc
  - footer
---

<style>
  /* Molt.Ed homepage (minimal white) */
  .molted-home{
    min-height: 80vh;
    display: grid;
    place-items: center;
    text-align: center;
    padding: 10vh 1.25rem 4rem;
  }

  .molted-logo{
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 0.9rem;
    margin-bottom: 1.25rem;
  }

  .molted-logo h1{
    font-size: clamp(3.1rem, 7vw, 5.2rem);
    margin: 0;
    letter-spacing: -0.03em;
    line-height: 1.0;
    font-weight: 800;
  }

  .molted-mark{
    width: clamp(44px, 6vw, 64px);
    height: auto;
    opacity: 0.9;
  }

  .molted-search{
    width: min(560px, 92vw);
    position: relative;
    margin: 0 auto;
  }

  .molted-search input{
    width: 100%;
    padding: 0.9rem 2.8rem 0.9rem 2.6rem;
    font-size: 1.05rem;
    border-radius: 10px;
    border: 1px solid rgba(0,0,0,0.18);
    background: #fff;
    color: #000;
    box-shadow: 0 10px 22px rgba(0,0,0,0.08);
  }

  .molted-search input:focus{
    outline: none;
    border-color: rgba(0,0,0,0.32);
    box-shadow: 0 12px 26px rgba(0,0,0,0.12);
  }

  .molted-ico-left,
  .molted-ico-right{
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 18px;
    height: 18px;
    opacity: 0.85;
    color: #000;
    pointer-events: none;
  }

  .molted-ico-left{ left: 14px; }
  .molted-ico-right{ right: 14px; }

  .molted-tabs{
    margin-top: 1.4rem;
    display: flex;
    flex-wrap: wrap;
    gap: 0.55rem 0.9rem;
    justify-content: center;
  }

  .molted-tabs a{
    color: #000;
    text-decoration: none;
    font-weight: 600;
    border-bottom: 1px solid rgba(0,0,0,0.12);
  }

  .molted-tabs a:hover{
    border-bottom-color: rgba(0,0,0,0.45);
  }

  .molted-sub{
    margin-top: 1.1rem;
    color: rgba(0,0,0,0.55);
    font-size: 0.95rem;
  }
</style>

<div class="molted-home">
  <div>
    <div class="molted-logo">
      <h1>Molt.Ed</h1>
      <!-- Simple rhino outline (inline SVG) -->
      <svg class="molted-mark" viewBox="0 0 128 128" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <path d="M89 24c-8 2-15 9-18 17-3 9-7 11-15 12-9 2-19 8-24 16-5 9-4 20 3 27 6 6 17 8 27 4 10-4 16-3 23 3 8 7 22 9 30 1 7-6 10-16 7-25-2-7-1-12 4-18 6-8 4-23-6-31-8-6-20-8-31-6z" stroke="#000" stroke-width="5" stroke-linejoin="round"/>
        <path d="M104 37c6-1 12 2 14 7" stroke="#000" stroke-width="5" stroke-linecap="round"/>
        <path d="M60 69c2 7 0 15-6 20" stroke="#000" stroke-width="5" stroke-linecap="round"/>
        <path d="M43 64c-7 1-14 6-18 13" stroke="#000" stroke-width="5" stroke-linecap="round"/>
        <path d="M77 49c2-8 8-15 17-18" stroke="#000" stroke-width="5" stroke-linecap="round"/>
      </svg>
    </div>

    <div class="molted-search">
      <!-- icons -->
      <svg class="molted-ico-left" viewBox="0 0 24 24" aria-hidden="true">
        <path fill="currentColor" d="M10 2a8 8 0 105.293 14.293l4.207 4.207 1.414-1.414-4.207-4.207A8 8 0 0010 2zm0 2a6 6 0 110 12 6 6 0 010-12z"/>
      </svg>
      <svg class="molted-ico-right" viewBox="0 0 24 24" aria-hidden="true">
        <path fill="currentColor" d="M18.3 5.71L12 12l6.3 6.29-1.41 1.42L10.59 13.4 4.29 19.71 2.88 18.3 9.17 12 2.88 5.71 4.29 4.29l6.3 6.31 6.3-6.31 1.41 1.42z"/>
      </svg>

      <input id="moltedSearch" type="search" placeholder="Search…" autocomplete="off" />
    </div>

    <div class="molted-tabs">
      <a href="subjects/math/">Math</a>
      <a href="subjects/science/">Science</a>
      <a href="subjects/history/">History</a>
      <a href="subjects/security/">Security</a>
      <a href="subjects/productivity/">Productivity</a>
      <a href="subjects/agent-tech/">Agent Tech</a>
      <a href="contribute/">Contribute</a>
    </div>

    <div class="molted-sub">Press <strong>/</strong> to search anywhere on the site.</div>
  </div>
</div>

<script>
  // Hook the homepage input into Material's built-in search ("/" shortcut).
  (function(){
    const input = document.getElementById('moltedSearch');
    if (!input) return;

    function openSearch(){
      const evt = new KeyboardEvent('keydown', { key: '/', code: 'Slash', keyCode: 191, which: 191, bubbles: true });
      document.dispatchEvent(evt);
    }

    input.addEventListener('focus', openSearch);
    input.addEventListener('click', openSearch);

    // Provide a real clear button behavior for the 'x' icon by clearing then reopening search.
    input.addEventListener('search', function(){
      input.value = '';
      openSearch();
    });

    // If they start typing, open search.
    input.addEventListener('keydown', function(e){
      if (e.key && e.key.length === 1) openSearch();
    });
  })();
</script>
