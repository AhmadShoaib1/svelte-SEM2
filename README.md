# create-svelte

Everything you need to build a Svelte project, powered by [`create-svelte`](https://github.com/sveltejs/kit/tree/master/packages/create-svelte).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npm create svelte@latest

# create a new project in my-app
npm create svelte@latest my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.
>
> ## Overview of the Project
The website is about anime in general in the first/main page it displays 6 chracater of anime series Naruto and they are also set as a button which if you click on it will take you to a new window with google search of the name, which i most likely will change to a better websites.
The second page is about Quotes, it lets you search an anime name and it will display a random quote from that anime series and also name the character, and there is a second api which is used for the picture i am planning to change the because it does not have enough pictures for anime, it is high quality but there just not enough. 
Then there is my 3rd and 4th page which about Jujutsu Kaisen and One Piece which has button to a website where you can watch the anime, but it is not gooing to open if your not using a private connection(otago poly computer won't open the anime website i have linked to the button).


## Languages
The website is created using Javascript, HTML and css.
honestly the javascript was the hardest part of the whole project.

## Purpose fo the Repo

To create a functional website using sveltekit to a proffisionall standards.
In this repo you will find the website i designed from scratch and i obviously lack imagination and creativity in it, but still i feel proud of it.

## Technologies used
API, we had to fetch some data  from an API which i used 2 different API in one of the pages(Quote), the first API searches a quote with the character name and anime name, and the second API will be used for the picture of the anime.

## Known Bugs
The Contact button exist in Nav bar but it does not lead to anywhere.
And my main bugs right now would be if the user resize the window the pictures in main page doesnt fit their container nicely, haven't done proper media query for them.

## Future Roadmap
find a better API for fetching the picture
finish the Contact page which is not done yet
Add proper media query for the images so they fit properly when resized
