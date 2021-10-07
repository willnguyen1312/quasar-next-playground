<template>
  <div class="q-pa-md q-gutter-sm">
    <q-tree :nodes="simple" node-key="label" />
  </div>
</template>

<script>
/* eslint-disable @typescript-eslint/no-unsafe-assignment */
import faker from 'faker';

export default {
  setup() {
    const children = Array.from({ length: 1000 }, () => ({
      label: faker.random.words(3),
      icon: 'restaurant_menu',
      children: [
        { label: faker.random.words(3) },
        { label: faker.random.words(3) },
      ],
    }));

    return {
      simple: [
        {
          label: 'Satisfied customers (with avatar)',
          avatar: 'https://cdn.quasar.dev/img/boy-avatar.png',
          children,
        },
      ],
    };
  },
};
</script>
