<template>
  <q-card
    style="width: 100%;"
    bordered
    class="text-secondary q-ma-xs q-pa-none shadow-11"
  >
    <q-card-section>
      <div class="text-h6 q-mx-sm">
        {{ proposal.id }} - {{ proposal.title }} ({{ proposal.status }})
      </div>
    </q-card-section>

    <GovernanceCardTabPanel
      :proposal="proposal"
    />
    <q-separator />
    <q-card-actions class="q-pa-md">
      <q-btn
        color="secondary"
        text-color="primary"
        class="q-pa-sm"
      >
        Vote
      </q-btn>
      <q-btn
        color="secondary"
        text-color="primary"
        class="q-pa-sm"
      >
        Deposit
      </q-btn>
    </q-card-actions>
    <!-- </q-card-section> -->
    <!-- <q-list class="q-ma-md">
        <q-item>
          <q-item-section avatar>
            <q-icon
              color="yestally"
              name="check"
            />
          </q-item-section>
          <q-item-section>
            <q-item-label>Yes</q-item-label>
            <q-item-label caption>      <q-tab
        label="Votes"
        name="votes"
      />
              {{ asPercent(proposal.tally.yes_percent) }}
            </q-item-label>
          </q-item-section>
        </q-item>
        <q-item>
          <q-item-section avatar>
            <q-icon
              color="notally"
              name="clear"
            />
          </q-item-section>
          <q-item-section>
            <q-item-label>No</q-item-label>
            <q-item-label caption>
              {{ asPercent(proposal.tally.no_percent) }}
            </q-item-label>
          </q-item-section>
        </q-item>
        <q-item>
          <q-item-section avatar>
            <q-icon
              color="grey"
              name="not_interested"
            />
          </q-item-section>
          <q-item-section>
            <q-item-label>Abstain</q-item-label>
            <q-item-label caption>
              {{ asPercent(proposal.tally.abstain_percent) }}
            </q-item-label>
          </q-item-section>
        </q-item>
        <q-item>
          <q-item-section avatar>
            <q-icon
              color="red"
              name="remove_circle_outline"
            />
          </q-item-section>
          <q-item-section>
            <q-item-label>No with Veto</q-item-label>
            <q-item-label caption>
              {{ asPercent(proposal.tally.no_with_veto_percent) }}
            </q-item-label>
          </q-item-section>
        </q-item>
      </q-list> -->
  </q-card>
</template>

<script>
import GovernanceCardTabPanel from './GovernanceCardTabPanel';

export default {
  name: 'GovProposalContainer',
  components: {
    GovernanceCardTabPanel,
  },
  props: {
    proposal: {
      type: Object,
      required: false,
      default: Object.assign({}),
    },
  },
  data() {
  },
  methods: {
    asPercent(val) {
      const perc = (val * 100).toFixed(2);
      return `${perc}%`;
    },
  },
};
</script>

<style>

</style>
