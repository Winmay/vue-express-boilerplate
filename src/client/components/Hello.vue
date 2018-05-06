<template>
  <div>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
import AjaxModel from '../../server/model/ajaxModel'
  import axios from 'axios'
// import {loginIn} from '../../sqlServer/api';
export default {
  data: function () {
    return {
      // note: changing this line won't causes changes
      // with hot-reload because the reloaded component
      // preserves its current state and we are modifying
      // its initial state.
      msg: 'Hello World!',
      value: []
    }
  },
  created: function(){
      console.log(this.value);
      axios({
          method: 'get',
          url: '/api/list',
          data: {}
      }).then(function(response){
          console.log(response);
      }).catch(function(error) {
          console.log(error);
      });
      /*AjaxModel.ajaxGet('/api/list', res => {
          console.log(res);
      })*/
      /*AjaxModel.ajaxPost(loginIn, {"userName": 'qq',"password":'123'})
      .then((res) => {
          console.log(res);
      })
      .catch((error) => {
          console.log(error);
        // error
      })*/
  }
}
</script>
