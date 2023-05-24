<template>
    <div>
        <header>
            <div @click="navToggled = false" class="logo-container">
                <NuxtLink to="/">
                    <svg xmlns="http://www.w3.org/2000/svg" width="97" height="40"><path fill="#1B1D23" d="M10.822 39.27l2.26-6.256h13.836l2.26 6.255H40L24.658 1.6h-9.316L0 39.268h10.822zM23.493 24.2h-6.986L20 15.252l3.493 8.95zm21.804 15.07V27.807c0-.776.22-1.499.662-2.169a5.14 5.14 0 011.746-1.632A4.51 4.51 0 0150 23.379c.64 0 1.343.13 2.112.388.769.259 1.434.601 1.998 1.028l3.972-7.991c-.654-.487-1.484-.883-2.488-1.188-1.005-.304-1.956-.456-2.854-.456-1.385 0-2.729.354-4.03 1.061-1.301.708-2.44 1.694-3.413 2.957V15.89h-9.498v23.38h9.498zm18.995.73c1.507 0 2.942-.21 4.304-.628 1.362-.418 2.439-.91 3.23-1.472l-3.105-6.393c-.289.198-.688.377-1.198.536-.51.16-1.07.24-1.678.24-.99 0-1.85-.217-2.58-.65a4.449 4.449 0 01-1.678-1.724 4.806 4.806 0 01-.582-2.33c0-.669.163-1.369.49-2.1.328-.73.845-1.347 1.553-1.849s1.625-.753 2.751-.753c1.187 0 2.161.258 2.922.776l3.105-6.393c-.76-.578-1.841-1.073-3.242-1.484a15.324 15.324 0 00-4.337-.616c-1.903 0-3.665.346-5.286 1.039-1.62.692-3.029 1.628-4.224 2.808a13.053 13.053 0 00-2.785 3.995 11.177 11.177 0 00-.993 4.6c0 1.69.354 3.285 1.062 4.784.707 1.5 1.678 2.82 2.91 3.961a13.79 13.79 0 004.258 2.683c1.606.647 3.307.97 5.103.97zm14.703-.73V26.392c0-.792.16-1.477.48-2.055a3.374 3.374 0 011.347-1.347c.578-.32 1.248-.48 2.01-.48 1.156 0 2.084.354 2.784 1.062.7.708 1.05 1.648 1.05 2.82v12.876h9.498V24.338c0-1.75-.41-3.314-1.232-4.692a9.088 9.088 0 00-3.345-3.276c-1.408-.807-3.003-1.21-4.783-1.21-1.4 0-2.782.255-4.144.765a12.064 12.064 0 00-3.665 2.157V0h-9.497v39.27h9.497z"/></svg>
                </NuxtLink>
            </div>
            <ul class="nav-list">
                <li class="nav-list-item" v-for="(nav, index) of navData" :key="index">
                    <NuxtLink :to="nav.route">
                        {{ nav.label }}
                    </NuxtLink>
                </li>
            </ul>
            <div class="mobile-nav-toggle" :class="{'toggled': navToggled}" @click="navToggled = !navToggled">
                <div class="line1"></div>
                <div class="line2"></div>
                <div class="line3"></div>
            </div>
        </header>
        <Transition name="fade" mode="out-in">
            <div @click="navToggled = false" class="mobile-nav-backdrop" v-if="navToggled"></div>
        </Transition>
        <Transition name="slide" mode="out-in">
            <ul class="mobile-nav-list" v-if="navToggled">
                <li @click="navToggled = !navToggled" class="nav-list-item" v-for="(nav, index) of navData" :key="index">
                    <NuxtLink :to="nav.route">
                        {{ nav.label }}
                    </NuxtLink>
                </li>
            </ul>
        </Transition>
    </div>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        header {
            background-color: white;
            padding: 0 var(--mobile-x-padding);
            position: relative;
            z-index: 10;
            height: 12rem;
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
            .nav-list {
                display: none;
            }
            .mobile-nav-toggle {
                cursor: pointer;
                div {
                    width: 24px;
                    height: 3px;
                    background-color: var(--color-primary);
                    margin: 5px;
                    transition: all 0.3s ease;
                }
                &.toggled {
                    .line1 {
                        transform: rotate(-45deg) translate(-5px, 6px);
                    }
                    .line2 {
                        opacity: 0;
                    }
                    .line3 {
                        transform: rotate(45deg) translate(-5px, -6px);
                    }
                }
            }
        }
        .mobile-nav-backdrop {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: 9;
            background-color: var(--color-backdrop);
        }
        .mobile-nav-list {
            position: fixed;
            top: 12rem;
            right: 0;
            background-color: white;
            z-index: 9;
            padding: 8rem;
            padding-right: 18rem;
            display: flex;
            flex-direction: column;
            gap: 5rem;
            a {
                text-decoration: none;
                font-size: 32px;
                color: var(--color-primary);
                font-weight: bold;
                line-height: 40px;
            }
        }
    }
    @media screen and (min-width: 768px) {
        header {
            padding: 0 var(--tablet-x-padding);
            justify-content: flex-start;
            gap: 8rem;
            .nav-list {
                display: flex;
                flex-direction: row;
                gap: 8rem;
                a {
                    font-size: 18px;
                    font-weight: bold;
                    text-decoration: none;
                    color: var(--color-med-gray);
                }
            }
            .mobile-nav-toggle {
                display: none;
            }
        }
    }
    @media screen and (min-width: 1440px) {
        header {
            padding: 0 var(--desktop-x-padding);
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { navData } from '@/const/navData';

    export default defineComponent({
        name: 'Header',
        data: () => {
            return {
                navData,
                navToggled: false,
            }
        },
    })
</script>