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
                        class="equality1"
                        src="https://images.unsplash.com/photo-1589578527966-fdac0f44566c?q=80&w=687&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                    />
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <h1>To many of us, this doesn't feel fair</h1>
            </ArticleText>

            <ArticleText>
                <h2>
                    Just because our answers and circumstances are different from
                    the person who is next to me, why should we be starting at
                    different places. We should be treated with equality right?
                </h2>
            </ArticleText>

            <ArticleText>
                <h1>So what is equality?</h1>
                <h2>
                    Equality is when everyone is treated the same and everything
                    one person gets, everyone else gets as well.
                </h2>
                <h2>
                    So to make this race more equal, the judges have decided to
                    move everyone up by one spot.
                </h2>
                <img class="race2-img" src="race2.jpg" alt="Race diagram with racers moved up a position" />
                <h2>This should make the race fair right?</h2>
                <h2>
                    The judges treated everyone with equality and each person
                    got moved up a spot regardless of where they started from
                    and the circumstances that determined these spots
                </h2>
                <h1>
                    Do you feel that where you are starting from now is fair?
                </h1>
            </ArticleText>
        {/snippet}
    </Scroller>

    <style>
        .equality1 {
            width: 100%;
        }
        .race2-img {
            width: 100%;
        }
    </style>
</div>
