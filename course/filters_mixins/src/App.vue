<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Filters &amp; Mixins</h1>
                <p>{{ text | toUppercase | to-lowercase }}</p>
                <hr>
                <button class="btn btn-primary" @click="fruits.push('Berries')">Add New Item</button>
                <input type="text" v-model="filterText">
                <ul>
                    <li v-for="fruit in filteredFruits">{{ fruit }}</li>
                </ul>
                <app-list></app-list>
            </div>
        </div>
    </div>
</template>

<script>
import List from "./List.vue";
import { fruitMixin } from "./fruitMixin";
export default {
  data() {
    return {
      text: "hello there!"
    };
  },
  filters: {
    toUppercase(value) {
      return value.toUppercase();
    }
  },
  components: {
    appList: List
  },
  mixins: [fruitMixin]
};
</script>

<style>
</style>
