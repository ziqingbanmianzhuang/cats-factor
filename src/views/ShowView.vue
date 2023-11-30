<template>
    <div class="show-box">
        <search @updateCatList="updateCatList" :keywords="keywords" :catKind="catKind" @updateKeyWords="updateKeyWords">
        </search>
        <waterFall :catsList="catsList" :keywords="keywords" :catKind="catKind" @addCatList="addCatList"></waterFall>
    </div>
</template>
  
<script>
// @ is an alias to /src
import search from '../components/search.vue';
import waterFall from '../components/waterFall.vue';

export default {
    name: 'ShowView',
    data() {
        return {
            catsList: [],
            keywords: '布偶',
            catKind: [
                { id: 'abys', name: '阿比西尼亚' },
                { id: 'aege', name: '爱琴海' },
                { id: 'abob', name: '美国短尾猫' },
                { id: 'acur', name: '美式卷猫猫' },
                { id: 'asho', name: '美式短毛猫' },
                { id: 'awir', name: '美国刚毛猫' },
                { id: 'amau', name: '阿拉伯毛猫' },
                { id: 'amis', name: '澳大利亚薄毛猫' },
                { id: 'bali', name: '巴黎岛猫' },
                { id: 'bamb', name: '班比诺猫' },
                { id: 'beng', name: '孟加拉国猫' },
                { id: 'birm', name: '伯曼猫' },
                { id: 'bomb', name: '孟买猫' },
                { id: 'bslo', name: '英国长毛猫' },
                { id: 'bsho', name: '英国短毛猫' },
                { id: 'buri', name: '布尔米拉' },

                { id: 'cspa', name: '加州亮片猫' },
                { id: 'ctif', name: '尚蒂伊蒂芙尼' },
                { id: 'char', name: '查特勒' },
                { id: 'chau', name: '乔西' },
                { id: 'chee', name: '猎豹' },
                { id: 'csho', name: '重点色短毛猫' },
                { id: 'crex', name: '康沃尔霸王龙' },
                { id: 'cymr', name: '西姆里克' },
                { id: 'cypr', name: '塞浦路斯' },
                { id: 'drex', name: '德文霸王龙' },
                { id: 'dons', name: '顿斯科伊' },
                { id: 'emau', name: '埃及猫' },
                { id: 'ebur', name: '欧洲缅甸猫' },
                { id: 'esho', name: '异国短毛猫' },

                { id: 'hbro', name: '哈瓦那棕猫' },
                { id: 'hima', name: '喜马拉雅猫' },
                { id: 'jbob', name: '日本短尾' },
                { id: 'java', name: '爪哇猫' },
                { id: 'khao', name: '考马尼猫' },
                { id: 'kuri', name: '库里利安猫' },
                { id: 'lape', name: '拉珀姆猫' },
                { id: 'mcoo', name: '缅因猫' },
                { id: 'mala', name: '马来猫' },
                { id: 'manx', name: '马恩岛猫' },
                { id: 'munc', name: '曼基金猫' },
                { id: 'nebe', name: '内伯龙猫' },
                { id: 'norw', name: '挪威森林猫' },
                { id: 'ocic', name: '奥卡特猫' },
                { id: 'orie', name: '东方猫' },

                { id: 'pers', name: '波斯猫' },
                { id: 'pixi', name: '精灵猫' },
                { id: 'raga', name: '布偶猫' },
                { id: 'ragd', name: '布娃娃猫' },
                { id: 'rblu', name: '俄罗斯蓝猫' },
                { id: 'sava', name: '草原猫' },
                { id: 'sfol', name: '苏格兰折耳猫' },
                { id: 'srex', name: '塞尔扣克火山猫' },
                { id: 'siam', name: '暹罗猫' },
                { id: 'sibe', name: '西伯利亚猫' },
                { id: 'sing', name: '新加坡猫' },
                { id: 'snow', name: '雪猫' },
                { id: 'soma', name: '索马里猫' },
                { id: 'sphy', name: '斯芬克斯猫' },

                { id: 'tonk', name: '东奇尼塞猫' },
                { id: 'toyg', name: '玩具虎猫' },
                { id: 'tang', name: '土耳其安哥拉猫' },
                { id: 'tvan', name: '土耳其猫' },
                { id: 'ycho', name: '约克巧克力猫' },
            ]
        }
    },
    components: {
        search,
        waterFall
    },
    methods: {
        updateCatList: function (data) {
            this.catsList = [];
            data.forEach(cat => {
                this.catsList.push(cat);
            });
        },
        updateKeyWords: function (val) {
            console.log('updatekeyword');
            this.keywords = val;
        },
        addCatList: function (data) {
            data.forEach(cat => {
                this.catsList.push(cat);
            });
        }
    }
}

</script>
  
<style scoped>
.show-box {
    width: 98vw;
    height: calc(100vh - 80px);
    border-radius: 20px;
    margin: 0 auto;
    background-color: #ffdef8;
    background-image: linear-gradient(194deg, #ffdef8 0%, #b5d7ff 69%, #ffffff 100%);
}
</style>
  