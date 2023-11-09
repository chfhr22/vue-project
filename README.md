## setting
1. `npm init vue@latest`
✔ Add TypeScript? … No <br>
✔ Add JSX Support? … Yes<br>
✔ Add Vue Router for Single Page Application development? … Yes  <br>
✔ Add Pinia for state management? … No   <br>
✔ Add Vitest for Unit Testing? … No   <br>
✔ Add an End-to-End Testing Solution? › No   <br>
✔ Add ESLint for code quality? … Yes<br>
✔ Add Prettier for code formatting? … Yes<br>

2. 
gsap 설치 : `npm i gsap`<br>
sass 설치 : `npm i sass`<br>
lenis 설치 : `npm i @studio-freight/lenis`<br>

3. section별로 components 만들기<br>
<template>
    header
</template>

4. HomeView에 import<br>

5. app.vue에 <RouterView /> 해서 보이도록 설정

6. sass 세팅

7. main.js에 sass import
import "./assets/scss/style.scss"

8. 각 components에 내용넣고 스타일 입히기
<style lang="scss"></style>

9. contants에 데이터 입력

10. 입력된 데이터를 각 components에 불러오기
<script setup>
import { headerNav } from "@/constants/index";
</script>