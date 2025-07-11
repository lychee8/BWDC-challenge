<script>
    // @ts-nocheck
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div>
                <ArticleText>
                    <h1>Equity vs. Equality</h1>
                </ArticleText>
                <p>You can use Svelte to add and remove data from the chart.</p>
                <p>
                    When you click the button above, a third group is toggled in
                    the chart. Check out the source code to see how it's done.
                </p>
                <p>
                    How might you use other HTML elements, like checkboxes or
                    radio buttons, in a similar way to filter data?
                </p>
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                You might notice that this template doesn't have certain
                features that are common in scrollytelling.
            </ArticleText>

            <ArticleText>
                For example, you might want a component that doesn't feature a
                sticky component at all. Or a component that is solely a sticky
                component.
            </ArticleText>

            <ArticleText>
                You might also want to add more interactivity or gamify parts of
                your scrollytelling piece.
            </ArticleText>
        {/snippet}
    </Scroller>
</div>
