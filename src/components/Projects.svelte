<script lang="ts">
    import Card from './Card.svelte';
    let thunderforgeButtons = ["Modrinth", "Github"];
    let thunderforgeHrefs = ["", "https://github.com/sudo-CuriousLad/Thunderforge"]
    let pageButtons = ["Github"];
    let pageHrefs = ["https://github.com/sudo-CuriousLad"];
    let attractorsButtons = ["Github"];
    let attractorsHrefs = ["https://github.com/sudo-CuriousLad/strange-attractors"];
</script>

<div class="h-full w-3/4 scroll-smooth overflow-auto justify-content items-center p-8 text-white essay">

    <Card
        imgSrc="../assets/thunderforge.png"
        text="Thunderforge, a Minecraft mod based around lightning, electricity, magic and a trolling amount of physics."
        buttonList={thunderforgeButtons}
        hrefList={thunderforgeHrefs}
        />
    <Card
        imgSrc="../assets/website.png"
        text="This website has all its code open source!"
        buttonList={pageButtons}
        hrefList={pageHrefs}
        />
    <Card
        imgSrc="../assets/attractors.png"
        text="A simulator for different systems of differential equations which form beautiful paths called strange attractors."
        buttonList={attractorsButtons}
        hrefList={attractorsHrefs}
        />
</div>

<style>
    figure {
        background-color: #262626;
        text-align: center;
        align-items: center;
        margin-bottom: 2em;
        border-radius: 1em;
        box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
    }

</style>
