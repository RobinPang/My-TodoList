<template>
  <div class="side_content">
    <nav aria-label="列表">
      <ul>
        <li v-for="(item,index) in list" :key="`navlist${index}`" @click="goto(item.path)">
          <div class="list-item" :class="{'active': route.path === item.path}">
            <i class="iconfont" :class="`icon-${item.icon}`"></i>
            <span class="item-title">{{item.title}}</span>
            <span class="item-count">6</span>
          </div>
        </li>
      </ul>
    </nav>
  </div>
</template>


<script setup lang="ts">
import { useRouter, useRoute } from 'vue-router'

const router = useRouter()
const route = useRoute()
const props = defineProps({
  list: {
    type: Object,
    default: () => {}
  }
})


// 跳转
function goto(path: string): void {
  router.push(path)
}
</script>

<style lang="less" scoped>
@import "./index";
</style>