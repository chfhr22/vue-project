<script setup>
import { headerNav } from "@/constants/index";
</script>

<template>
    <header id="header" role="heading">
        <div class="header__inner">
            <h1 class="header__logo">
                <a href="#">portfolio<em>vue.js</em></a>
            </h1>
            <nav class="header__nav" role="navigation" aria-label="메인 메뉴" :class="{ show: isNavVisible }">
                <ul>
                    <li v-for="(nav, key) in headerNav" :key="key">
                        <a :href="nav.url" @click="scrollLink($event)">{{ nav.title }}</a>
                    </li>
                </ul>
            </nav>
            <div class="header__nav__mobile" id="headerToggle" aria-controls="primary-menu"
                :aria-expanded="isNavVisible.toString()" @click="toggleMobileMenu">
                <span></span>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            isNavVisible: false,
        };
    },
    methods: {
        toggleMobileMenu() {
            this.isNavVisible = !this.isNavVisible;
        },
        scrollLink(event) {
            event.preventDefault();

            const targetId = event.target.getAttribute("href");
            const targetElement = document.querySelector(targetId);

            if (targetElement) {
                targetElement.scrollIntoView({ behavior: "smooth" });
            }
        },
    },
};
</script>

<style lang="scss">
#header {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    z-index: 10000;
    /* display: none; */
    background-color: var(--subBg100);
}

.header__inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    /* background-color: rgba(0, 0, 0, 0.3); */
    padding: 1rem;
    border-bottom: 1px solid var(--black);
    text-transform: uppercase;
    box-sizing: border-box;
}

.header__logo {
    width: 10%;
    font-family: var(--intro-font);
    font-size: 2.4vw;
    white-space: nowrap;
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    text-align: center;
    line-height: 1;
}

.header__logo a:hover {
    color: var(--mainFont-color);
}

.header__logo em {
    display: block;
    font-size: 0.8vw;
}

.header__nav {
    width: 80%;
    display: flex;
    justify-content: right;
}

.header__nav li {
    display: inline;
    padding: 1vw;
    font-size: 1.2vw;
}

.header__nav li a {
    display: inline-block;
    padding: 0.3rem 1rem;
    font-weight: 400;
    position: relative;
}

.header__nav li a::before {
    content: '';
    width: calc(100% - 30px);
    height: 1px;
    background-color: #000;
    position: absolute;
    left: 15px;
    bottom: 5px;
    transform: scaleX(0);
    transition: all 0.3s;
}

.header__nav li a:hover::before {
    transform: scaleX(1);
}

.header__nav__mobile {
    width: 40px;
    height: 40px;
    cursor: pointer;
    display: none;
}

.header__nav__mobile span {
    display: block;
    width: 40px;
    height: 2px;
    background-color: var(--white);
    margin-top: 19px;
    position: relative;
    background-color: var(--black);
}

.header__nav__mobile span::before {
    content: '';
    width: 40px;
    height: 2px;
    background-color: var(--black);
    position: absolute;
    right: 0;
    top: 8px;
    transition: width 0.3s;
}

.header__nav__mobile span::after {
    content: '';
    width: 40px;
    height: 2px;
    background-color: var(--black);
    position: absolute;
    left: 0;
    top: -8px;
    transition: width 0.3s;
}

@media (max-width: 800px) {
    .header__nav {
        display: none;
    }

    .header__nav.show {
        display: block;
    }

    .header__nav.show ul {
        display: block;
        position: absolute;
        right: 0;
        top: 69px;
        background-color: #00000078;
        color: var(--white);
        z-index: 10000;
        min-width: 150px;
        padding: 20px 0;
    }

    .header__nav.show li {
        display: block;
        text-align: right;
    }

    .header__nav.show li a {
        display: inline-block;
        padding: 10px;
    }

    .header__nav.show+.header__nav__mobile span::before {
        width: 20px;
    }

    .header__nav.show+.header__nav__mobile span::after {
        width: 20px;
    }

    .header__nav__mobile {
        display: block;
    }
}
</style>