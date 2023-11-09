<script setup>
import { siteText } from "@/constants/index";
</script>
<template>
    <section id="site">
        <div class="site__inner">
            <div class="site__title">
                Site Coding <em>나의 작업물</em>
            </div>
            <div class="site__wrap">
                <div v-for="(site, key) in siteText" :key="key" class="site__item" :class="'s' + (key + 1)">
                    <span class="num">{{ key + 1 }}. </span>
                    <div class="text">
                        <div>{{ site.text[0] }}</div>
                        <div>{{ site.text[1] }}</div>
                        <div>{{ site.text[2] }}</div>
                    </div>
                    <h3 class="title">
                        {{ site.title }}
                    </h3>
                    <div class="btn">
                        <a href="site.code">code</a>
                        <a href="side.view">view</a>
                    </div>
                    <div class="info">
                        <span>{{ site.info[0] }}</span>
                        <span>{{ site.info[1] }}</span>
                        <span>{{ site.info[2] }}</span>
                    </div>
                </div>

            </div>
        </div>
    </section>
</template>

<style lang="scss">
.site__inner {
    padding: 1vw;
    color: var(--mainFont-color);
}

.site__title {
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
}

.site__title em {
    font-family: var(--mainKor-font);
    font-size: 1.2rem;
    font-weight: 400;
}

.site__item {
    width: 100%;
    height: 60vw;
    background-color: #ccc;
    position: sticky;
    left: 0;
    padding: 1vw;
}

.site__item .num {
    font-size: 5vw;
    font-weight: 800;
}

.site__item .text {
    font-size: 2.5vw;
    font-weight: 600;
    line-height: 2;
    display: block;
    /* display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center; */
}

.site__item .title {
    font-size: 2vw;
}

.site__item .btn {
    display: inline-block;
    padding: 7px 20px;
    border: 1px solid #000;
    border-radius: 30px;
    margin: 3vw;
}

.site__item .btn:hover {
    background-color: #000;
    color: #fff;
}

.site__item .btn a {
    text-transform: uppercase;
    font-family: var(--mainEng-font);
    font-weight: 500;
}

.site__item .info {
    display: flex;
    flex-direction: column;
    justify-content: right;
    text-align: right;
    font-size: 2vw;
    font-weight: 600;
}

.site__item.s1 {
    background-color: var(--subBg300);
    top: 180px;
}

.site__item.s2 {
    background-color: var(--subBg400);
    top: 200px;
}

.site__item.s3 {
    background-color: var(--subBg500);
    top: 220px;
}

.site__item.s4 {
    background-color: var(--subBg600);
    top: 240px;
}
</style>