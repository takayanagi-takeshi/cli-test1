<template>
  <div>
    <h2 id="outPutField">{{time}}</h2>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      time: ''
    }
  },
  created: function () {
    let that = this
    // console.log(this)
    // setInterval(this.getTime, 500);
        setInterval(that.getTime, 500);
        // setInterval(function(){
        //   console.log(this)
        // },500)
  },
  methods: {
    getTime: function () {
      //本日の日付オブジェクトを作る
      let today = new Date();
      let week = ['Sun','Mon','Tue','Wed','Thu','Fri','Sat'];
      // console.log(week[5]);

      //現在の時を取得
      // let hour = today.getHours();
      //010の場合、10。01の場合、01
      let hour = ("0"+today.getHours()).slice(-2);
      //現在の分を取得
      // let min = today.getMinutes();
      let min = ("0"+today.getMinutes()).slice(-2);
      //現在の秒を取得
      // let sec = today.getSeconds();
      let sec = ("0"+today.getSeconds()).slice(-2)
      //曜日を取得
      let day = today.getDay();
      // console.log(day);
      this.time = `${hour}：${min}：${sec} (${week[day]})`;
    }
  },
  beforeDestroy function () {
    clearInterval(this.)
  }

}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* p {
  color: blue;
} */

</style>
