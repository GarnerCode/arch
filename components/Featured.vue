<template>
    <section id="featured">
        <div class="section-header">
            <h2>Featured</h2>
            <NuxtLink class="button button-default" to="/portfolio">
                See All
                <svg width="24" height="20" viewBox="0 0 24 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M15 1L24 10L15 19" stroke="white" stroke-width="2"/><path d="M0 10H24" stroke="white" stroke-width="2"/></svg>
            </NuxtLink>
        </div>
        <div class="features-list">
            <div class="feature" v-for="(feature, index) of featuredData" :key="index">
                <picture class="feature-img">
                    <source media="(max-width: 767px)" :srcset="feature.image.mobile">
                    <source media="(max-width: 1439px)" :srcset="feature.image.tablet">
                    <source media="(min-width: 1440px)" :srcset="feature.image.desktop">
                    <img :src="feature.image.desktop" :alt="feature.title">
                </picture>
                <div class="feature-content">
                    <div class="feature-text">
                        <h4>{{ feature.title }}</h4>
                        <NuxtLink to="/portfolio">View All Projects</NuxtLink>
                    </div>
                    <div class="feature-count">
                    {{ index + 1 }}
                    </div>
                </div>
            </div>
            <NuxtLink class="button button-default" to="/portfolio">
                See All
                <svg width="24" height="20" viewBox="0 0 24 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M15 1L24 10L15 19" stroke="white" stroke-width="2"/><path d="M0 10H24" stroke="white" stroke-width="2"/></svg>
            </NuxtLink>
        </div>
    </section>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #featured {
            padding: 0 var(--mobile-x-padding);
            .section-header {
                margin-bottom: 5rem;
                a {
                    display: none;
                }
            }
            .features-list {
                display: flex;
                flex-direction: column;
                gap: 3rem;
                a {
                    width: calc(100% - 6rem);
                }
            }
            .feature {
                position: relative;
                img {
                    filter: var(--image-filter);
                    width: 100%;
                }
                .feature-content {
                    position: absolute;
                    top: 0;
                    height: calc(100% - 6rem);
                    width: calc(100% - 8rem);
                    padding: 3rem 4rem;
                    display: flex;
                    flex-direction: column;
                    justify-content: flex-end;
                }
                .feature-text {
                    width: 300px;
                }
                h4, a {
                    color: white;
                }
                a {
                    margin: 1rem 0;
                    text-decoration: none;
                    display: block !important;
                    font-size: 18px;
                    transition: var(--transition);
                    &:hover {
                        letter-spacing: 5px;
                    }
                }
                .feature-count {
                    display: none;
                }
            }
        }
    }
    @media screen and (min-width: 768px) {
        #featured {
            padding: 0 var(--tablet-x-padding);
            .section-header {
                display: flex;
                flex-direction: row;
                justify-content: space-between;
                a {
                    display: flex;
                }
            }
            .feature {
                .feature-content {
                    flex-direction: row;
                    justify-content: space-between;
                    align-items: flex-end;
                }
                .feature-count {
                    display: block;
                    color: white;
                    opacity: 0.5;
                    font-size: 250px;
                    font-weight: bold;
                }
            }
            .features-list {
                a {
                    display: none;
                }
            }
        }
    }
    @media screen and (min-width: 1440px) {
        #featured {
            padding: 0 var(--desktop-x-padding);
            .features-list {
                flex-direction: row;
            }
            .feature {
                .feature-img {
                    img {
                        width: 100%;
                    }
                }
                .feature-content {
                    flex-direction: column-reverse;
                    align-items: flex-start;
                    .feature-count {
                        align-self: flex-end;
                        position: absolute;
                        right: -1.5rem;
                        top: 3rem;
                    }
                }
            }
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { featuredData } from '~/const/portfolioData';

    export default defineComponent({
        name: 'Featured',
        data: () => {
            return {
                featuredData,
            }
        }
    })
</script>