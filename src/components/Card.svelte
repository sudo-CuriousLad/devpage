<script lang="ts">
    export let imgSrc: string = "";
    export let text: string = "";
    export let buttonList: any;
    export let hrefList: any;
</script>

<figure>

</figure>
<figure class="bg-neutral-700 text-center items-center mb-8 drop-shadow-md rounded-md">
    <img src="{imgSrc}" class="w-full rounded-t-md text-3xl bg-neutral-800" alt="Banner for the Minecraft mod Thunderforge.">
    <figcaption class="px-8 py-6 text-3xl">
        {text}
    </figcaption>
    <div class="flex flew-row items-center justify-content w-full px-4 gap-4">
        {#each buttonList as button, index}
            <button class="flex-1 grow rounded-lg text-2xl bg-cyan-600 p-4 w-full h-full mb-4"><a href="{hrefList[index]}">{button}</a></button>
        {/each}
    </div>
</figure>

