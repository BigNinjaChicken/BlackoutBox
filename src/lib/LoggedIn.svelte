<!-- LoggedIn.svelte -->
<script>
    import {
        getAuth,
        GoogleAuthProvider,
        signInWithPopup,
        signOut,
    } from "firebase/auth";

    export let user;

    async function logout() {
        const auth = getAuth();
        signOut(auth);
    }

    console.log(user)
</script>

<div class="column content">
    <button class="button is-danger" on:click={logout}>
        Logout
    </button>
    <div class="hero is-large">
        <div class="hero-body has-text-centered">
            <p>Logged in as {user.displayName}</p>
        </div>
    </div>
</div>

<style>
    .column.content {
        position: relative;
    }

    .button.is-danger {
        position: absolute;
        top: 0;
        right: 0;
        margin: 2rem;
    }
</style>
