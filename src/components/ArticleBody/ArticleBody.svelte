<!-- 
@component
### ArticleBody component
This is a general workspace illustrating what an article body might look like if you use only the components included in this template.  
ArticleBody doesn't accept any props. All contents will need to be hand-placed by a designer directly inside this component.  
In this example, Grid and GridRow help establish the width of the article body's contents. 
Documentation included with those components and accessed by VSCode tooltip explains each component in greater detail.

#### State in this component
- innerWidth: int - pixel width of the viewport.
- isMobile: boolean - derived from innerWidth, true if less than 768 pixels
- isTablet: boolean - derived from innerWidth, true if between 768 pixels inclusive and 1160 pixels exclusive
- isDesktop: boolean - derived from innerWidth, true if greater than 1160 pixels inclusive

#### Using state in this component
You can use any of the three derived states to render different variants of a GridRow component reactively.
The following example uses a ternary to render an image edge-to-edge on mobile but inline otherwise.

#### Example
```svelte
  <GridRow
    variant={isMobile ? "fullBleed" : "inline"}
  >
    <Image
      src="https://arc.stimg.co/startribunemedia/4SPNT7DI36ANT2SOB5N5EJAIJU.jpg"
      alt="Descriptive alt text"
      caption="Caption tk tk tk"
    />
  </GridRow>
```
-->

<script>
  import Grid from "../Grid/Grid.svelte";
  import GridRow from "../Grid/_GridRow.svelte";
  import Subhead from "./_Subhead.svelte";
  import Paragraph from "./_Paragraph.svelte";
  import Dropcap from "./_Dropcap.svelte";
  import Image from "../Image/Image.svelte";
  import Gallery from "../Image/Gallery.svelte";
  import ScrollySection from "../Scrolly/ScrollySection.svelte";
  import JWPlayer from "../Video/JWPlayer.svelte";

  let innerWidth = $state(0);
  let isMobile = $derived(innerWidth < 768);
  let isTablet = $derived(innerWidth >= 768 && innerWidth < 1160);
  let isDesktop = $derived(innerWidth >= 1160);
</script>

<svelte:window bind:innerWidth />
<Grid additionalClasses={"pt-4 pb-8"}>
<GridRow variant={"inline"}>
    <p class="!font-publico-headline-roman font-regular leading-heading-extra-tight text-[1.75rem] md:max-w-[420px] xs:max-w-[430px] text-text-primary md:text-left xs:text-left xs:pb-4 pt-4">How Minneapolis' ICE resistance forged a new identity for the state.</p>
    <div class="rt-Box flex items-center w-full gap-x-2 mb-2">
      <p class="rt-Text !text-[.875rem] !font-[graphik-semibold] text-text-primary relative">By <a href="https://www.startribune.com/author/rachel-hutton/6370540">Rachel Hutton</a></p>
    </div>
  <span class="rt-Text text-text-secondary font-utility-label-reg-02 mb-1 !text-[.875rem]">The Minnesota Star Tribune</span>
  <span class="!text-[#666666]  !text-[.75rem] tracking-[1px] rt-Text font-utility-label-reg-caps-03 text-text-secondary mb-8">March 2, 2026</span>
  </GridRow>


  <GridRow variant={"inline"} additionalClasses={"gap-y-5 pt-8"}>
    <Paragraph>
      <Dropcap dropCapLines={4}>A</Dropcap>s the federal government’s immigration crackdown recedes, Minnesotans remain divided by agents’ aggressive tactics, with <a href="https://www.startribune.com/poll-trumps-immigration-crackdown-deeply-unpopular-in-minnesota/601579330" target="_blank" rel="" title="https://www.startribune.com/poll-trumps-immigration-crackdown-deeply-unpopular-in-minnesota/601579330" data-mrf-link="https://www.startribune.com/poll-trumps-immigration-crackdown-deeply-unpopular-in-minnesota/601579330" cmp-ltrk="Article Links" cmp-ltrk-idx="0" mrfobservableid="16a3df96-8bd3-480c-9e60-a2b05ee9c62d">two-thirds believing</a> they’ve gone too far. 
    </Paragraph>

    
    <Paragraph>
    But residents’ collective response to the surge — “One of the greatest mass displays of neighborly love that I’ve seen in my lifetime,” as an <a href="https://www.theatlantic.com/family/2026/01/ice-minnesota-neighbor/685827/" target="_blank" rel="" title="https://www.theatlantic.com/family/2026/01/ice-minnesota-neighbor/685827/" data-mrf-link="https://www.theatlantic.com/family/2026/01/ice-minnesota-neighbor/685827/" cmp-ltrk="Article Links" cmp-ltrk-idx="1" mrfobservableid="d14edade-c573-496b-98f6-abe843e451ff">Atlantic writer described it </a>— has ricocheted across the internet, captivated the country’s attention and given the state a new identity.
    </Paragraph>

    <Paragraph>
      On social media, people started calling Minneapolis the “City of Freedom” and saying “to Minnesotan” should be a verb. “I’m a Black man from Charlotte and you guys are the ‘Americans’ they tell us about in the history books,” a commenter wrote on Minneapolis Reddit. 
      </Paragraph>
  </GridRow>
  







  <GridRow variant={"fullBleed"} additionalClasses={"!max-w-6xl gap-y-5 pt-12"}>
    <img alt="" data-chromatic="ignore" data-testid="InLineImage" loading="lazy" width="0" height="0" decoding="async" data-nimg="1" class="object-cover h-auto w-full" src="https://arc.stimg.co/startribunemedia/FTL5RYNNYBF7DABMNGMAMC2CVM.JPG?&amp;w=1080" style="color: transparent;">
    <div class="photo-cap">Clergy and community members came together on Jan. 23 outside Minneapolis-St. Paul International Airport in protest over connections among the airport, Delta Air Lines and ICE’s enforcement actions. About 100 clergy leaders were detained by airport police.<div class="attrib"><span style="white-space: nowrap;">Elizabeth Flores/The Minnesota Star Tribune</span></div></div>
  </GridRow>





  <GridRow variant={"inline"} additionalClasses={"gap-y-5 pt-8"}>
    <Paragraph>
    Many Americans once considered Mill City a mere blip on the radar in flyover country, or the site of a 2020 racial reckoning that set the city ablaze. 
    </Paragraph>
    
    <Paragraph>
    Then Operation Metro Surge went viral, with a flood of stories and images showing heavily armed agents questioning people based on their appearance and accent, using excessive force, detaining U.S. citizens and fatally shooting two of them, Renee Good and Alex Pretti. 
    </Paragraph>
    
    <Paragraph>
    Department of Homeland Security leadership repeatedly criticized antagonists and observers for impeding federal immigration enforcement, and some Trump administration supporters blamed Good and Pretti for their own deaths. While protesters heckled the federal officers and some threw snowballs and even a few punches, most civilians simply filmed them with phones. 
    </Paragraph>
    
    <Paragraph>
    Through social and traditional media, people around the world saw Minneapolis shrouded in tear gas, as if under siege. But they also saw a little city that could, where everyday folk stand up for one another.
    </Paragraph>
    
    <Paragraph>
    Minnesotans marched by the tens of thousands in below-zero temps, carrying a giant copy of the Constitution. Networks of neighbors came to immigrants’ aid: blowing whistles, patrolling schools, donating food and giving rides.
    </Paragraph>
  </GridRow>





  <GridRow variant={"fullBleed"} additionalClasses={"!max-w-6xl gap-y-5 pt-8"}>
  <div class="col-span-full w-screen relative left-1/2 -translate-x-1/2 max-w-[2000px] ">
    <div class="md:max-w-6xl mt-8 mb-8 mx-auto px-2">
      <div class="md:max-w-6xl mt-2 mb-0 mx-auto px-0">
        <img class="block mb-2" src="https://arc.stimg.co/startribunemedia/PCUWLTGN25E25IFTTAAVQR7VQE.jpg?&amp;w=1080" alt="photo">
      </div>
      <div class="md:flex">
        <div class="mr-0 lg:w-1/2 md:w-full xs:w-full md:mr-2 xs:mr-0 xs:mb-2 md:mb-0">
          <div class="bg-no-repeat bg-cover bg-center xl:h-[28rem] lg:h-[28rem] md:h-[28rem] mb-0  xs:h-[20rem]" style="background-image: url('https://arc.stimg.co/startribunemedia/KIVM3N65TRGRHF5ODNN5VVUX2E.jpg?&amp;w=1080');">
          </div>
        </div>
        <div class="md:ml-0 lg:w-1/2 md:w-full xs:w-full xs:ml-0">
          <div class="bg-no-repeat bg-cover bg-center xl:h-[28rem] lg:h-[28rem] md:h-[28rem] mb-0  xs:h-[20rem]" style="background-image: url('https://arc.stimg.co/startribunemedia/QX4ONHAKRZAOBP43CF43Z3SQWY.jpg?&amp;w=1080');">
          </div>
        </div>
      </div>
      <div class="photo-cap">Protest came in many forms, from signing an art installation modeled after the U.S. Constitution to filming the activities of federal immigration agents. Alongside marches and rallies were efforts — such as donating and delivering food — to help those unable to leave their homes for fear of being arrested.<div class="attrib"><span style="color: #666;">Alex Kormann and Richard Tsong-Taatarii/The Minnesota Star Tribune</span></div>    </div>
  </div>
  </GridRow>










    <GridRow variant={"inline"} additionalClasses={"gap-y-5 pt-8"}>  
    <Paragraph>
    Celebrities lent their influence, roasting Immigration and Customs Enforcement agents in Grammys speeches and late-night bits. <a href="https://www.startribune.com/bruce-springsteen-streets-of-minneapolis-alex-pretti-renee-good-trump-kristi-noem-tom-morello/601572512" target="_blank" rel="" title="https://www.startribune.com/bruce-springsteen-streets-of-minneapolis-alex-pretti-renee-good-trump-kristi-noem-tom-morello/601572512" data-mrf-link="https://www.startribune.com/bruce-springsteen-streets-of-minneapolis-alex-pretti-renee-good-trump-kristi-noem-tom-morello/601572512" cmp-ltrk="Article Links" cmp-ltrk-idx="2" mrfobservableid="d6f24022-984a-41a5-b9fa-b12f06130d6a">Bruce Springsteen</a> and <a href="https://www.startribune.com/u2-renee-good-minneapolis-bono-larry-mullen-bob-dylan-ed-sheeran-ice-american-obituary-protest-song/601584538" target="_blank" rel="" title="https://www.startribune.com/u2-renee-good-minneapolis-bono-larry-mullen-bob-dylan-ed-sheeran-ice-american-obituary-protest-song/601584538" data-mrf-link="https://www.startribune.com/u2-renee-good-minneapolis-bono-larry-mullen-bob-dylan-ed-sheeran-ice-american-obituary-protest-song/601584538" cmp-ltrk="Article Links" cmp-ltrk-idx="3" mrfobservableid="312ee4ee-6b2c-4b75-a7da-13c301bacbc6">U2</a> penned protest songs. The Nation <a href="https://www.thenation.com/article/activism/the-nation-nominates-minneapolis-for-the-nobel-peace-prize/" target="_blank" rel="" title="https://www.thenation.com/article/activism/the-nation-nominates-minneapolis-for-the-nobel-peace-prize/" data-mrf-link="https://www.thenation.com/article/activism/the-nation-nominates-minneapolis-for-the-nobel-peace-prize/" cmp-ltrk="Article Links" cmp-ltrk-idx="4" mrfobservableid="509970f8-8fa7-4a2f-94ef-33610b20cc4a">nominated the city of Minneapolis</a> for the 2026 Nobel Peace Prize.
    </Paragraph>
    
    <Paragraph>
    Former Minneapolis Mayor R.T. Rybak said people from across the country have told him how inspired they’ve been by Minnesotans’ pushback against the feds’ overreach. “These wonderfully crazy people who cut holes in ice to fish in and jump in showed the country what sticking together against bullying looks like,” Rybak said. “A massive power can’t defeat a united people who are caring for more than themselves.”
    </Paragraph>
    
    <Paragraph>
    <Subhead>Kindness, community and creativity</Subhead>
    </Paragraph>
    
    <Paragraph>
    Washington, D.C.-based journalist Michele Norris of MS NOW has an insiders’ and outsiders’ perspective on her hometown, as an alum of Minneapolis’ Washburn High School and the University of Minnesota. 
    </Paragraph>
    
    <Paragraph>
    She said Minnesota is often known by its geography, institutions and pop culture, citing the state’s cold weather and 10,000 lakes; the Mall of America, Target and the Mayo Clinic; Prince, Betty White, and “Fargo.” “It’s a place where people talk a little bit funny and have a strong moral core,” she said. 
    </Paragraph>
  </GridRow>



  <GridRow variant={"fullBleed"} additionalClasses={"!max-w-6xl gap-y-5 pt-8"}>
  <div class="col-span-full w-screen relative left-1/2 -translate-x-1/2 max-w-[1800px] ">
    <div class="col-span-full w-screen relative left-1/2 -translate-x-1/2 max-w-[2000px]">
      <div class="md:!max-w-6xl mt-8 mb-8 mx-auto px-2">
        <div class="md:flex">
          <div class="mr-0 lg:w-1/2 md:w-full xs:w-full md:mr-2 xs:mr-0 xs:mb-2 md:mb-0">
            <div class="bg-no-repeat bg-cover bg-top !aspect-[1.4/1] mb-0 h-auto" style="background-image: url('https://arc.stimg.co/startribunemedia/4MZENQE5CFCD7O7U72L5WVNBGQ.jpg?&amp;w=1080');">
            </div>
          </div>
          <div class="md:ml-0 lg:w-1/2 md:w-full xs:w-full xs:ml-0">
            <div class="bg-no-repeat bg-cover bg-top !aspect-[1.4/1] mb-0 h-auto" style="background-image: url('https://arc.stimg.co/startribunemedia/I7JHQJPTBVAM7BQZ5SF4NQZNDM.jpg?&amp;w=1080');">
            </div>
          </div>
        </div>
        <div class="photo-cap">Community members from all walks of life, such as church groups, came out to protest, bringing their creativity: Lit luminaria spelling out "ICE OUT" were placed on the surface of Lake Nokomis in Minneapolis.<div class="attrib"><span style="white-space: nowrap;">Jerry Holt and Jeff Wheeler/The Minnesota Star Tribune</span></div>
        </div>
      </div>
    </div>
</GridRow>








      <GridRow variant={"inline"} additionalClasses={"gap-y-5 pt-8"}>
    <Paragraph>
    After reporting on the immigration crackdown from Minnesota, Norris described residents’ resistance as much broader than typical protests, more grassroots and freewheeling, “a cocktail of kindness, community and creativity.” It’s encompassed everything from politicians dropping f-bombs to brass bands dropping beats.
    </Paragraph>
    
    <Paragraph>
    Minnesota Nice extended even to presumed adversaries. Two women arrested by ICE in Brooklyn Park <a href="https://www.startribune.com/detained-by-ice-two-women-became-first-responders-during-agents-seizure/601569667" target="_blank" rel="" title="https://www.startribune.com/detained-by-ice-two-women-became-first-responders-during-agents-seizure/601569667" data-mrf-link="https://www.startribune.com/detained-by-ice-two-women-became-first-responders-during-agents-seizure/601569667" cmp-ltrk="Article Links" cmp-ltrk-idx="5" mrfobservableid="4b5440d4-d0ed-4cc4-965f-858e54399f78">provided medical care to an agent</a> who had a seizure while taking them into custody. When Jake Lang, a Jan. 6 rioter known for his racist rhetoric, was surrounded by counter-protesters near Minneapolis City Hall, a Black man helped<a href="https://www.startribune.com/man-reveals-why-he-rescued-right-wing-influencer-jake-lang-from-mob-outside-minneapolis-city-hall/601566873" target="_blank" rel="" title="https://www.startribune.com/man-reveals-why-he-rescued-right-wing-influencer-jake-lang-from-mob-outside-minneapolis-city-hall/601566873" data-mrf-link="https://www.startribune.com/man-reveals-why-he-rescued-right-wing-influencer-jake-lang-from-mob-outside-minneapolis-city-hall/601566873" cmp-ltrk="Article Links" cmp-ltrk-idx="6" mrfobservableid="a75e75ee-e8ec-4e52-92b3-b5ee02a76da4"> lead him out of the crowd.</a> When Lang approached a car and begged for help, the Black women inside gave him a ride. The last thing Renee Good said to immigration agents before one fatally shot her in south Minneapolis was, “That’s fine, dude, I’m not mad at you.”
    </Paragraph>
      </GridRow>









      <GridRow variant={"fullBleed"} additionalClasses={"!max-w-6xl gap-y-5 pt-8"}>
        <div class="col-span-full w-screen relative left-1/2 -translate-x-1/2 max-w-[1800px] ">
          <div class="col-span-full w-screen relative left-1/2 -translate-x-1/2 max-w-[2000px]">
            <div class="md:!max-w-6xl mt-8 mb-8 mx-auto px-2">
              <div class="md:flex">
                <div class="mr-0 lg:w-1/2 md:w-full xs:w-full md:mr-2 xs:mr-0 xs:mb-2 md:mb-0">
                  <div class="bg-no-repeat bg-cover bg-top !aspect-[1.4/1] mb-0 h-auto" style="background-image: url('https://arc.stimg.co/startribunemedia/D4SLNOFAUBC2DFOZYR3K2LBOS4.JPG?&amp;w=1080');">
                  </div>
                </div>
                <div class="md:ml-0 lg:w-1/2 md:w-full xs:w-full xs:ml-0">
                  <div class="bg-no-repeat bg-cover bg-top !aspect-[1.4/1] mb-0 h-auto" style="background-image: url('https://arc.stimg.co/startribunemedia/UUIRKANZFZE5ZP6EWCVJZLAXKY.JPG?&amp;w=1080');">
                  </div>
                </div>
              </div>
              <div class="photo-cap">March Against Minnesota Fraud organizer Jake Lang was escorted away from his own rally by an unidentified man after an altercation with counterprotesters near Minneapolis City Hall. He then asked women in a car for a ride and crawled into the backseat.<div class="attrib"><span style="white-space: nowrap;">Yuki Iwamura/The Associated Press</span></div>
              </div>
            </div>
          </div>
      </GridRow>








    <GridRow variant={"inline"} additionalClasses={"gap-y-5 pt-8"}>
    <Paragraph>
    Both Norris and Rybak cited the sum of so many ordinary acts as the reason for the movement’s impact. That includes neighbors posting up at immigrant-owned businesses or coffee shops and churches providing humanitarian relief. 
    </Paragraph>
    
    <Paragraph>
    The anti-ICE coalition has drawn unlikely advocates, including <a href="https://www.startribune.com/this-suburban-dads-rant-became-touchpoint-of-ice-opposition/601568067" target="_blank" rel="" title="https://www.startribune.com/this-suburban-dads-rant-became-touchpoint-of-ice-opposition/601568067" data-mrf-link="https://www.startribune.com/this-suburban-dads-rant-became-touchpoint-of-ice-opposition/601568067" cmp-ltrk="Article Links" cmp-ltrk-idx="7" mrfobservableid="5c2554fb-fded-4b4a-ba96-89ebdb9a894b">privileged suburban white guys</a> who don’t consider themselves activists, and conservatives disturbed by the operations’ civil rights violations and immense cost. 
    </Paragraph>
    
    <Paragraph>
    Some of the resistance’s most powerful voices were not those of pundits but regular people, including the poignant testimony of Stella Carlson, the lady in the pink coat who filmed the agents who fatally shot Alex Pretti. It wasn’t venture capitalists raising Vegas-casino volumes of cash to pay immigrants’ rent, but <a href="https://www.startribune.com/the-unexpected-resistance-to-ice-in-minnesota-the-soccer-moms-of-signal/601571253" target="_blank" rel="" title="https://www.startribune.com/the-unexpected-resistance-to-ice-in-minnesota-the-soccer-moms-of-signal/601571253" data-mrf-link="https://www.startribune.com/the-unexpected-resistance-to-ice-in-minnesota-the-soccer-moms-of-signal/601571253" cmp-ltrk="Article Links" cmp-ltrk-idx="8" mrfobservableid="23fae88b-fc20-4f03-9d21-7e43b45fcac0">Signal-savvy minivan moms</a>. 
    </Paragraph>
    </GridRow>




      <GridRow variant={"fullBleed"} additionalClasses={"!max-w-6xl gap-y-5 pt-8"}>
        <div class="col-span-full w-screen relative left-1/2 -translate-x-1/2 max-w-[2000px] ">
          <div class="md:max-w-6xl mt-8 mb-8 mx-auto px-2">
            <div class="md:max-w-6xl mt-2 mb-0 mx-auto px-0">
              <img class="block mb-2" src="https://arc.stimg.co/startribunemedia/G5L54YAI5NH5PKKKFVFNULHEBM.jpg?&amp;w=1080" alt="photo">
            </div>
            <div class="md:flex">
              <div class="mr-0 lg:w-1/2 md:w-full xs:w-full md:mr-2 xs:mr-0 xs:mb-2 md:mb-0">
                <div class="bg-no-repeat bg-cover bg-center xl:h-[28rem] lg:h-[28rem] md:h-[28rem] mb-0  xs:h-[20rem]" style="background-image: url('https://arc.stimg.co/startribunemedia/VZP7BCZ4FBA2LDV2H4RE3W26PU.jpg?&amp;w=1080');">
                </div>
              </div>
              <div class="md:ml-0 lg:w-1/2 md:w-full xs:w-full xs:ml-0">
                <div class="bg-no-repeat bg-cover bg-center xl:h-[28rem] lg:h-[28rem] md:h-[28rem] mb-0  xs:h-[20rem]" style="background-image: url('https://arc.stimg.co/startribunemedia/JYCVYCY2ZJFRNCMUL5AR6NEFLM.jpg?&amp;w=1080');">
                </div>
              </div>
            </div>
            <div class="photo-cap" style="max-width:660px !important;">Protesters took to the streets in downtown Willmar, Minn., a day after a 19-year-old Somali woman was taken by ICE agents, and in North St. Paul, where high school students staged a walkout.<div class="attrib"><span style="color: #666;">Richard Tsong-Taatarii and Anthony Souffle/The Minnesota Star Tribune</span></div></div>
        </div>
        </GridRow>







      <GridRow variant={"inline"} additionalClasses={"gap-y-5 pt-8"}>
    <Paragraph>
    Some forms of protest have been quirky and lighthearted, even: people in fanciful costumes describing themselves as Inflatable Unicorns United Against Fascism, a “rebel loon” logo, anti-ICE art sleds, quilts and crocheted blankets, even kids coloring sheets of an ICE agent falling on his can. There have been <a href="https://www.startribune.com/popping-up-by-the-hour-bike-rides-to-honor-alex-pretti-going-global/601572511" target="_blank" rel="" title="https://www.startribune.com/popping-up-by-the-hour-bike-rides-to-honor-alex-pretti-going-global/601572511" data-mrf-link="https://www.startribune.com/popping-up-by-the-hour-bike-rides-to-honor-alex-pretti-going-global/601572511" cmp-ltrk="Article Links" cmp-ltrk-idx="9" mrfobservableid="d1968fb0-ca1a-4df9-a79c-53d819f3a8fd">bicycle pelotons</a>, tossed sex toys, jingle dances and a <a href="https://www.startribune.com/minnesotas-singing-resistance-seeks-to-heal-through-love/601582250" target="_blank" rel="" title="https://www.startribune.com/minnesotas-singing-resistance-seeks-to-heal-through-love/601582250" data-mrf-link="https://www.startribune.com/minnesotas-singing-resistance-seeks-to-heal-through-love/601582250" cmp-ltrk="Article Links" cmp-ltrk-idx="10" mrfobservableid="ab1e9588-2b3a-4fae-a927-a44cd41cf08c">Singing Resistance</a>. “These are incredibly brave people in the cold who also seem to have a great sense of humor,” Rybak remarked.
    </Paragraph>

    <Paragraph>
    Several videos depict Minnesotans as straight-talking and gutsy. There’s the lone security guard at a Northside McDonald’s who prevents immigration agents from breaching the counter. The Somali American Uber driver responding with a joke to agents’ racially motivated request he prove citizenship: “Why the hell would I show random people my ID? You want to steal my identity?”
    </Paragraph>
    
    <Paragraph>
    “For a clinically humble people, this is as close to swagger as we get,” Rybak said of notoriously conflict-avoidant Minnesotans being moved to expletive-filled tirades. “And that’s empowering people from elsewhere.”
    </Paragraph>
    
    <Paragraph>
    <Subhead>Why Minnesota? </Subhead>
    </Paragraph>
    
    <Paragraph>
    Minnesota’s anti-ICE protests have inspired demonstrators in other cities, including Bostonians’ chanting: “We’re not cold, we’re not afraid, Minnesota taught us to be brave!”
    </Paragraph>
    
    <Paragraph>
    Some people in other cities were moved enough to considered moving, including the Black man from Charlotte posting on Reddit.
    </Paragraph>
    </GridRow>



    <GridRow variant={"fullBleed"} additionalClasses={"!max-w-6xl gap-y-5 pt-12 pb-4"}>
    <img alt="" data-chromatic="ignore" data-testid="InLineImage" loading="lazy" width="0" height="0" decoding="async" data-nimg="1" class="object-cover h-auto w-full" src="https://arc.stimg.co/startribunemedia/5JUSWTZKEJH4ZMNO6I5U6TAUX4.JPG?&amp;w=1080" style="color: transparent;">
    <div class="photo-cap">Even subzero temperatures couldn't keep people from exercising their right to protest.<div class="attrib"><span style="white-space: nowrap;">Elizabeth Flores/The Minnesota Star Tribune</span></div></div>
    </GridRow>
    





    <GridRow variant={"inline"} additionalClasses={"gap-y-5 pt-8"}>    
      <Paragraph>
      “Out in -4 degrees standing up for the American ideals. I promise you that MOST of your fellow citizens don’t have that type of heart,” he wrote. “Looking like the most righteous city in our nation at the moment. Never thought I’d say this, but I wouldn’t mind living there.”
      </Paragraph>

    <Paragraph>
    Why did federal agents encounter such robust resistance in the country’s 46<sup>th</sup> largest city, in a state with an <a href="https://www.startribune.com/how-ice-numbers-compare-to-twin-cities-largest-police-forces/601562617" target="_blank" rel="" title="https://www.startribune.com/how-ice-numbers-compare-to-twin-cities-largest-police-forces/601562617" data-mrf-link="https://www.startribune.com/how-ice-numbers-compare-to-twin-cities-largest-police-forces/601562617" cmp-ltrk="Article Links" cmp-ltrk-idx="11" mrfobservableid="921a273f-1122-4978-8d8b-6c7319f1ab5f">estimated 1%</a> of the country’s undocumented immigrants?
    </Paragraph>
    
    <Paragraph>
    Geography has something to do with it. The Twin Cities are a rare urban center that draws from a large rural area, Rybak noted, and people a generation or two off the farm tend to maintain ties to small towns and a know-all-your-neighbors mentality.
    </Paragraph>
    
    <Paragraph>
    Norris pointed to Minnesota’s harsh weather as underpinning a culture of collectivism and mutual aid. A place where strangers will push your car out of a snowbank because someday you’ll return the favor is one that maintains some of the country’s highest voting and volunteering rates. When the “ICE storm” descended, Norris said, pre-existing networks — neighborhood groups, religious communities, school associations, unions, service clubs — sprang into action.
    </Paragraph>
    </GridRow>





<GridRow variant={"fullBleed"} additionalClasses={"!max-w-6xl gap-y-5 pt-12"}>
    <img alt="" data-chromatic="ignore" data-testid="InLineImage" loading="lazy" width="0" height="0" decoding="async" data-nimg="1" class="object-cover h-auto w-full" src="https://arc.stimg.co/startribunemedia/JFYVTJHASJAUXOUUICMTV3QLXY.JPG?&amp;w=1080" style="color: transparent;">
    <div class="photo-cap">Residents’ collective response to Operation Metro Surge has ricocheted across the internet, captivated the country’s attention and given Minnesota a new identity.
      <div class="attrib"><span style="white-space: nowrap;">Alex Kormann/The Minnesota Star Tribune</span></div></div>
    </GridRow>





 
   <GridRow variant={"inline"} additionalClasses={"gap-y-5 pt-8"}>
      <Subhead>From ‘The Good Life’ to good neighbor</Subhead>
<Paragraph>
    Rybak remembers the pride felt statewide, in 1973, when Minnesota’s plaid-shirted governor hoisted a northern pike on the cover of Time to tout the state’s “good life.” The story highlighted Minnesota’s high quality of life, bipartisan cooperation, thriving arts scene and education system, but overlooked its gaping racial disparities. 
    </Paragraph>
    
    <Paragraph>
    The “good life” was certainly not so good for everyone. Norris, who is Black, lived the nuance and complexity of Minnesotans’ views on race. Her parents’ south Minneapolis home had a racial covenant, she said, and after they bought the place, several of their white neighbors moved. And yet the state had harbored mixed-race families when most of the country forbade interracial marriage, and her neighborhood, school and church communities were mostly welcoming and diverse. 
    </Paragraph>
    
    <Paragraph>
    Rybak says a good-neighbor identity offers a more realistic portrayal than Minnesota’s overly glossy “good life” magazine cover. “George Floyd’s murder exposed our imperfections to the world, and it was ugly, but it was the work we had to do,” he said. “The place that showed the power of love over hate was a humbler, but more sincere, Minnesota.” 
    </Paragraph>
    </GridRow>
  </Grid>
    


<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>
<!------------------------------------- sample article elements below ------------------------------>





  
  <!-- <GridRow variant={"inline"} additionalClasses={"gap-y-5 pt-8"} additionalClasses="gap-y-5">
    <Paragraph>
      <Dropcap dropCapLines={3}>L</Dropcap>orem ipsum dolor sit amet consectetur
      adipisicing elit.
      <a href="https://www.startribune.com/" target="_blank" rel="noreferrer"
        >Debitis quas</a
      >, facilis itaque minus totam repudiandae magnam esse asperiores
      temporibus sed laborum nisi ut corporis ab officiis dolorum odio, porro
      eveniet. Quis quaerat tempore adipisci nostrum quia non.</Paragraph
    >

    <Paragraph
      >Voluptate molestiae, perferendis iusto dolor officiis eaque cum quisquam
      quidem, doloremque dicta temporibus fuga ducimus voluptatum excepturi
      ratione laborum ab omnis quibusdam, accusamus vel eum culpa repellendus
      exercitationem. Fugit, consequatur!</Paragraph
    >

    <Paragraph
      >Voluptate molestiae, perferendis iusto dolor officiis eaque cum quisquam
      quidem, doloremque dicta temporibus fuga ducimus voluptatum excepturi
      ratione laborum ab omnis quibusdam, accusamus vel eum culpa repellendus
      exercitationem. Fugit, consequatur!</Paragraph
    >
  </GridRow> -->
<!-- 
  <GridRow variant="fullBleed">
    <Gallery />
  </GridRow>

  <GridRow variant={"fullBleed"}>
    <Image
      variant={"captionCentered"}
      src="https://arc.stimg.co/startribunemedia/4SPNT7DI36ANT2SOB5N5EJAIJU.jpg"
      alt="Descriptive alt text"
      caption="Caption tk tk tk"
    />
  </GridRow>

  <GridRow variant="inline">
    <Paragraph
      >Voluptate molestiae, perferendis iusto dolor officiis eaque cum quisquam
      quidem, doloremque dicta temporibus fuga ducimus voluptatum excepturi
      ratione laborum ab omnis quibusdam, accusamus vel eum culpa repellendus
      exercitationem. Fugit, consequatur!</Paragraph
    >
  </GridRow>

  <GridRow variant={isMobile ? "fullBleed" : "inline"}>
    <Image
      src="https://arc.stimg.co/startribunemedia/4SPNT7DI36ANT2SOB5N5EJAIJU.jpg"
      alt="Descriptive alt text"
      caption="Caption tk tk tk"
    />
  </GridRow>

  <GridRow variant={"fullBleed"}>
    <ScrollySection
      data={[
        {
          step: 0,
          color: "#143D11",
          text: "In response to this card's appearance in the viewport, the background color is now #143D11.",
        },
        {
          step: 1,
          color: "#5E95D6",
          text: "In response to this card's appearance in the viewport, the background color is now #5E95D6.",
        },
        {
          step: 2,
          color: "#CCCCCC",
          text: "In response to this card's appearance in the viewport, the background color is now #CCCCCC.",
        },
        {
          step: 3,
          color: "#B13B5B",
          text: "In response to this card's appearance in the viewport, the background color is now #B13B5B.",
        },
        {
          step: 4,
          color: "#804316",
          text: "In response to this card's appearance in the viewport, the background color is now #804316.",
        },
        {
          step: 5,
          color: "#B28333",
          text: "In response to this card's appearance in the viewport, the background color is now #B28333.",
        },
        {
          step: 6,
          color: "#052949",
          text: "In response to this card's appearance in the viewport, the background color is now #052949.",
        },
      ]}
    />
  </GridRow>

  <GridRow variant="inline" additionalClasses={"gap-y-5"}>
    <Subhead>Subhead</Subhead>

    <Paragraph
      >Quis quaerat tempore adipisci nostrum quia non. Provident, eum! Non quam
      suscipit omnis asperiores cupiditate, a eos, aliquid libero, reprehenderit
      rerum excepturi ex. Eius perferendis rem fugit nostrum eveniet magnam.</Paragraph
    >

    <JWPlayer
      mediaid={"hvh0xHRH"}
      aspectRatio="9:16"
      showOverlay={true}
      loop={false}
    />

    <JWPlayer
      mediaid={"0CljWbDv"}
      aspectRatio="1:1"
      showOverlay={true}
      loop={false}
    />

    <Paragraph
      >Quis quaerat tempore adipisci nostrum quia non. Provident, eum! Non quam
      suscipit omnis asperiores cupiditate, a eos, aliquid libero, reprehenderit
      rerum excepturi ex. Eius perferendis rem fugit nostrum eveniet magnam.</Paragraph
    >

    <Paragraph
      >Quis quaerat tempore adipisci nostrum quia non. Provident, eum! Non quam
      suscipit omnis asperiores cupiditate, a eos, aliquid libero, reprehenderit
      rerum excepturi ex. Eius perferendis rem fugit nostrum eveniet magnam.</Paragraph
    >
  </GridRow>

  <GridRow variant={isMobile ? "fullBleed" : "default"}>
    <Image
      src="https://arc.stimg.co/startribunemedia/4SPNT7DI36ANT2SOB5N5EJAIJU.jpg"
      alt="Descriptive alt text"
      caption="Caption tk tk tk"
    />
  </GridRow>
</Grid> -->

<style>
  a {
    text-decoration-line: underline;
    text-decoration-color: #00854b;
    text-underline-offset: 2px;
  }

  a:hover {
    color: #00854b;
  }

	@font-face {
		font-family:graphik-regular;
		src:url("https://static.startribune.com/fonts/GraphikRegular/Graphik-Regular.woff2") format("woff2");
		font-style:normal;
		font-display:swap;
	}
	p {
		font-family:graphik-regular;
	}

  .photo-cap {
    font-family: graphik-regular;
    font-size: 14px;
    margin: auto;
    text-align: center;
    max-width: 610px;
    padding: 10px 10px 0 10px;
  }

  .photo-cap .attrib {
    padding-top: 10px;
    color: #666; 
  line-height: 120%;
  text-transform: uppercase;
  letter-spacing: .5px;
  font-size:11px;
  max-width: 600px;
  margin: auto;
  }
</style>
