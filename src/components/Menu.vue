<template>
    <div class="menu" :class="{menuOpen : menuOpen}" >
        <span class="page" v-for="(page, key) in pages" :key="key" ><a href="#">{{page}}</a></span>
    </div>    
</template>

<script>
export default {
    props: ["pages", "menuOpen"]
}
</script>

<style lang="scss">
    @import "../assets/settings.scss";

    .menu {
        position: fixed;
        top: -377px;
        width: 100%;
        padding: 16px 0;
        color: black;
        background-color: $white;
        transition: top .6s;
        z-index: 2;
        border: 1px $midnight solid;
        span {
            display: block;
            height: 24px;
            a {
                text-decoration: none;
                color: $midnight;
                font-weight: 900;
                transition: color .3s;
                &:hover {
                    color: $orange;
                }
            }
        }
        &.menuOpen {
            top: 37px;
        }
    }

    @media (min-width: $mobile-break-pt) {
        .menu.menuOpen {
            display: none;
        }
    }

</style>
