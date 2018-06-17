<template>
    <div class="cookie">
        <div class="cookie-img" :style="imgStyle" ></div>
        <h3 class="cookie-name"><a href="#">{{cookie.name}}</a></h3>
        <div class="cookie-backsplash"></div>
    </div>
</template>

<script>
export default {
    props: ["cookie"],
    data: function() {
        return {
            imgStyle: {
                backgroundImage: `url(${this.cookie.img})`
            }
        }
    }
    
}
</script>

<style lang="scss">
    @import "../assets/settings.scss";

    .cookie {
        position: relative;
        width: calc((100% - 9px)/2);
        box-sizing: border-box;
        display: inline-block;
        vertical-align: top;
        margin-right: 4px;
        .cookie-img {
            width: 150px;
            height: 90px;
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
            z-index: 1;
        }
        .cookie-name {
            color: $white;
            z-index: 1;
            text-align: left;
            font-size: 14px;
            position: relative;
            left: 20px;
            width: 140px;
            a {
                text-decoration: none;
                color: $white;
            }
        }
        .cookie-backsplash {
            position: absolute;
            top: 20px;
            left: 12px;
            height: 120px;
            width: 150px;
            background-color: $orange;
            z-index: -1;
            transition: background-color .6s;
        }
        &:hover {
            .cookie-backsplash {
                background-color: $midnight;
            }
        }
    }

    @media (min-width: $mobile-break-pt) {
        .cookie {
            margin-bottom: 32px;
            .cookie-img {
                width: 300px;
                height: 200px;
            }
            .cookie-name {
                left: 48px;
                width: 250px;
                font-size: 18px;
            }
            .cookie-backsplash {
                width: 300px;
                height: 240px;
                left: 24px;
            }
        }
    }

</style>
