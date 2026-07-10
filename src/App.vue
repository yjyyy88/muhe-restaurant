<script setup>
const navItems = [
  { label: '菜单', href: '#menu' },
  { label: '环境', href: '#space' },
  { label: '到店', href: '#visit' },
]

const heroInfo = [
  { label: '今日营业', value: '17:30 - 23:00' },
  { label: '人均', value: '¥180 - ¥260' },
  { label: '位置', value: '上海 · 衡山路' },
]

const tableValues = [
  {
    number: '01',
    title: '像家一样热闹',
    text: '每晚都有暖胃汤品和现烤小食，先把一天的疲惫轻轻放下。',
  },
  {
    number: '02',
    title: '适合慢慢分享',
    text: '菜品分量适合两三人一起点，边吃边聊，刚好把夜晚拉长一点。',
  },
  {
    number: '03',
    title: '被照顾的小细节',
    text: '灯光、座位和上菜节奏都尽量舒服，让每一桌都能自在相处。',
  },
]

const dishes = [
  {
    tag: '炭烤',
    title: '迷迭香炭烤牛排',
    text: '熟成牛排配烤蒜泥、时令根茎蔬菜和红酒肉汁。',
    price: '¥150',
  },
  {
    tag: '当季',
    title: '柠檬黄油海鲈鱼',
    text: '外皮煎脆，搭配白芦笋、酸豆和轻盈香草汁。',
    price: '¥168',
  },
  {
    tag: '手作',
    title: '松露菌菇宽面',
    text: '手工宽面、混合菌菇、帕玛森芝士和一抹黑松露香气。',
    price: '¥128',
  },
]

const spaceFeatures = [
  '开放式厨房，能看见每一道菜的完成过程。',
  '晚间低噪音乐，适合轻松聊天。',
  '每日 18:00 前接受当晚订位确认。',
]
</script>

<template>
  <header class="site-header">
    <a class="brand" href="#" aria-label="暮禾餐厅首页">
      <span class="brand-mark">暮</span>
      <span>暮禾餐厅</span>
    </a>
    <nav class="nav" aria-label="主导航">
      <a v-for="item in navItems" :key="item.href" :href="item.href">
        {{ item.label }}
      </a>
    </nav>
    <a class="header-cta" href="tel:021-88661234">电话订位</a>
  </header>

  <main>
    <section class="hero" aria-label="暮禾餐厅首页首屏">
      <img
        class="hero-image"
        src="/assets/hero-restaurant.png"
        alt="暮禾餐厅温暖灯光下的餐桌、酒杯与当季菜品"
      />
      <div class="hero-overlay"></div>
      <div class="hero-content">
        <p class="eyebrow">Seasonal Kitchen · Shanghai</p>
        <h1>暮禾餐厅</h1>
        <p class="hero-copy">
          用当季食材做一顿不赶时间的晚餐。炭烤、慢炖、手工甜点和一张刚刚好的餐桌，
          适合两个人，也适合久违的一群人。
        </p>
        <div class="hero-actions">
          <a class="button primary" href="#visit">立即订位</a>
          <a class="button secondary" href="#menu">查看菜单</a>
        </div>
        <dl class="hero-info" aria-label="餐厅关键信息">
          <div v-for="item in heroInfo" :key="item.label">
            <dt>{{ item.label }}</dt>
            <dd>{{ item.value }}</dd>
          </div>
        </dl>
      </div>
    </section>

    <section class="section intro" aria-label="Our Table 餐厅理念">
      <div class="intro-copy">
        <p class="eyebrow dark">Our Table</p>
        <h2>留一盏灯，等你坐下来慢慢吃饭。</h2>
        <p>
          暮禾想做的，是一间下班后也愿意来的小餐厅。热汤、刚出炉的面包、
          适合分享的主菜，还有不急不赶的聊天时间，都在这张桌上慢慢展开。
        </p>
      </div>
      <div class="intro-panel">
        <article v-for="item in tableValues" :key="item.number">
          <span>{{ item.number }}</span>
          <div>
            <h3>{{ item.title }}</h3>
            <p>{{ item.text }}</p>
          </div>
        </article>
        <div class="intro-note">
          <strong>今晚给你留了位置</strong>
          <span>提前说一声，我们会把餐桌准备好</span>
        </div>
      </div>
    </section>

    <section class="section menu-section" id="menu">
      <div class="section-heading">
        <p class="eyebrow dark">Signature</p>
        <h2>今晚推荐</h2>
      </div>
      <div class="menu-grid">
        <article v-for="dish in dishes" :key="dish.title" class="dish-card">
          <span class="dish-tag">{{ dish.tag }}</span>
          <h3>{{ dish.title }}</h3>
          <p>{{ dish.text }}</p>
          <strong>{{ dish.price }}</strong>
        </article>
      </div>
    </section>

    <section class="feature-band" id="space">
      <div class="feature-copy">
        <p class="eyebrow">Private Evening</p>
        <h2>小型聚餐、纪念日和周末晚餐，都能被妥帖照顾。</h2>
        <p>
          24 个室内座位、6 个吧台座位。可提前沟通忌口、花束、蛋糕和无酒精配餐。
        </p>
      </div>
      <div class="feature-list" aria-label="餐厅特色">
        <div v-for="(feature, index) in spaceFeatures" :key="feature">
          <span>{{ String(index + 1).padStart(2, '0') }}</span>
          <p>{{ feature }}</p>
        </div>
      </div>
    </section>

    <section class="section visit" id="visit">
      <div class="visit-card">
        <p class="eyebrow dark">Visit Us</p>
        <h2>来吃晚饭</h2>
        <p>上海市徐汇区衡山路 88 号 1 楼</p>
        <p>周二至周日 17:30 - 23:00，周一店休</p>
      </div>
      <form class="booking-form" aria-label="订位表单">
        <label>
          姓名
          <input type="text" name="name" placeholder="请输入姓名" />
        </label>
        <label>
          日期
          <input type="date" name="date" />
        </label>
        <label>
          人数
          <select name="party">
            <option>2 位</option>
            <option>3-4 位</option>
            <option>5-6 位</option>
            <option>包场咨询</option>
          </select>
        </label>
        <button type="submit">提交订位</button>
      </form>
    </section>
  </main>

  <footer class="footer">
    <span>暮禾餐厅</span>
    <span>电话：021-8866-1234</span>
    <span>Instagram：@muhe.table</span>
  </footer>
</template>
