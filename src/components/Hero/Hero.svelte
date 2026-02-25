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
  #slider { 
	animation: changeBg 24s infinite;
	background-repeat: no-repeat;
	background-size:cover;
  position: relative;
}
@keyframes changeBg { 
   0%,100%  {background-image: url("https://min.merlinone.net/mx/thumbsx3/2026/01/tdir96339/6167_x346_2974_9.jpg"); background-position: center;}
   25% {background-image: url("https://min.merlinone.net/mx/thumbsx3/2026/01/tdir96404/6a78_x316_1edd_9.jpg"); background-position: center;}
   50% {background-image: url("https://min.merlinone.net/mx/thumbsx3/2026/01/tdir96421/1b01_x087_2216_9.jpg"); background-position: center;}
   75% {background-image: url("https://min.merlinone.net/mx/thumbsx3/2026/01/tdir95584/0ca2_x403_1d18_9.jpg"); background-position: center;}
}
</style>

<Grid>
  <GridRow variant="fullBleed">
    <div class="bg-[#bdcfee] hero-text md:h-[50vw] md:min-h-[450px]  md:float-left xs:float-none xs:block px-4 md:w-[385px] xs:w-[100%]  !text-white">
      <div class="md:absolute bottom-[40px] max-w-[360px] !text-white">
      <Headline>From ‘The Good Life’<br>to good neighbors:<br>Minnesota’s resistance to ICE rebranded the state </Headline>
      <Dek>How Minneapolis’ response to the immigration crackdown forged a new national identity.</Dek></div>
    </div>
    <div id='slider' class="md:h-[50vw] md:max-h-[50vw] md:min-h-[450px] md:w-[calc(100vw-385px)] md:left-[385px] xs:max-h-[600px] xs:h-[50vh] xs:w-[100vw] xs:block">

    </div>
  </GridRow>
</Grid>
