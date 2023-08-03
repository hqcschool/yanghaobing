<!--  -->
<template>
    <div class="AsPort">
        <h2>{{message}}</h2>
        <button @click="currtab = 'tab'">tab</button>
        <button @click="currtab = 'tab1'">tab1</button>
        <button @click="currtab = 'tab2'">tab2</button>
        <div v-show="currtab === 'tab'" id=img1>
            <img src="https://img1.baidu.com/it/u=3539595421,754041626&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1691168400&t=92147dc54c087237b747be417bfdc579"
                alt="">
        </div>
        <div v-show="currtab === 'tab1'">
            <img src="https://img2.baidu.com/it/u=3853345508,384760633&fm=253&fmt=auto&app=120&f=JPEG?w=800&h=1200" alt="">
        </div>
        <div v-show="currtab === 'tab2'">
            <img src="https://img1.baidu.com/it/u=1458656822,2078909008&fm=253&fmt=auto&app=120&f=JPEG?w=500&h=750" alt="">
        </div>

        <div class="carousel">
        <div class="image">
          <div v-for="(item, index) in image" :key="index" :class="{ 'active': currentIndex === index }">
            <img :src="item.src" alt="">
          </div>
        </div>
        <div class="controls">
          <span v-for="(item, index) in image" :key="index" @click="changeSlide(index)" :class="{ 'active': currentIndex === index }"></span>
        </div>
      </div>
        
       
    </div>
</template>

<script>
export default {
    name: "AsPort",
    data() {
        return {
        currtab: "tab",
        message:"你好太阳",
        currentIndex:0,
       image:[
        {   
            src:'https://img1.baidu.com/it/u=3566017934,720052675&fm=253&fmt=auto&app=138&f=JPEG?w=647&h=500'
        },
        {
          
            src:"https://img2.baidu.com/it/u=569567859,3207263806&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"
        },
        {
           
           src:'https://img1.baidu.com/it/u=1805271423,1669425307&fm=253&fmt=auto&app=138&f=JPEG?w=769&h=500'
        }
    ]
        }
    },
    // props: {
    //        msg:String
    // },
mounted() {
        this.startimageshow();
    },
  methods: {
     changeSlide(index) {
            this.currentIndex = index;
        },
        startimageshow() {
            setInterval(() => {
                this.currentIndex = (this.currentIndex + 1) % this.image.length;
            }, 3000); // 每3秒切换一张轮播图
        }
  },
    created() {

    },

}
</script>
<style lang="less" scoped>
/* @import url(); 引入css类 */
.carousel {
  position: relative;
  width: 100%;
  height: 300px;
}

.images {
  display: flex;
  transition: all 0.5s;
}

.images .active {
  opacity: 1;
}

.images img {
  width: 400px;
  height: 400px;
  object-fit: cover;
}

.controls {
  position: absolute;
  bottom: 10px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  justify-content: center;
  align-items: center;
}

.controls span {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background-color: #ccc;
  margin: 5px;
  cursor: pointer;
}

.controls span.active {
  background-color: #333;
}
#val {
    width: 500px;
    height: 500px;
    border: 1px solid #000;
    overflow: hidden;
}

button {
    width: 160px;
    height: 50px;
    border: 1px solid #000;
    margin-left: 3px;
}

img {
    width: 500px;
    height: 500px;
}

#img1 {
    display: block;
}</style>