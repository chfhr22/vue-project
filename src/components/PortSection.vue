<script setup>
import { portText } from "@/constants/index";
</script>
<template>
    <section id="port">
        <div class="port__inner">
            <div class="port__title">
                portfolio <em>포폴 작업물</em>
            </div>
            <div class="port__wrap">
                <div v-for="(port, key) in portText" :key="key" class="port__item" :class="'p' + (key + 1)">
                    <span class="num">{{ port.num }}.</span>
                    <a :href="port.code">
                        <img :src=port.img alt="">
                    </a>
                    <h3 class="title">{{ port.title }}</h3>
                    <p class="desc">
                        {{ port.desc }}
                    </p>
                    <a :href="port.view" class="view">사이트 보기</a>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);

export default {
    mounted: function () {
        this.scrollAnimation();
    },
    methods: {
        scrollAnimation() {
            const horSection = gsap.utils.toArray(".port__item");

            gsap.to(horSection, {
                xPercent: -120 * (horSection.length - 1),
                ease: "none",
                scrollTrigger: {
                    trigger: "#port",
                    start: "top 56px",
                    end: "+=3000",
                    pin: true,
                    scrub: 1,
                    markers: false,
                    invalidateOnRefresh: true,
                    anticipatePin: 1
                }
            });
        }
    }
}
</script>

<style lang="scss">
#port {
    width: 100%;
    overflow: hidden;
}

.port__inner {
    padding: 1vh;
    color: var(--mainFont-color);
}

.port__wrap {
    display: flex;
    flex-wrap: wrap;
    width: 7000px;
}

.port__title {
    position: sticky;
    top: 62px;
    left: 0;
    width: 48%;
    height: 5.7vw;
    font-size: 4vw;
    font-weight: 900;
    line-height: 1.6;
    text-transform: uppercase;
    font-family: var(--intro-sub-font);
    border-bottom: 0.5vw solid;
    white-space: nowrap;
    margin-bottom: 3vh;
}

.port__title em {
    font-family: var(--mainKor-font);
    font-size: 1.2rem;
    font-weight: 400;
}

.port__item {
    width: 500px;
    height: 70vh;
    margin-right: 20px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    position: relative;
    margin-top: 43px;
}

.port__item .num {
    font-size: 3vh;
    font-weight: 500;
    position: absolute;
    left: 20px;
    top: 30px;
}

.port__item img {
    width: 450px;
    height: 30vh;
    background-color: #fff;
    margin-top: 50px;
}

.port__item .title {
    font-size: 2vw;
    border-bottom: 2px solid var(--mainFont-color);
    width: 90%;
    margin-bottom: 20px;
    text-align: center;
}

.port__item .desc {
    width: 90%;
}

.port__item .view {
    width: 90%;
    height: 50px;
    line-height: 50px;
    display: inline-block;
    border: 1px solid var(--black);
    text-align: center;
    margin: 10px 0;
}

.port__item:nth-child(odd) {
    background-color: var(--subBg500);
}

.port__item:nth-child(even) {
    background-color: var(--subBg400);
}
</style>