<template>
    <div id="app">
        <router-view></router-view>
    </div>
</template>
<script>
export default {
    name: 'app',
    mounted() {
        let imgUrl = localStorage.getItem('imgUrl')
        if (imgUrl) {
            var imgSrc = require('./assets/imgs/' + imgUrl + '.jpg')
            var img = new Image()
            img.src = imgSrc
            img.onload = () => {
                document.body.style.background = 'url(' + imgSrc + ') no-repeat center center'
                document.body.style.backgroundSize = '100% 100%'
                document.body.style.backgroundAttachment = 'fixed'
            }

        } else {
            var imgSrc = require('./assets/imgs/1.jpg')
            var img = new Image()
            img.src = imgSrc
            img.onload = () => {
                document.body.style.background = 'url(' + imgSrc + ') no-repeat center center'
                document.body.style.backgroundSize = '100% 100%'
                document.body.style.backgroundAttachment = 'fixed'
            }
        }
    }
}
</script>
<style lang="less">
@import url('./assets/css/init.css');
#app {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}

html::-webkit-scrollbar,
.layout::-webkit-scrollbar,
.layout-content::-webkit-scrollbar {
    display: none;
}

html,
body,
#app {
    height: 100%;
}

body {
    transition: 1s;
}

.read-article,
.editor-preview-side {
    pre code {
        display: block;
        max-width: 100%;
        color: #8492a6;
        background: #23241f;
        font: 16px Consolas, Liberation Mono, Menlo, Courier, monospace;
        border-radius: 5px;
        line-height: 1.5em;
        padding: .4rem .6rem;
        overflow-x: auto;
    }
}


/* 返回顶部 */

.ivu-back-top-inner {
    border-radius: 2px;
    cursor: pointer;
    background: rgba(151, 147, 165, 0.8) !important;
}

.ivu-page-item-jump-next {
    background: #fff;
}

//加载中
.spin-icon-load {
    animation: ani-demo-spin 1s linear infinite;
}

@keyframes ani-demo-spin {
    from {
        transform: rotate(0deg);
    }
    50% {
        transform: rotate(180deg);
    }
    to {
        transform: rotate(360deg);
    }
}

.ivu-page-total {
    color: #fff;
}
</style>
