<template>
  <div id="app">
    <!--<commontop></commontop>-->
    <router-view/>

  </div>
</template>

<script>


// import commontop from './components/commontop'
export default {
  name: 'App',
  data(){
    return {
      //some data
    }
  },
  created: function () {

//    this.$axios({
//      method: 'post',
//      url: 'http://192.168.10.27:8887/login.json',
//      headers: {
//        'Content-Type': 'application/x-www-form-urlencoded; charset=UTF-8'
//      },
//      data: { name: 'test10', pwd:'newtest10'}
//    }).then(data => {
//    })

//     axios.post('http://192.168.10.27:8887/login.json', {name: 'test10', pwd:'newtest10'}, {
//      headers: {
//        'Content-Type': 'application/x-www-form-urlencoded',
//      },
//    }).then(response => response.data)
//      .then(data => {
//      });

  },
  mounted: function() {
    $(document).click(function(){
      $(".hoverLogout").fadeOut();
    });
    $(".title_rig").click(function (event) {
      event.stopPropagation();
//        $(".hoverLogout").fadeIn();
      $(".hoverLogout").slideDown()
    })

    $(".title_rig").hover(function (event) {
      $(".hoverLogout").addClass("divshow")
    },function () {
      $(".hoverLogout").removeClass("divshow")
    })

  }


}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
  body{
    margin: 0;
    padding: 0;
  }
</style>
