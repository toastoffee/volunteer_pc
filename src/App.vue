<template>
<a-locale-provider :locale="zh_CN">
    <div id="app">
        <router-view></router-view>
    </div>
</a-locale-provider>
</template>

<script>
import zh_CN from 'ant-design-vue/lib/locale-provider/zh_CN'

export default {
    name: 'app',
    data() {
        return {
            zh_CN,
        }
    },
    beforeCreate(){
        let info = JSON.parse(localStorage.getItem('info'))
        this.$store.commit('commitInfo',info)
    }
}
</script>

<style>
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    height: 100%;
}
</style>
