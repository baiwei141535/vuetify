<template>
    <nav>
        <v-navigation-drawer v-model="drawer" dark app class="grey darken-3 py-0">
            <v-container>
                <v-row>
                    <v-col md="9">
                        <v-progress-circular
                        :rotate="300"
                        :size="50"
                        :width="7"
                        :value="value"
                        color="lime accent-3"
                        class="mt-n1">
                        {{value}}

                        </v-progress-circular>
                    </v-col>
                    <v-col md="3">
                            <v-icon right class="mt-1">fas fa-bars</v-icon>
                    </v-col>
                </v-row>
            </v-container>
            <v-list nav>
                <v-list-item router to ="/Login">
                    <v-list-item-action >
                        <v-icon small>fa fa-tachometer-alt</v-icon>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title>Dashboard</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
                <v-list-item router to ="/">
                    <v-list-item-action >
                        <v-icon small>fa fa-users</v-icon>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title>Applicants</v-list-item-title>
                        <v-chip color="yellow darken-3" small>3</v-chip>
                    </v-list-item-content>
                </v-list-item>
                <v-list-item router to ="/jobs">
                    <v-list-item-action >
                        <v-icon small>fas fa-briefcase</v-icon>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title>Jobs</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
                <v-list-item router to ="/calander">
                    <v-list-item-action >
                        <v-icon small>fas fa-calender</v-icon>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title>Calendar</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
                <v-list-item router to ="/reports">
                    <v-list-item-action >
                        <v-icon small>fas fa-clipboard-list</v-icon>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title>Reports</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>
    </nav>
</template>

<script>
export default {
    data: ()=>({
        drawer: true,
        interval: {},
        value:0,
    }),
    beforeDestroy (){
        clearInterval(this.interval)
    },
    mounted (){
        this.interval = setInterval(() =>{
            if(this.value === 100){
                return (this.value = 0)
            }
            this.value +=1 
        },1000)
    }
}
</script>

<style scoped>
.v-progress-circular{
    margin: 1rem;
}
</style>