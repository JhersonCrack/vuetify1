<template>
    <v-container>
        <v-layout>
            <v-flex>
                <v-btn>Boton 1</v-btn>
                <v-btn color="primary">Boton 2</v-btn>
                <v-btn dark color="blue">Boton 3</v-btn>
                <v-btn color="secondary" flat>Boton 4</v-btn>
                <v-btn color="success" large>Boton 5</v-btn>
                <v-btn color="warning" small>Boton 5</v-btn>
                <v-btn color="primary" large disabled>Boton 5</v-btn>
                <v-btn color="info" depressed>Boton 6</v-btn>

                <v-btn>
                    <v-icon>favorite</v-icon>
                </v-btn>
                
                <v-btn flat icon>
                    <v-icon color="orange">add_circle</v-icon>
                </v-btn>

                <v-btn fab color="white">
                    <v-icon color="black">add_circle</v-icon>
                </v-btn>

                <v-btn fab color="white" small>
                    <v-icon color="black" large>add_circle</v-icon>
                </v-btn>

                <v-btn fab color="white" large>
                    <v-icon color="black">add_circle</v-icon>
                </v-btn>

                <v-btn>
                    <v-icon>search</v-icon>
                    Buscar
                </v-btn>

                <v-btn color="success" outlined>
                    <v-icon left>forum</v-icon>
                    Boton X
                </v-btn>

                <v-btn color="success" outlined block rounded>
                    <v-icon left>forum</v-icon>
                    Boton X
                </v-btn>
            </v-flex>
        </v-layout>
    </v-container>
</template>

<script>
export default {
    data(){
        return{

        };
    },
}
</script>