<script lang="ts">
  import { invoke } from "@tauri-apps/api/core";
  import Icon from "@iconify/svelte";
  import { goto } from '$app/navigation';

  let loading = $state(false);

  async function connect(event: Event) {
    event.preventDefault();
    const form = event.target as HTMLFormElement;
    const data = new FormData(form);
    const card = data.get("card") as string;
    const pin = data.get("pin") as string;

    loading = true;
    invoke("login", { card, pin }).then((res) => {
      console.log(res);
    }, (err) => {
      console.error(err);
    }).finally(() => {
      loading = false;
      goto(`/order`, true);
    });
  }
</script>

<!-- Onboarding page -->

<main>
  <div id="header">
    <h1>Bonjour !</h1>
    <p>Quel petit plat vous ferait plaisir aujourd'hui ?</p>
  </div>
  
  <form id="login" onsubmit={connect} method="post">
    <div id="card-row">
      <button><Icon icon="material-symbols:nfc-outline" inline="true"></Icon></button>
      <input name="card" type="text" placeholder="Numéro de carte" />
    </div>
    <input name="pin" type="password" pattern="[0-9]*" maxlength="12" placeholder="Code PIN"/>
    <button type="submit">
      {#if loading}
        Connexion...
      {:else}
        Se connecter
      {/if}
      <div id="loading" class:show={loading}>
        <Icon icon="line-md:loading-twotone-loop" inline="true"></Icon>
      </div>
    </button>
  </form>
</main>

<style lang="scss">
  h1 {
    font-size: 4 * $font-size-normal;
  }

  main {
    display: flex;
    position: relative;
    flex-direction: column;
    align-items: stretch;
    gap: 2em;
    justify-content: center;
    height: 100vh;
  }

  #header {
    margin: 1rem 1rem;
    p {
      font-size: 1.5 * $font-size-normal;
    }
  }

  form#login {
    display: flex;
    flex-direction: column;
    margin: 0 1rem;
    gap: 1rem;

    button[type="submit"] {
      position: relative;
    }
  }

  #card-row {
    display: flex;
    flex-direction: row;
    gap: 1rem;
    align-items: stretch;
    
    input {
      flex-grow: 1;
    }

    button {
      padding: 0.25rem 0.75rem;
      font-size: 2 * $font-size-normal;
      align-items:center;
      justify-content: center;
      color: map-get($slate, 700);
    }
  }

  #loading {
    position: absolute;
    right: 1rem;
    top: 50%;
    origin: center;
    transform: translateY(-50%);
    justify-content: center;
    align-items: center;
    font-size: 1.5 * $font-size-normal;
    opacity: 0;
    transition: opacity 0.5s;
  }

  #loading.show {
    opacity: 1;
  }
</style>