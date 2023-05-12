<template>
    <section id="welcome">
        <h1>Welcome</h1>
        <div class="welcome-content">
            <div class="welcome-text">
                <h2>Welcome to Arch Studio</h2>
                <div class="paragraphs">
                    <p>We have a unique network and skillset to help bring your projects to life. Our small team of highly skilled individuals combined with our large network put us in a strong position to deliver exceptional results.</p>
                    <p>Over the past 10 years, we have worked on all kinds of projects. From stations to high-rise buildings, we create spaces that inspire and delight.</p>
                    <p>We work closely with our clients so that we understand the intricacies of each project. This allows us to work in harmony the surrounding area to create truly stunning projects that will stand the test of time.</p>
                </div>
            </div>
        <img src="assets/home/desktop/image-welcome.jpg" alt="Building facade">
        </div>
    </section>
</template>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #welcome {
            padding: 0 var(--mobile-x-padding);
            img {
                display: none;
            }
        }
    }
    @media screen and (min-width: 768px) {
        #welcome {
            padding: 0 var(--tablet-x-padding);
        }
    }
    @media screen and (min-width: 1440px) {
        #welcome {
            padding: 0 var(--desktop-x-padding);
            position: relative;
            h1 {
                position: absolute;
                bottom: 440px;
                z-index: 5;
            }
            h2 {
                position: relative;
                z-index: 6;
            }
            .welcome-content {
                display: flex;
                flex-direction: row;
                align-items: flex-end;
            }
            .welcome-text {
                padding: 0 10rem;
                height: fit-content;
            }
            img {
                display: block;
                position: relative;
                z-index: 4;
            }
        }
    }
</style>