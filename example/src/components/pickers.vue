<template>
  <v-container fluid >

    <h4>Pickers</h4>

    <v-form>
      <v-form-base id="form-base-pickers" :value= "myValue" :schema= "mySchema" @update:form-base-pickers= "update">
        <!-- <div slot="slot-bottom-key-dateLookup" /> -->
          <!-- <v-form-base id="form-base-data-sync" value= "myValue" :schema= "mySchema" @update:form-base-data-sync= "update">
          </v-form-base>> -->
          <!-- <v-date-picker></v-date-picker> -->
        <!-- </div> -->
      </v-form-base>
    </v-form>

    <infoline :value= "myValue" :schema= "mySchema" ></infoline>

  </v-container>
</template>

<script>
import VFormBase from '@/components/vFormBase'
import Infoline from '@/components/infoline'
import update from '@/lib'

export default {
  name: 'pickers',
  components: { VFormBase, Infoline },
  data () {
    return {
      myValue: {
        colorPicker: '#88000080',
        timePicker: '10:15',
        datePicker: '2019-03-16',
        scheduledPicker: '2017-01-02',
        dateLkup: '2017-12-09'
      },
      mySchema: {
        colorPicker: { type: 'color', flex: { xs: 12, sm: 6, md: 4 } },
        timePicker: { type: 'time', format: '24hr', flex: { xs: 12, sm: 6, md: 4 } },
        datePicker: { type: 'date', color: 'green', flex: { xs: 12, sm: 6, md: 4 } },
        scheduledPicker: { type: 'date', color: 'orange', flex: { xs: 12, sm: 6, md: 4 } },
        dateLkup: { type: 'dateLookup', color: 'blue', flex: { xs: 12, sm: 6, md: 4 } }
      }
    }
  },
  methods: {
    update
  }
}
</script>
