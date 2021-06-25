<!--<template>-->
<!--  &lt;!&ndash;  所有的元素必须在根节点下&ndash;&gt;-->
<!--  <div>-->
<!--    <h1>个人信息</h1>-->
<!--    {{$route.params.id}}-->
<!--  </div>-->
<!--</template>-->


<!--<script>-->
<!--    export default {-->
<!--        name: "Profile"-->
<!--    }-->
<!--</script>-->
<template>
  <div>
    个人信息
    {{ id }}
  </div>
</template>
<script>
    export default {
        name: "UserProfile",
        beforeRouteEnter: (to, from, next) => {
            console.log("准备进入个人信息页");
            next(vm => {
                //进入路由之前执行getData方法
                vm.getData()
            });
        },
        beforeRouteLeave: (to, from, next) => {
            console.log("准备离开个人信息页");
            next();
        },
        //axios
        methods: {
            getData: function () {
                this.axios({
                    method: 'get',
                    url: 'http://localhost:8080/static/mock/data.json'
                }).then(function (response) {
                    console.log(response)
                })
            }
        }
    }
</script>
<style scoped>
</style>


<style scoped>

</style>
