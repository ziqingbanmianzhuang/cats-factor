<template>
    <div class="search-box">
        <input type="text" @focus="popHistory" :value="a" placeholder="serach your like" @input="updateFilterHistory"
            @mouseleave="($event) => { $event.target.blur() }">
        <button @click="searchCat">serach</button>
    </div>
    <transition name="fade">
        <div class="history-list" v-show="isShowHistory">
            <ul ref="ulScroll" @mouseleave="hideHistory">

                <template v-for="(cat) in filterHistory" :key="cat.id">
                    <li v-if="cat.name" @click="searchCatByLi(cat.name)">
                        <a href="#">{{ cat.name }}</a>
                        <a href="#" @click="deleteHistoryItem(cat.id)">-</a>
                    </li>
                </template>
            </ul>
        </div>
    </transition>
</template>
  
<script>
import { nextTick } from 'vue';
import axios from 'axios'
// @ is an alias to /src


export default {
    name: 'ShowView',
    props: {
        keywords: {
            type: String
        },
        catKind: {
            type: Array
        }

    },

    data() {
        return {
            isShowHistory: false,
            a: this.keywords,
            historys: [
            ],
            // filterHistory:[]
        }
    },
    computed: {
        filterHistory: function () {
            return this.historys.filter((item) => {
                let regx = new RegExp(this.a, "i")
                return regx.test(item.name)
            })
        },
        sonKey: function () {
            return this.keywords
        }
    },
    mounted() {
        console.log('localstorage', localStorage);
        let loalsFilter = Object.entries(localStorage).filter(([key]) => {
            return key === 'count' ? false : true;
        })
        loalsFilter = loalsFilter.map((item) => {
            return {
                id: JSON.parse(item[1]).id,
                name: JSON.parse(item[1]).name
            }
        })
        console.log('loalsFilter', loalsFilter);
        loalsFilter.forEach((item) => {
            this.historys.push(item)
        })
    },
    methods: {
        popHistory: function () {
            this.filterHistory.length === 0 ? this.$refs.ulScroll.style.height = '0px' : this.$refs.ulScroll.style.height = '200px'
            this.isShowHistory = true;
        },
        deleteHistoryItem(id) {
            localStorage.removeItem(id)
            this.historys = this.historys.filter((item) => {
                return item.id !== id
            })
            this.filterHistory = this.historys.filter((item) => {
                let regx = new RegExp(this.a, "i")
                return regx.test(item.name)
            })
            nextTick(() => {

                this.filterHistory.length === 0 ? this.$refs.ulScroll.style.height = '0px' : this.$refs.ulScroll.style.height = '200px'
            })
        },
        hideHistory: function () {
            this.isShowHistory = false;
        },
        updateFilterHistory: function ($event) {
            nextTick(() => {
                this.a = $event.target.value
                console.log('\\\\\\\\\\\\', this.a);
                this.filterHistory.length === 0 ? this.$refs.ulScroll.style.height = '0px' : this.$refs.ulScroll.style.height = '200px'
            })
        },
        searchCatByLi: function (name) {
            console.log('li////////////////');
            this.$emit('updateKeyWords', name)
            let cat = this.catKind.filter((cat) => {
                let regx = new RegExp(name, 'i');
                return regx.test(cat.name)
            })
            const _this = this
            if (!cat[0]) {
                return;
            }
            axios.get(`https://api.thecatapi.com/v1/images/search?limit=20&breed_ids=${cat[0].id}`)
                .then(function (response) {
                    // 处理成功情况
                    _this.$emit('updateCatList', response.data)
                    console.log('lires////////////////', cat[0].id, response.data);
                })
                .catch(function (error) {
                    // 处理错误情况
                    console.log(error);
                })
                .finally(function () {
                    // 总是会执行
                });
        },
        searchCat: function () {
            nextTick(() => {
                this.$emit('updateKeyWords', this.a)
                console.log('///////////////', this.a);
            })
            let count = localStorage.getItem('count');
            count ? count : count = 0;
            count++;
            localStorage.setItem('count', count)
            let catObj = {
                id: count,
                name: this.a
            }
            localStorage.setItem(count, JSON.stringify(catObj))
            let obj = JSON.parse(localStorage.getItem(`${count}`))
            this.historys.push(obj)
            // 获取所有的猫猫的品种
            axios.get(' https://api.thecatapi.com/v1/breeds')
                .then(function (response) {
                    // 处理成功情况
                    console.log('catskinds', response.data);
                })
                .catch(function (error) {
                    // 处理错误情况
                    console.log(error);
                })
                .finally(function () {
                    // 总是会执行
                    console.log("endRequest");
                });

            // 获取某一个品种的猫猫
            let cat = this.catKind.filter((cat) => {
                let regx = new RegExp(this.a, 'i');
                return regx.test(cat.name)
            })
            const _this = this
            if (!cat[0]) {
                return;
            }
            axios.get(`https://api.thecatapi.com/v1/images/search?limit=20&breed_ids=${cat[0].id}`)
                .then(function (response) {
                    // 处理成功情况
                    _this.$emit('updateCatList', response.data)
                })
                .catch(function (error) {
                    // 处理错误情况
                    console.log(error);
                })
                .finally(function () {
                    // 总是会执行
                });

        }
    }
}

</script>
  
<style scoped>
.fade-enter-active,
.fade-leave-active {
    transition: opacity 1s;
}

.fade-enter,
.fade-leave-to

/* .fade-leave-active below version 2.1.8 */
    {
    opacity: 0;
}

.search-box {
    width: 80%;
    height: 50px;
    background-color: #fff;
    margin: 0 auto;
    transform: translateY(10px);
    border-radius: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    z-index: 999;
}

.search-box input {
    border: 1px solid #ccc;
    border-radius: 20px;
    width: 50%;
    height: 10px;
    outline: none;
    padding: 10px;
}


.search-box button {
    width: 60px;
    height: 30px;
    background-color: #c4968e;
    border-radius: 20px;
    border: none;
    outline: none;
    color: #fff;
}

.search-box button:hover {
    background-color: #d59288;
}

.history-list {
    background-color: #fff;
    border-radius: 10px;
    transform: translateY(10px) translateX(-50%);
    width: 78%;
    margin: 20px auto;
    position: absolute;
    left: 50%;
    z-index: 999;
}

.history-list ul {
    margin: 0;
    padding: 0;
    list-style: none;
    height: 200px;
    overflow: auto;
}

.history-list ul li {
    margin: 10px;
    padding: 10px;
    display: flex;
    justify-content: space-between;
    border-radius: 10px;
}

.history-list ul li:hover {
    background-color: rgba(254, 226, 222, .4);
}

.history-list ul li a {
    text-decoration: none;
    color: #dd8f83fb;
}

.history-list ul li a:nth-child(2) {
    display: block;
    width: 20px;
    height: 20px;
    background-color: #fee2de;
    border-radius: 10px;
}
</style>
  