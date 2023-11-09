<script setup>
import { footerText } from '@/constants/index';
</script>
<template>
    <footer id="footer" role="contentinfo">
        <div class="footer__inner">
            <h2 class="footer__text">
                <div>green</div>
                <div>@green</div>
            </h2>
            <div class="footer__info">
                <div class="left">
                    <div class="title">
                        <a href="#">sign up</a>
                    </div>
                    <p class="desc">회원가입을 하시면 댓글과 게시판 기능을 이용할 수 있습니다.</p>
                </div>
                <div class="right">
                    <h3>social</h3>
                    <ul>
                        <li v-for="(footer, key) in footerText" :key="key">
                            <a href="footer.link">{{ footer.title }}</a>
                            <em>{{ footer.desc }}</em>
                        </li>

                    </ul>
                </div>
            </div>
            <div class="footer__right">
                &copy; 2023 green<br />
                이 사이트는 비트를 이용하여 제작하였습니다.
            </div>
        </div>
    </footer>
</template>

<style lang="scss">
#footer {
    background-color: var(--subBg100);
    border-top: 1px solid var(--black);
    text-transform: uppercase;
    font-family: var(--intro-sub-font);
}

.footer__inner {
    padding: 1vh;
    display: flex;
    flex-wrap: wrap;
    text-align: center;
}

.footer__text {
    width: 100%;
}

.footer__info {
    width: 100%;
    display: flex;
    justify-content: space-between;
}

.footer__info .left {
    width: 40%;
    justify-content: left;
    padding: 1vh;
}

.footer__info .left .title {
    border-bottom: 2px solid var(--black);
}

.footer__info .left .title a {
    font-size: 3vh;
    display: inline-block;
    width: 100%;
    text-align: left;
    line-height: 0.9;
}

.footer__info .left .desc {
    text-align: right;
}

.footer__info .right {
    width: 40%;
    justify-content: right;
    text-align: left;
    padding: 1vh;
}

.footer__info .right h3 {
    font-size: 3vh;
    display: inline-block;
    width: 100%;
    text-align: left;
    line-height: 0.9;
    border-bottom: 2px solid var(--black);
    padding-bottom: 5px;
}

.footer__info .right a {
    padding: 5px 10px;
    display: inline-block;
    border: 1px solid #000;
    margin: 5px;
    background-color: var(--mainFont-color);
    color: var(--mainBg-color);
}

.footer__right {
    width: 100%;
    justify-content: right;
}
</style>