<template>
  <div class="red lighten-3 pa-3">
      <h3>자세한 회원정보 확인 합니다.</h3>
      <p>상세상항</p>
      <v-list dense>
          <v-list-tile>
              <v-list-tile-content>이름:</v-list-tile-content>
              <v-list-tile-content class="align-end">
                  {{ name }}
              </v-list-tile-content>
          </v-list-tile>
          <v-list-tile>
              <v-list-tile-content>주소:</v-list-tile-content>
              <v-list-tile-content class="align-end">
                  {{ address }}
              </v-list-tile-content>
          </v-list-tile>
          <v-list-tile>
              <v-list-tile-content>전화:</v-list-tile-content>
              <v-list-tile-content class="align-end">
                  {{ phone }}
              </v-list-tile-content>
          </v-list-tile>
          <v-list-tile>
              <v-list-tile-content>반려견:</v-list-tile-content>
              <v-list-tile-content class="align-end">
                  {{ hadDog }}
              </v-list-tile-content>
              
          </v-list-tile>
          <v-list-tile>
              <v-list-tile-content>수정일자:</v-list-tile-content>
              <v-list-tile-content class="align-end">
                  {{ editedDate }}
              </v-list-tile-content>
              
          </v-list-tile>
      </v-list>
  </div>
</template>
<script>
import { eventBus } from '../main'

export default {
    data () {
        return{
            editedDate : null
        }
    },
    props:['name','address','phone','hadDog'],
    computed: {
        hasDog() {
            return this.hasDog === true ? '있슴' : '없음'
        }
    },
    created() {
        eventBus.$on('userWasEdit',(date) => {
            this.editedDate = date
        })
    }
}
</script>