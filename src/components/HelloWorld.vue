<template>
    <div class="hello">
        <div class="left">
            <iframe
                src="https://blog.csdn.net/vivianluolita/article/details/53689745"
                frameborder="0"
                width="100%"
                height="100%"
                @select="selectHandle"
                id="testIframe"
            ></iframe>
            <!-- <img src="../assets/logo.png" alt="" /> -->
        </div>
        <div
            class="right"
            ref="dragTarget"
            @dragenter="testDrag"
            @dragover="dragoverHandler"
            @drop.prevent="testDrag"
        >
            我是可拖拽区域,我是docker测试
        </div>
    </div>
</template>

<script>
export default {
    name: 'HelloWorld',
    props: {
        msg: String,
    },
    mounted() {
        let iframe = document.getElementById('testIframe');
        iframe.onload = function() {
            // let i = iframe.contentWindow.document.getElementById('head');
            // let i = iframe.contentDocument.getElementById('head');
            // console.log(
            //     iframe.contentWindow.document.getElementById('csdn-toolbar')
            // );
            // iframe.onclick = function() {
            //     console.log('====', 222);
            // };
            // iframe.contentDocument.addEventListener(
            //     'click',
            //     function() {
            //         alert(222);
            //     },
            //     false
            // );
            // iframe.contentWindow.onclick = function() {
            //     console.log('====', 222);
            // };
            // iframe.contentDocument.onclick = function() {
            //     console.log('4444444444');
            // };

            window.addEventListener('click', function() {
                console.log('2222');
            });
        };
    },
    methods: {
        selectHandle(e) {
            console.log(e);
        },
        dragoverHandler(event) {
            event.preventDefault();
        },
        testDrag(e) {
            console.log(e);
        },
    },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
    display: flex;
    height: 100%;
}
.left {
    width: 80%;
    height: 100%;
}
.right {
    width: 20%;
    background: gray;
    height: 100%;
}
</style>
