<template>
  <div>
    <div class="breadcrumb">
      <div class="container">
        <h2>
          <a href="">首页</a>&gt;<a href="">公司动态</a>
        </h2>
      </div>
    </div>
    <!--页面主体-->
    <div class="main container">
      <div class="news">
        <ul>
          <li v-for="(temp,key) in newsList" :key=key>
            <span>{{temp.pubtime}}</span>
            <a href="">{{temp.title}}</a></li>
        </ul>
      </div>
      <!-- 分页导航-->
      <div class="pages">
        <a href="" @click.self.prevent="togglePage(-1)" :class="{default:pno<=1}">上一页</a>
        <a v-for="(temp,key) in realPage" :key=key :class="{cur:pno==temp}" href="" @click.self.prevent="changePage(temp)">{{temp}}</a>
        <a href="" @click.self.prevent="togglePage(1)" :class="{default:pno>=pageCount}">下一页</a>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data (){
    return {
      newsList:[],
      pno:1,
      pageCount:0
    }
  },
  mounted(){
    this.getList() //挂载的时候获取新闻列表
  },
  watch: { //监听页码变化,这里可以通知其他组件做出相应改变
      pno: function(newValue , oldValue){
          console.log(arguments);
      }
  },
  methods: {
    getList(){
      var self=this;
      self.$axios({
        method: 'get',
        baseURL:'http://127.0.0.1:3000/',
        url: '/news/list/'+self.pno,
        withCredentials: true,
        responseType: 'json',
        transformResponse:function(response){
          self.newsList=response.data;
          self.pageCount=response.pageCount;
        },
      });
    },
    // 点击页面切换
    changePage(index){
      var self=this;
      self.pno=index;
      self.$axios({
        method: 'get',
        baseURL:'http://127.0.0.1:3000/',
        url: '/news/list/'+self.pno,
        withCredentials: true,
        responseType: 'json',
        transformResponse:function(response){
          self.newsList=response.data;
          self.pageCount=response.pageCount;
        },
      });
    },
    //点击上一页/下一页事件
    togglePage(index){ //通过对index赋值来识别按钮
      var self=this;
      if(index>0){
        if(self.pno>=self.pageCount)return;
        self.pno++;
      }else{
        if(self.pno<=1)return
        self.pno--;
      }
      self.$axios({
        method: 'get',
        baseURL:'http://127.0.0.1:3000/',
        url: '/news/list/'+self.pno,
        withCredentials: true,
        responseType: 'json',
        transformResponse:function(response){
          self.newsList=response.data;
          self.pageCount=response.pageCount;
        },
      });
    }
  },
  computed :{
    realPage:function(){
      let left=1;
      let right=this.pageCount;
      var realCount=[];
      if(right>=3){//控制最多显示3页
        if(this.pno>1 && this.pno+1<this.pageCount){
          left=this.pno-1;
          right=this.pno+1;
        }else {
          if(this.pno<=3){
          left=1;
          right=3;
         }else{
           left=this.pageCount-2;
           right=this.pageCount;
         }
        }
      }
      while(left<=right){
        realCount.push(left);
        left++;
      }
      return realCount;
    }
  }
}
</script>

