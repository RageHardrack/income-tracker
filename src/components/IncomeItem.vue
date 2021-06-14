<template>
  <div class="income-item">
    <div class="removeItem">x</div>
    <div class="desc">{{ income.desc }}</div>
    <div class="price">S/. {{ income.value }}</div>
    <div class="date">{{ formattedDate }}</div>
  </div>
</template>

<script>
export default {
  props: {
    income: Object,
  },
  setup(props) {
    let date = new Date(props.income.date);
    let day = date.getDate();
    let month = date.getMonth();
    let year = date.getFullYear();

    let formattedDate = `${day}/${month}/${year}`;

    return { formattedDate };
  },
};
</script>

<style scoped>
.income-item {
  position: relative;
  display: flex;
  padding: 15px 15px 15px 0;
  background-color: #fff;
  border-radius: 8px;
  max-width: 600px;
  margin: 0 auto 30px;
}

.removeItem {
  color: #ef2d2d;
  font-weight: 600;
  font-size: 20px;
  line-height: 1;
  text-align: center;
  margin: 0px 15px;
}

.desc {
  color: #666;
  flex: 1 1 100%;
  font-size: 20px;
}

.price {
  color: #666;
  min-width: 100px;
  font-size: 20px;
}

.date {
  color: #666;
  text-align: right;
  font-size: 20px;
}
</style>
