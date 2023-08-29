<script>
    import { onMount } from 'svelte';
    import { clickToCopy } from "../clickToCopy.js"

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
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,400,0,0" />

<div class="flex flex-col md:flex-row text-base">
    <div class="basis-1/1 md:basis-1/3 m-10">
        <h1 class="text-2xl"><b>Povečaj</b> svoj nivo varnosti</h1>
        <ul class="py-10">
            <li><span class="material-symbols-outlined pr-2">check</span> 12 znakov</li>
            <li><span class="material-symbols-outlined pr-2">check</span> Male tiskane črke</li>
            <li><span class="material-symbols-outlined pr-2">check</span> Velike tiskane črke</li>
            <li><span class="material-symbols-outlined pr-2">check</span> Številke</li>
            <li><span class="material-symbols-outlined pr-2">check</span> Posebni znaki</li>
        </ul>
        <div>Spletna stran lahko generira <b>26345088000</b> različnih gesel.</div>
    </div>
    <div class="basis-1/1 md:basis-2/3 m-10">
        <div class="pb-10">Geslo sestoji iz črk in številk, ki si med seboj niso podobne in nudi dovolj visok nivo kompleksnosti, da ustreza zahtevam za gesla, ki jih predpisujejo spletne strani in aplikacije v katere se prijavljamo</div>
        <div class="pt-10">
            <div class="text-xl">Tvoje naključno generirano geslo je</div>
            <p class="text-2xl password"><b>{password}</b></p>
            <div use:clickToCopy={"p"} class="w-fit cursor-pointer copy" >Kopiraj geslo <span class="pl-2 material-symbols-outlined">content_copy</span></div>
        </div>
    </div>
</div>




<slot />