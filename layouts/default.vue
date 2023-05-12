<template>
    <div>
        <Header></Header>
        <main>
            <Nuxt />
        </main>
    </div>
</template>

<style lang="scss">
@import 'static/assets/styles.scss';

    :root {
        --color-primary: #1B1D23;
        --color-dark-gray: #60636D;
        --color-med-gray: #7D828F;
        --color-light-gray: #C8CCD8;
        --color-lighter-gray: #EEEFF4;
        --color-red: #DF5656;
        --color-backdrop: rgba(0,0,0,0.5);

        --transition: 0.3s ease;
        --mobile-x-padding: 5rem;
    }
    body {
        font-family: 'League Spartan', sans-serif;
        margin: 0;
    }
    h1, h2, h3, h4 {
        font-weight: bold;
        margin: 0;
    }
    h2, h3, h4 {
        color: var(--color-primary);
    }
    p {
        color: var(--color-dark-gray);
        font-size: 18px;
        font-weight: 500;
    }
    ul {
        list-style: none;
        padding: 0;
        margin: 0;
    }
    .button {
        border: none;
        font-size: 18px;
        font-weight: bold;
        cursor: pointer;
        transition: var(--transition);
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        gap: 2rem;
        width: 177px;
        height: 72px;
        &.button-default {
            background-color: var(--color-primary);
            color: white;
            &:hover {
                background-color: var(--color-dark-gray);
            }
            &:active {
                background-color: var(--color-light-gray);
            }
        }
        &.button-small {
            width: 72px;
        }
    }
    .button-group {
        display: flex;
        flex-direction: row;
        button {
            background-color: white;
            color: var(--color-med-gray);
            &:hover {
                background-color: var(--color-lighter-gray);
            }
            &.active {
                background-color: var(--color-primary);
                color: white;
            }
        }
    }
    .slide-enter, .slide-leave-to {
        opacity: 0;
        transform: translateX(2rem);
    }
    .slide-enter-active, .slide-leave-active {
        transition: all 0.3s ease;
    }
    .fade-enter, .fade-leave-to {
        opacity: 0;
    }
    .fade-enter-active, .fade-leave-active {
        transition: all 0.3s ease;
    }
    @media screen and (min-width: 0px) {
        h1 {
            display: none;
        }
    }
    @media screen and (min-width: 768px) {
        h1 {
            display: block;
            font-size: 120px;
            color: var(--color-lighter-gray);
        }
    }
    @media screen and (min-width: 1440px) {
        h1 {
            font-size: 250px;
        }
        h2 {
            font-size: 96px;
        }
        h3 {
            font-size: 72px;
        }
        h4 {
            font-size: 32px;
        }
    }
</style>