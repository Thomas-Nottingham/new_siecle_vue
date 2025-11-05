<template>
  <div>
    <!-- 
      Floating Chat Bubble
      Clicking this will toggle the chat widget.
      The SVG icon has been removed.
    -->
    <div class="chatkit-bubble" title="Chat with us!" @click="toggleWidget">
      <!-- The SVG icon was here -->
    </div>

    <!-- 
      Chat Window
      This uses v-show to toggle visibility, which is the Vue equivalent
      of changing style.display = 'none'/'block'.
    -->
    <div class="chatkit-widget" v-show="isWidgetVisible">
      <iframe
        :src="chatUrl"
        width="100%"
        height="100%"
        style="border: none"
        allow="clipboard-write; camera; microphone"
      ></iframe>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

// Define the 'chatUrl' prop so you can pass the URL from your parent component.
// This makes the component reusable.
const props = defineProps({
  chatUrl: {
    type: String,
    // The default value is from your screenshot.
    // Remember to replace this!
    default: "https://openai-chatkit-starter-app-quqf.vercel.app/",
  },
});

// This is the reactive state that will control if the widget is open or closed.
const isWidgetVisible = ref(false);

// This function will be called when the bubble is clicked.
const toggleWidget = () => {
  isWidgetVisible.value = !isWidgetVisible.value;
};
</script>

<style scoped>
/* 'scoped' means these styles will ONLY apply to this component
  and won't interfere with the rest of your site's CSS.
*/

.chatkit-bubble {
  position: fixed;
  bottom: 20px;
  right: 20px;

  /* UPDATED: Removed background color, color, and flex properties */
  /* background: #0071e3; */
  /* color: white; */
  /* display: flex; */
  /* align-items: center; */
  /* justify-content: center; */

  /* ADDED: Background image properties */
  /* === REPLACE THIS PATH === */
  background-image: url("C:\Users\tommy\Desktop\Vue-Sielie\my-vue-app\src\assets\images\siecle.png");
  /* ========================= */
  background-size: cover; /* Makes your image fill the circle */
  background-position: center; /* Centers your image */

  border-radius: 50%;
  width: 64px;
  height: 64px;
  cursor: pointer;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.25);
  z-index: 9999;
  transition: transform 0.2s ease; /* Removed background transition */
}

.chatkit-bubble:hover {
  transform: scale(1.1);
  /* Removed background color change on hover */
  /* background: #0056c7; */
}

.chatkit-widget {
  /* We don't need 'display: none' here anymore, 
    v-show handles it for us.
  */
  position: fixed;
  bottom: 90px;
  right: 20px;
  width: 400px;
  /* Your image was cut off, I guessed 60vh. Adjust if needed! */
  height: 60vh;
  border: none;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  z-index: 9998;
}

/* Responsive styles from your image */
@media (max-width: 768px) {
  .chatkit-widget {
    width: 90%;
    height: 80%;
    right: 5%;
    /* bottom: 90px; (already set) */
  }
}
</style>
