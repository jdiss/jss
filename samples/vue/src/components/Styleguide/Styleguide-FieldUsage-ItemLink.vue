<!--
  Demonstrates usage of a Content Link content field within JSS.
  Content links are a reference to a single other piece of content.
-->

<template>
  <styleguide-specimen v-bind="$props">
    <h5>Shared Item Link</h5>
      <!--
        Item link fields are returned with their value as the referenced item value.
      -->
      <div v-if="sharedItemLink">
        <h5>{{ sharedItemLink.displayName }}</h5>
        <!-- The referenced item's fields can be rendered and edited using normal helper components: -->
        <p>
          Field: <sc-text :field="sharedItemLink.fields.textField" />
        </p>
      </div>


      <h5>Local Item Link</h5>
      <div v-if="localItemLink">
        <p>
          Field: <sc-text :field="localItemLink.fields.textField" />
        </p>
      </div>
  </styleguide-specimen>
</template>

<script>
import { Text } from '@sitecore-jss/sitecore-jss-vue';
import StyleguideSpecimen from './Styleguide-Specimen';

export default {
  name: 'Styleguide-FieldUsage-ItemLink',
  props: {
    fields: {
      type: Object,
    },
    rendering: {
      type: Object,
    },
  },
  components: {
    ScText: Text,
    StyleguideSpecimen,
  },
  computed: {
    sharedItemLink() {
      return this.fields.sharedItemLink;
    },
    localItemLink() {
      return this.fields.localItemLink;
    },
  },
};
</script>
