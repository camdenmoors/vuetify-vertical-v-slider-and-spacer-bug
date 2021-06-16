<template>
  <v-container>
    <v-dialog persistent :value="showDialog" class="text-center">
      <v-tabs
        :vertical="$vuetify.breakpoint.mdAndUp"
        active
        :value="local_tab"
        color="primary-visible"
        show-arrows
      >
        <v-tab id="select-tab-one" href="#tab-one">Tab One</v-tab>
        <v-tab id="select-tab-two" href="#tab-two">Tab Two</v-tab>
        <v-spacer />
        <v-divider />
        <v-tab id="select-tab-three" href="#tab-three">Tab Three</v-tab>

        <v-tab-item value="tab-one">
          <v-card>
          <v-card-title>
            Tab One
          </v-card-title>
          <v-card-text>
            To reproduce the bug, click on tab two.<pre>


















              </pre>
          </v-card-text>
        </v-card>
        </v-tab-item>
        <v-tab-item value="tab-two">
          <v-card>
          <v-card-title>
            Tab Two
          </v-card-title>
          <v-card-text>
            Now select tab three.
          </v-card-text>
        </v-card>
        </v-tab-item>
        <v-tab-item value="tab-three">
          <v-card>
          <v-card-title>
            Tab Three
          </v-card-title>
          <v-card-text>
            The v-group-slider should now be stuck between the tab one and tab two selector.<pre>


















              </pre>
          </v-card-text>
        </v-card>
        </v-tab-item>
        
      </v-tabs>
    </v-dialog>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld',
    computed: {
      local_tab: {
        get: function() {
          return localStorage.getItem('nexus_curr_tab')
        },
        set: function(value) {
          return localStorage.setItem('nexus_curr_tab', value)
        }
      }
    },
    data: () => ({
      showDialog: true
    }),
  }
</script>
