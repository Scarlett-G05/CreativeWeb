<script>
  import Home from "./routes/Home.svelte";
  import Portfolio from "./routes/Portfolio.svelte";

  let username = $state('');
  let password = $state('');
  let loggedIn = $state(false);
  let registered = $state(false);
  let currentTab = $state('home');
 

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
    <p>
      Hello! This is my work so far, its very bare bones but I've made some drafts of what my website will look like and will start to work on the 
      css and content from there. I'm also in the process of making a proper login system.
    </p>
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

