<script lang="ts">
  import Sidebar from "./lib/Sidebar.svelte";
  import LoggedIn from "./lib/LoggedIn.svelte";
  import LoginButton from "./lib/LoginButton.svelte";

  import { onMount } from "svelte";
  import { getAuth, onAuthStateChanged } from "firebase/auth";
  import { getFirestore } from "firebase/firestore";
  import { doc, getDoc } from "firebase/firestore";

  // Import the functions you need from the SDKs you need
  import { initializeApp } from "firebase/app";

  // Your web app's Firebase configuration
  const firebaseConfig = {
    apiKey: "AIzaSyD7lKzmUBcgmf2vXrVNLp7fgnjSiFp9Xkw",
    authDomain: "blackout-box.firebaseapp.com",
    projectId: "blackout-box",
    storageBucket: "blackout-box.appspot.com",
    messagingSenderId: "441855547252",
    appId: "1:441855547252:web:360893ceedc51ff9fbfe21",
    measurementId: "G-YZKW8N6KNR",
  };

  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const db = getFirestore(app);
  
  let user;
  const auth = getAuth();

  onMount(() => {
    onAuthStateChanged(auth, (userAuth) => {
      user = userAuth;
    });
  });
</script>

<main>
  <div class="is-widescreen">
    <div class="columns is-fullwidth">
      {#if user}
        <Sidebar />
        <LoggedIn {user} />
      {:else}
        <LoginButton />
      {/if}
    </div>
  </div>
</main>

<style>
</style>
