<script setup lang='ts'>
import BaseButton from './BaseButton.vue';

const messages =  [
    {
        from: 'You',
        message: `Sure, I'll see you later.`,
        time: '10:42am',
        color: 'deep-purple-lighten-1',
    },
    {
        from: 'John Doe',
        message: 'Yeah, sure. Does 1:00pm work?',
        time: '10:37am',
        color: 'green',
    },
    {
        from: 'You',
        message: 'Did you still want to grab lunch today?',
        time: '9:47am',
        color: 'deep-purple-lighten-1',
    },
]

const toHome = () =>{
    console.log('>> Clicou no Botão <<')
}
</script>
    
<template>
    <v-container>
        <v-row justify="space-around">
        <v-card width="400">
            <v-img
            height="200"
            src="https://cdn.pixabay.com/photo/2020/07/12/07/47/bee-5396362_1280.jpg"
            cover
            class="text-white"
            >
                <v-toolbar
                    color="rgba(0, 0, 0, 0)"
                    theme="dark"
                >
                    <v-toolbar-title class="text-h6">
                    Messages
                    </v-toolbar-title>

                    <template v-slot:append>
                    <v-btn icon="mdi-dots-vertical"></v-btn>
                    </template>
                </v-toolbar>
            </v-img>

            <v-card-text>
                <div class="font-weight-bold ms-1 mb-2">
                    Today
                </div>

                <v-timeline density="compact" align="start">
                    <v-timeline-item
                    v-for="message in messages"
                    :key="message.time"
                    :dot-color="message.color"
                    size="x-small"
                    >
                    <div class="mb-4">
                        <div class="font-weight-normal">
                        <strong>{{ message.from }}</strong> @{{ message.time }}
                        </div>
                        <div>{{ message.message }}</div>
                    </div>
                    </v-timeline-item>
                </v-timeline>
                <BaseButton class="base-button" label="Abrir" color="secondary" @action="toHome" />
            </v-card-text>
        </v-card>
        </v-row>
    </v-container>
</template>
    
<style lang='postcss' scoped>
.base-button{
    @apply mt-4 font-semibold;
}
</style>