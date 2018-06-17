<template>
    <div class="footer" >
        <div class="footer-container" >
            <h3>{{site.title}} </h3>
            <div class="footer-content" >
                <div v-for="(note, key) in site.footer" :key="key" class="footnote" >
                    <span class="footnote-key" >{{key}}</span>
                    <span class="footnote-content" >{{note}}</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ["site"]
}
</script>

<style lang="scss">
    @import "../assets/settings.scss";

    .footer {
        background-color: $orange;
        padding: 32px 16px;
        color: $white;
        text-align: left;
        h3 {
            margin-bottom: 48px;
        }
        .footnote {
            text-transform: uppercase;
            font-weight: 900;
            font-size: 12px;
            letter-spacing: 2px;
            span {
                margin: 8px 0;
                vertical-align: top;
            }
            .footnote-key {
                width: 100px;
                display: inline-block;
            }
            .footnote-content {
                display: inline-block;
                width: 240px;
            }
        }
    }

    @media (min-width: $mobile-break-pt) {
        .footer {
            .footer-container {
                width: 1100px;
                position: relative;
                left: calc((50vw) - 550px );
                margin-bottom: 100px;
                h3 {
                    font-size: 24px;
                }
                .footnote {
                    font-size: 14px;
                    .footnote-key {
                        width: 150px;
                    }
                    .footnote-content {
                        width: 500px;
                    }
                }
                .footer-content {
                    position: absolute;
                    left: 400px;
                    top: 0;
                }
            }
        }
    }
</style>
