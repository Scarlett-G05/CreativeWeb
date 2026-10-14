<script>
  import Home from "./routes/Home.svelte";
  import Portfolio from "./routes/Portfolio.svelte";

  let username = $state('');
  let password = $state('');
  let loggedIn = $state(false);
  let registered = $state(false);
  let currentTab = $state('home');
  let users = []

  function login() {
    if (username && password) loggedIn = true;
  }

  function register() {
    if (username && password) registered = true;
  }
</script>

<h1>Photografreak</h1>

{#if !loggedIn}
  <div>
    <input placeholder="Username" bind:value={username} /> 
    <input placeholder="Password" bind:value={password} />
    <button onclick={login}>Login</button>
    <button onclick={register}>Register</button>
  </div>
{:else}
  <nav>
    <button onclick={() => currentTab = 'home'}>Home</button> | 
    <button onclick={() => currentTab = 'portfolio'}>Portfolio</button>
    <button onclick={() => loggedIn = false}>Logout</button>
  </nav>

  <main>
    {#if currentTab === 'home'}
      <Home />
    {:else}
      <Portfolio />
    {/if}
  </main>
{/if}
