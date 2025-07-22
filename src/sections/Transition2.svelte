<script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

    let educationIsVisible = $state(false);
    let familyIsVisible = $state(false);

    const options = {
        threshold: [0.85, 0.95],
    };

    const simpleCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                // "active" state
                elem.style.backgroundColor = "#b99095";
            } else if (entry.intersectionRatio < 0.9) {
                // "inactive" state
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const showeducationCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#b99095";
                educationIsVisible = true;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const showfamilyCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#b99095";
                familyIsVisible = true;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const removeeducationCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#b99095";
                educationIsVisible = false;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#888888";
            }
        });
    };

    const removefamilyCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#b99095";
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
                {#if familyIsVisible}
                    <img
                        class="family-img"
                        src="family.png"
                        alt="Mother and daughter"
                        in:fly={{ y: 200, duration: 2000 }}
                        out:fade
                    />
                {:else if !familyIsVisible && educationIsVisible}
                    <img
                        class="education-img"
                        src="education.png"
                        alt="Person holding sign that says: Education for all!"
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
                    So how are these generational difficulties accounted for?
                </h1>
            </ObservedArticleText>

            <ObservedArticleText callback={showeducationCallback} {options}>
                <h1>
                    Interventions, such as affirmative action, are necessary to
                    obtain equity and in the future equality.
                </h1>
            </ObservedArticleText>

            <ObservedArticleText callback={removefamilyCallback} {options}>
                <h1>
                    Before we dive into this statement we need to understand an
                    important concept...
                </h1>
            </ObservedArticleText>

            <ObservedArticleText callback={simpleCallback} {options}>
                <h1>Equity vs. Equality</h1>
            </ObservedArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .family-img {
        width: 100%;
    }
</style>
