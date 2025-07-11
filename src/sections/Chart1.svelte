<script lang="ts">
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import Scroller from "../lib/Scroller.svelte";

    // Apply Highcharts modules

    let options = {
        chart: {
            type: "column",
        },
        title: {
            text: "Add Highcharts modules",
        },
        subtitle: {
            text: "You can easily add all the Highcharts modules in Svelte with @highcharts/svelte",
        },
        xAxis: {
            categories: ["USA", "China", "Brazil", "EU", "Argentina", "India"],
            crosshair: true,
            accessibility: {
                description: "Countries",
            },
        },
        yAxis: {
            min: 0,
            title: {
                text: "1000 metric tons (MT)",
            },
        },
        tooltip: {
            valueSuffix: " (1000 MT)",
        },
        plotOptions: {
            column: {
                pointPadding: 0.2,
                borderWidth: 0,
            },
        },
        series: [
            {
                name: "Corn",
                data: [387749, 280000, 129000, 64300, 54000, 34300],
            },
            {
                name: "Wheat",
                data: [45321, 140000, 10000, 140500, 19500, 113500],
            },
        ],
    };
</script>

<Scroller layout="transition1">
    {#snippet sticky()}
        <ArticleText>
            <h1>Now I want to point your attention to this statistic</h1>
        </ArticleText>
    {/snippet}
    {#snippet scrolly()}
        <Chart {options} highcharts={Highcharts} />
        <ArticleText>
            This stat shows that between 2019-2021, the amount of Black females
            in STEM decreased, but the amount of White males remained the same.</ArticleText
        >
    {/snippet}
</Scroller>
