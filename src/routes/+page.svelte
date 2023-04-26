<script lang="ts">
    import { fly } from 'svelte/transition';
    import IntersectionObserver from 'svelte-intersection-observer';
    import Projects from '../components/Projects.svelte';

    function transition(node: any) {
        visible = true;

        return {
            destroy() {
                visible = false;
            }
        }
    }

    let visible = false;
    let linksElement: any;
    let intersectingLinks: any;
    let duration = 3000;
    let flyY = -300;
</script>


<div class="grid grid-cols-2 w-screen grid-rows-1 h-screen" use:transition>

    <div class="bg-neutral-900 w-full h-full flex-cols flex items-center h-full p-16 flex-col" >
        {#if visible}
            <img src="src/assets/curiouslad.png" class="rounded-full object-scale-down" width="620px" height="620px" alt="Curiouslad's avatar." transition:fly="{{y:flyY, duration:duration}}">
            <h1 class="mb-8 text-center pt-20 text-9xl w-full p-2 text-transparent bg-clip-text bg-gradient-to-r name from-[#00ffff] to-[#ff0000]" transition:fly="{{y:flyY, duration:duration}}">CuriousLad</h1>
        {/if}
        
    </div>

    <div class="bg-neutral-950 w-full h-full p-16">
        {#if visible}
        <div transition:fly="{{y:flyY, duration:duration}}">
        <div class="mb-16">
            <h1 class="text-7xl text-white essay-heading"><span class="underline underline-offset-8">He</span>y there!</h1>
        </div>
        <p class="text-3xl text-white leading-loose essay tracking-16">
            I'm CuriousLad, a (currently) teenager interested in programming, math, physics and Minecraft.<br><br>
            
            My interests lie mainly in graphics programming and full-stack development, quantum mechanics and pure mathematics.
            I am currently developing a Minecraft mod called <span class="text-[#00ffff]">Thunderforge.</span>
        </p>
        </div>
        {/if}
    </div>
</div>

<div class="h-1 bg-gradient-to-r from-[#00ffff] to-[#ff0000] w-screen" />

<IntersectionObserver element={linksElement} bind:intersecting={intersectingLinks}>
    <div class=" grid grid-cols-2 grid-rows-1 h-screen w-screen">
        <div class="bg-slate-500 w-full h-full items-center justify-content flex flex-col">
            <Projects />
        </div>
        <div bind:this={linksElement} class="bg-gradient-to-b from-neutral-950 via-enutral-950 to-neutral-900 w-full h-full" class:intersecting={intersectingLinks}>
            {#if intersectingLinks}
                <h1 class="text-9xl mt-32 text-transparent bg-clip-text bg-gradient-to-r from-[#00ffff] to-[#ff0000] name text-center" transition:fly="{{y:flyY, duration:duration}}">
                        Links
                </h1>
            {/if}
        </div>
        <div id="">
        </div>
    </div>
</IntersectionObserver>
