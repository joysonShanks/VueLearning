<template>
    <div class="todo">
        <div class="todo-title">
            <input style="width:100%;" type="text" placeholder="TODO Title"/>
        </div>
        <div class="todo-items" v-for="checkList in checkLists" :key="checkList.id">
            <label :for="checkList.id" v-bind:class="{ checked: checkList.isCompleted }"><input :id="checkList.id" type="checkbox" name="todo-checkbox" @click="checkItem(checkList.id)"/> {{checkList.name}}</label>
        </div>
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
        }
    },
    data: function () {
        return {
            checkLists : [
                { name: 'Get Milk', id: '1', isCompleted: false },
                { name: 'Get Suger', id: '2', isCompleted: false},
                { name: 'Fix Water Tap', id: '3', isCompleted: false},
                { name: 'Pet the cat', id: '4', isCompleted: false}
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
.checked {
    text-decoration: line-through;
}
</style>

