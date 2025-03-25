<script setup lang="ts">
</script>

<template>
  <header>
    <img src="~/assets/Logo.svg" alt="Logo">
    <div class="head_left">
        <nav>
            <a>Works</a>
            <a>About</a>
        </nav>
        <div class="head_buttons">
            <div class="country">
                <img src="~/assets/Country.png" alt="Country">
            </div>
            <button>Let’s work</button>
        </div>
    </div>
  </header>
  <slot/>
  <footer>
    <div class="footer_top">
        <div class="main_info">
            <p>Is there a project?</p>
            <h1>Let’s work together</h1>
        </div>
        <div class="address">
            <p>For all questions</p>
            <p>+7 (920) 278—00—68</p>
            <p>qtim@agency.com</p>
            <br/>
            <p>Office in Russia</p>
            <p>139 Ruben Station Lake Drew, NM 52678</p>
            <button><img src="~/assets/Tg.svg" alt="Tg"></button>
            <br/>
            <p>Office in Dubai</p>
            <p>139 Ruben Station Lake Drew, NM 52678</p>
            <button><img src="~/assets/Tg.svg" alt="Tg"></button>
        </div>
    </div>
    <div class="footer_bottom">
        <div class="link">
            <p>Facebook</p>
            <p>Instagram</p>
            <p>Telegram</p>
        </div>
        <div class="go">
            <p>Go</p>
        </div>
        <div class="link">
            <p>Behance</p>
            <p>Linkedn</p>
            <p>Privacy Policy</p>
        </div>
    </div>
  </footer>
</template>

<style scoped>
header{
    display: flex;
    justify-content: space-between;
    padding: 35px 40px;
}
nav{
    display: flex;
    align-items:center;
    gap: 58px;
}
nav a{
    font-family: "TT Commons", sans-serif;
    font-weight: 400;
    font-size: 20px;
    line-height: 100%;
    color: #101010;
    text-decoration: none;
}
.head_left{
    display: flex;
    gap: 91px;
}
.head_buttons{
    display: flex;
    align-items:center;
    gap: 16px;
}
.country{
    border: 2px solid rgba(0, 0, 0, 0.1);
    border-radius: 999px;
    padding: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.country img {
    max-width: 100%;
    height: auto;
}
h1{
    font-weight: 400;
    font-size: 112px;
    color: #101010;
    text-decoration: underline;
}

button{
    border-radius: 999px;
    padding: 16px 32px;
    background: #101010;
    font-family: "TT Commons", sans-serif;
    font-weight: 400;
    font-size: 20px;
    line-height: 100%;
    color: #fff;
    cursor: pointer;
}
p{
    font-family: "TT Commons", sans-serif;
    font-weight: 400;
    font-size: 16px;
    line-height: 120%;
    letter-spacing: 0.01em;
    color: #101010;
}
footer { 
    display: flex;
    flex-direction: column;
    gap: 273px;
    margin-top: 140px;
    padding: 140px 112px 0 112px; 
    background: #e2beff;
    overflow: hidden;
    button{
        border-radius: 999px;
        padding: 10px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    button img {
        max-width: 100%;
        height: auto;
    }
}
.footer_top{
    display: flex;
    justify-content: space-between;
}
.main_info{
    max-width: 484px;
    display: flex;
    flex-direction: column;
    gap: 56px;
}
.address{
    display: flex;
    flex-direction: column;
    align-items:start;
    text-align: start;
    max-width: 170px;
    margin-right: 232px;
    margin-top: 75px;
}
.footer_bottom{
    display: flex;
    justify-content: space-between;
}
.link{
    display: flex;
    gap: 32px;
    text-decoration: underline;
}
.go{
    position: relative;
    z-index: 1;
    p{
        font-size: 32px;
        line-height: 100%;
        color: #f3f3f3;
        color:#fff;  
    }
}
.go::after {
  content: '';
  position: absolute;
  bottom: -179px;
  left: 50%;
  transform: translateX(-48%);
  width:  358px;
  height: 358px;
  border-radius: 50%;
  background-color: #000000;
  z-index: -1;
}
</style>