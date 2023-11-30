<template>
    <div class="container root-box">
        <div class="waterfalls">
            <div class="box" v-for="(cat) in catsList" :key="cat.id">
                <div class="pic">
                    <img :src="cat.url" alt="1.jpg">
                    <div class="tip">
                        <h1>{{ cat.id }}</h1>
                        <p>{{ cat.url }}</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="load">load ...</div>
    </div>
</template>

<script  >
import axios from 'axios'
export default {
    name: 'waterFall',
    props: {
        catsList: {
            type: Array
        },
        keywords: {
            type: String
        },
        catKind: {
            type: Array
        }
    },
    data() {
        return {

        }
    },
    mounted() {
        const load = document.getElementsByClassName('load')[0];
        const rootBox = document.getElementsByClassName('root-box')[0]
        console.log('root', rootBox);
        let _this = this;
        let pageNum = 1;
        const ob = new IntersectionObserver((target) => {
            console.log('重叠', target);
            if (target[0].isIntersecting) {
                console.log("被观察者完全与视口重叠");
                // 获取某一个品种的猫猫
                let cat = this.catKind.filter((cat) => {
                    let regx = new RegExp(this.keywords, 'i');
                    return regx.test(cat.name)
                })

                axios.get(`https://api.thecatapi.com/v1/images/search?limit=20&breed_ids=${cat[0].id}&page=${pageNum}`)
                    .then(function (response) {
                        // 处理成功情况
                        _this.$emit('addCatList', response.data)
                        console.log('page', response);
                    })
                    .catch(function (error) {
                        // 处理错误情况
                        console.log(error);
                    })
                    .finally(function () {
                        // 总是会执行
                    });
                pageNum++;
            }
        }, {
            root: rootBox,
            threshold: [0.2]
        })
        ob.observe(load)
    }
}

</script>

<style  scoped>
.load {
    width: 100vw;
    height: 30px;
    color: #999;
}

.container {
    height: calc(100vh - 150px);
    margin: 0 auto;
    width: 98vw;
    overflow-x: hidden;
    overflow-y: auto;
    transform: translateY(15px);
}

.waterfalls {
    padding: 10px;
    position: relative;
    margin: 0 auto;
    background-color: transparent;
    /* //每列每个元素最小的宽度 */
    /* columns: 100px; */
    columns: 160px;
    /* 每列的距离 */
    column-gap: 20px;


}

.box {
    /* break-inside: avoid; */
    /* 这个是设置多列布局页面下的内容盒子如何中断，如果不加上这个，每列的头个元素就不会置顶，配合columns使用  */
    margin-bottom: 15px;
    color: #fff;
    border-radius: 5px;
}

.pic img {
    width: 100%;
    /* 建议每个图片宽高为100%，如果不设置宽高，就会溢出外层盒子的，或者设置固定宽度，最好不要宽过外层盒子或者高过外层盒子。这里说的外层盒子就是html代码里的 .box  */
    height: 100%;
    border-radius: 5px;
    border: 1px solid #ccc;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    transition: all 0.4s ease-in-out;
}


.pic {
    width: 100%;
    height: 100%;
    overflow: hidden;
    position: relative;
}

.pic:hover img {
    transform: scale(1.3);
}

.pic .tip {
    position: absolute;
    bottom: -50px;
    left: 0;
    width: 100%;
    height: 50px;
    background-color: rgba(0, 0, 0, 0.4);
}

.pic .tip h1 {
    font-size: 10px;
}

.pic .tip p {
    font-size: 8px;
}

.pic:hover .tip {
    bottom: 0px;
}
</style>