<!--
@component
### Hero component 
Renders a visual replica of the Immersive Template hero. 

#### Optional properties
- sectionLabel: string;
- headline: string;
- timestamp: string;
- heroImageUrl: string;
- heroImageCaption: string;
- heroImageAltText: string;
- dek: string;
- authorName: string;
- authorBioUrl: string;

#### Example
```svelte
<Hero
  sectionLabel = "Section label",
  headline = "Lorem ipsum dolor sit amet consectetur adipiscing elit",
  timestamp = "Dec. 1, 1977",
  heroImageUrl = "https://arc.stimg.co/startribunemedia/4SPNT7DI36ANT2SOB5N5EJAIJU.jpg",
  heroImageCaption = "",
  heroImageAltText = "",
  dek = "Lorem ipsum dolor sit amet consectetur adipiscing elit, fusce sociis at montes vitae tempor enim, venenatis tristique feugiat arcu dis ridiculus.",
  authorName = "Bryan Brussee",
  authorBioUrl = "https://www.startribune.com/bryan-brussee/8455834",
>
```
-->

<script>
  import Grid from "../Grid/Grid.svelte";
  import GridRow from "../Grid/_GridRow.svelte";
  import SectionLabel from "./_SectionLabel.svelte";
  import Headline from "./_Headline.svelte";
  import Timestamp from "./_Timestamp.svelte";
  import Image from "../Image/Image.svelte";
  import Dek from "./_Dek.svelte";
  import Byline from "./_Byline.svelte";

  /** @type {{sectionLabel?: string; headline?: string; timestamp?: string; heroImageUrl?: string; heroImageCaption?: string; heroImageAltText?: string; dek?: string; authorName?: string; authorBioUrl?: string;}} */
  let {
    sectionLabel = "",
    headline = "",
    timestamp = "",
    heroImageUrl = "",
    heroImageCaption = "",
    heroImageAltText = "",
    dek = "",
    authorName = "",
    authorBioUrl = "",
  } = $props();
</script>

<style>
  #mydiv { 
	animation: changeBg 30s infinite;
	width:100vw;
	height:80vh;
	min-height: 800px;
	background-repeat: no-repeat;
	background-size:cover;
  position: relative;
}
@keyframes changeBg { 
   0%,100%  {background-image: url("https://min.merlinone.net/mx/thumbsx3/2026/01/tdir96339/6167_x346_2974_9.jpg");}
   25% {background-image: url("https://min.merlinone.net/mx/thumbsx3/2026/01/tdir96404/6a78_x316_1edd_9.jpg");}
   50% {background-image: url("https://min.merlinone.net/mx/thumbsx3/2026/01/tdir96421/1b01_x087_2216_9.jpg");}
   75% {background-image: url("https://min.merlinone.net/mx/thumbsx3/2026/01/tdir95584/0ca2_x403_1d18_9.jpg");}
}
</style>

<Grid additionalClasses="!max-w-[100vw]">
  <GridRow additionalClasses="!max-w-[100vw]">
    <div id='mydiv'>
      <div class="hero-text">
        <h1>From ‘The Good Life’ to good neighbors: Minnesota’s ICE resistance rebranded the state </h1>
        <h2>How Minneapolis’ response to the immigration crackdown forged a new national identity.</h2>
      </div>
    </div>
  </GridRow>
</Grid>
