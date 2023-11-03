<svelte:head>
    <link rel="stylesheet" href="css/main.css" />
</svelte:head>

<slot />

<nav class="nav">
    <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/characters">Characters</a></li>
        <li>
            <a href="/recommendation">Recommendation</a>
            <ul class="dropdown">
                <li><a href="/recommendation/jujutsu">Jujutsu Kaisen</a></li>
                <li><a href="/recommendation/one-piece">One Piece</a></li>
            </ul>
        </li>
        <li><a href="/">Contact</a></li>
    </ul>
</nav>
