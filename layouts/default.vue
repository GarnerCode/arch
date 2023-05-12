<template>
    <div>
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

        --transition: 0.3s ease;
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
    .button {
        border: none;
        font-size: 18px;
        font-weight: bold;
        padding: 2rem;
        cursor: pointer;
        transition: var(--transition);
        &.button-default {
            background-color: var(--color-primary);
            color: white;
            &:hover {
                background-color: var(--color-dark-gray);
            }
        }
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