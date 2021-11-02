<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fun Card</title>
</head>

<body>
    <div class="card">
        <div class="card-content">
            <h2 class="card-title">Something Awesome</h2>
            <p class="card-body">Lorem ipsum dolor sit amet consectetur adipisicing elit. Corrupti aliquid?</p>
            <a href="#" class="button">Learn More</a>
        </div>
    </div>
</body>
<style>
    :root {
    --clr-neutral-900: hsl(207, 19%, 9%);
    --clr-neutral-100: hsl(0, 0%, 100%);
    --clr-accent-400: hsl(142, 90%, 61%);
}

*,
*::before,
*::after {
    box-sizing: border-box;
}

body {
    display: grid;
    min-height: 100vh;
    place-items: center;
    line-height: 1.6;
    background: var(--clr-neutral-900);
    font-family: sans-serif;
}

.card {
    color: var(--clr-neutral-100);
    background-image: url("img/card-bg.jpeg");
    background-size: cover;
    padding: 8rem 0 0;
    max-width: 35ch;
    border-radius: 0.5rem;
    overflow: hidden;

    transition: transform 500ms ease;
}

.card:hover {
    transform: scale(1.05);
}

.card-content {
    --padding: 1.5rem;
    padding: var(--padding);
    background: linear-gradient(
        hsl(0 0% 0% / 0),
        hsl(20 0% 0% / 0.3) 20%,
        hsl(0 0% 0% / 1)
    );
    transform: translateY(65%);
    transition: transform 500ms ease;
}

.card-content > * {
    opacity: 0;
    transition: opacity 500ms linear;
}

.card:hover .card-content {
    transform: translateY(0);
}

.card:hover .card-content > * {
    opacity: 1;
}

.card-title {
    position: relative;
    width: max-content;
}

.card-title::after {
    content: "";
    position: absolute;
    height: 3px;
    left: calc(var(--padding) * -1);
    bottom: -2px;
    width: calc(100% + var(--padding));
    background: var(--clr-accent-400);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 500ms ease;
}

.card:hover .card-title::after {
    transform: scaleX(1);
}

.card-body {
    color: rgb(255 255 255 / 0.85);
}

.button {
    cursor: pointer;
    display: inline-block;
    text-decoration: none;
    color: var(--clr-neutral-900);
    background-color: var(--clr-accent-400);
    padding: 0.5em 1.25em;
    border-radius: 0.25em;
}

.button:hover,
.button:focus {
    background-color: var(--clr-neutral-100);
}
</style>
</html>
