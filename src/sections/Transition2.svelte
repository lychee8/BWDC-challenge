<script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

    let scientistIsVisible = $state(false);
    let familyIsVisible = $state(false);

    const options = {
        threshold: [0.85, 0.95],
    };

    const simpleCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                // "active" state
                elem.style.backgroundColor = "#e3ff00";
            } else if (entry.intersectionRatio < 0.9) {
                // "inactive" state
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const showscientistCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#e3ff00";
                scientistIsVisible = true;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const showfamilyCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#e3ff00";
                familyIsVisible = true;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const removescientistCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#e3ff00";
                scientistIsVisible = false;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const removefamilyCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#e3ff00";
                familyIsVisible = false;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div>
                {#if scientistIsVisible}
                    <img
                        class="scientist-img"
                        src="scientist.png"
                        alt="Female scientist"
                        in:fly={{ y: 200, duration: 2000 }}
                        out:fade
                    />
                {/if}
                {#if familyIsVisible}
                    <img
                        class="family-img"
                        src="family.png"
                        alt="Mother and daughter"
                        in:fly={{ y: 200, duration: 2000 }}
                        out:fade
                    />
                {/if}
                <br />
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ObservedArticleText callback={showfamilyCallback} {options}>
                <h1>
                    These two charts were examples of a problem that has been
                    debated on for a while, especially in the United States.
                    There are generational difficulties and challenges that have
                    affected current generations.
                </h1>
            </ObservedArticleText>

            <ObservedArticleText callback={removefamilyCallback} {options}>
                <h1>
                    Interventions, such as affirmative action, are necessary to
                    obtain equity and in the future equality.
                </h1>
            </ObservedArticleText>

            <ObservedArticleText callback={removescientistCallback} {options}>
                When this box scrolls into view, the callback will set
                <code>duckIsVisible</code> to <code>false</code>.
                <br /><br />
                Svelte then automatically updates the page (more precisely, the DOM)
                and removes the duck component.
                <br /><br />
                The Svelte transition
                <code>{"out:fade"}</code>
                handles animating the transition.
            </ObservedArticleText>

            <ObservedArticleText callback={simpleCallback} {options}>
                Pretty slick, huh?
                <br /><br />
                🤔
                <strong
                    >How might you use a transition like this for emotional
                    impact in your final project?</strong
                >
            </ObservedArticleText>
        {/snippet}
    </Scroller>
</div>

<!-- <script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let scientistIsVisible = $state(false);

    const options = {
        threshold: [0.85, 0.95],
    };

    const simpleCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                // "active" state
                elem.style.backgroundColor = "#e3ff00";
            } else if (entry.intersectionRatio < 0.9) {
                // "inactive" state
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const showScientistCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#e3ff00";
                scientistIsVisible = true;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const removeScientistCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#e3ff00";
                scientistIsVisible = false;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div>
                {#if scientistIsVisible}
                    <img
                        class="scientist-img"
                        src="scientist.png"
                        alt="Female Scientist"
                        in:fly={{ y: 200, duration: 2000 }}
                        out:fade
                    />
                {/if}
                <br />
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ObservedArticleText callback={simpleCallback} {options}>
                <h1>
                    These two charts were examples of a problem that has been
                    debated on for a while, especially in the United States.
                    There are generational difficulties and challenges that have
                    affected current generations. Interventions, such as
                    affirmative action, are necessary to obtain equity and in
                    the future equality.
                </h1>

                <br /><br />
                <h1>
                    Before we dive into this statement we need to understand
                    an important concept...
                </h1>
                <br /><br />
                You can also
                <a
                    href="https://svelte.dev/tutorial/svelte/custom-css-transitions"
                >
                    build your own transitions
                </a> (it's not as hard as you think!).
            </ObservedArticleText>

            <ObservedArticleText callback={showScientistCallback} {options}>
                <h1>Equity vs. Equality</h1>
                <br /><br />
                The svelte transition
                <code>{"in:fly={{ y: 200, duration: 2000 }}"}</code>
                handles <strong>animating</strong> the transition.
            </ObservedArticleText>

            <ObservedArticleText callback={removeScientistCallback} {options}>
                When this box scrolls into view, the callback will set
                <code>duckIsVisible</code> to <code>false</code>.
                <br /><br />
                Svelte then automatically updates the page (more precisely, the DOM)
                and removes the duck component.
                <br /><br />
                The Svelte transition
                <code>{"out:fade"}</code>
                handles animating the transition.
            </ObservedArticleText>

            <ObservedArticleText callback={simpleCallback} {options}>
                Pretty slick, huh?
                <br /><br />
                🤔
                <strong
                    >How might you use a transition like this for emotional
                    impact in your final project?</strong
                >
            </ObservedArticleText>
        {/snippet}
    </Scroller>
</div> -->

<!-- <script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    
    let scientistIsVisible = $state(false);
    const options = {
        threshold: [0.85, 0.95],
    }

    const simpleCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                // "active" state
                elem.style.backgroundColor = "#e3ff00";
            } else if (entry.intersectionRatio < 0.9) {
                // "inactive" state
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const showScientistCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#e3ff00";
                scientistIsVisible = true;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const removeScientistCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#e3ff00";
                scientistIsVisible = false;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div class="img1">
                {#if scientistIsVisible}
                    <img
                        class="scientist-img"
                        src="scientist.png"
                        alt="Female Scientist"
                        in:fly={{ y: 200, duration: 2000 }}
                        out:fade
                    >
                {/if}
            <br /> -->

<!-- <img
                        class="Pic1"
                        src="https://images.unsplash.com/photo-1582719471257-05db68be5ae5?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Nnx8QmxhY2slMjBmZW1hbGUlMjBzY2llbnRpc3R8ZW58MHx8MHx8fDA%3D"
                    /> -->
<!-- </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText callback={removeScientistCallback} {options}>
                <h1>
                    These two charts were examples of a problem that has been
                    debated on for a while, especially in the United States.
                    There are generational difficulties and challenges that have
                    affected current generations. Interventions, such as
                    affirmative action, are necessary to obtain equity and in
                    the future equality.
                </h1>
            </ArticleText>

            <ArticleText callback={showScientistCallback} {options}>
                <h1>
                    Before we dive into this statement we need to understand
                    an important concept...
                </h1>
            </ArticleText>

            <ArticleText callback={removeScientistCallback} {options}>
                <h1>Equity vs. Equality</h1>
            </ArticleText>
        {/snippet}
    </Scroller>
</div> -->

<!-- <script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    const options = {
        threshold: [0.85, 0.95],
    };

    const callback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                // "active" state
                elem.style.backgroundColor = "#e3ff00";
            } else if (entry.intersectionRatio < 0.9) {
                // "inactive" state
                elem.style.backgroundColor = "#888888";
            }
        });
    };
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div>
                <img
                    src="https://images.unsplash.com/photo-1599041125553-a3b967646ca5?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTZ8fGJsYWNrJTIwd29tYW4lMjBjb2Rpbmd8ZW58MHx8MHx8fDA%3D"
                />
            </div>
        {/snippet}

        {#snippet scrolly()}
            <ObservedArticleText {callback} {options}>
                <h1>These two charts were examples of a problem that has been debated on for a 
                    while, especially in the United States. There are generational difficulties 
                    and challenges that have affected current generations. Interventions, such 
                    as affirmative action, are necessary to obtain equity and in the future equality.</h1>
            </ObservedArticleText>

            <ObservedArticleText {callback} {options}>
                <h1>
                    Before we dive into this statement we need to understand animport concept...
                </h1>
            </ObservedArticleText>

            <ObservedArticleText {callback} {options}>
                <h1>Equity vs. Equality</h1>
            </ObservedArticleText>
        {/snippet}
    </Scroller>
</div> -->

<!-- <style>
    .img1 {
        background-color: #458883;
    }
</style> -->

<!-- <style>
    .scientist-img {
        margin: 0px auto;
    }
</style> -->

<style>
    .family-img {
        width: 50%;
    }
    .scientist-img {
        width: 50%;
    }
</style>
