        
        <template>
        
                <img  class="responseIcon" src="src\components\icons\question.png" alt="">
                <h1 v-html="result"></h1>
        
            <div id="randomAnswer" class="responseBtns">
                <button @click="verifyAnswer()" v-for="answer in answers_list" :key="answer" v-html="answer" class="Question"></button>
        
            </div> 
            <div >
                <button>
                <RouterLink to="/category">
                <svg xmlns="http://www.w3.org/2000/svg" role="img" width="26" height="26"  viewBox="0 0 448 512">
                        <path  d="m77.25 256l137.4-137.4c12.5-12.5 12.5-32.75 0-45.25s-32.75-12.5-45.25 0l-160 160c-12.5 12.5-12.5 32.75 0 45.25l160 160c6.2 6.3 14.4 9.4 22.6 9.4s16.38-3.125 22.62-9.375c12.5-12.5 12.5-32.75 0-45.25L77.25 256zm192.05 0l137.4-137.4c12.5-12.5 12.5-32.75 0-45.25s-32.75-12.5-45.25 0l-160 160c-12.5 12.5-12.5 32.75 0 45.25l160 160c6.15 6.3 14.35 9.4 22.55 9.4s16.38-3.125 22.62-9.375c12.5-12.5 12.5-32.75 0-45.25L269.3 256z"/></svg>
                </RouterLink>
                </button>
        </div>
        
        </template>
<script>

import axios from "axios";

export default {

    props: {
        category: {
            type: String,
            default: '',
        },
        difficulty: {
            type: String,
            default: '',
        },
    },

//25

    data: () => ({
        result: null,
        answers_list:[],
        incorrect_answer:'',
        incorrect_answer1:'',
        incorrect_answer2:'',
        correct_answer:'',

    }),
    async created() {
        await axios.get("https://opentdb.com/api.php?amount=1&type=multiple").then((result) => {
            this.result = result.data.results[0].question;
            this.correct_answer = result.data.results[0].correct_answer;
            this.incorrect_answer = result.data.results[0].incorrect_answers[0];
            this.incorrect_answer1 = result.data.results[0].incorrect_answers[1];
            this.incorrect_answer2 = result.data.results[0].incorrect_answers[2];
            
            this.answers_list = [this.incorrect_answer, this.incorrect_answer1, this.incorrect_answer2];

            let randomAnswer = Math.floor(Math.random() * (this.answers_list.length+1));
            console.log(randomAnswer);

            randomAnswer = this.answers_list[randomAnswer];

            this.answers_list.splice(randomAnswer, 0, this.correct_answer);
            

        }) 
    },

    methods: {
        
        verifyAnswer(){
            if (this.answers_list[0] === this.correct_answer) {
                this.result = "Correct!";
            } else {
                this.result = "Incorrect!";
            }

            console.log(verifyAnswer);
        }
    },
};

</script>

<style>

*{
    margin: 0.1rem;
}

h1{
    margin-bottom:50px;
    display: flex;
    justify-content: center;
    font-weight: 800;
    font-size: x-large;
    text-align: center;
}

.Question {
    width: 100%;
    height: 100%;
    border: none;
    outline: none;
    font-size: 1.5em;
    font-weight: 300;
    color: black;
    padding: 10px;
    border-radius: 20px;
    box-shadow: 0px 0px 5px #000;
    margin-bottom: 40px;
    font-family: 'JetBrains Mono', monospace;
}

.Question2 {
    width: 100%;
    height: 100%;
    border: none;
    outline: none;
    font-size: 1.5em;
    font-weight: 300;
    color: black;
    padding: 10px;
    border-radius: 20px;
    box-shadow: 0px 0px 5px #000;
    margin-bottom: 40px;
    font-family: 'JetBrains Mono', monospace;
}

.Question3 {
    width: 100%;
    height: 100%;
    border: none;
    outline: none;
    font-size: 1.5em;
    font-weight: 300;
    color: #fff;
    padding: 10px;
    border-radius: 20px;
    box-shadow: 0px 0px 5px #000;
    margin-bottom: 40px;
    font-family: 'JetBrains Mono', monospace;
}

.Question4 {
    width: 100%;
    height: 100%;
    border: none;
    outline: none;
    font-size: 1.5em;
    font-weight: 300;
    color: #fff;
    padding: 10px;
    border-radius: 20px;
    box-shadow: 0px 0px 5px #000;
    font-family: 'JetBrains Mono', monospace;   
}

.responseIcon{
    margin-bottom: 4rem;
    margin-left: auto;
    margin-right: auto;
    display: flex;
    justify-content: center;
    align-items: center;

}

</style>


