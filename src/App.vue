<template>
  <div class="dashboard  min-h-screen flex bg-gray-100 ">
    <!-- 左侧垂直导航栏 -->
    <nav class="bg-white w-16 flex flex-col items-center py-4 fixed h-full">
      <div class="relative group">
        <button class="mb-6 p-3 rounded-lg bg-blue-100 text-blue-600">
          <HomeIcon class="w-6 h-6" />
        </button>
        <div class="absolute left-16 top-0 bg-blue-600 text-white px-3 py-2 rounded-r-lg opacity-0 group-hover:opacity-100 transition-opacity duration-200 ease-in-out whitespace-nowrap">
          首页
        </div>
      </div>
      <button class="mb-6 p-3 rounded-lg hover:bg-gray-100">
        <UserIcon class="w-6 h-6 text-gray-600" />
      </button>
      <button class="mb-6 p-3 rounded-lg hover:bg-gray-100">
        <BriefcaseIcon class="w-6 h-6 text-gray-600" />
      </button>
      <button class="mb-6 p-3 rounded-lg hover:bg-gray-100">
        <FileTextIcon class="w-6 h-6 text-gray-600" />
      </button>
      <button class="mb-6 p-3 rounded-lg hover:bg-gray-100">
        <MailIcon class="w-6 h-6 text-gray-600" />
      </button>
    </nav>

    <!-- 主要内容区 -->
    <div class="flex-1 ml-16">
      <!-- 顶部导航栏 -->
      <nav class="bg-white shadow-sm p-4 flex justify-between items-center">
        <div class="flex items-center">
          <!-- <img src="/placeholder.svg?height=48&width=48" alt="Logo" class="w-12 h-12 mr-6"> -->
          <input type="text" placeholder="在全部简历中搜索" class="border rounded-md px-4 py-2 w-96 text-lg">
        </div>
        <div class="flex items-center space-x-6">
          <span class="text-lg">来播文化3</span>
          <button class="p-3 rounded-full bg-gray-200">
            <CalendarIcon class="w-6 h-6 text-gray-600" />
          </button>
          <button class="p-3 rounded-full bg-gray-200">
            <BellIcon class="w-6 h-6 text-gray-600" />
          </button>
          <button class="p-3 rounded-full bg-gray-200">
            <HelpCircleIcon class="w-6 h-6 text-gray-600" />
          </button>
          <div class="bg-yellow-400 rounded-full w-12 h-12 flex items-center justify-center text-white font-bold text-lg">
            无
          </div>
        </div>
      </nav>

      <div class="container mx-auto mt-10 px-6 max-w-7xl">
        <!-- 数据卡片 -->
        <div class="grid grid-cols-6 gap-6 mb-10">
          <div class="bg-blue-500 text-white rounded-lg p-6">
            <h3 class="text-4xl font-bold mb-2">5</h3>
            <p class="text-xl">倍简历加速</p>
            <p class="text-lg mt-2">AI智聘</p>
          </div>
          <div class="bg-yellow-400 text-white rounded-lg p-6">
            <h3 class="text-4xl font-bold mb-2">67</h3>
            <p class="text-xl">本周：1419</p>
            <p class="text-lg mt-2">简历初筛</p>
          </div>
          <div class="bg-purple-500 text-white rounded-lg p-6">
            <h3 class="text-4xl font-bold mb-2">0</h3>
            <p class="text-xl">今日跟进</p>
          </div>
          <div class="bg-pink-500 text-white rounded-lg p-6">
            <h3 class="text-4xl font-bold mb-2">0</h3>
            <p class="text-xl">今日面试</p>
            <p class="text-lg mt-2">未面试：0 已面试：0</p>
          </div>
          <div class="bg-green-500 text-white rounded-lg p-6">
            <h3 class="text-4xl font-bold mb-2">0</h3>
            <p class="text-xl">待入职</p>
          </div>
          <div class="bg-blue-400 text-white rounded-lg p-6">
            <h3 class="text-4xl font-bold mb-2">39,414</h3>
            <p class="text-xl">全部简历</p>
            <p class="text-lg mt-2">+252</p>
          </div>
        </div>

        <!-- 日历和统计信息 -->
        <div class="grid grid-cols-3 gap-8">
          <!-- 面试日历 -->
          <div class="bg-white rounded-lg shadow p-8">
            <h3 class="text-2xl font-semibold mb-6">面试日历</h3>
            <p class="text-xl mb-2">2024年08月12日</p>
            <p class="text-lg text-gray-600 mb-4">农历七月初九，星期一</p>
            <!-- 日历网格 -->
            <div class="grid grid-cols-7 gap-2 mt-6">
              <!-- 这里应该循环生成日历日期 -->
              <div v-for="day in 31" :key="day" class="text-center p-2">
                {{ day }}
              </div>
            </div>
          </div>

          <!-- 今日待办 -->
          <div class="bg-white rounded-lg shadow p-8">
            <h3 class="text-2xl font-semibold mb-6">今日待办</h3>
            <ul class="list-disc pl-6 text-lg space-y-4">
              <li>您今天卡片入简历，快去寻人吧！</li>
              <li>您今天有67份新简历，请尽快查看处理！</li>
            </ul>
          </div>

          <!-- BOSS智聘 -->
          <div class="bg-white rounded-lg shadow p-8">
            <h3 class="text-2xl font-semibold mb-6">BOSS智聘</h3>
            <div class="grid grid-cols-3 gap-6 mb-6">
              <div>
                <p class="text-3xl font-bold mb-2">4,150</p>
                <p class="text-lg text-gray-600">昨日沟通</p>
              </div>
              <div>
                <p class="text-3xl font-bold mb-2">253</p>
                <p class="text-lg text-gray-600">昨日简历</p>
              </div>
              <div>
                <p class="text-3xl font-bold mb-2">0</p>
                <p class="text-lg text-gray-600">昨日面试</p>
              </div>
            </div>
            <h4 class="text-xl font-semibold mb-4">近七天简历投递数量</h4>
            <!-- 这里应该插入一个图表组件，为了简化，我们用文本代替 -->
            <p class="text-lg">图表显示08-06到08-12的数据趋势</p>
          </div>
        </div>

        <!-- AI人才库和51智聘 -->
        <div class="grid grid-cols-2 gap-8 mt-10">
          <div class="bg-white rounded-lg shadow p-8">
            <h3 class="text-2xl font-semibold mb-6">AI人才库</h3>
            <div class="flex justify-between mb-6">
              <div>
                <p class="text-3xl font-bold mb-2">39,414</p>
                <p class="text-lg text-gray-600">总计</p>
              </div>
              <div>
                <p class="text-3xl font-bold mb-2">67</p>
                <p class="text-lg text-gray-600">今日入库</p>
              </div>
              <div>
                <p class="text-3xl font-bold mb-2">653</p>
                <p class="text-lg text-gray-600">近三天活跃</p>
              </div>
            </div>
            <!-- 这里应该插入一个饼图组件，为了简化，我们用文本代替 -->
            <p class="text-lg">饼图显示AI人才库的分布情况</p>
          </div>

          <div class="bg-white rounded-lg shadow p-8">
            <h3 class="text-2xl font-semibold mb-6">51智聘</h3>
            <div class="grid grid-cols-3 gap-6 mb-6">
              <div>
                <p class="text-3xl font-bold mb-2">0</p>
                <p class="text-lg text-gray-600">前程职位</p>
              </div>
              <div>
                <p class="text-3xl font-bold mb-2">0</p>
                <p class="text-lg text-gray-600">昨日点击</p>
              </div>
              <div>
                <p class="text-3xl font-bold mb-2">0</p>
                <p class="text-lg text-gray-600">昨日投递</p>
              </div>
            </div>
            <h4 class="text-xl font-semibold mb-4">近七天简历投递数量</h4>
            <!-- 这里应该插入一个图表组件，为了简化，我们用文本代替 -->
            <p class="text-lg">图表显示近七天的投递数量趋势</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import './index.css'
import { HomeIcon, UserIcon, BriefcaseIcon, FileTextIcon, MailIcon, CalendarIcon, BellIcon, HelpCircleIcon } from 'lucide-vue-next'
</script>

<style scoped>
/* 可以添加一些自定义样式 */
</style>
