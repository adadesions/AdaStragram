<template>
    <div id="grid-images">
        <InstraCard v-for="(data, idx) in info" :info="data" :key="data.username+idx"></InstraCard>
    </div>
    
</template>

<script>
import axios from 'axios';
import InstraCard from '@/components/InstraCard';

export default {
    name: 'GridImages',
    data: function() {
        return {
            usernames: ['AdaBrain', 'Peter Parker', 'Steve Jobs', 'Bill Gates', 'Elon Musk'],
            apis: null,
            fakeApi: null,
            info: [
                {
                    username: 'AdaDeSions',
                    avatarImg: 'https://avatars0.githubusercontent.com/u/3336816?s=460&u=a3def04c56afd7220d835005dbf1879a0b497554&v=4',
                    image: 'https://www.onekind.scot/wp-content/uploads/Fox-fox-controlling-wpcf_805x805.jpg',
                    numOfLikes: 92,
                    numOfComment: 108
                },               
                {
                    username: 'Anakin Skywalker',
                    avatarImg: 'https://avatars0.githubusercontent.com/u/3336816?s=460&u=a3def04c56afd7220d835005dbf1879a0b497554&v=4',
                    image: 'https://render.fineartamerica.com/images/rendered/default/greeting-card/images-medium/white-fox-at-matterhorn-julie-l-hoddinott.jpg',
                    numOfLikes: '80K',
                    numOfComment: '3.2K'
                },
                {
                    username: 'AdaDeSions',
                    avatarImg: 'https://avatars0.githubusercontent.com/u/3336816?s=460&u=a3def04c56afd7220d835005dbf1879a0b497554&v=4',
                    image: 'https://www.onekind.scot/wp-content/uploads/Fox-fox-controlling-wpcf_805x805.jpg',
                    numOfLikes: 92,
                    numOfComment: 108
                },
                {
                    username: 'AdaDeSions',
                    avatarImg: 'https://avatars0.githubusercontent.com/u/3336816?s=460&u=a3def04c56afd7220d835005dbf1879a0b497554&v=4',
                    image: 'https://www.onekind.scot/wp-content/uploads/Fox-fox-controlling-wpcf_805x805.jpg',
                    numOfLikes: 92,
                    numOfComment: 108
                },        
            ]
        }
    },
    mounted: function() {
        axios
        .get('https://dog.ceo/api/breed/pomeranian/images/random/10')
        .then(response => this.apis = response.data.message)

        axios
        .get('https://api.mocki.io/v1/9caa0ba8')
        .then(response => this.fakeApi = response)
    },
    components: {
        InstraCard,
    }
}
</script>

<style>
    #grid-images {
        display: flex;
        flex-flow: row wrap;
        justify-content: space-around;
    }

</style>