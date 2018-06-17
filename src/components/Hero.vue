<template>
    <div class="hero" >
        <div class="img-container" :style="imgStyle" ></div>
        <div class="hero-card" >
            <h1>{{hero.title}}</h1>
            <p>{{hero.content}}</p>
            <button class="hero-btn" disabled="disabled">{{hero.action}} </button>
        </div>
    </div>
</template>

<script>
export default {
    props: ["hero"],
    data: function() {
        return {
            imgStyle: {
                backgroundImage: `url(${this.hero.img})`,
            }
        }
    },

}
</script>

<style lang="scss">
    @import "../assets/settings.scss";

    .hero {
        position: relative;
        .img-container {
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
            width: 100vw;
            height: 400px;
            background-attachment: fixed;
        }
        .hero-card {
            position: absolute;
            top: 100px;
            right: 10vw;
            z-index: 1;
            background-color: $white;
            padding: 20px;
            width: 80vw;
            height: 200px;
            box-sizing: border-box;
            h1 {
                color: $orange;
                text-indent: -100px;
                width:180px;
                height: 66px;
                position: relative;
                left: calc(40vw - 90px);
            }
            p {
                text-align: left;
                font-size: 14px;
                line-height: 16px;
            }
            .hero-btn {
                background-color: $orange;
                padding: 10px 20px;
                width: 200px;
                height: 65px;
                color: $white;
                font-size: 18px;
                font-weight: 900;
                border: none;
                position: relative;
                top: 0px;
                transition: background-color .3s;
                cursor: pointer;
                &:hover {
                    background-color: $midnight;
                }
            }
        }
    }

    @media (min-width: $mobile-break-pt) {
        .hero {
            .img-container {
                height: 500px;
            }


            .hero-card {
                height: 225px;
                width: 400px;
                right: 20vw;
                    h1 {
                        left: 60px;
                    }
                    p {
                        line-height: 24px;
                        width: 300px;
                        margin-bottom: 16px;
                    }
                    .hero-btn {
                        left: 80px;
                    }
            }
        }
    }

</style>
