<!-- LoginButton.svelte -->
<script lang="ts">
    import { getAuth, GoogleAuthProvider, signInWithPopup } from "firebase/auth";
    
    async function login() {
        const provider = new GoogleAuthProvider();
        const auth = getAuth();
        signInWithPopup(auth, provider)
            .then((result) => {
                const user = result.user;
                console.log(user);
            })
            .catch((error) => {
                const errorCode = error.code;
                const errorMessage = error.message;
            });
    }
</script>

<div class="column content">
    <div class="hero is-large">
        <div class="hero-body">
            <div class="buttons is-centered">
                <button class="button is-success is-large" on:click={login}>
                    Login
                </button>
            </div>
        </div>
    </div>
</div>

<style>
    .content {
        display: inline-block;
    }
</style>
