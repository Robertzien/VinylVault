<template>
	<div class="container container--nav">
		<div class="navbar__logo">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" width="28" height="28" stroke-width="2">
            <path d="M16 3.937a9 9 0 1 0 5 8.063"></path>
            <path d="M12 12m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
            <path d="M20 4m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
            <path d="M20 4l-3.5 10l-2.5 2"></path>
            </svg>
            <h3>VinylVault</h3>
        </div>
        <div class="navbar__nav">
            <ul class="navbar__links">
                <li>
                    <a href="#">Home</a>
                </li>
                <li>
                    <a href="#">Link1</a>
                </li>
                <li>
                    <a href="#">Link2</a>
                </li>
                <li>
                    <a href="#">Link3</a>
                </li>
            </ul>
        </div>
	</div>
</template>

<style>
.container--nav {
    flex-flow: row nowrap;
    align-items: center;
}

.navbar__logo {
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    svg {
        margin-right: .5rem;
    }
}

.navbar__links {
    display: flex;
    flex-flow: row nowrap;
    list-style: none;
    li {
        margin-right: 2rem;
        a {
            text-decoration: none;
        }
    }
}
</style>
