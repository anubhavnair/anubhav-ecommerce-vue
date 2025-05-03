<template>
<div class="faq-section p-6 bg-gray-100 rounded-lg shadow-md">
    <h2 class="text-2xl font-bold text-gray-800 mb-4">Frequently Asked Questions</h2>
    <div class="faq-item" v-for="(faq, index) in faqs" :key="index">
        <h3 
            @click="toggleFaq(index)" 
            class="faq-question text-lg font-medium text-gray-700 cursor-pointer hover:text-blue-500 transition-colors"
        >
            {{ faq.question }}
        </h3>
        <p 
            v-if="faq.show" 
            class="faq-answer mt-2 text-gray-600"
        >
            {{ faq.answer }}
        </p>
        <hr class="my-4 border-gray-300">
    </div>
</div>
</template>

<script>
export default {
  name: "ProdcutFaq",
  data() {
    return {
      // Your data here
    faqs: [
        {
            question: "What is the return policy?",
            answer: "You can return any item within 30 days of purchase.",
            show: false
        },
        {
            question: "Do you offer international shipping?",
            answer: "Yes, we ship to most countries worldwide.",
            show: false
        },
        {
            question: "How can I track my order?",
            answer: "You will receive a tracking link via email once your order is shipped.",
            show: false
        }
    ]
    };
  },
  methods: {
    // Your methods here
    toggleFaq(index) {
        this.faqs[index].show = !this.faqs[index].show;
    }
  }
};
</script>

<style scoped>
/* Your styles here */
.faq-section {
    max-width: 800px;
    margin: 0 auto;
}

.faq-item {
    padding: 10px 0;
}

.faq-question {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.faq-answer {
    line-height: 1.6;
}

.faq-question:hover {
    color: #2563eb; /* Tailwind's blue-500 */
    transition: color 0.3s ease;
}
</style>