<script>
    let animeList = [
        {
            name: "Gojo",
            image: "Gojo.jpg",
            info: [
                "Limitless Cursed Technique, manipulating space.",
                "Six Eyes enhance perception, making him unbeatable in combat.",
                "Combines strategic intelligence with overwhelming strength.",
                "Wears a blindfold to suppress his power; removing it unleashes immense strength.",
                "Known as the 'Strongest Jujutsu Sorcerer' in the series.",
                "Charismatic and humorous personality, a fan favorite.",
                "Iconic design with white hair and striking blue eyes.",
            ],
        },
        {
            name: "Sukuna",
            image: "Sukuna.jpg",
            info: [
                "Sukuna, also known as Ryomen Sukuna, is a major antagonist in 'Jujutsu Kaisen.'",
                "An ancient and immensely powerful Cursed Spirit, he is feared as the 'King of Curses' with a dark and malevolent reputation.",
                "Sukuna possesses a collection of powerful Cursed Techniques and immense strength.",
                "He is divided into twenty fingers, each containing a portion of his power.",
                "Yuji Itadori, the protagonist, unwittingly consumes one of Sukuna's fingers, leading to a significant turning point in the story.",
                "Sukuna's presence and influence play a pivotal role in the series' narrative.",
                "Known for his sadistic and cunning nature, Sukuna is a formidable adversary.",
                "He has an intricate design with distinctive facial markings and a fearsome demeanor.",
                "Sukuna's existence adds depth to the series, exploring the consequences of Cursed Energy.",
            ],
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
<body>
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
</body>
