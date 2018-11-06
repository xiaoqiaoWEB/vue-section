<template>
    <div>
        <h1>bottom</h1>
    </div>
</template>
<script>
export default {
    created() {
        //在这this.$root.$on 监听事件
        this.$root.$on("toBottomFn", (v) => {
            console.log("找到了",v)
        })
    }
}
</script>
