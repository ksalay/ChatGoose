<template>
    <md-card>
        <md-card-header>
            <md-card-header-text>
                <div class="md-title">New users</div>
            </md-card-header-text>
            <md-tabs md-sync-route md-alignment="right" >
                <md-tab id="tab-dashboard" md-label="Today" :to="{name:'dashboard'}"></md-tab>
                <md-tab id="tab-editor" md-label="Week" :to="{name:'dashboard'}"></md-tab>
                <md-tab id="tab-analytics" md-label="Month" :to="{name:'dashboard'}"></md-tab>
                <md-tab id="tab-buy" md-label="Year" :to="{name:'dashboard'}"></md-tab>
            </md-tabs>
        </md-card-header>

        <img src="data:image/png;base64,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"/>

        <!--<FiltersForChart/>-->

        <md-card-actions>
            <md-button class="md-raised">More Details</md-button>
        </md-card-actions>
    </md-card>
</template>

<script>
    // @ is an alias to /src

    import FiltersForChart from '@/components/DashboardComponents/DashboardTab/FiltersForChartCmponent.vue'

    export default {
        name: 'NewUsersChart',
        components: {
            FiltersForChart
        }
    }
</script>


<style lang="scss" scoped>
    .md-card-header-text {
        text-align: left;
    }
    .md-button {
        width: 800px;
    }
    img {
        height: 315px;
    }
</style>
