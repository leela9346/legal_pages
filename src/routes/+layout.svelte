<script>
  let isMenuOpen = false;
  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
</script>

<style>
  header {
    background: white;
    box-shadow: 0 2px 10px rgba(0,0,0,0.05);
    position: sticky;
    top: 0;
    z-index: 1000;
  }

  nav {
    max-width: 1200px;
    margin: auto;
    padding: 0.8rem 1.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .logo {
    font-size: 1.5rem;
    font-weight: 800;
    background: linear-gradient(90deg, #06b6d4, #4f46e5);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  ul {
    display: flex;
    gap: 1.5rem;
    list-style: none;
    align-items: center;
  }

  li a {
    text-decoration: none;
    font-weight: 500;
    color: #333;
    transition: color 0.2s;
  }

  li a:hover {
    color: #4f46e5;
  }

  .btn-primary {
    background: linear-gradient(90deg, #06b6d4, #4f46e5);
    color: white;
    padding: 0.6rem 1.2rem;
    border-radius: 2rem;
    font-weight: 600;
    border: none;
    cursor: pointer;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(79,70,229,0.3);
  }

  .menu-toggle {
    display: none;
    background: none;
    border: none;
    font-size: 1.8rem;
    cursor: pointer;
  }

  @media (max-width: 768px) {
    ul {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      background: white;
      position: absolute;
      top: 4rem;
      right: 1rem;
      padding: 1rem 2rem;
      border-radius: 1rem;
      box-shadow: 0 6px 20px rgba(0,0,0,0.1);
      display: none;
    }

    ul.show {
      display: flex;
    }

    .menu-toggle {
      display: block;
    }
  }

  main {
    min-height: 80vh;
    padding: 1.5rem;
  }
</style>

<header>
  <nav>
    <div class="logo">Vinn.AI</div>

    <button class="menu-toggle" on:click={toggleMenu}>
      {isMenuOpen ? "✖" : "☰"}
    </button>

    <ul class={isMenuOpen ? "show" : ""}>
      <li><a href="/product">Product</a></li>
      <li><a href="/solutions">Solutions</a></li>
      <li><a href="/resources">Resources</a></li>
      <li><a href="/pricing">Pricing</a></li>
      <li><a href="/company">Company</a></li>
      <li><a href="/login" class="btn-primary">Login</a></li>
      <li><a href="/contact">Contact Us</a></li>
      <li><a href="/start" class="btn-primary">Start for Free-trail</a></li>
    </ul>
  </nav>
</header>

<main>
  <slot />
</main>

