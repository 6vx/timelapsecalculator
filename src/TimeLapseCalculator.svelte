<script lang="ts">
    // This bobble is for calculating the length of timelapses using
    // a variety of settings. 
    // It's for personal use, so the pre-existing options are the ones
    // available in my Xiaomi Yi 4k Action Camera
    export let show = false; 
    function handleClick(){
        show = !show;
    }   
    let frameRateSelected: number = 30;
    let frameRateOptions: Array<number> = [24, 30, 60, 120];
    let frameIntervalSelected: number = 0.5;
    let frameIntervalOptions: Array<number> = [0.5, 1, 2, 5, 10, 30, 60];
    let captureDuration: number = (3600);
    let calculatedVideoLength: number;
    function getVideoLength (){
        calculatedVideoLength = (captureDuration/(frameIntervalSelected * frameRateSelected));
        return calculatedVideoLength;
    }
    function click () {
        console.log(getVideoLength());
    }
    console.log(getVideoLength());
</script>

<tlc>
    <div>
    <h3>Timelapse Calculator</h3>
    <div class="flex-item">
        <p>IN:<span>{captureDuration}</span>s</p>
    </div>
    <div class="flex-item">
        <p>OUT:<span>{calculatedVideoLength}</span>s</p>
    </div>
    <div class="flex-item">
        <p><span>{frameIntervalSelected}</span>SPF</p>   
    </div>
    <div class="flex-item">
        <p><span>{frameRateSelected}</span>FPS</p>
    </div>
    
    
    <!-- <button on:click={click}>Recalculate</button> -->
    </div>
</tlc>

<style>
    tlc {
        font-family: monospace;
        font-size: 1.4em;
        background-color: black;
        color: white;
        display: flexbox;
        flex-direction: row;
        flex-wrap: wrap;
    }
    span {
        color: pink;
    }
    .flex-item {
        flex: auto;
        border: pink 2px dotted;
        border-radius: 25% 25% 25% 25%;
        margin-top: 10px;
    }
    

</style>


<!-- <div class="evenbiggermofo">
<div class="wholemofo">
    <div on:click="{handleClick}">
        <button>Timelapse Calculator</button>
    </div>
    {#if show}
    <div class="flex-container">
        
        <div class="flex-item">
            <span>Frames per Second</span>
            <div class="selectorGrid">
                {#each frameRateOptions as option}
                        <label for="{option.toString()}">
                            <input type="radio" name="frameRateSelected" id="{option.toString()}" bind:group="{frameRateSelected}" value="{option}">
                            {option.toString()}
                        </label>
                    
                {/each}
            </div>
        </div>
        
        <div class="flex-item">
            <span>Seconds per Frame</span> 
            <div class="selectorGrid">
                {#each frameIntervalOptions as option}
                    <label for="{option.toString()}">
                        <input type="radio" name="frameIntervalSelected" id="{option.toString()}" bind:group="{frameIntervalSelected}" value="{option}">
                        {option.toString()}
                    </label> 
                {/each}
            </div>
        </div>
        
        <div class="flex-item">
            <span>Recording Duration (s)</span>
            <div class="textbox">
                <input type="number" bind:value="{captureDuration}" required name="captureDuration">
            </div> 
        </div>
    </div> 
    <span class="example-spacer"></span>
    <div class="flex-container">
        <div class="flex-item">
            <button on:click="{getVideoLength}">
                Calculate
            </button>
        </div>
        <div class="flex-item">
            <span>Timelapse Length:</span><br>
            {#if calculatedVideoLength}
            <span>{calculatedVideoLength}s / {calculatedVideoLength/60}m</span>
            {/if}
        </div>
            
        
    </div>
    {/if}
</div>
</div>
<style>
    .flex-container {
        display: flex;
        flex-direction: row;
        margin-top: 50px;
    }
    .flex-item {
        flex: auto;
        width: 100px;
        margin: 25px;
        padding: 25px;
        border: black 1px solid;
        border-radius: 2em;
        text-align: center;
    }
    .selectorGrid {
        display: grid;
        justify-content: center;
        grid-template-columns: repeat(3, 3em);
        grid-template-rows: repeat(3, 3em);
        margin-top: 10px;
    }
    input {
        margin: 0;
    }
    .example-spacer {
        flex: 1 1 auto;
    }
    input[type="number"] {
        width: 75px;
        margin-top: 10px;
    }
    .wholemofo {
        text-align: center;
    }
    .evenbiggermofo {
        flex: 1 1 0%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
    }
</style> -->