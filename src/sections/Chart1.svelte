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
    <Scroller layout="chart1">
        {#snippet sticky()}
            <div class="chart">
                <Chart {options} highcharts={Highcharts} />
            </div>
            <img
                src="https://images.unsplash.com/photo-1686213011376-d20df949af59?w=900&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTV8fGJsYWNrJTIwd29tZW4lMjBncmFkdWNhdGlvbnxlbnwwfHwwfHx8MA%3D%3D"
            />
        {/snippet}

        {#snippet scrolly()}
            <div>
                <ArticleText>
                    <h1>
                        One of the boundaries/challenges Black women face is
                        less access to attain higher education
                    </h1>
                </ArticleText>

                <ArticleText>
                    <p>
                        <strong>
                            In order for Black Women to get jobs in STEM, they
                            would need to further their education beyond high
                            school. However, in the figure to the left, even in
                            the states with the largest Black population, the
                            percentage of women who have attained higher
                            education is less than the percentage of white men.
                            The proportion of black women who have attained
                            higher education is not proportionate to their
                            population. Since the Black population in these
                            states is higher, the amount of black women who
                            attained high education should be proportionate, but
                            this is not the case.
                        </strong>
                    </p>
                </ArticleText>

                <ArticleText>
                    <h1>
                        So now this begs the question...Why does this happen?
                    </h1>
                </ArticleText>
            </div>
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

<style>
    .chart {
        width: 100%;
        height: 100%;
        background-color: #458883;
    }
    img {
        background-color: #458883;
    }
    p {
        font-size: 2em;
    }
</style>
