<script>

export default {
    data() {
        return {
            difficulty: '',
            easy: this.select,
            medium: false,
            hard: false,
        }
    },
    methods: {
        setDificulty(select) {
            const easy = new Vue({
                el: '#easy',
                data: {
                    select: true,
                }
            })
            return easy
            const medium = 'medium' ? this.medium = true : this.medium = false
            const hard = 'hard' ? this.hard = true : this.hard = false
            
            this.difficulty = select
            console.log(this.difficulty)
        }
    }
}

</script>

<template>

    <main>
        <img class="mainIcon" src="../icons/titleIcon.png" alt="">

        <div class="title">
            <h1>Trivial Game</h1>
        </div>

        <section class="selectDificulty">
            <h2>Choose your dificulty:</h2>
            <div class="dificultyBtns">
                <button class="easy" @click="setDificulty(easy)">EASY</button>
                <button class="medium" @click="setDificulty(medium)">MEDIUM</button>
                <button class="hard" @click="setDificulty(hard)">HARD</button>
            </div>
        </section>

        <router-link to="category" class="startBtn">
            <img class="startIcon" src="../icons/start.png" alt="">
        </router-link>
    </main>

</template>

<style scoped>

main{
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
}

.mainIcon {
    width: 374px;
    height: 384px;
    display: flex;
    align-items: center;
    justify-content: center;
    animation: rotation 40s infinite linear;
}

@keyframes rotation {
    from {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(359deg);
    }
}

h1{
    font-family: 'JetBrains Mono', monospace;
    font-weight: 800;
    font-size: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
}

h2{
    font-family: 'JetBrains Mono', monospace;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 15px;
    font-weight: 600;
}

.startBtn{
    display: flex;
    justify-content: center;
    align-items: flex-end;
    margin-top: -1.5rem;
}

.startIcon{
    width: 200px;
    height: 200px;
    display: flex;
    justify-content: center;
}

.easy{
    background: #71FF7F;
}

.medium{
    background: #feef8f;
}

.hard{
    background: #FF7F7F;
}

.dificultyBtns button{
    display: flex;
    justify-content: center;
    align-items: center;
    box-sizing: border-box;
    border-radius: 30px;
    width: 118px;
    height: 45px;
    font-weight: 600;
}

.dificultyBtns{
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 6px;
}

</style>
