<template>
  <div class="list-item">
    <div class="item-selector">
      <check-button @click.native="changeChecked" :is-checked="itemInfo.checked"/>
    </div>
    <div class="item-img">
      <img :src="itemInfo.image" alt="">
    </div>
    <div class="item-info">
      <div class="item-title">{{ itemInfo.title }}</div>
      <div class="item-desc">{{ itemInfo.desc }}</div>
      <div class="info-bottom">
        <div class="item-price left">¥{{ itemInfo.price }}</div>
        <div class="item-count right">×{{ itemInfo.count }}</div>
      </div>
    </div>
  </div>
</template>

<script>
  // sub cpn
  import CheckButton from "../../../components/content/checkButton/CheckButton";

  export default {
    name: "CartListItem",
    components: {
      CheckButton
    },
    props: {
      itemInfo: {
        type: Object,
        default() {
          return {}
        }
      }
    },
    methods: {
      changeChecked() {
        this.itemInfo.checked = !this.itemInfo.checked;
      }
    }
  }
</script>

<style scoped>
  .list-item {
    width: 100%;
    display: flex;
    font-size: 0;
    padding: 5px;
    border-bottom: 1px solid #ccc;
  }

  .item-selector {
    width: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .item-title, .item-desc {
    overflow: hidden;
    white-space: nowrap;
    -ms-text-overflow: ellipsis;
    text-overflow: ellipsis;
  }

  .item-title {
    font-size: 16px;
    margin-bottom: 4px;
  }

  .item-img {
    padding: 5px;
  }

  .item-img img {
    width: 75px;
    /*height: 100px;*/
    display: block;
    -webkit-border-radius: 5px;
    -moz-border-radius: 5px;
    border-radius: 5px;
  }

  .item-info {
    font-size: 17px;
    color: #333;
    padding: 5px 10px;
    position: relative;
    overflow: hidden;
  }

  .item-info, .item-desc {
    color: #666;
    font-size: 14px;
  }

  .item-desc {
    margin-top: 15px;
  }

  .info-bottom {
    display: flex;
    justify-content: space-between;
    margin-top: 16px;
  }

  .item-price {
    color: #ffb805;
    font-size: 18px;
  }

  .item-count {
    font-size: 20px;
  }
</style>
