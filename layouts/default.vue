<template>
    <div>
        <Header></Header>
        <main>
            <Nuxt />
        </main>
        <Footer></Footer>
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
        --tablet-x-padding: calc((100vw - 573px)/2);
        --desktop-x-padding: calc((100vw - 1110px)/2);

        --image-filter: brightness(60%);
    }
    html {
        scroll-behavior: smooth;
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
        line-height: 24px;
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
        padding: 3rem;
        width: fit-content;
        text-decoration: none;
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
        &.button-secondary {
            background-color: var(--color-white);
            color: var(--color-primary);
        }
        &.button-small {
            width: 72px;
            height: 72px;
        }
        &.button-full {
            width: 100%;
        }
    }
    .button-group {
        display: flex;
        flex-direction: row;
        button {
            background-color: white;
            color: var(--color-med-gray);
            padding: 0;
            height: 72px;
            width: 72px;
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
        h2 {
            font-size: 48px;
        }
        h4 {
            font-size: 32px;
        }
        .page-tag {
            display: none;
        }
    }
    @media screen and (min-width: 768px) {
        h1 {
            display: block;
            font-size: 120px;
            color: var(--color-lighter-gray);
        }
        h2 {
            font-size: 96px;
        }
        .page-tag {
            display: flex;
            flex-direction: row;
            align-items: center;
            gap: 3rem;
            position: absolute;
            z-index: 10;
            top: 0rem;
            left: 8rem;
            transform: rotate(90deg);
            transform-origin: 0%;
            .tag-line {
                height: 1px;
                width: 104px;
                background-color: var(--color-light-gray);
            }
            .tag-label {
                font-size: 18px;
                font-weight: 500;
                color: var(--color-light-gray);
                text-transform: uppercase;
                letter-spacing: 18px;
            }
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
    }
</style>