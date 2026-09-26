<script>
    import Hero from "$lib/Hero.svelte";

    // Create an array of 14 empty objects to simulate the grid structure
    const placeholders = Array.from({ length: 14 }, (_, i) => i + 1);
</script>

<Hero section_name="illustration">
    <div id="illustration-section">
        <h2>Illustrations</h2>
        <div class="grid-container">
            {#each placeholders as index}
                <div class={`featured-grid-${index}`}>
                    <div class="illustration-placeholder">
                        <!-- Placeholder content -->
                        <span>Illustration {index}</span>
                    </div>
                </div>
            {/each}
        </div>
    </div>
</Hero>