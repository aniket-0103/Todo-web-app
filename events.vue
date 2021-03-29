<template>
    <div style="padding: 2vw; margin:2vw">
        <section class="hero">
            <div class="hero-body">    
                <div class="container">
                    <h1 class="title">
                        Todo app
                    </h1>
                    <h3 class="subtitle">Manage your Todo items here.</h3> 
                   </div>
            </div>
        </section>
        <div>
            <input @keydown.prevent.enter="addtodo" v-model="todo" class="input" type="text" placeholder="Add a todo type" >
        </div>
        <div class="has-text-left notification">
            <h3 class="is-size-3">ToDo </h3>
            <ul type="none">
                <li class="has-text-left" v-for="(todo,index) in todoList" :key='todo.timestamp'>
                    <input @change="markDone(index)" type="checkbox" v-model="todo.state"> &nbsp;
                    <span v-if="!todo.state">{{todo.item}} </span>
                    <s v-else>{{todo.item}} </s>
                </li>
            </ul>
            
                
        </div>
        <div class="has-text-left notification">
            <h3 class="is-size-3">Done</h3>
            <span class="has-text-left" v-for="todo in done" :key="todo.timestamp">
                <span>{{todo.item}} <br></span>
            </span>
        </div>
    </div>
</template>

<style scoped>

</style>

<script>
export default {
    name: 'events' ,
    methods:{
        addtodo(){
            this.todoList.push({
                'item': this.todo,
                'state':false,
                'timestamp':Date.now()
            })
            this.todo= ''
        
        },
        markDone(ind){
            setTimeout(() => {
                this.done.push(this.todoList[ind])
                this.todoList.splice(ind,1)
            }, 1000)
        }
        
    },
    data() {
        return {
            todo: '',
            todoList:[],
            done:[],
        }
    },
    
}
</script>