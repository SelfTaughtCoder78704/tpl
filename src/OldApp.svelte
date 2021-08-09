<script>
  import Actions from "./thesis-pattern-library/OldActions.svelte";

  import "../node_modules/@glidejs/glide/dist/css/glide.core.min.css";
  import TitleBlock from "./thesis-pattern-library/TitleBlock.svelte";
  import CtaBlock from "./thesis-pattern-library/CtaBlock.svelte";
import ListBlock from "./thesis-pattern-library/ListBlock.svelte";

  let secIndex = 0;

  function makeIndex() {
    let indexToReturn = secIndex;
    secIndex++;
    return indexToReturn;
  }
</script>

<main>
  <div>
    <TitleBlock
      title="THIS IS A TITLE BLOCK"
      kicker="This is the kicker"
      subTitle="This is the sub title"
      finePrint="This is the title's fine print"
      classes="orangeBg"
      id="title-block-1"
    />
  </div>
 <div>
  <ListBlock 
  classes="list-block--light"
  items={[
    {
      text: "This is a list item",
      icon: "https://picsum.photos/id/46/900"
    },
    {
      text: "This is another list item",
      icon: "https://picsum.photos/id/46/900"
    },
  ]}
  />
 </div>
  <div>
    <CtaBlock
      classes="cta-block--light"
      id="cta-block-1"
      ctaLink="#"
      ctaText="This is a call to action"
      trackable="true"
      interaction="click"
      ctaRel="nofollow"
      ctaFinePrint="This is the fine print"
    />
  </div>
  <div>
    <div>
      <Actions
        actionIsCarousel={false}
        titleFinePrint="Title Fine Print"
        actionSlideType="slider"
        perView={4}
        arrows={true}
        bullets={true}
        classes="sectionOne"
        section_index={makeIndex()}
        titleBlock={true}
        titleBlockTitle="Action One Title Block"
        titleBlockText="This is section one paragraph stuff."
        id="firstAction"
        actions={[
          {
            index: 0,
            title: "Go to the first page",
            text: "First page",
            clickable: true,
            list: true,
            ctaBlock: true,
            ctaText: "Go to the first page",
            ctaLink: "/bangbang",
            mediaBlock: true,
            isCarousel: true,
            finePrint: "Fine Print",
            listItems: [
              {
                text: "First list item",
                icon: "https://media.istockphoto.com/vectors/flat-icon-check-vector-id496603666?k=6&m=496603666&s=170667a&w=0&h=CdaZL0kvQieOEjq0Vt8gLzlZvVQDKtiqZEx32WDDEYs=",
              },
              {
                text: "Second list item",
                icon: "https://media.istockphoto.com/vectors/flat-icon-check-vector-id496603666?k=6&m=496603666&s=170667a&w=0&h=CdaZL0kvQieOEjq0Vt8gLzlZvVQDKtiqZEx32WDDEYs=",
              },
              {
                text: "Third list item",
                icon: "https://media.istockphoto.com/vectors/flat-icon-check-vector-id496603666?k=6&m=496603666&s=170667a&w=0&h=CdaZL0kvQieOEjq0Vt8gLzlZvVQDKtiqZEx32WDDEYs=",
              },
            ],
            media: [
              {
                src: "https://picsum.photos/id/766/900",
                type: "image",
                imgAlt: "A nice image",
              },
              {
                src: "https://picsum.photos/id/76/900",
                type: "image",
                imgAlt: "A nice image",
              },
              {
                src: "https://picsum.photos/id/9/900",
                type: "image",
                imgAlt: "A nice image",
              },
            ],
          },
          {
            index: 1,
            title: "Go to the second page",
            text: "Second page",
            clickable: true,
            ctaBlock: true,
            ctaText: "Go to the second page",
            ctaLink: "/bangbang",
            mediaBlock: true,
            isCarousel: true,
            media: [
              {
                src: "https://picsum.photos/id/766/900",
                type: "image",
                imgAlt: "A nice image",
              },
              {
                src: "https://picsum.photos/id/76/900",
                type: "image",
                imgAlt: "A nice image",
              },
              {
                src: "https://picsum.photos/id/9/900",
                type: "image",
                imgAlt: "A nice image",
              },
            ],
          },
          {
            index: 2,
            title: "Go to the third page",
            text: "Third page",
            clickable: true,
            ctaLink: "/bangbang",
            mediaBlock: true,
            isCarousel: true,
            media: [
              {
                src: "https://picsum.photos/id/766/900",
                type: "image",
                imgAlt: "A nice image",

                dataIndex: 0,
              },
              {
                src: "https://picsum.photos/id/76/900",
                type: "image",
                imgAlt: "A nice image",

                dataIndex: 1,
              },
              {
                src: "https://picsum.photos/id/9/900",
                type: "image",
                imgAlt: "A nice image",

                dataIndex: 2,
              },
            ],
          },
          {
            index: 3,
            title: "Go to the fourth page",
            text: "Fourth page",
            clickable: true,
            list: true,
            listItems: [
              {
                text: "First list item",
                
              },
              {
                text: "Second list item",
               
              },
              {
                text: "Third list item",
               
              },
            ],
            ctaBlock: true,
            ctaText: "Go to the fourth page",
            ctaLink: "/bangbang",
            mediaBlock: true,
            isCarousel: true,
            finePrint: "Fine Print",
            media: [
              {
                src: "https://picsum.photos/id/766/900",
                type: "image",
                imgAlt: "A nice image",
              },
              {
                src: "https://picsum.photos/id/76/900",
                type: "image",
                imgAlt: "A nice image",
              },
              {
                src: "https://picsum.photos/id/9/900",
                type: "image",
                imgAlt: "A nice image",
              },
            ],
          },
        ]}
      />
    </div>
    <div>
      <Actions
        actionIsCarousel={true}
        titleFinePrint="Title Fine Print"
        actionSlideType="slider"
        focusAt={0}
        arrows={true}
        bullets={true}
        classes="sectionTwo"
        section_index={makeIndex()}
        titleBlock={true}
        titleBlockTitle="Action Two Title Block"
        perView={3}
        titleBlockText="This is section two paragraph stuff."
        id="secondAction"
        actions={[
          {
            index: 0,
            title: "Go to the first page",
            text: "First page",
            clickable: true,
            list: true,
            ctaBlock: true,
            ctaText: "Go to the first page",
            ctaLink: "/bangbang",
            mediaBlock: true,
            isCarousel: false,
            finePrint: "Fine Print",
            media: [
              {
                src: "https://picsum.photos/id/23/900",
                type: "image",
                imgAlt: "A nice image",
              },
            ],
          },
          {
            index: 1,
            title: "Go to the second page",
            text: "Second page",
            clickable: true,
            list: true,
            ctaBlock: true,
            ctaText: "Go to the second page",
            ctaLink: "/bangbang",
            mediaBlock: true,
            isCarousel: false,
            finePrint: "Fine Print",
            media: [
              {
                src: "https://picsum.photos/id/34/900",
                type: "image",
                imgAlt: "A nice image",
              },
            ],
          },
          {
            index: 2,
            title: "Go to the third page",
            text: "Third page",
            clickable: true,
            list: true,
            ctaBlock: true,
            ctaText: "Go to the third page",
            ctaLink: "/bangbang",
            mediaBlock: true,
            isCarousel: false,
            finePrint: "Fine Print",
            media: [
              {
                src: "https://picsum.photos/id/84/900",
                type: "image",
                imgAlt: "A nice image",
              },
            ],
          },
          {
            index: 3,
            title: "Go to the fourth page",
            text: "Fourth page",
            clickable: true,
            list: true,
            ctaBlock: true,
            ctaText: "Go to the fourth page",
            ctaLink: "/bangbang",
            mediaBlock: true,
            isCarousel: false,
            finePrint: "Fine Print",
            media: [
              {
                src: "https://picsum.photos/id/84/900",
                type: "image",
                imgAlt: "A nice image",
              },
            ],
          },
        ]}
      />
    </div>
  </div>
</main>

<style>
  main {
    width: 100%;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(100%, auto));
  }

  main div {
    border: 1px solid rgb(69, 67, 67);
    padding: 20px 10px;
  }
</style>
