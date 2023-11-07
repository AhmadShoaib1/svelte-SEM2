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
      name: "Nanami Kento",
      image: "nanami.jpg",
      info: [
        "Nanami Kento is a character in 'Jujutsu Kaisen.'",
        "A jujutsu sorcerer known for his pragmatic and no-nonsense approach to combat.",
        "Nanami is a former salaryman who became a jujutsu sorcerer, adding a unique twist to his character.",
        "Possesses exceptional analytical skills and a strong sense of duty.",
        "His signature technique is the 'Ratio Technique,' allowing him to assess and exploit the efficiency of cursed techniques.",
        "Despite his stern exterior, Nanami is a principled and honorable individual.",
        "He becomes a mentor to Yuji Itadori and plays a crucial role in guiding the protagonist.",
        "Nanami's character brings a sense of realism to the series, navigating the challenges of the jujutsu sorcerer world with a practical mindset.",
        "With a distinctive appearance and calm demeanor, Nanami Kento has become a fan-favorite character.",
      ],
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
      <div class="anime-entry grid">
        <div class="image-container-jj s1">
          <img src={`../img/${image}`} alt={name} />
        </div>
        <div class="s2">
          <h2>{name}</h2>
        </div>
        <div class="s3">
          <ul>
            {#each info as item (item)}
              <li>{item}</li>
            {/each}
          </ul>
        </div>
      </div>
    {/each}
  </div>
</body>
