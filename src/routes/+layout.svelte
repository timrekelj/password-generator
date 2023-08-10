<script>
    import { onMount } from 'svelte';

    let length = 12;
    const small_letters = "abcdefghijkmnprstuvz"
    const big_letters = "ABCDEFGJKLMNPRSTUVZ"
    const numbers = "123456789"
    const special_characters = "?!*=%#"

    const chars = small_letters + big_letters + numbers + special_characters

    let password = '';

    onMount(async () => {

        for (let i = 0; i < length; i++) {
            password += chars[Math.floor(Math.random() * chars.length)];
        }
    });
</script>

<h1>Your password:</h1>
<div>{password}</div>

<slot />