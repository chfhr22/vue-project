<script setup>
import { contactText } from "@/constants/index";
</script>
<template>
    <section id="contact">
        <div class="contact__inner">
            <h2 class="contact__title">Contact</h2>

            <div class="contact__lines" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
            <div class="contact__text">
                <div class="text">
                    <div v-for="(cont, key) in contactText" :key="key">
                        <a href="cont.link">{{ cont.title }}</a>
                    </div>
                </div>
            </div>
            <div class="contact__lines bottom" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
        </div>
    </section>
</template>

<style lang="scss">
#contact {
    height: 100vh;
}

.contact__inner {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: flex-start;
    justify-content: flex-end;
    flex-direction: column;
    padding: 1vw;
}

.contact__title {
    font-family: var(--intro-font);
    font-size: 10.12vw;
    text-transform: uppercase;
    font-weight: 800;
    color: var(--mainFont-color);
    line-height: 1.05;
    letter-spacing: -0.1vw;
    white-space: nowrap;
}

.contact__lines {
    display: block;
    width: 100%;
}

.contact__lines .line {
    display: block;
    width: 100%;
    height: 1px;
    background-color: var(--mainFont-color);
    margin-bottom: 0.5vw;
}

.contact__lines.bottom {
    display: none;
}

.contact__lines .line:nth-child(1) {
    height: 7px;
}

.contact__lines .line:nth-child(2) {
    height: 6px;
}

.contact__lines .line:nth-child(3) {
    height: 5px;
}

.contact__lines .line:nth-child(4) {
    height: 4px;
}

.contact__lines .line:nth-child(5) {
    height: 3px;
}

.contact__lines .line:nth-child(6) {
    height: 2px;
}

.contact__lines .line:nth-child(7) {
    height: 1px;
}

.contact__lines.bottom .line:nth-child(1) {
    height: 1px;
}

.contact__lines.bottom .line:nth-child(2) {
    height: 2px;
}

.contact__lines.bottom .line:nth-child(3) {
    height: 3px;
}

.contact__lines.bottom .line:nth-child(4) {
    height: 4px;
}

.contact__lines.bottom .line:nth-child(5) {
    height: 5px;
}

.contact__lines.bottom .line:nth-child(6) {
    height: 6px;
}

.contact__lines.bottom .line:nth-child(7) {
    height: 7px;
}

.contact__text {
    background-color: var(--mainFont-color);
    height: 35vh;
    /* padding: 10vw 0; */
    width: 100%;
    color: var(--mainBg-color);
    font-size: 3vw;
    line-height: 1;
    font-family: var(--intro-sub-font);
    position: relative;
}

.contact__text .text {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-transform: uppercase;
    text-decoration: underline;
    /* height: inherit; */
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    z-index: 1;
}

.contact__text .text div {
    margin-bottom: 20px;
}

@media (max-width: 800px) {
    .contact__title {
        display: none;
    }

    .contact__inner {
        justify-content: center;
    }

    .contact__lines.bottom {
        display: block;
    }

    .contact__text .text {
        font-size: 30px;
    }
}
</style>
