# Vue 3

## 变化
* 自定义指令
* data
* v-model

## 新增
* emits
* 片段

## 移除
* $children
* filter
* .native

## 全新API


### 组合式API
Vue选项：函数
setup() {

}

ref:创建响应式变量
注册生命周期函数 Vue提供的钩子注册函数
watch函数

。。。

### Mixin
局部应用 mixins: []
全局应用 .mixin()

### 自定义指令


### teleport
  修改node位置
  
### 渲染函数：比模板更接近编译器
render() {
  return h({
    
  })
}