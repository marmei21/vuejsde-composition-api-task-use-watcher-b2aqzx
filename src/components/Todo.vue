<template>
  <div class="todo">
    <p class="text-primary h1">{{ todoTitle }}</p>
    <p>[TodoLength: {{ todoLength }}, Items quantity: {{ itemsQuantity }}]</p>
    <div class="form-group d-flex">
      <input v-model="todo" type="text" class="form-control" />
      <button class="btn btn-primary" @click="add">Add</button>
    </div>

    <div class="list-group mt-4">
      <div
        class="list-group-item d-flex justify-content-between"
        v-for="(item, index) in items"
        :key="index"
      >
        <span>{{ item }}</span>
        <button class="close" @click="remove(index)">
          <span>&times;</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, computed } from 'vue';
export default {
  props: {
    title: String,
    initInput: String,
  },
  setup(props) {
    const todo = ref(props.initInput);
    const items = ref(['This', 'is']);
    const todoTitle = computed(() => '- ' + props.title + ' -');

    const add = () => {
      if (todo.value) {
        items.value.push(todo.value);
        todo.value = '';
      }
    };

    const remove = (index) => {
      items.value.splice(index, 1);
    };

    return {
      todoTitle,
      todo,
      items,
      add,
      remove,
    };
  },
};
</script>

<style lang="scss">
.todo {
  display: flex;
  flex-direction: column;
  width: 50%;
  margin: auto;
}
</style>
