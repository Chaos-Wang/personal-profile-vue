<template>
  <section class="archive">
    <p class="archive-title">
      <svg class="icon" aria-hidden="true">
        <use xlink:href="#icon-archive"></use>
      </svg>Achievements
    </p>

    <div class="archive-com-sec archive-cat">
      <p class="sort-title">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-cat"></use>
        </svg>Categories
      </p>
      <div class="sort-items">
        <nuxt-link :to="`/search/category/${cat.id}`" v-for="cat in categories" :key="cat.id" v-if="cat.count > 0">{{ cat.name }} ({{ cat.count }})</nuxt-link>
      </div>
    </div>

    <div class="archive-com-sec archive-time">
      <p class="sort-title">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-time"></use>
        </svg>Timeline
      </p>
      <div class="sort-items">
        <time-line v-for="(time, index) in timePosts" :key="index" :time-post="time"></time-line>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios';
import TimeLine from '~/components/TimeLine';
export default {
  head () {
    return {
      title: 'Achievements'
    };
  },
  data () {
    return {};
  },
  asyncData () {
    return axios.get(`/post/getArchive`).then(res => {
      if (res.data.success === 1) {
        return {
          categories: res.data.categories,
          timePosts: res.data.times
        };
      } else {
        return { categories: [] };
      }
    });
  },
  components: {
    TimeLine
  }
};
</script>


<style lang="scss" scoped>
@import '~assets/sass/app';
.archive {
  padding-top: 2em;
  background-color: #fff;

  .archive-title {
    margin-bottom: 1.5em;
    font-size: 2.5em;
    color: #333;
    line-height: 1;
    text-align: center;

    .icon {
      width: 0.9em;
      height: 0.9em;
      vertical-align: -0.1em;
      margin-right: 0.3em;
    }
  }
  .archive-com-sec {
    margin-bottom: 1em;

    &:last-child {
      margin-bottom: 0;
    }
  }
  .sort-title {
    position: relative;
    font-size: 1.5em;
    padding: 0.5em 0 0.5em 1em;
    box-sizing: border-box;
    border-left: 0.15em solid $base-color;
    display: block;
    .icon {
      width: 0.9em;
      height: 0.9em;
      vertical-align: -0.1em;
      margin-right: 0.2em;
    }
    .show-more {
      position: absolute;
      right: .8em;
      top: 50%;
      transform: translateY(-50%);
      height: 1.5em;
      font-size: 0.8em;
      color: $base-color;
      background: rgba(27,31,35,.05);
      border-radius: .2em;
      padding: 0 0 0 .8em;
      display: flex;
      align-items: center;
      cursor: pointer;
      span {
        font-size: 0.8em;
      }
      .icon {
        margin-left: .8em;
        width: 1em;
        height: 1em;
        transform: translateX(-50%) rotate(90deg);
        transition: transform .2s linear;

        &.hide {
          transform: translateX(-50%) rotate(-90deg);
        }
      }
    }
  }
  .sort-items {
    position: relative;
    padding: 0.5em 1em;
    font-size: 1.2em;
    a {
      display: inline-block;
      padding: 0.6em 0.8em;
      margin: 0.5em;
      border-radius: 0.2em;
      background-color: rgba(27,31,35,.05);
      color: $base-color;
    }
  }
}
</style>

