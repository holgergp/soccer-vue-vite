<script>
import draggable from "vuedraggable";
import { SAMPLE_LEAGUE_TABLE } from "../constants/SampleData";
import Position from "./Position.vue";
import Positions from "../model/Positions.js";
import position from "./Position.vue";

const LEAGUE_TABLE = "LEAGUE_TABLE";

export default {
  name: "LeagueTable",
  computed: {
    position() {
      return position;
    },
  },
  components: { Position, draggable },
  data() {
    return {
      list: SAMPLE_LEAGUE_TABLE,
    };
  },
  props: {},

  methods: {
    updateTeamname(event) {
      const { position, updatedTeamname } = event;
      this.list = Positions.recalculatePositionsWithRenamedTeam(
        position,
        updatedTeamname,
        this.list,
      );
    },
  },
};
</script>

<template>
  <div>
    <h1 class="text-sky-900 font-semibold text-4xl pb-4">Ligatabelle zum Selberstecken</h1>
    <div class="">
      <draggable
        v-model="list"
        :component-data="{ name: 'fade' }"
        item-key="id"
        class="grid grid-cols-1"
      >
        <template #item="{ element, index }">
          <Position
            :position="element"
            :rank="index + 1"
            v-on:teamnameUpdated="updateTeamname"
          />
        </template>
      </draggable>
    </div>
  </div>
</template>
