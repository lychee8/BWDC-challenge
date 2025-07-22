<script>
    // @ts-nocheck
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div>
                <img
                    class="race3-img"
                    src="race3.jpg"
                    alt="Race diagram with racers at the same starting point"
                />
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <h1>
                    If you still feel that it is unfair you are justified
                    feeling that way
                </h1>
                <h2>
                    Even though we were all treated equally, it didn't account
                    for the fact that even though we were all moved up a spot,
                    we all didn't start at the same spot.
                </h2>
                <h2>This is where equity comes in</h2>
                <h1>So what is Equity</h1>
                <h2>
                    Equity accounts the fact that everyone has different
                    circumstances and that their starting points are different.
                    It takes these differences into account and creates a way to
                    ensure that eveyone has an equal opportunity
                </h2>
                <h2>
                    So when we use equity, the judges tell each person to move
                    up a different amount of spots in order to have their new
                    spot be the same as the person closest to the finish line.
                </h2>
                <h2>Once the judges have done this, the race can begin.</h2>

                <h1>
                    Do you feel that where you are starting from now is fair?
                </h1>
            </ArticleText>
        {/snippet}
    </Scroller>

    <style>
        .race3-img {
            width: 100%;
        }
    </style>
</div>
