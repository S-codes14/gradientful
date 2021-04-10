<template>
  <div class="loader" v-once>
    <div class="loader__content">


      <p class="loader__tip">
        {{ messages | randomize }}
      </p>

      <div class="spinner loader__spinner"></div>

    </div>
  </div>
</template>


<script>
export default {
  name: 'preload',
  data() {
    return {
      messages: [
        'Use the left and right arrow keys to quickly navigate between gradients - gradientful',
        'Use the top and bottom arrow keys to change gradient direction - gradientful',
        'Click the colored square next to hex value to copy to clipboard - gradientful',
        'Hit the shift key to see all gradients - gradientful',
        'Press the enter key to get the css code for the gradient - gradientful',
      ],
    };
  },
  filters: {
    randomize(messages) {
      if (!messages) return '';
      const randomMessage = Math.floor(Math.random() * messages.length);
      return messages[randomMessage];
    },
  },
};
</script>
