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
            text: "Percent of Bachelor's Degree or Higher Attainment from states with the largest Black population",
        },
        subtitle: {
            text: "You can easily add all the Highcharts modules in Svelte with @highcharts/svelte",
        },
        xAxis: {
            categories: [
                "District of Columbia",
                "Mississippi",
                "Georgia",
                "Louisiana",
                "Maryland",
                "Alabama",
            ],
            crosshair: true,
        },
        yAxis: {
            min: 0,
            max: 100,
            title: {
                text: "Percentage of each race and sex that attained higher education out of the population of that race and sex in each state",
            },
        },
        plotOptions: {
            column: {
                pointPadding: 0.2,
                borderWidth: 0,
            },
        },
        series: [
            {
                name: "Black Females",
                data: [33.8, 21.9, 30.8, 21.7, 36, 23.2],
            },
            {
                name: "White Males",
                data: [91.7, 25.9, 37, 28.4, 47.2, 30.4],
            },
        ],
    };
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <div class="chart">
                <Chart {options} highcharts={Highcharts} />
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <h1>
                    One of the boundaries/challenges Black women face is less
                    access to attain higher education
                </h1>
            </ArticleText>

            <ArticleText>
                In order for Black Women to get jobs in STEM, they would need to
                further their education beyond high school. However, in the
                figure to the left, even in the states with the largest Black
                population, the amount of women who have attained higher
                education is less than the amount of white men. Even though
                there is a larger Black population, the amount of white males is
                still significantly larger than the Black Female amount.
            </ArticleText>

            <ArticleText>
                You can use this template as a starting point for your project.
                Or, if you want to build something from scratch, you can use it
                as a reference for specific functionality.
            </ArticleText>

            <ArticleText>
                This is just one way that scrollytelling can look. If you use
                this template, be sure to modify it and make it your own!
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<!-- <Scroller layout="transition1">
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
</Scroller> -->
