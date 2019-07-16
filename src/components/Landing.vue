<template>
  <v-container class="no-padding bg" fluid>
    <v-parallax dark src="https://i.imgur.com/fBmnj4I.jpg">
      <v-layout align-center column justify-center>
        <h1 class="display-2 font-weight-thin mb-3">Offerta Mediolanum</h1>
        <h4 class="subheading">format Wealth Advisor</h4>
      </v-layout>
    </v-parallax>

    <v-toolbar dark>
      <v-toolbar-title>
        Location: Milano, Novara
      </v-toolbar-title>
      <v-spacer></v-spacer>

      <v-toolbar-title>
        Data: 01/09/2019
      </v-toolbar-title>
    </v-toolbar>

    <v-container>
      <v-layout>
        <v-flex xs12>
          <v-toolbar dark>
            <v-toolbar-title
              >#CaffèconStile <small>standard</small></v-toolbar-title
            >
            <v-spacer></v-spacer>
            <v-toolbar-title>Domenica, 01/09/2019</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-title>10 pax.</v-toolbar-title>
          </v-toolbar>
          <v-list>
            <v-list-group
              v-for="item in items"
              :key="item.title"
              v-model="item.active"
              :prepend-icon="item.action"
              no-action
            >
              <template v-slot:activator>
                <v-list-tile>
                  <v-list-tile-content>
                    <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                  </v-list-tile-content>
                </v-list-tile>
              </template>

              <v-list-tile
                v-for="subItem in item.items"
                :key="subItem.title"
                @click=""
              >
                <v-list-tile-content>
                  <v-list-tile-title>{{ subItem.title }}</v-list-tile-title>
                </v-list-tile-content>

                <v-list-tile-action>
                  <v-icon>{{ subItem.action }}</v-icon>
                </v-list-tile-action>
              </v-list-tile>
            </v-list-group>
          </v-list>
        </v-flex>
      </v-layout>
    </v-container>
    <v-footer dark height="auto">
      <v-card class="flex" flat tile>
        <v-card-title class="teal">
          <h3>PROPOSTA ECONOMICA</h3>
          <v-spacer></v-spacer>
          <h2>La nostra miglior offerta : € 500.00 + IVA</h2>
        </v-card-title>

        <v-card-actions class="grey darken-3 justify-center">
          &copy;2019 — <strong>Stile Catering</strong>
        </v-card-actions>
      </v-card>
    </v-footer>
  </v-container>
</template>

<script>
export default {
  name: "Landing",
  data: () => ({
    items: [
      {
        action: "restaurant",
        title: "FOOD",
        active: true,

        items: [
          { title: "Breakfast & brunch" },
          { title: "New American" },
          { title: "Sushi" }
        ]
      },
      {
        action: "local_bar",
        title: "BEVERAGE",
        items: [{ title: "List Item" }]
      },
      {
        action: "airline_seat_legroom_normal",
        title: "FORNITURE",
        items: [{ title: "List Item" }]
      },
      {
        action: "local_activity",
        title: "ATTRACTIONS",
        items: [{ title: "List Item" }]
      }
    ]
  })
};
</script>

<style scoped>
.no-padding {
  padding: 0;
}

.bg {
  background-color: lightgrey;
}
</style>
