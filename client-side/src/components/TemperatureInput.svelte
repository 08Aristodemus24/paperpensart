    <script>
    export let style = "sharp-minimal";
    export let theme = "dark";

    $:palette = {
        'sharp-minimal':{
            dark: {
                primary_color: "white",
                secondary_color: "black",
                tertiary_color: "rgba(255, 255, 255, 0.267)",
                primary_background: "black",
            },
            light: {
                primary_color: "black",
                secondary_color: "white",
                tertiary_color: "rgba(0, 0, 0, 0.267)",
                primary_background: "white",
            }
        },
        'light-neomorphic': {
            light: {
                primary_color: "black",
                secondary_color: "rgb(231, 238, 246)",
                tertiary_color: "rgba(0, 0, 0, 0.267)",
                primary_shadow: "rgba(0, 0, 0, 0.25)",
                secondary_shadow: "rgba(255, 255, 255, 0.5)",
                primary_background: "rgb(231, 238, 246)",
            }
        },
        'dark-neomorphic': {
            dark: {
                primary_color: "rgb(231, 238, 246)",
                secondary_color: "rgb(38, 39, 43)",
                tertiary_color: "rgba(255, 255, 255, 0.267)",
                primary_shadow: "rgba(0, 0, 0, 0.25)",
                secondary_shadow: "rgba(210, 210, 210, 0.5)",
                primary_background: "rgb(38, 39, 43)",
            },
        }
    };

    export let temperature;
</script>

<div 
    class={`temp-container ${style}`} 
    style:--primary-color={palette[style][theme].primary_color} 
    style:--secondary-color={palette[style][theme].secondary_color} 
    style:--tertiary-color={palette[style][theme].tertiary_color}
    style:--primary-shadow={palette[style][theme].primary_shadow}
    style:--secondary-shadow={palette[style][theme].secondary_shadow}
>
    <label for="temp" class="temp-label">Temperature</label>
    <input bind:value={temperature} type="range" min={0.0} max={2.0} step={0.01} id="field" class={`temp-field ${style}`}/>
</div>

<style>
    .sharp-minimal .temp-label{
        /* design */
        font-family: 'Nunito Sans', sans-serif;
        font-weight: 300;
        font-size: clamp(12px, 1vw, 1rem);
        color: var(--primary-color);
        /* outline: 1px solid brown; */

        /* spacing */
        margin-block: 1em;
    
        /* display */
        display: block;
    }

    .sharp-minimal .temp-field{
        /* size */
        width: 12rem;
        /* width: 30rem; */

        /* design */
        background-color: var(--primary-color);
        -webkit-appearance: none;
    }

    .sharp-minimal .temp-field::-webkit-slider-runnable-track{
        /* size */
        height: 0.5px;

        /* design */
        cursor: pointer;
        border-radius: 0px;
        border: 0px solid black;
        box-shadow: none;
        appearance: none;
    }

    .sharp-minimal .temp-field::-ms-track{
        /* size */
        height: 1px;

        /* design */
        cursor: pointer;
        border-radius: 0px;
        border: 0px solid black;
        box-shadow: none;
        appearance: none;
    }

    .sharp-minimal .temp-field::-webkit-slider-thumb{
        /* size */
        height: 20px;
        width: 3px;

        /* design */
        box-shadow: none;
        border: 0px solid black;
        background-color: var(--primary-color);
        cursor: pointer;
        margin-top: -10px;
        -webkit-appearance: none;
    }

    .sharp-minimal .temp-field::-ms-thumb{
        /* size */
        height: 20px;
        width: 3px;

        /* design */
        box-shadow: none;
        border: 0px solid black;
        background-color: var(--primary-color);
        cursor: pointer;
        margin-top: -10px;
        -webkit-appearance: none;
    }

    .light-neomorphic.temp-container{
        /* design */
        background-color: var(--secondary-color);

        /* size */
        padding: 1em;
    }

    .light-neomorphic .temp-label{
        /* design */
        font-family: 'Poppins', sans-serif;
        font-weight: 300;
        font-size: clamp(12px, 1vw, 1rem);
        color: var(--primary-color);
        background-color: var(--secondary-color);
        /* outline: 1px solid brown; */

        /* spacing */
        margin-block: 1em;
    
        /* display */
        display: block;
    }

    .light-neomorphic .temp-field{
        /* size */
        width: 12rem;
        /* width: 30rem; */

        /* design */
        background-color: var(--secondary-color);
        border-radius: 10px;
        box-shadow: 
            inset 3px 3px 7px 0 var(--primary-shadow),
            inset -3px -3px 7px 0 var(--secondary-shadow);
        -webkit-appearance: none;
    }

    .light-neomorphic .temp-field::-webkit-slider-runnable-track{
        /* size */
        height: 20px;

        /* design */
        cursor: pointer;
        border-radius: 10px;
        border: 0px solid black;
        box-shadow: none;
        appearance: none;
    }

    .light-neomorphic .temp-field::-ms-track{
        /* size */
        height: 20px;

        /* design */
        cursor: pointer;
        border-radius: 10px;
        border: 0px solid black;
        box-shadow: none;
        appearance: none;
    }

    .light-neomorphic .temp-field::-webkit-slider-thumb{
        /* size */
        height: 20px;
        width: 20px;

        /* design */
        background-color: var(--secondary-color);
        box-shadow: 
            3px 3px 10px 0 var(--primary-shadow),
            -3px -3px 10px 0 var(--secondary-shadow),
            -3px 3px 10px 0 var(--primary-shadow);
            
        border-radius: 50%;
        border: 0px solid black;
        cursor: pointer;
        -webkit-appearance: none;

        /* position */
        margin-top: -0.5px;
    }

    .dark-neomorphic.temp-container{
        /* design */
        background-color: var(--secondary-color);

        /* size */
        padding: 1em;
    }

    .dark-neomorphic .temp-label{
        /* design */
        font-family: 'Poppins', sans-serif;
        font-weight: 300;
        font-size: clamp(12px, 1vw, 1rem);
        color: var(--primary-color);
        background-color: var(--secondary-color);
        /* outline: 1px solid brown; */

        /* spacing */
        margin-block: 1em;
    
        /* display */
        display: block;
    }

    .dark-neomorphic .temp-field{
        /* size */
        width: 12rem;
        /* width: 30rem; */

        /* design */
        background-color: var(--secondary-color);
        border-radius: 10px;
        box-shadow: 
            inset 3px 7px 8px 0 var(--primary-shadow),
            inset -2px -2px 5px -2px var(--secondary-shadow);
        -webkit-appearance: none;
    }

    .dark-neomorphic .temp-field::-webkit-slider-runnable-track{
        /* size */
        height: 20px;

        /* design */
        cursor: pointer;
        border-radius: 10px;
        border: 0px solid black;
        box-shadow: none;
        appearance: none;
    }

    .dark-neomorphic .temp-field::-ms-track{
        /* size */
        height: 20px;

        /* design */
        cursor: pointer;
        border-radius: 10px;
        border: 0px solid black;
        box-shadow: none;
        appearance: none;
    }

    .dark-neomorphic .temp-field::-webkit-slider-thumb{
        /* size */
        height: 20px;
        width: 20px;

        /* design */
        background-color: var(--secondary-color);
        box-shadow: 
            3px 2px 8px 1px var(--primary-shadow),
            -2px -1.5px 5px -1px var(--secondary-shadow);
            
        border-radius: 50%;
        border: 0px solid black;
        cursor: pointer;
        -webkit-appearance: none;

        /* position */
        margin-top: -0.5px;
    }
</style>