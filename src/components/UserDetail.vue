<template>
  <div class="red lighten-3 pa-3">
    <h3>자세한 회원 정보를 확인합니다.</h3>
    <p>{{ childofname }}</p>
    <!-- <p>{{ childofname.familyname }}</p> -->
    <p>{{ sayHello }}</p>
    <v-btn @click="switchName()">변경</v-btn>
  </div>
</template>
<script>
export default {
    props: {
        childofname: {
            type: String,
            //required: true,
            default: 'Lego'
        }
    },
    data () {
        return{
            age:40
            
        }
    },
    computed:{
        sayHello () {
           return  this.childofname+ "입니다"
        }
    },
    methods:{
        switchName() {
            this.childofname='커뮤'
        }
    }
}
</script>
