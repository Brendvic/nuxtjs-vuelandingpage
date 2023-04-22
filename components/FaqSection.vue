<template>
 <div class="card">
  <section class="faq-section">
    <h2>Frequently Asked Questions</h2>
    <div v-for="(item, index) in faqItems" :key="index" class="faq-item">
      <h3 @click="toggleAnswer(index)" :class="{ active: item.active }" class="faq-question">{{ item.question }}</h3>
      <div v-show="item.active" class="faq-answer">
        <p>{{ item.answer }}</p>
      </div>
    </div>
  </section>
 </div>
</template>

<script>
export default {
  data() {
    return {
      faqItems: [
        {
          question: 'What is HiveMed?',
          answer: 'HiveMed is a healthcare solution that provides easy and convenient access to medical services. It allows users to find doctors, schedule appointments, order medications, and receive remote medical advice and treatment through telemedicine. HiveMed aims to make healthcare more accessible and convenient for everyone, by leveraging technology and innovation to bring medical services to users fingertips. HiveMed is committed to providing fast and reliable healthcare solutions, so that users can focus on their health and well-being.',
          active: false
        },
        {
          question: 'How do I sign up for HiveMed?',
          answer: 'You can sign up for HiveMed by visiting our website and clicking the "Sign Up" button.',
          active: false
        },
        {
          question: 'What are the benefits of using HiveMed?',
          answer: 'Easy and convenient access to medical services from the comfort of your home, fast and efficient scheduling of appointments, and access to a network of qualified and experienced healthcare professionals.',
          active: false
        }
      ]
    };
  },
  methods: {
    toggleAnswer(index) {
      this.faqItems[index].active = !this.faqItems[index].active;
    }
  },
  mounted() {
    const questions = this.$el.querySelectorAll('.faq-question');
    questions.forEach(question => {
      question.addEventListener('click', () => {
        const answer = question.nextElementSibling;
        answer.classList.toggle('show');
        question.classList.toggle('active');
      });
    });
  }
};
</script>

<style scoped lang="scss">
.faq-section {
  margin: 50px auto;
  max-width: 600px;
}

.faq-item {
  border: 1px solid #ccc;
  border-radius: 5px;
  margin-bottom: 20px;
}

.faq-question {
  background-color: #f2f2f2;
  color: #444;
  cursor: pointer;
  font-size: 18px;
  font-weight: bold;
  margin: 0;
  padding: 10px;
  transition: background-color 0.3s ease;
}

.faq-question:hover {
  background-color: #e2e2e2;
}

.faq-answer {
  display: none;
  padding: 10px;
}

.faq-answer.show {
  display: block;
  animation: fade-in 0.5s ease;
}

@keyframes fade-in {
  from { opacity: 0; }
  to { opacity: 1; }
}
.card {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  margin: 50px auto;
  max-width: 600px;
  padding: 20px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
}

.faq-section {
  margin: 0;
}
</style>
