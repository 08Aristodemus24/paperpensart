<script>
    import Hero from "$lib/Hero.svelte";

    const images = [
        '0983.jpg',
        'IMG_2530.jpg', 
        'IMG_0470.png', 
        'IMG_0513.jpg', 
        'IMG_1451.png', 
        'IMG_0469.png', 
        'IMG_2872.jpg', 
        'IMG_3751.jpg', 
        'IMG_4993.jpg', 
        'IMG_5393.png', 
        'IMG_7288.jpg', 
        'IMG_9774.jpg', 
        'IMG_9897.jpg', 
        'Waiting.jpg'
    ]
</script>

<!-- Landing Hero Section -->
<Hero>
    <div class="featured-image-container">
        <div class="landing-content">
            <h1 class="landing-title">Lara Cueva</h1>
            <p class="landing-subtitle">Illustrator & Visual Storyteller</p>
            <p class="landing-description">
                Crafting narratives through vibrant colors and expressive lines. 
                Exploring the intersection of digital art and visual communication.
            </p>
            <a href="#featured-section" class="landing-cta">View Portfolio</a>
        </div>
    </div>
</Hero>

<!-- Featured Work Section -->
<Hero section_name="featured">
    <div class="featured-header-container">
        <h2 class="featured-header">Featured Works</h2>
        <p class="featured-subheader">A selection of recent illustrations and concept pieces</p>
    </div>
    
    <div class="grid-container">
        {#each images as image, index}
            <div class={`featured-grid-${index + 1}`} data-grid-index={`${index + 1}`}>
                <img class="featured-grid-image" src={`https://raw.githubusercontent.com/08Aristodemus24/lalais-portfolio/master/client-side/src/assets/mediafiles/compressed/${image}`} alt="Portfolio piece ${index + 1}"/>
            </div>
        {/each}
    </div>
</Hero>