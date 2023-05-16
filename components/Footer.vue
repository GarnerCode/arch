<template>
    <footer>
        <div class="logo-container">
            <NuxtLink to="/">
                <picture>
                    <source media="(max-width: 1439px)" srcset="assets/logo-light-small.svg">
                    <source media="(min-width: 1440px)" srcset="assets/logo-light.svg">
                    <img src="assets/logo.svg" alt="Arch Logo">
                </picture>
            </NuxtLink>
        </div>
        <ul class="nav-list">
            <li class="nav-list-item" v-for="(item, index) of navData" :key="index">
                <NuxtLink :to="item.route">
                    {{ item.label }}
                </NuxtLink>
            </li>
        </ul>
        <NuxtLink class="button button-default" to="/portfolio">
            See Our Portfolio
            <svg width="24" height="20" viewBox="0 0 24 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M15 1L24 10L15 19" stroke="white" stroke-width="2"/><path d="M0 10H24" stroke="white" stroke-width="2"/></svg>
        </NuxtLink>
    </footer>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        footer {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            margin-top: 15rem;
            background-color: var(--color-lighter-gray);
            padding: 0 var(--mobile-x-padding);
            padding-bottom: var(--mobile-x-padding);
            .logo-container {
                background-color: var(--color-primary);
                height: 120px;
                width: 120px;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                position: relative;
                bottom: 60px;
            }
            .nav-list {
                display: flex;
                flex-direction: column;
                gap: 4rem;
                a {
                    font-size: 18px;
                    font-weight: bold;
                    text-decoration: none;
                    color: var(--color-med-gray);
                }
            }
            .button {
                margin-top: 60px;
            }
        }
    }
    @media screen and (min-width: 768px) {
        footer {
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
            padding: 0;
            .logo-container {
                position: static;
            }
            .nav-list {
                flex-direction: row;
            }
            .button {
                margin: 0;
            }
        }
    }
    @media screen and (min-width: 1440px) {
        footer {
            margin: 0 var(--desktop-x-padding);
            margin-top: 15rem;
            .logo-container {
                width: 200px;
                height: 200px;
            }
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { navData } from '~/const/navData';

    export default defineComponent({
        name: 'Footer',
        data: () => {
            return {
                navData,
            }
        }
    })
</script>