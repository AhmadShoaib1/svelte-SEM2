<svelte:head>
    <link rel="stylesheet" href="css/main.css" />
</svelte:head>

<slot />

<nav class="nav">
    <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/character">Characters</a></li>
        <li>
            <a href="/recommendation">Recommendation</a>
            <ul class="dropdown">
                <li><a href="/recommendation/option1">Option 1</a></li>
                <li><a href="/recommendation/option2">Option 2</a></li>
            </ul>
        </li>
        <li><a href="/">Contact</a></li>
    </ul>
</nav>
