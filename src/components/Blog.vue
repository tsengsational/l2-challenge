<template>
    <div class="blog">
        <h1>{{blog.title}}</h1>
        <div class="blog-entries" >
            <div v-for="(entry, key) in blog.entries" :key="key" class="blog-entry" >
                <div class="blog-border"></div>
                <h3>{{entry.title}} </h3>
                <p>{{entry.content}} </p>
                <a href="#">Read more</a>
            </div>
        </div> 

    </div>
</template>

<script>
export default {
    props: ["blog"]
}
</script>

<style lang="scss">
    @import "../assets/settings.scss";

    .blog {
        padding: 16px;
        text-align: left;
        h1 {
            color: $orange;
        }
        .blog-entry {
            padding: 24px 0;
            margin-bottom: 16px;
            .blog-border {
                height: 3px;
                width: 50px;
                background-color: $orange;
            }
            a {
              color: $orange;  
            }
            p {
                line-height: 24px;
            }
        }
    }

    @media (min-width: $mobile-break-pt) {
        .blog {
            width: 1100px;
            position: relative;
            left: calc(50vw - 550px);
            .blog-entries {
                margin-bottom: 48px;
                .blog-entry {
                    display: inline-block;
                    width: calc(1100px/3);
                    box-sizing: border-box;
                    padding: 16px 16px 16px 0;
                }
            }
        }
    }
    
</style>
