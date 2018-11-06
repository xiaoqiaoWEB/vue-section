<template>
    <div>
        <input type="text" value="" placeholder="情书投入" @keydown="downFn">
    </div>
</template>
<script>
export default {
    name:"hInput",
    methods: {
        downFn() {
            console.log('通知 bottomA')
            //利用 根实例额 做 event bus   发布事件
            this.$root.$emit('toBottomFn','通知 bottomB'); 
        }
    }
}
</script>

