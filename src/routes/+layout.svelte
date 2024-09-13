<nav>
    <h1> NEDTELLING TIL JUL </h1>
</nav>

<slot />

<footer>
    <span> Laget med <span>{"<3"} </span> </span>
</footer>

<style>
    :global(body) {
        background-color: #333;
        margin: 0;
        font-family: Arial, sans-serif;
        color: white;
    }

  nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: #333;
    color: white;
    padding: 1rem;
    text-align: center;
    z-index: 1000;
  }

  footer {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    background-color: #333;
    color: white;
    padding: 1rem;
    text-align: center;
    z-index: 1000;
  }
</style>