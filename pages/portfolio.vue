<template>
    <div class="portfolio-page">
        <div class="projects-container">
            <div class="project" v-for="(project, index) of portfolioData" :key="index">
                <img class="project-img img-mobile" :src="project.image.mobile" :alt="`${project.title} facade`">
                <img class="project-img img-tablet" :src="project.image.tablet" :alt="`${project.title} facade`">
                <img class="project-img img-desktop" :src="project.image.desktop" :alt="`${project.title} facade`">
                <div class="project-text">
                    <div class="project-title">
                        {{ project.title }}
                    </div>
                    <div class="project-date">
                        {{ project.date }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        .portfolio-page {
            padding: 0 var(--mobile-x-padding);
            .projects-container {
                display: flex;
                flex-direction: column;
                gap: 3rem;
                .project {
                    position: relative;
                }
                .project-img {
                    width: 100%;
                    filter: var(--image-filter);
                }
                .img-tablet {
                    display: none;
                }
                .img-desktop {
                    display: none;
                }
                .project-text {
                    position: absolute;
                    bottom: 4rem;
                    left: 3rem;
                    display: flex;
                    flex-direction: column;
                    gap: 1rem;
                }
                .project-title {
                    font-size: 32px;
                    color: white;
                    font-weight: bold;
                }
                .project-date {
                    font-size: 18px;
                    color: white;
                    opacity: 0.75;
                    font-weight: medium;
                }
            }
        }
    }
    @media screen and (min-width: 768px) {
        .portfolio-page {
            padding: 0 var(--tablet-x-padding);
            .projects-container {
                .project-img {
                    width: 100%;
                }
                .img-mobile {
                    display: none;
                }
                .img-tablet {
                    display: block;
                }
            }
        }
    }
    @media screen and (min-width: 1440px) {
        .portfolio-page {
            padding: 0 var(--desktop-x-padding);
            .projects-container {
                display: grid;
                grid-template-columns: 1fr 1fr 1fr;
                gap: 3rem;
                .img-tablet {
                    display: none;
                }
                .img-desktop {
                    display: block;
                }
            }
        }
    }
</style>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { portfolioData } from '~/const/portfolioData';

    export default defineComponent({
        name: 'PortfolioPage',
        data: () => {
            return {
                portfolioData,
            }
        }
    })
</script>