<template>
    <div>
        <h1>Welcome to {{title}}</h1>    
        <input type="text" v-model="input1"/>
        <button type="button" @click="getData">Get</button>
        <button type="button" @click="setData">Set</button>
        <select class="form-control" v-model="regin" @change="changeRegin">
            <option :key="i" :value="d.v" v-for="(d,i) in options">{{d.t}}</option>
        </select>
        <table class="table table-bordered">
            <tr :key="i" v-for="(d,i) in options">
                <td>{{d.v}}</td>
                <td>{{d.t}}</td>
            </tr>
        </table>
    </div>
</template>
<script>
export default {
    data() {        //데이타 선언
        return {
            title: "개발자의 품격",
            input1:"abc",
            options: [
                {v: "A", t:"Seoul"},
                {v: "B", t:"Busan"},
                {v: "C", t:"Jeju"},
                {v: "D", t:"Indo"},
            ],
            regin: "A",
            tableShow: false
        };
    },
    watch:{
        input1(){
            console.log(this.input1)
        }
    },
    methods:{
        getData(){
            alert(this.input1);      //메소드 안에서 데이터에 접근을 하려면 this로 접근 가능
        },
        setData(){
            this.input1="12345";
        },
        changeRegin(){
            alert(this.regin)
        }
    },
    //라이클 사이클
    beforeCreate() {

    },
    created(){ //화면이 띄어질 때 미리 데이타를 가져 올 때 렌더링

    },
    beforeMount(){ //화면이 로딩 될 때 렌더링

    },
    mounted(){ //화면이 로딩 될 때 렌더링

    },
    beforeUpdate(){ //데이터가 변경전 렌더링

    },
    updated(){  //데이터가 변경후 때 렌더링

    },
    beforeDestroy(){

    },
    destroyed(){

    }
}
</script> 