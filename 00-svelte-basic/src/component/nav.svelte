<script>
  import { Link } from "svelte-routing";
  let { loggedIn = $bindable(), onlogout } = $props();
</script>

<h1>Photografreak</h1>

{#if loggedIn}
  <nav>
    <Link to="/">Home</Link> |
    <Link to="/portfolio">Portfolio</Link>
    <button onclick={onlogout}>Logout</button>
  </nav>
{/if}
