<template>
    <div class="nav-container">
        <nav>
            <div class="title">
                {{site.title}}
            </div>
            <div class="links">
                <span v-for="(page, key) in site.pages" :key="key"><a href="#">{{page}}</a></span>
            </div>

            <button class="menu-btn" @click="handleMenuClick" v-bind:class="{menuOpen: menuOpen}">
                <div class="menu-top" @click="handleMenuClick"></div>
                <div class="menu-mid" @click="handleMenuClick"></div>
                <div class="menu-btm" @click="handleMenuClick"></div>
            </button>

        </nav>
        <site-menu :pages="site.pages" :menuOpen="menuOpen" ></site-menu>
    </div>
</template>

<script>
import SiteMenu from "./Menu"

export default {
    components: {
        SiteMenu
    },
    data: function () {
        return {
            menuOpen: false
        }
    },
    props: ['site'],
    methods: {
        handleMenuClick: function() {
            this.menuOpen = !this.menuOpen
         }
    }
    
}
</script>

<style lang="scss">
    @import "../assets/settings.scss";

    nav {
        background-color: $midnight;
        color: $white;
        position: relative;
        padding: 10px 0;
        z-index: 3;
        .title {
            color: $orange;
            font-weight: 900;
        }
    }

    .links {
        display: none;
    }

    .menu-btn {
        border: 0;
        background-color: transparent;
        cursor: pointer;
        height: 35px;
        position: absolute;
        right: 0;
        padding: 0 14px;
        top: calc(50% - 17.5px);
        width: 45px;
        &.menuOpen {
        .menu-top {
            transform: rotate(45deg);
            transform-origin: left center 0px;
        }
        .menu-mid {
            opacity: 0;
        }
        .menu-btm {
            transform: rotate(-45deg);
            transform-origin: left center 0px;
        }
        }
    }
    .menu-btn>.menu-top, .menu-mid, .menu-btm {
        background-color: $white;
        height: 2px;
        margin-bottom: 4px;
        transition: transform .3s, opacity .3s;
        width: 17px;
        border-radius: 10px;
    }

    @media (min-width: 400px) {
        .menu-btn {
            display: none;
        }

        .title {
            position: absolute;
            left: 100px;
        }

        .links {
            text-align: right;
            position: relative;
            right: 5vw;
            display: block;
            span {
                margin: 0 10px;
            }
        }
    }
</style>
