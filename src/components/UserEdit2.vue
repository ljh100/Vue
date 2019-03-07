<template>
  <div class="red lighten-3 pa-3">
    <h3>자세한 회원 정보를 확인합니다.</h3>
    <p>상세사항</p>
    <v-flex xs12 sm6 md3>
        <v-text-field label="이름"
        v-model="user.name">
        </v-text-field>
    </v-flex>
    <v-flex xs12 sm6 md3>
        <v-text-field label="주소"
        v-model="user.address">
        </v-text-field>
    </v-flex>
    <v-flex xs12 sm6 md3>
        <v-text-field label="전화"
        v-model="user.phone">
        </v-text-field>
    </v-flex>
    <v-radio-group v-model="user.hadDog">
      <v-radio       
        label="반려견있음"
        :value="true"
      ></v-radio>
      <v-radio       
        label="반려견없음"
        :value="false"
      ></v-radio>
    </v-radio-group>
    <v-btn @click="ChangeUser">수정 완료</v-btn>
  </div>
</template>

<script>
import { eventBus } from '../main'

export default {
     props:['name','address','phone','hadDog'],
     data () {
         return {
             user: {}
         }
     },
     created (){
         this.user.name = this.name,
         this.user.address =this.address,
         this.user.phone = this.phone,
         this.user.hadDog = this.hasDog
     },
     methods: {
         ChangeUser() {
            // console.log(this.user)
             this.$emit('child',this.user)
            // child(this.user)
            //eventBus.$emit('userWasEdit',new Date())
            //이것도 가능 위와 동리
            eventBus.userWasEdited(new Date())
         }
     }
}
</script>
