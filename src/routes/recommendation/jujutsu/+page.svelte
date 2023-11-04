<script>
    let animeList = [
        {
            name: "Gojo",
            image: "Gojo.jpg",
            info: "Information about Anime 1",
        },
        {
            name: "Sukuna",
            image: "Sukuna.jpg",
            info: "Information about Anime 2",
        },
        {
            name: "Nanami",
            image: "nanami.jpg",
            info: "Information about Anime 3",
        },
    ];
    let additionalInfo = "will put info here";
</script>

<svelte:head>
    <link rel="stylesheet" href="static/css/main.css" />
</svelte:head>

<div class="additional-info">
    <p>{additionalInfo}</p>
</div>

<div class="anime-container">
    {#each animeList as { name, image, info } (name)}
        <div class="anime-entry">
            <div class="image-container-jj">
                <img src={`../img/${image}`} alt={name} />
            </div>
            <div class="info-container">
                <h2>{name}</h2>
                <p>{info}</p>
            </div>
        </div>
    {/each}
</div>
