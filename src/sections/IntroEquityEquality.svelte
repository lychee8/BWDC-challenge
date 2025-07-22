<script>
    // @ts-nocheck
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div class="body">
    <Scroller layout="left">
        {#snippet sticky()}
            <div>
                <ArticleText>
                    <h1>Equity vs. Equality</h1>
                    <img
                        class="race"
                        src="https://images.unsplash.com/photo-1532444458054-01a7dd3e9fca?q=80&w=1241&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                    />
                </ArticleText>
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <h1>Let's begin with you answering a few questions</h1>
                <h2>Are you female or non-cisgender?</h2>
                <h2>
                    Do you have a college degree or plan to enroll in college
                    after high school?
                </h2>
                <h2>
                    Do you have a high school degree or plan to graduate high
                    school?
                </h2>
                <h2>Do/Did you have a job in high school?</h2>
                <h2>Do/Did you qualify for free lunch in high school?</h2>
                <h2>
                    Did you borrow a technology device long term for classes?
                </h2>
                <h2>Do you have internet availible at home?</h2>
            </ArticleText>

            <ArticleText>
                <h2>
                    Based on your answers, you have been given a spot to start a
                    race from
                </h2>
                <img
                    class="race1-img"
                    src="race1.jpg"
                    alt="Race diagram with racers at different starting points"
                />
            </ArticleText>

            <ArticleText>
                <h2>
                    Each runner has been placed at a different staring point
                    based on their answers
                </h2>
                <h2>
                    Now each runner must start the race from the indicated spot
                    and the winner is the person who gets to the finish line
                    first.
                </h2>
                <h2>
                    Seeing where you start in relation to others, do you feel
                    that where you are starting is fair?
                </h2>
            </ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .race {
        width: 100%;
    }
    .race1-img {
        width: 100%;
    }
    h2 {
        text-align: center;
    }
</style>
