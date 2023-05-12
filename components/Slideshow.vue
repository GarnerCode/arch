<template>
    <div class="slideshow">
        <div class="slides-container">
            <div class="slide" v-for="(slide, index) of filterActiveSlide()" :key="index">
                <img :src="slide.image" :alt="`${slide.title} facade`">
                <div class="slide-content">
                    <h2>{{ slide.title }}</h2>
                    <p>{{ slide.description }}</p>
                    <NuxtLink to="'/portfolio'" class="button button-default">
                        See Our Portfolio
                        <svg width="24" height="20" viewBox="0 0 24 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M15 1L24 10L15 19" stroke="white" stroke-width="2"/><path d="M0 10H24" stroke="white" stroke-width="2"/></svg>
                    </NuxtLink>
                </div>
            </div>
        </div>
        <div class="button-group">
            <button 
            @click="setActiveSlide(index)"
                class="button button-small" 
                :class="{'active': item.active}" 
                v-for="(item, index) of slideShowData" 
                :key="index">
                {{ index + 1 }}
            </button>
        </div>
    </div>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        .slideshow {
            display: none;
        }
    }
    @media screen and (min-width: 1440px) {
        .slideshow {
            display: block;
            .slides-container {
                display: flex;
                flex-direction: row;
                max-width: 1110px;
            }
            .slide {
                position: relative;
            }
            img {
                filter: var(--image-filter);
            }
            .slide-content {
                position: absolute;
                top: 0;
                left: 0;
                height: 100%;
                width: 50%;
                display: flex;
                flex-direction: column;
                justify-content: center;
                padding-left: 17rem;
            }
            h2, p {
                color: white;
            }
            .button-group {
                position: relative;
                bottom: 73px;
                right: 72px;
            }
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { slideShowData } from '~/const/portfolioData';

    export default defineComponent({
        name: 'Slideshow',
        data: () => {
            return {
                slideShowData,
            }
        },
        methods: {
            setActiveSlide(target: number): void {
                this.slideShowData.forEach((slide: any, index) => {
                    slide.active = false;
                    if (target === index) {
                        slide.active = true;
                    }
                });
            },
            filterActiveSlide(): Array<any> {
                return this.slideShowData.filter((slide: any) => {
                    return slide.active;
                });
            }
        }
    })
</script>