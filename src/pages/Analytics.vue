<template>
<q-page class="q-pa-md">
    <div class="flex q-gutter-sm justify-around q-mb-md text-grey text-weight-bold">
        <q-card class="card-item">
            <q-card-section>
                <div class="text-black">
                    Sales
                    <q-btn flat dense round icon="help" class="text-grey-4 text-caption text-weight-thin" />
                </div>
            </q-card-section>
            <div class="row wrap">
                <div class="col-6">
                    <div class="row text-center">
                        <q-badge color="blue" round>
                            20%
                            <q-icon color="white" class="q-ml-xs" />
                        </q-badge>
                    </div>
                </div>
                <div class="col-6">
                    <div class="row">
                        Lifetime Sales
                    </div>
                    <div class="row  text-weight-bolder text-black">
                        <q-icon name="mdi-currency-php" color="orange"></q-icon>
                        <p>175,000</p>
                    </div>
                    <div class="row">
                        Revenue Sales
                    </div>
                    <div class="row text-weight-bolder text-black">
                        <q-icon name="mdi-currency-php" color="orange"></q-icon>
                        <p>175,000</p>
                    </div>
                </div>

            </div>
            <q-separator inset />

            <q-card-section>
                <div class="row">
                    <div class="col-6">
                        Average order value
                    </div>
                    <div class="col-6">
                        <div class="row">
                            <q-icon name="mdi-currency-php" color="orange"></q-icon>
                            <p>1,000.00</p>
                        </div>
                    </div>
                </div>
            </q-card-section>

        </q-card>
        <q-card class="card-item">
            <q-card-section>
                <div class="text-black">
                    Engagement
                    <q-btn flat dense round icon="help" class="text-grey-4 text-caption text-weight-thin" />
                </div>
            </q-card-section>
            <div class="row wrap">
                <div class="col-6">
                    <div class="row text-center">
                        <q-badge color="blue" round>
                            20%
                            <q-icon color="white" class="q-ml-xs" />
                        </q-badge>
                    </div>
                </div>
                <div class="col-6">
                    <div class="row text-">
                        Lifetime SMS Engagement
                    </div>
                    <div class="row">
                        285
                    </div>
                    <div class="row">
                        Daily Average
                    </div>
                    <div class="row">
                        57
                    </div>
                </div>

            </div>
            <q-separator inset />
            <q-card-section>
                <div class="row">
                    20% decrease in 30 days
                </div>
            </q-card-section>

        </q-card>
        <q-card class="card-item ">
            <q-card-section>
                <div class="text-black">
                    Acquisition
                    <q-btn flat dense round icon="help" class="text-grey-4 text-caption text-weight-thin" />
                </div>
            </q-card-section>
            <div class="row wrap">
                <div class="col-6">
                    <div class="row">

                    </div>
                </div>
                <div class="col-6">
                    <div class="row">
                        Registered User
                    </div>
                    <div class="row">
                        285
                    </div>
                    <div class="row">
                        Daily Average
                    </div>
                    <div class="row">
                        57
                    </div>
                </div>

                <q-separator inset />
                <q-card-section>
                    <div class="">
                        20% decrease in 30 days
                    </div>
                </q-card-section>
            </div>

        </q-card>
        <q-card class="card-item ">
            <q-card-section>
                <div class="text-black">
                    Rewards Program
                    <q-btn flat dense round icon="help" class="text-grey-4 text-caption text-weight-thin" />
                </div>
            </q-card-section>
            <div class="row wrap">
                <div class="col-6">
                    <div class="row">

                    </div>
                </div>
                <div class="col-6">
                    <div class="row">
                        Rewards Redeemed
                    </div>
                    <div class="row">
                        175,000
                    </div>
                    <div class="row">
                        Issued Rewards
                    </div>
                    <div class="row">
                        175,000
                    </div>
                </div>

                <q-separator inset />
                <q-card-section>
                    <div class="">
                        20% decrease in 30 days
                    </div>
                </q-card-section>
            </div>

        </q-card>
    </div>

    <div class="flex q-gutter-md row-inline q-mb-md ">
        <q-select outlined v-model="model1" :options="options1" class="bg-white dropdown" />
        <q-select outlined v-model="model2" :options="options2" class="bg-white dropdown" />
    </div>

    <div class="row q-mb-md">
        <q-card class="full-width">
            <q-card-section>
                <div class="row">
                    <div class="col text-weight-bold">
                        Sales Overview
                        <q-btn flat dense round icon="help" class="text-grey-4 text-caption text-weight-thin" />
                    </div>
                    <div class="row q-gutter-sm">

                        <q-select outlined v-model="model3" :options="options3" class="bg-white dropdown" />
                        <q-select outlined v-model="model4" :options="options4" class="bg-white dropdown" />
                    </div>
                </div>
            </q-card-section>
            <div>
                <VueApexCharts class="" type="bar" :options="plotOptions" :series="series"></VueApexCharts>
            </div>
        </q-card>
    </div>

    <div class="wrap row q-gutter-md q-mb-md">
        <q-card class="col">
            <q-card-section>
                <div class="text-weight-bold">
                    Branch Performance
                    <q-btn flat dense round icon="help" class="text-grey-4 text-caption text-weight-thin" />
                </div>
            </q-card-section>
            <q-table :data="tableData" :columns="columns" row-key="name" />

        </q-card>
        <q-card class="col">
            <q-card-section>
                <div class="text-weight-bold">
                    Rewards Performance
                    <q-btn flat dense round icon="help" class="text-grey-4 text-caption text-weight-thin" />
                </div>
            </q-card-section>
            <q-table :data="tableData" :columns="columns" row-key="name" />
        </q-card>
    </div>
</q-page>
</template>

<script>
import VueApexCharts from 'vue-apexcharts'

export default {
    name: 'Analytics',
    components: {
        VueApexCharts
    },
    data() {
        return {
            options1: ['Last 7 days'],
            options2: ['1 Jan 2019 - 7 Jan 2019'],
            options3: ['All Transactions'],
            options4: ['All Branches'],
            model1: 'Last 7 days',
            model2: '1 Jan 2019 - 7 Jan 2019',
            model3: 'All Transactions',
            model4: 'All Branches',
            columns: [{
                    name: 'branch',
                    required: true,
                    label: 'Branch',
                    align: 'left',
                    field: 'branch',
                    sortable: true,
                    classes: 'my-class',
                    style: 'width: 500px'
                },
                {
                    name: 'totalSales',
                    required: true,
                    label: 'Total Sales (P)',
                    align: 'left',
                    field: 'totalSales',
                    sortable: true,
                    classes: 'my-class',
                    style: 'width: 500px'
                }
            ],
            tableData: [{
                branch: 'Makati',
                totalSales: '5,000'
            }, {
                branch: 'BGC Taguig',
                totalSales: '4,000'
            }, {
                branch: 'Mall of Asia, Pasay',
                totalSales: '5,000'
            }, {
                branch: 'Quezon City',
                totalSales: '4,000'
            }, {
                branch: 'Greenhills',
                totalSales: '5,000'
            }],
            series: [{
                name: "Sales",
                data: [44, 55, 41, 64, 22, 43, 21]
            }, {
                name: "Revenue",
                data: [53, 32, 33, 52, 13, 44, 32]
            }],
            plotOptions: {
                bar: {
                    horizontal: true,
                    dataLabels: {
                        position: 'center',
                    },
                },
                chart: {
                    type: 'bar',
                    height: '100',
                    toolbar: {
                        show: false
                    },
                },
                dataLabels: {
                    enabled: false,
                },
                stroke: {
                    show: true,
                    width: 1,
                    colors: ['#fff']
                },
                legend: {
                    show: true,
                    position: 'top',
                    horizontalAlign: 'right'
                },
                xaxis: {
                    categories: [2001, 2002, 2003, 2004, 2005, 2006, 2007],
                },
            },
            dateRange: null

        }
    },
}
</script>
