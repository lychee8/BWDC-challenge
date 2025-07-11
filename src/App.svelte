<script>
  import Transition1 from "./sections/Transition1.svelte";
  import Transition2 from "./sections/Transition2.svelte";
  import EquityEquality from "./sections/EquityEquality.svelte";
  import Chart1 from "./sections/Chart1.svelte";
  import LeftAlignedExample from "./sections/LeftAlignedExample.svelte";
  import RightAlignedExample from "./sections/RightAlignedExample.svelte";
  import ImageExample from "./sections/ImageExample.svelte";
  import TitleSection from "./sections/TitleSection.svelte";
</script>

<main>
  <TitleSection />
  <Transition1 />
  <div
    class="tableauPlaceholder"
    id="viz1752197793637"
    style="position: relative"
  >
    <noscript
      ><a href="#"
        ><img
          alt="Percentage Disitribution with a Bachelor&#39;s Degree by Occupation and Race&#47;Ethnicity "
          src="https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;BW&#47;BWDC-PersonLevel-V1&#47;STEMEmployment&#47;1_rss.png"
          style="border: none"
        /></a
      ></noscript
    ><object class="tableauViz" style="display:none;"
      ><param name="host_url" value="https%3A%2F%2Fpublic.tableau.com%2F" />
      <param name="embed_code_version" value="3" />
      <param name="site_root" value="" /><param
        name="name"
        value="BWDC-PersonLevel-V1&#47;STEMEmployment"
      /><param name="tabs" value="no" /><param
        name="toolbar"
        value="yes"
      /><param
        name="static_image"
        value="https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;BW&#47;BWDC-PersonLevel-V1&#47;STEMEmployment&#47;1.png"
      /> <param name="animate_transition" value="yes" /><param
        name="display_static_image"
        value="yes"
      /><param name="display_spinner" value="yes" /><param
        name="display_overlay"
        value="yes"
      /><param name="display_count" value="yes" /><param
        name="language"
        value="en-US"
      /></object
    >
  </div>
  <script type="text/javascript">
    var divElement = document.getElementById("viz1752197793637");
    var vizElement = divElement.getElementsByTagName("object")[0];
    vizElement.style.width = "1244px";
    vizElement.style.height = "727px";
    var scriptElement = document.createElement("script");
    scriptElement.src = "https://public.tableau.com/javascripts/api/viz_v1.js";
    vizElement.parentNode.insertBefore(scriptElement, vizElement);
  </script>
  <Chart1 />
  <Transition2 />
  <EquityEquality />
  <RightAlignedExample />
  <LeftAlignedExample />
  <ImageExample />
</main>
