<template>
  <div class="blue lighten-3 pa-3">
    <h1>User 컴포넌트</h1>
    <p>이름: {{ name }}</p>
    <!-- <button class="btn button-normal" @click="ChangeName()">이름변경</button> -->
    <v-btn color="success" @click="ChangeName()">이름변경</v-btn>
    <hr>
    <v-layout row wrap>
      <v-flex xs12 sm6>
        <UserDetail2 
            :name="name" 
            :address="address" 
            :phone="phone" 
            :hadDog="hadDog" 
            >
        </UserDetail2>
      </v-flex>
      <v-flex xs12 sm6>
        <UserEdit2
            :name="name" 
            :address="address" 
            :phone="phone" 
            :hadDog="hadDog"
            @child = "parents"
            >
        </UserEdit2>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
import UserDetail2 from "./UserDetail2.vue"
import UserEdit2 from "./UserEdit2.vue"


export default {
  components: {
    UserDetail2,
    UserEdit2
  },
  data () {
      return{
        name : "Hoza",
        address : "Seoul",
        phone : "1234-5678",
        hadDog : true
      }

  },
  methods: {
      parents(user){
          console.log("부모가 잘 받았다")
          this.name = user.name,
          this.address=user.address,
          this.phone=user.phone,
          this.hadDog = user.hadDog

      }
  }
}
</script>