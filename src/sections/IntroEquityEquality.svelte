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
                    <h1>Equity vs. Equality</h1>
                    <img
                        class="Pic1"
                        src="https://images.unsplash.com/photo-1582719471257-05db68be5ae5?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Nnx8QmxhY2slMjBmZW1hbGUlMjBzY2llbnRpc3R8ZW58MHx8MHx8fDA%3D"
                    />
                </ArticleText>
                <p>
                    Each runner has been placed at a different staring point
                    based on their answers
                </p>
                <p>
                    Now each runner must start the race from the indicated spot
                    and the winner is the person who gets to the finish line
                    first.
                </p>
                <p>
                    Seeing where you start in relation to others, do you feel
                    that where you are starting is fair?
                </p>
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <h1>Let's begin with you answering a few questions</h1>
                <h2>Are you female or non-cisgender?</h2>
                <Radio {options} fontSize={16} />
                <h2>
                    Do you have a college degree or plan to enroll in college
                    after high school?
                </h2>
                <Radio {options} fontSize={16} />
                <h2>
                    Do you have a high school degree or plan to graduate high
                    school?
                </h2>
                <Radio {options} fontSize={16} />
                <h2>Do/Did you have a job in high school?</h2>
                <Radio {options} fontSize={16} />
                <h2>Do/Did you qualify for free lunch in high school?</h2>
                <Radio {options} fontSize={16} />
                <h2>Did you borrow technology device long term for classes?</h2>
                <Radio {options} fontSize={16} />
                <h2>Do you have internet availible at home?</h2>
                <Radio {options} fontSize={16} />
            </ArticleText>

            <ArticleText>
                <h2>
                    Based on your answers, you have been given a spot to start a
                    race from
                </h2>
            </ArticleText>

            <ArticleText>
                <h1>ADD RACE SIM</h1>
            </ArticleText>
        {/snippet}
    </Scroller>

    <style>
        .Pic1 {
            width: 100%;
        }
    </style>
</div>
