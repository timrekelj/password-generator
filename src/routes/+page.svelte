<script>
    let length = 10;
    function generate() {
        const small_letters = "abcdefghijkmnprstuvz"
        const big_letters = "ABCDEFGJKLMNPRSTUVZ"
        const numbers = "123456789"
        const special_characters = "?!*=%#"

        const chars = small_letters + big_letters + numbers + special_characters

        let password = '';

        for (let i = 0; i < length; i++) {
            password += chars[Math.floor(Math.random() * chars.length)];
        }
        alert(password);
    }
</script>

<h1>Password manager</h1>

<label>Password length:</label>

<input type="number" min="1" max="100" bind:value={length} />

<button on:click={generate}>Generate</button>
