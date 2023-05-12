<template>
    <section id="about">
        <picture class="about-img">
            <source media="(max-width: 767px)" srcset="assets/home/mobile/image-small-team.jpg">
            <source media="(max-width: 1439px)" srcset="assets/home/tablet/image-small-team.jpg">
            <source media="(min-width: 1440px)" srcset="assets/home/desktop/image-small-team.jpg">
            <img src="assets/home/desktop/image-small-team.jpg" alt="">
        </picture>
        <div class="about-content">
            <h2>Small team,<br/> big ideas</h2>
            <NuxtLink to="/about" class="button button-default">
                About Us
                <svg width="24" height="20" viewBox="0 0 24 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M15 1L24 10L15 19" stroke="white" stroke-width="2"/><path d="M0 10H24" stroke="white" stroke-width="2"/></svg>
            </NuxtLink>
        </div>
    </section>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #about {
            position: relative;
            .about-img {
                filter: var(--image-filter);
            }
            .about-content {
                padding: 0 var(--mobile-x-padding);
                position: absolute;
                top: 0;
                height: 100%;
                display: flex;
                flex-direction: column;
                justify-content: center;
                gap: 3rem;
            }
            h2 {
                color: white;
            }
        }
    }
    @media screen and (min-width: 768px) {
        #about {
            padding: 0 var(--tablet-x-padding);
            .about-content {
                padding: 0 5rem;
            }
            h2 {
                font-size: 72px;
            }
        }
    }
    @media screen and (min-width: 1440px) {
        #about {
            padding: 0 var(--desktop-x-padding);
            .about-content {
                padding-left: 10rem;
            }
        }
    }
</style>