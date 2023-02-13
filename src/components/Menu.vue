<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="container menu_container">
    <div class="top">
      <h2>Menu</h2>
    </div>
    <div class="buttons">
      <md-button
        v-for="(button, index) in buttons"
        :key="index"
        :class="{ 'md-raised': button.active }"
        @click="changeMenu(button.name)"
      >
        {{ button.name }}
      </md-button>
    </div>
    <div class="products_items">
      <!-- Ето пример в който се ползва v-show вместо v-if. Ако ползваме v-if при итерация, получаваме грешка. -->
      <md-card
        v-for="(product, index) in documents"
        :key="index"
        v-show="product.type == activeProduct"
      >
        <md-card-media md-ratio="16:9">
          <img
            :src="require(`@/assets/images/products/${product.img}`)"
            alt=""
          />
        </md-card-media>
        <md-card-header>
          <h2 class="md-title">
            {{ product.name }}
          </h2>
          <div class="md-subhead">
            <span>$ {{ product.price }}</span>
          </div>
        </md-card-header>
        <md-card-content>
          {{ product.desc }}
        </md-card-content>
      </md-card>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  data() {
    return {
      activeProduct: "pizza",
      documents: [],
      buttons: [
        { name: "pizza", active: true },
        { name: "burgers", active: false },
        { name: "salat", active: false },
        { name: "dessert", active: false },
      ],
    };
  },
  mounted() {
    this.$http.get("products").then((response) => {
      console.log(response);
      response.data.documents.forEach((doc) => {
        let currDoc = {
          id: doc.name.substring(doc.name.length - 20, doc.name.length),
          desc: doc.fields.desc.stringValue,
          name: doc.fields.name.stringValue,
          price: Number(doc.fields.price.integerValue),
          type: doc.fields.type.stringValue,
          img: doc.fields.img.stringValue,
        };
        this.documents.push(currDoc);
      });
      console.log(this.documents);
    });
  },
  methods: {
    changeMenu(buttonName) {
      this.buttons.forEach((b) => {
        if (b.name == buttonName) {
          b.active = true;
          this.activeProduct = buttonName;
        } else {
          b.active = false;
        }
      });
    },
  },
};
</script>

<style scoped>
.md-card {
  width: 32%;
  margin-bottom: 20px;
}
.products_items {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
</style>
