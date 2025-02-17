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
        <div class="wishlist">
            <button href="#">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" width="18" height="18" stroke-width="2">
                <path d="M11.537 19.542l-7.037 -6.97a5 5 0 1 1 7.5 -6.566a5 5 0 0 1 8.212 5.693"></path>
                <path d="M19 22.5a4.75 4.75 0 0 1 3.5 -3.5a4.75 4.75 0 0 1 -3.5 -3.5a4.75 4.75 0 0 1 -3.5 3.5a4.75 4.75 0 0 1 3.5 3.5"></path>
                </svg>
                Verlanglijst
            </button>
        </div>
	</div>
</template>

<style>
.container--nav {
    flex-flow: row nowrap;
    align-items: center;
    justify-content: space-between;
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
    }
}

.wishlist {
    button {
        align-items: center;
        display: flex;
        flex-flow: row nowrap;
        font-weight: bold;
        transition: all .2s;
        svg {
            margin-right: .5rem;
        }
    }
    button:hover {
        background: #df8032;
    }
}
</style>
