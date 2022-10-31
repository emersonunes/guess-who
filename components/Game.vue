<template>
  <div>
    <v-container v-if="currentIndex === 6" fluid>
      <v-row>
        <v-col class="my-10">
          <h1 class="text-center">You have finished the game!</h1>
          <p class="text-center">Your score is: {{scorePercentage}}%</p>
        </v-col>
      </v-row>
      <v-row>
        <v-col class="my-2 d-flex justify-center">
          <v-btn
          color="blue"
          @click="reset">
            Try again
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
    <v-container v-else fluid>
      <v-row>
        <v-col class="my-10">
          <p class="text-center">Your current score is: {{score}}</p>
        </v-col>
      </v-row>
      <v-row>
        <v-col class="my-10">
          <h1 class="text-center">{{questions[currentIndex].question}}</h1>
        </v-col>
      </v-row>
      <v-row>
        <v-col
          v-for="(answer, index) in questions[currentIndex].answers" :key="index"
          cols="12"
          md="6"
          class="my-5"
          >

          <v-btn
          block
          color="grey"
          x-large
          :active-class="isCorrectAnswer"
          @click="submitAnswer(index, questions[currentIndex].correctIndex)"
          >
            {{answer}}
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
import Quizz from '@/static/questions/questions.json'
export default {
  name: 'GameComponent',
  data(){
    return {
      questions: Quizz.questions,
      currentIndex: 0,
      score: 0,
      scorePercentage: 0,
    }
  },
  computed:{
    isCorrectAnswer(){
      return 'success'
    }
  },
  methods:{
    submitAnswer(index, correctIndex){
      this.currentIndex++;
      if(index === correctIndex){
        this.score++
        this.scorePercentage = (this.score / 6) * 100
      }
    },
    reset(){
      this.currentIndex = 0;
      this.score = 0
      this.scorePercentage = 0
    }
  }
}
</script>
