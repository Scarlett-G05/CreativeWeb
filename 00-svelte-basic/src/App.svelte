<script>
  let {username = '', password = ''} = $props();
  let loggedIn = $state(false)
</script>

<div>
    <h1>Hello</h1>
    <p>Make main page with login and 2nd page with portfolio
        make login usestate variable and button
    </p>
    <input bind:value={username} />
    <input bind:value={password} />
    
</div>

<!-- Gotta make a validation script to match username to pass
 gotta change the CSS
 make submit button to login -->