<template>
  <div>
    <v-container fluid class="grey lighten-4 fluid" :class="$vuetify.breakpoint.smAndDown ? 'px-3' : 'px-6'">
      <h3>Home page</h3>
      <v-row>
        <v-col cols="12" xs="12" sm="3" class="">
          <v-card color="#
          " dark height="180">
            <v-card-title>
              <v-icon large left>
                mdi-twitter
              </v-icon>
              <span class="title font-weight-light">Twitter</span>
            </v-card-title>

            <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.
            </v-card-subtitle>
            <v-divider></v-divider>
            <v-card-actions>
              <v-btn text>
                Listen Now
              </v-btn>
              <v-icon class="mr-1">
                mdi-heart
              </v-icon>
              <v-spacer></v-spacer>
            </v-card-actions>
          </v-card>
        </v-col>
        <v-col cols="12" xs="12" sm="3" class="">
          <v-card color="#385F73" dark height="180">
            <v-card-title>Employees</v-card-title>
            <v-card-text class="display-2">65</v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" xs="12" sm="3" class="">
          <v-card color="#385F73" dark height="180">
            <v-card-title class="headline">
              Unlimited music now
            </v-card-title>

            <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.
            </v-card-subtitle>

            <v-card-actions>
              <v-btn text>
                Listen Now
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
        <v-col cols="12" xs="12" sm="3" class="">
          <v-card color="#385F73" dark height="180">
            <v-card-title class="headline">
              Unlimited music now
            </v-card-title>

            <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.
            </v-card-subtitle>

            <v-card-actions>
              <v-btn text>
                Listen Now
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12">
          <v-card>
            <v-card-title>
              <v-text-field v-model="search" append-icon="mdi-magnify" label="Search" single-line hide-details>
              </v-text-field>
            </v-card-title>
            <v-data-table :items-per-page="5" :headers="headers" :items="desserts" :search="search" class="mb-10">
              <template v-slot:item.calories="{ item }">
                <v-chip :color="getColor(item.calories)" dark>
                  {{ item.calories }}
                </v-chip>
              </template>
              <template v-slot:top>
                <v-toolbar flat>
                  <v-toolbar-title>My table</v-toolbar-title>
                  <v-spacer></v-spacer>
                  <v-dialog v-model="dialog" max-width="500px">
                    <template v-slot:activator="{ on, attrs }">
                      <v-btn large rounded color="#fe7b5f" dark class="mb-2" v-bind="attrs" v-on="on">
                        <v-icon left dark>
                          mdi-plus
                        </v-icon>
                        Add New
                      </v-btn>
                    </template>
                    <v-card>
                      <v-card-title>
                        <span class="headline">Form Test Title</span>
                      </v-card-title>
                      <v-card-text>
                        <v-container>
                          <v-row>
                            <v-col cols="12" sm="6">
                              <div>Label 1</div>
                              <v-text-field outlined dense required></v-text-field>
                            </v-col>
                            <v-col cols="12" sm="6">
                              <div>Label 2</div>
                              <v-text-field outlined dense required></v-text-field>
                            </v-col>
                            <v-col cols="12" sm="6">
                              <div>Label 1</div>
                              <v-text-field outlined dense required></v-text-field>
                            </v-col>
                            <v-col cols="12" sm="6">
                              <div>Label 2</div>
                              <v-text-field outlined dense required></v-text-field>
                            </v-col>
                            <v-col cols="12">
                              <div>Label 3</div>
                              <v-text-field outlined dense type="password" required></v-text-field>
                            </v-col>
                          </v-row>
                        </v-container>
                      </v-card-text>
                      <v-card-actions>

                        <v-spacer></v-spacer>
                        <v-btn color="#fe7b5f" dark @click="dialog = false">
                          Close
                        </v-btn>
                        <v-btn color="#fe7b5f" dark @click="dialog = false">
                          Save
                        </v-btn>
                      </v-card-actions>
                    </v-card>
                  </v-dialog>
                </v-toolbar>
              </template>

            </v-data-table>
          </v-card>

        </v-col>

      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      dialog: false,
      search: "",
      headers: [
        {
          text: "Dessert (100g serving)",
          align: "start",
          filterable: true,
          value: "name"
        },
        {
          text: "Calories",
          value: "calories"
        },
        {
          text: "Fat (g)",
          value: "fat"
        },
        {
          text: "Carbs (g)",
          value: "carbs"
        },
        {
          text: "Protein (g)",
          value: "protein"
        },
        {
          text: "Iron (%)",
          value: "iron"
        }
      ],
      desserts: [
        {
          name: "Frozen Yogurt",
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          iron: "1%"
        },
        {
          name: "Ice cream sandwich",
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          iron: "1%"
        },
        {
          name: "Eclair",
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          iron: "7%"
        },
        {
          name: "Cupcake",
          calories: 305,
          fat: 3.7,
          carbs: 67,
          protein: 4.3,
          iron: "8%"
        },
        {
          name: "Gingerbread",
          calories: 356,
          fat: 16.0,
          carbs: 49,
          protein: 3.9,
          iron: "16%"
        },
        {
          name: "Jelly bean",
          calories: 375,
          fat: 0.0,
          carbs: 94,
          protein: 0.0,
          iron: "0%"
        },
        {
          name: "Lollipop",
          calories: 392,
          fat: 0.2,
          carbs: 98,
          protein: 0,
          iron: "2%"
        },
        {
          name: "Honeycomb",
          calories: 408,
          fat: 3.2,
          carbs: 87,
          protein: 6.5,
          iron: "45%"
        },
        {
          name: "Donut",
          calories: 452,
          fat: 25.0,
          carbs: 51,
          protein: 4.9,
          iron: "22%"
        },
        {
          name: "KitKat",
          calories: 518,
          fat: 26.0,
          carbs: 65,
          protein: 7,
          iron: "6%"
        }
      ]
    };
  },
  methods: {
    getColor(calories) {
      if (calories > 400) return "red";
      else if (calories > 200) return "orange";
      else return "green";
    }
  }
};
</script>