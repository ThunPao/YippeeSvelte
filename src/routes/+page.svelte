<script lang="ts">
    import { Confetti } from "svelte-confetti";
    let yipVal = 0;
    function addYippee() {
        yipVal++;
        loadSong();
    }
    let song = null;
    function loadSong() {
		song = new Audio("/yippee.mp3")
		song.volume = 0.2
		song.play()		
	}
</script>

<div
    style="
 position: absolute;
 top: -50px;
 left: 0;
 height: 100vh;
 width: 100vw;
 display: flex;
 justify-content: center;
 overflow: hidden;
 pointer-events: none;"
>
    <Confetti
        x={[-5, 5]}
        y={[0, 0.1]}
        delay={[500, 2000]}
        infinite
        duration="5000"
        amount="200"
        fallDistance="100vh"
    />
</div>
<div class="grid justify-center select-none ">
    <p class="text-4xl font-bold">YIPPEE!</p>
    <button class="text-6xl text-center">{yipVal}</button>
</div>

<div class="h-screen overflow-hidden select-none">
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <div
        title="YIPPEE"
        on:click={addYippee}
        id="yippee"
        class="text-lg h-screen active:scale-110 overflow-hidden"
    ></div>
</div>

<!-- <img src="/yippee.webp" class="bg-cover" width="1920" height="1080" alt="YIPPEE"/> -->

<style>
    #yippee {
        background-image: url("/yippee.webp");
        background-repeat: no-repeat;
        background-size: contain;
        background-position: 50%;
    }
</style>
