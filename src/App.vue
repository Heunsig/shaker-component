<script setup>
import { ref } from 'vue';
import Shaker from './components/Shaker.vue';
import CustomButton from './components/CustomButton.vue';

const isShaking = ref(false);
</script>

<template>
  <main>
    <section>
      <h1>Shake Component Example</h1>
      <p>We can shake any element with the Shaker component.</p>

      <button 
        type="button"
        @click="isShaking = true"
      >Click to shake</button>
    </section>

    <section>
      <h2>Shake a &lt;div&gt;</h2>
      <Shaker 
        v-model="isShaking"
      >
        <div>DIV</div>
      </Shaker>
    </section>

    <section>
      <h2>Shake a &lt;button&gt;</h2>
      <Shaker
        v-model="isShaking"
      >
        <button>Button</button>
      </Shaker>
    </section>

    <section>
      <h2>Shake a &lt;CustomButton&gt;</h2>
      <Shaker
        v-model="isShaking"
      >
        <CustomButton />
      </Shaker>
    </section>
  </main>
</template>