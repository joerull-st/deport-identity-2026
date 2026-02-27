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
   0%,100%  {background-image: url("https://arc.stimg.co/startribunemedia/IKKH4ZHCIVBKTNZUXKPSTN2NYY.jpg?w=1000px"); background-position: center;}
   25% {background-image: url("https://arc.stimg.co/startribunemedia/OBR3Q2CGUJHQBOPZRY6KAHR3KQ.JPG?w=1000px"); background-position: center;}
   50% {background-image: url("https://arc.stimg.co/startribunemedia/JB77IPYOERBNRIBQWMFQFP7LCQ.JPG?w=1000px"); background-position: center;}
   75% {background-image: url("https://arc.stimg.co/startribunemedia/UIPH37G65BEAPJKQDAEGQWKCP4.JPG?w=1000px"); background-position: center;}
}

.byline-holder {
  font-family: graphik-regular;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-size:11px;
  background: 	rgb(102, 102, 102, 0.5);
  margin-left: auto;
  padding: 3px 6px;
  text-align: right;
display: inline-block;
position: absolute;
right: 0px;
bottom: 0px;
color: #f2f2f2;
}


.bylineanimated:before {
  content: "ALEX KORMANN";
  animation: topToBottom 24s infinite 0s;
}

@keyframes topToBottom {
  0%,100% {
    content: "ALEX KORMANN, The Minnesota Star Tribune";
  }
  25% {
    content: "ALEX KORMANN, The Minnesota Star Tribune";
  }
  50% {
    content: "RICHARD TSONG-TAATARII, The Minnesota Star Tribune";
  }
  75% {
    content: "RICHARD TSONG-TAATARII, The Minnesota Star Tribune";
  }
}
</style>

<Grid>
  <GridRow variant="fullBleed" additionalClasses="block">
    <div class="bg-[#0d0d0d] hero-text md:h-[50vw] md:min-h-[450px]  md:float-left xs:float-none xs:block md:pl-7 md:w-[440px] xs:w-[100vw]  !text-white">
      <div class=" md:absolute md:bottom-[25px] md:max-w-[385px] md:pt-0 md:pb-0 xs:pt-8 xs:pb-6 xs:max-w-[370px] xs:mx-auto !text-white">
      <p class="text-right !text-white font-editorial-news-heading-01 text-[3.25rem] text-text-primary pb-2 md:text-left xs:text-center ">From ‘The Good Life’ to good neighbors</p>
      <!-- <p class="!text-white font-editorial-non-news-heading-05 pt-2 md:font-editorial-non-news-heading-04 text-[1.45rem] md:max-w-[340px] text-text-primary md:text-left xs:text-center xs:pb-4">How Minneapolis’ response to the immigration crackdown forged a new national identity.</p></div> -->
    </div>
    <div id='slider' class="md:h-[50vw] md:max-h-[50vw] md:min-h-[450px] md:w-[calc(100vw-440px)] md:max-w-[1360px] md:left-[calc(440px-1.75rem)] xs:left-[0px] xs:max-h-[600px] xs:h-[50vh] xs:w-[100vw] xs:left-[0px]">
      <div class="byline-holder">
        <span class="bylineanimated"> </span>
      </div>
    </div>

  </GridRow>
</Grid>
