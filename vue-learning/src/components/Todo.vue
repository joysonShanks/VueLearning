<template>
    <div class="todo">
        <form id="signup-form" @submit.prevent="processForm">
            <v-container grid-list-xl>
                <v-flex xs12 sm6 md12>
                    <v-text-field style="width:100%;" label="TODO Title" name="title" v-model="title" outline></v-text-field>
                </v-flex>
                <div v-for="checkList in checkLists" :key="checkList.id">
                    <v-flex xs12 sm6 md12>
                        <v-checkbox name="checkLists" v-bind:class="{ 'todo-checked': checkList.isCompleted }" :label="checkList.name" @click="checkItem(checkList.id)"></v-checkbox>
                    </v-flex>
                </div>
                <v-btn color="red" style="width:100%;" type="submit" dark>
                    Submit
                </v-btn>
            </v-container>
        </form>
    </div>
</template>

<script>
export default {
    name: 'todo',
    methods: {
        checkItem(id) {
            this.checkLists.forEach(function (entry) {
               if(entry.id === id) {
                   entry.isCompleted = !entry.isCompleted;
               }
            })
        },
        processForm() {
            console.log({ title: this.title, checkLists: this.checkLists })
        }
    },
    data: function () {
        return {
            title: '',
            checkLists : [
                { name: 'Get Milk', id: '1', isCompleted: false },
                { name: 'Get Suger', id: '2', isCompleted: false },
                { name: 'Fix Water Tap', id: '3', isCompleted: false },
                { name: 'Pet the cat', id: '4', isCompleted: false }
            ]
        }
    }
}
</script>

<style scoped>
.todo {
    width: 50%;
    padding: 10px;
    margin-left: auto;
    margin-right: auto;
}
.todo-title {
    left:auto;
}
.todo-items {
    left:auto;
    margin-top: 10px;
}
.todo-checked {
    text-decoration: line-through;
}
.todo-submit {
    left:auto;
    margin-top: 10px;
}
.v-input--selection-controls {
    margin:0px;
    padding: 0px;
}
</style>

