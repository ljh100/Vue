<template>
  <div class="blue lighten-3 pa-3">
    <h1>User 컴포넌트</h1>
    <p>이름: {{ name }}</p>
    <!-- <button class="btn button-normal" @click="ChangeName()">이름변경</button> -->
    <v-btn color="success" @click="ChangeName()">이름변경</v-btn>
    <hr>
    <v-layout row wrap>
      <v-flex xs12 sm6>
        <!-- <UserDetail :childofname="{name: 'hoza',familyname: 'lee'}"></UserDetail> -->
        <UserDetail :childofname="name"></UserDetail>
      </v-flex>
      <v-flex xs12 sm6>
        <UserEdit></UserEdit>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
import UserDetail from "./UserDetail.vue"
import UserEdit from "./UserEdit.vue"

export default {
  components: {
    UserDetail,
    UserEdit
  },
  data () {
      return {
          name: "이준희 뷰제이에스"
      }
  },
  methods: {
      ChangeName () {
          this.name = "이은경 뷰티파이"
      }
  }
}
</script>

