<template>
  <div class="app6">
    <div ref="input1" v-show="false">http://system.okuro-team.com/gate?filter={{ tem.strin }}</div>
    <ul class="nd1">
     
      <li class="nd" v-bind:style="{ backgroundColor: todo.active}" v-for="todo in todos" :key="todo.id">
         <h2 class="td"  v-show="todo.td">{{ todo.td1 }}</h2>
        <button class="btn" v-bind:style="{ backgroundColor: todo.active1}" @click="todo.an = !todo.an">{{todo.name}}</button>
        {{ todo.title }}
        <span>  {{ todo.nd }}</span>
        <div class="an" v-show="todo.an">
          <p class="nd3">{{ todo.nd }}</p>
          <div class="form">
            Parameters
            <button class="try" @click="todo.complete = !todo.complete" v-show="!todo.complete">
              Try it out
            </button>
            <button class="try" @click="todo.complete = !todo.complete"  v-show="todo.complete">
              cancel
            </button>
          </div>
          <div class="nd4">
            <div class="td3">
              <p class="tt">name</p>
              <p class="tt">Description</p>
            </div>
            <div class="nd5">
              <p class="tt">filter</p>
              <p class="tt">nhập filter</p>
              <input type="text" class="inp1"  v-model="tem.strin" v-show="todo.complete">
               <button class="ttt" v-show="todo.complete" @click="onSubmit()">Excute</button>
            </div>
          </div>
          <div class="form">
            Responses
            <button class="try">Response content</button>
          </div>
          <div class="nd4">
            <div class="form1" v-show="todo.complete">
             <div class="them">curl -X GET "http://system.sieuviet-team.com/gate?filter={{ tem.strin }}" -H "accept: application/json"</div>
             <div class="them1" ref="input">http://system.okuro-team.com/gate?filter={{ tem.strin }} </div>
            </div>
            <div class="td3">
              <p class="tt">Code</p>
              <p class="tt">Description</p>
            </div>
            <div class="nd5">
              <p class="tt">200</p>
              <p class="tt">
               <input type="text"  class="code" value="successfully">
               <input type="text" class="codes" value="{ 'code': 0, 'msg': 'string', 'data': {} }">
              </p>
            </div>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "app4",
  data() {
    return {
      todos: [
        { id: 1, td1:'GATE', title: "/gate", nd: "List gate", complete: false, an: false, td: true , name: 'GET'},
        {
          id: 2,
          title: "/gate/gate-job",
          nd: "Cổng công việc",
          complete: false,
          an: false, name: 'GET'
        },
        {
          id: 3,
          title: "/fe/gate/gate-job",
          nd: "Mức độ công việc",
          complete: false,
          an: false, name: 'GET'
        },
         { id: 4,td1: 'JOB', title: "/job-field", nd: "list job field", complete: false, an: false, td: true,  name: 'GET' },
        {
          id: 5,
          title: "/fe/job-level",
          nd: "list job level",
          complete: false,
          an: false, name: 'GET'
        },
        { id: 6,td1: 'Common Data', title: "/fe/common-data", nd: "common-data", complete: false, an: false, td: true, name: 'GET' },
         { id: 7,td1: 'Branch', title: "/branch-by-province/{province_id}", nd: "Branch", complete: false, an: false, td: true, name: 'GET' },
         {
          id: 8, td1:'Check Blacklist Keyword',name: 'POST',active:'rgb(73 204 144 / 22%)',  active1:'#49cc90',
          title: "check-blacklist-keyword",
          nd: "check-blacklist-keywordl",
          complete: false,
          an: false,
          td: true
        },
         {
          id: 9, td1:'Detail Template Email',
          title: "/email/detail-template",
          nd: "Detail Template Email",
          complete: false,
          an: false,
          td: true, name: 'GET'
        },
        {
          id: 10, td1:'Document Guide',
          title: "/document-guide",
          nd: "Tài liệu hướng dẫn",
          complete: false,
          an: false,
          td: true, name: 'GET'
        },
        {
          id: 11, 
          title: "/document-guide/{id}",
          nd: "Detail Tài liệu hướng dẫn",
          complete: false,
          an: false,
          td: false, name: 'GET'
        },
         {
          id: 12, 
          title: "/document-guide-display/{code}",
          nd: "Detail Tài liệu hướng dẫn",
          complete: false,
          an: false,
          td: false, name: 'GET'
        },
        {
          id: 13, td1:'District',
          title: "/district",
          nd: "Danh sách quận huyện",
          complete: false,
          an: false,
          td: true, name: 'GET'
        },
      ],
      tem:[
        { trin:''},
      ]
    };
  },
  methods: {
    toggleActive() {
      if (this.complete == true) {
        this.complete = false;
      } else {
        this.complete = true;
      }
    },
     onSubmit: function() {      
        alert(this.$refs.input1.innerText)
      }
  },
  mounted() {
    
  },
};
</script>
<style scoped>
.app6 {
  width: 100%;
  height: 100%;
}
.them, .them1{
  width: 80%;
  height: 50px;
  background-color: #333;
  color:aliceblue;
  padding-left: 20px;
  padding-top:5px;
  margin-bottom: 10px;
  margin-left: 10px;
}
.code{
  width: 250px;
  height: 25px;
  margin-right: 80%;
 margin-bottom: 10px;
  padding: 3px;
  float: left;
  background-color: #333;
  color: aliceblue;
}
.codes{
  width: 250px;
  height: 90px;
  padding: 0px 30px;
  background-color: #333;
  color: aliceblue;
  text-align: left;
}
.ttt{
    width: 80%;
    height: 30px;
    margin-top: 50px;
    margin-left: 90px;
    background-color:#61affe;
}
.inp1{
  width: 150px;
  height: 25px;
  padding: 3px;
  transform: translateX(-150px);
}
.tt {
  float: left;
  margin-right: 200px;
  font-size: 11px;
  padding-left: 10px;
}
.nd5 {
  text-align: left;
  width: 100%;
  height: 5%;
  margin-top: 10px;
}
.nd4 {
  width: 100%;
  height: 35%;
  text-align: left;
  margin-top: 5px;
}
.td3 {
  width: 100%;
  height: 30px;
  padding: 0 -10px;
  border-bottom: 1px solid #333;
}
.try {
  float: right;
  width: 9%;
  height: 95%;
  background-color: white;
  transform: translateY(-5px);
  border-radius: 5px;
  margin-right: 15px;
  cursor: pointer;
}
.form {
  width: 100%;
  height: 7%;
  background-color: white;
  padding-top: 10px;
  text-align: left;
  padding-left: 10px;
  margin-bottom: 10px;
}
.nd3 {
  width: 100%;
  height: 7%;
  text-align: left;
  padding-left: 10px;
}
.btn {
  width: 50px;
  height: 30px;
  background-color: #61affe;
  border-radius: 2px;
  border: none;
  color: whitesmoke;
  font-weight: bold;
  margin-right: 10px;
  float: left;
  cursor: pointer;
  margin-left: 10px;
}
.an {
  width: 100%;
  height: 900px;
  padding: 0 !important;
  margin-top: 20px;
  text-align: center;
  border-top: 1px solid #61affe;
}
.td {
  width: 100.3%;
  height: 30px;
  transform: translateY(-18px);
  padding: 7px 5px;
  text-align: left;
  background-color: rgba(34, 33, 33, 0.192);
  border-bottom: 1px solid #333;
}
.nd1 {
  padding-bottom: 20px;
}
li {
  list-style: none;
}
span {
  font-size: 12px;
  padding-left: 8px;
}
.nd {
  width: 100%;
  height: auto;
  margin: 10px;
  padding: 8px 13px 20px 0px;
  border: 1px solid #61affe;
  background-color: #61affe1a;
  border-radius: 5px;
  text-align: left;
  vertical-align: bottom;
  font-weight: bold;
  list-style: none;
}
ul {
  list-style: none;
  width: 75%;
  padding: 0 10%;
}
</style>