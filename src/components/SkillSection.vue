<script setup>
import { skillText } from "@/constants/index";
</script>

<template>
    <section id="skill">
        <div class="skill__inner">
            <h2 class="skill__title">
                challenge <em>나의 도전</em>
            </h2>
            <div class="skill__desc">
                <div v-for="(skill, key) in skillText" :key="key">
                    <span>{{ key + 1 }}.</span>
                    <h3>{{ skill.title }}</h3>
                    <p>
                        {{ skill.desc }}
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss">
.skill__inner {
    padding: 1vw;
    display: flex;
    justify-content: space-between;
    color: var(--mainFont-color);
}

.skill__title {
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

.skill__title em {
    font-family: var(--mainKor-font);
    font-size: 1.2rem;
    font-weight: 400;
}

.skill__desc {
    width: 50%;
}



.skill__desc span {
    font-size: 5vw;
    line-height: 1;
    font-weight: 900;
    font-family: var(--mainKor-fon);
}

.skill__desc span:first-child {
    line-height: 1.5;
}

.skill__desc h3 {
    font-size: 1.5rem;
    font-weight: 500;
    border-bottom: 0.8vw solid var(--mainFont-color);
}

.skill__desc p {
    color: var(--black);
    margin-bottom: 30vh;
    font-size: 1.1rem;
    font-family: var(--mainKor-fon);
    color: var(--black);
    word-break: keep-all;
}

@media (max-width: 800px) {
    .skill__inner {
        flex-direction: column;
    }

    .skill__title {
        width: 100%;
        margin-bottom: 1vw;
        height: auto;
        background-color: var(--mainBg-color);
    }

    .skill__desc {
        width: 100%;
    }

    .skill__desc span {
        font-size: 20vw;
    }

    .skill__desc h3 {
        text-decoration: underline;
        text-underline-position: under;
        width: 50%;
        border-bottom: 1vw;
    }
}
</style>