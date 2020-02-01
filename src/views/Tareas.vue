<template>
    <v-container grid-list-md>
        <v-layout>
            <v-flex md6>
                <v-card>
                    <v-card-title>Lista Tareas</v-card-title>
                    <v-list two-line>
                        <v-list-item-group>
                            <template v-for="(task, index) in tasks">
                            <v-list-item :key="task.title">
                                <template v-slot:default="{}">
                                <v-list-item-content>
                                    <v-list-item-title v-text="task.name"></v-list-item-title>
                                    <v-list-item-subtitle class="text--primary" v-text="task.description"></v-list-item-subtitle>
                                    <v-layout justify-space-around>
                                        <v-btn @click="edit_task(index)" color="orange">Editar</v-btn>
                                        <v-btn @click="delete_task(index)" color="red">Eliminar</v-btn>
                                    </v-layout>
                                </v-list-item-content>
                                </template>
                            </v-list-item>

                            <v-divider v-if="index + 1 < tasks.length" :key="index"></v-divider>
                            </template>
                        </v-list-item-group>
                        </v-list>
                </v-card>
            </v-flex>
            <v-flex md6>
                <v-card>
                    <v-card-title>{{action}} tarea</v-card-title>
                    <v-form
                            ref="form"
                            v-model="valid"
                            lazy-validation
                        >
                            <v-text-field
                            v-model="task_name"
                            label="Nombre"
                            required
                            ></v-text-field>

                            <v-text-field
                            v-model="description"
                            label="Descripción Tarea"
                            required
                            ></v-text-field>
                        </v-form>

                    <v-btn @click="() => { state ? push_new_task() : update_task()}" block color="green" outlined >{{action}}</v-btn>   

                </v-card>
            </v-flex>
        </v-layout>
    </v-container>
</template>

<script>
export default {
    data(){
        return{
            message: '',
            state: true,
            id_temp: 0,
            task_name: '',
            description: '',
            tasks: [
                {name: 'Do exercises', description: 'Do exercises is healthy for us'},
            ]
        }
    },
    computed: {
        action(){
            if(this.state){
                this.task_name = '';
                this.description = '';
                return 'Agregar'
            }
            else{
                return 'Editar'
            }
        }
    },
    methods: {
        push_new_task(){
            this.tasks.push({name: this.task_name, description: this.description});
            this.task_name = ' ';
            this.description = ' ';
        },
        edit_task(index){
            this.state = !this.state;
            this.task_name = this.tasks[index].name;
            this.description = this.tasks[index].description;
            this.id_temp = index;
        },
        update_task(){
            this.tasks[this.id_temp].name = this.task_name;
            this.tasks[this.id_temp].description = this.description;
            this.task_name = ' ';
            this.description = ' ';
            this.state = true;
        },
        delete_task(index){
            this.tasks.splice(index,1);
        }
    }
}
</script>