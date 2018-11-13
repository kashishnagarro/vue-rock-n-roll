<template>
  <div>
    <input type="text" placeholder="Add Band..." @click.stop @keyup.enter="addBand" v-model="newBand"> 
    <button> Add </button>

    <ul>
      <BandItem v-for="band in bands" :key="band.id" :band="band">
        {{band.name}}
      </BandItem>
    </ul>
  </div>
</template>


<script>
import BandItem from '@/components/BandItem.vue'

export default {
  name: 'BandList',
  components: {
    BandItem
  },
  data () {
    return {
      bands: [{
        id: 1,
        name: 'Black Sabbath',
        songs: ['Iron Man', 'War Pigs']
      }, {
        id: 2,
        name: 'ColdPlay',
        songs: ['Yellow', 'Fix you', 'Mylo xyloto']
      }],
      newBand : ''
    }
  },
  methods : {
    addBand(){
      debugger;
      this.bands.push({
        id:this.bands.length+1,
        name:this.newBand,
        songs:[]
      });
    }
  }
}
</script>
