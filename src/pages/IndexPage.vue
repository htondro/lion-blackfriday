<template>
  <q-page
    class="column items-center"
    :class="{ 'q-pa-md': $q.screen.lt.md }"
    style="max-width: 1140px; margin: auto"
    padding
  >
    <h1 class="text-center">تـــخفیف‌هــــای ســــوزان!</h1>
    <div class="col-auto full-width text-center">
      <q-img
        src="~assets/percentage-x1000.webp"
        class="gt-sm q-ma-auto"
        width="100%"
        style="max-width: 1000px; margin: auto"
        no-native-menu
      />
      <q-img
        src="~assets/percentage-x500.webp"
        class="lt-md"
        width="100%"
        style="max-width: 500px; margin: auto"
      />
    </div>
    <div class="lion-chip">تخفیف‌های جذاب لیون‌کامپیوتر رو از دست نده...!</div>
    <div class="col-auto full-width text-center" style="z-index: 5">
      <q-img
        src="~assets/lion-computer-x1000.webp"
        class="gt-sm q-ma-auto"
        width="100%"
        style="max-width: 1000px; margin: auto"
      />
      <q-img
        src="~assets/lion-computer-x500.webp"
        class="lt-md"
        width="100%"
        style="max-width: 500px; margin: auto"
        no-native-menu
      />
    </div>
    <div class="col-auto full-width text-center" style="margin-top: -0.75rem">
      <q-img
        src="~assets/date.webp"
        class="lt-md q-ma-auto"
        width="100%"
        style="max-width: 250px; margin: auto"
        no-native-menu
      />
      <q-img
        src="~assets/date.webp"
        class="gt-sm q-ma-auto"
        width="100%"
        style="max-width: 550px; margin: auto"
        no-native-menu
      />
    </div>
    <div class="col-auto full-width text-center q-my-lg">
      <q-btn
        label="مشاهده تمام تخفیف‌ها"
        color="primary"
        :size="$q.screen.lt.md ? 'lg' : 'xl'"
        rounded
        href="https://www.lioncomputer.com/shop/products/offers?sortBy=highest_discount&sortType=desc"
        target="_blank"
      />
    </div>
    <div class="col-auto full-width">
      <div
        class="row items-stretch justify-start"
        :class="{
          'q-col-gutter-lg': $q.screen.lt.md,
          'q-col-gutter-xl': $q.screen.gt.sm,
        }"
      >
        <div class="col-12">
          <div
            class="row q-col-gutter-sm items-center text-white"
            :class="{ 'text-h4': $q.screen.gt.sm, 'text-h5': $q.screen.lt.md }"
          >
            <div class="col-auto">
              <q-img
                src="~assets/percentage-icon.webp"
                class="gt-sm q-ma-auto"
                width="48px"
                no-native-menu
              />
              <q-img
                src="~assets/percentage-icon.webp"
                class="lt-md q-ma-auto"
                width="28px"
                no-native-menu
              />
            </div>
            <div class="col-auto">پیشنهادهای ویژه</div>
          </div>
        </div>
        <div
          class="col-xs-6 col-sm-3"
          v-for="(cat, index) in pictures"
          :key="index"
        >
          <q-card
            class="lion-card position-relative"
            tag="a"
            :href="cat.url"
            target="_blank"
          >
            <q-card-section
              :class="{ 'q-pa-none': !cat.img, 'q-my-auto': cat.img }"
            >
              <q-img
                :src="'/cats/' + cat.img"
                width="100%"
                height="auto"
                style="max-height: 160px"
                fit="contain"
                no-native-menu
                v-if="cat.img"
              />
              <q-btn
                v-else
                class="full-width"
                flat
                square
                :size="$q.screen.lt.md ? 'md' : 'xl'"
              >
                {{ cat.title }}
              </q-btn>
            </q-card-section>
            <q-card-section
              v-if="cat.img"
              class="text-subtitle1 text-center q-pa-none"
            >
              <q-btn
                class="full-width"
                flat
                square
                :size="$q.screen.lt.md ? 'md' : 'xl'"
              >
                {{ cat.title }}
              </q-btn>
            </q-card-section>
          </q-card>
        </div>
      </div>
    </div>
    <div class="col-auto full-width q-mt-xl">
      <div class="row flex-center q-col-gutter-md">
        <div class="col-xs-3 col-sm-2">
          <q-img
            src="~assets/percentage-x100.webp"
            class="q-ma-auto"
            width="100%"
            style="max-width: 100px; margin: auto"
            no-native-menu
          />
        </div>
        <div
          class="col-auto"
          :class="{ 'text-h2': $q.screen.gt.sm, 'text-h5': $q.screen.lt.md }"
        >
          فرصتی مناسب برای خرید
        </div>
      </div>
    </div>
  </q-page>
</template>

<script setup lang="ts">
const pictures = [
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=7dy6b',
    img: 'case.webp',
    title: 'کیس کامپیوتر',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=d38wb',
    img: 'external-hd.webp',
    title: 'هارد اکسترنال',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=7e23b',
    img: 'cpu.webp',
    title: 'واحد پردازنده (CPU)',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=pdv6b',
    img: 'monitor.webp',
    title: 'مانیتور',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=d65nb',
    img: 'mb.webp',
    title: 'مادربورد',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=d223d',
    img: 'headset.webp',
    title: 'هدست و هندزفری',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=bp52d',
    img: 'gpu.webp',
    title: 'کارت گرافیک (GPU)',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=bg9we',
    img: 'mouse.webp',
    title: 'ماوس',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=d4jkd',
    img: 'ram.webp',
    title: 'رم کامپیوتر',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=7e8xb',
    img: 'keyboard.webp',
    title: 'کیبورد',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=qe5ze',
    img: 'hdd.webp',
    title: 'هارد اینترنال',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=bw9qd',
    img: 'ssd-2.webp',
    title: 'هارد SSD',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=d5kzd',
    img: 'fan.webp',
    title: 'فن کیس',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=bnwrx',
    img: 'chair.webp',
    title: 'صندلی گیمینگ',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=dry1e',
    img: 'speaker.webp',
    title: 'اسپیکر',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=d893v',
    img: 'mic.webp',
    title: 'میکروفون',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=bknqb',
    img: '',
    title: 'کیبورد و ماوس (کمبو)',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=b17kb',
    img: '',
    title: 'ماوس پد',
  },

  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=ep575',
    img: '',
    title: 'کول‌پد',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=ex8qd',
    img: '',
    title: 'فلش مموری',
  },

  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=dz51d',
    img: '',
    title: 'روتر و اکسس‌پوینت',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=dk26x',
    img: '',
    title: 'مودم همراه',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=e2y9d',
    img: '',
    title: 'کارت حافظه',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=d88xd',
    img: '',
    title: 'وب‌کم',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=eqxg2',
    img: '',
    title: 'نوار LED',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=d571p',
    img: '',
    title: 'کابل اسلیو',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=bn5np',
    img: '',
    title: 'براکت کارت گرافیک',
  },
  {
    url: 'https://www.lioncomputer.com/shop/products/offers?category=eyw5b',
    img: '',
    title: 'سوئیچ شبکه',
  },
];
</script>
