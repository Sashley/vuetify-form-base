
<template>
  <v-container fluid >
    <h4>Select Item(s) from Schema-Array</h4>

    <v-form-base id="form-base-selection" :value= "myValue" :schema= "mySchema1" @change:form-base-selection= "update">
      <h4 slot="slot-top-key-name">Top Slot on Key Name</h4>
      <h4 slot="slot-top-type-radio">Top Slot on Types Radio</h4>

      <h4 slot="slot-item-key-password">Slot replaces Key Password</h4>

      <h4 slot="slot-bottom-key-name">Bottom Slot Key Name</h4>
      <h4 slot="slot-bottom-type-radio">Bottom Slot on Types Radio</h4>

    </v-form-base>

    <infoline :value= "myValue" :schema= "mySchema"></infoline>

  </v-container>
</template>

<script>
import VFormBase from '@/components/vFormBase'
import Infoline from '@/components/infoline'
import update from '@/lib'

const items = ['Musk', 'Jobs', 'Taleb', 'Harari']

export default {
  name: 'selection',
  components: { VFormBase, Infoline },
  data () {
    return {
      myValue: {
        selectSingle: 'Musk',
        selectMultiple: ['Musk', 'Taleb'],
        comboboxSingle: 'Harari',
        comboboxMultiple: ['Harari', 'Musk'],
        autocompleteSingle: 'Taleb',
        autocompleteMultiple: ['Taleb', 'Jobs']
      },
      mySchema: {
        selectSingle: { type: 'select', label: 'Select', selected: 0, items, flex: { xs: 12, sm: 6, md: 4 } },
        selectMultiple: { type: 'select', label: 'Multi-Select', items, multiple: true, flex: { xs: 12, sm: 6, md: 4 } },
        comboboxSingle: { type: 'combobox', label: 'Combobox', items, flex: { xs: 12, sm: 6, md: 4 } },
        comboboxMultiple: { type: 'combobox', label: 'Multi-Combobox', items, multiple: true, flex: { xs: 12, sm: 6, md: 4 } },
        autocompleteSingle: { type: 'autocomplete', label: 'AutoComplete', items, flex: { xs: 12, sm: 6, md: 4 } },
        autocompleteMultiple: { type: 'autocomplete', label: 'Multi-AutoComplete', multiple: true, items, flex: { xs: 12, sm: 6, md: 4 } }
      }
    }
  },
  methods: {
    update
  }
}
</script>
