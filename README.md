# vueTips
看vue官网的时候需要注意的一些地方，记录一下
官网：var vm = new Vue({
  el: '#example',
  data: {
    message: '123'
  }
})
vm.message = 'new message' // 更改数据
vm.$el.textContent === 'new message' // false
Vue.nextTick(function () {
  vm.$el.textContent === 'new message' // true
})
自己写的：
 <div id="example">{{message}}</div>
 var vm = new Vue({
     el: '#example',
     data: {
              message: 2 //本质是一个 字符串 而不是一个数
            }
        })
      vm.message = 3
      console.log(vm.$el.textContent === 3) //false
      Vue.nextTick(function () {
          console.log(vm.$el.textContent === 3) //false
  })
