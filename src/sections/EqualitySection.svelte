<script>
    // @ts-nocheck
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import Radio from "../lib/Radio.svelte";

    let radioValue;

    const options = [
        {
            value: "yes",
            label: "yes",
        },
        {
            value: "no",
            label: "no",
        },
    ];
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div>
                <ArticleText>
                    <img
                        class="Pic1"
                        src="https://images.unsplash.com/photo-1582719471257-05db68be5ae5?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Nnx8QmxhY2slMjBmZW1hbGUlMjBzY2llbnRpc3R8ZW58MHx8MHx8fDA%3D"
                    />
                </ArticleText>
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <h1>To many of us, this doesn't feel fair</h1>
            </ArticleText>

            <ArticleText>
                <p>
                    Just because our answers and circumstance are different from
                    the person who is next to me, why should we be starting at
                    different places. We should be treated with equality right?
                </p>
            </ArticleText>

            <h1>So what is equality?</h1>
            <h2>
                Equality is when everyone is treated the same and everything one
                person gets, everyone else gets as well.
            </h2>
            <p>
                So to make this race more equal, the judges have decided to move
                everyone up by one spot.
            </p>
            <p>This should make the race fair right?</p>
            <p>
                The judges treated everyone with equality and each person got
                moved up a spot regardless of where they started from and the
                circumstances that determined these spots
            </p>
            <h1>Do you feel that where you are starting from now is fair?</h1>
        {/snippet}
    </Scroller>

    <style>
        .Pic1 {
            width: 100%;
        }
    </style>
</div>
