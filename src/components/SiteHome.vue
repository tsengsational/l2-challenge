<template>
    <div class="home">
        <hero :hero="site.hero" ></hero>
        <div class="cookies" >
            <div class="cookie-content">
                <div class="cookie-title">
                   <h1>Our Cookies</h1>
                </div>
                <div v-for="(card, key) in site.cards" :key="key" class="card">
                    <div class="card-title">
                        <h3>{{card.title}}</h3>
                    </div>
                    <div class="card-content">
                        {{card.content}}
                    </div>
                </div>
            </div>
            <div class="cookie-container" >
                <cookie v-for="(cookie, key) in site.cookies" :key="key" :cookie="cookie" />
            </div>
        </div>
        <blog :blog="site.blog" ></blog>

    </div>
</template>

<script>
import Hero from "./Hero"
import Cookie from "./Cookie"
import Blog from "./Blog"

export default {
    props: ["site"],
    components: {
        Hero, Cookie, Blog
    }
}
</script>

<style lang="scss">
    @import "../assets/settings.scss";

    .cookie-content {
        width: 100%;
        padding: 16px;
        text-align: left;
        box-sizing: border-box;
        .cookie-title {
            color: $orange;
        }
        .card {
            width: 100%;
            padding: 16px;
            box-sizing: border-box;
            .card-title {
                color: $orange;
            }
            .card-content {
                line-height: 24px;
            }
        }
    }

    .cookie-container {
        padding: 16px;
        box-sizing: border-box;
        width: 100%;
        margin-bottom: 32px;
    }
</style>

