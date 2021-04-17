<template>
  <section>
    <!-- Button outside of grid -->
    <button id="toggleBtn" @click="changeView">
      Toggle View
    </button>
    <article id="viewType">
      <!-- forIn loop to create list/grid, Loops include outer html when running -->
      <div class="listView" v-for="tweetInfo in tweets" :key="tweetInfo.id">
        {{ tweetInfo.tweet }}
        <div class="infoGrid">
          <p class="createdBy">
            <span class="byOn">By:</span> {{ tweetInfo.username }}
          </p>
          <p class="createdOn">
            <span class="byOn">On:</span> {{ tweetInfo.created_at }}
          </p>
        </div>
      </div>
    </article>
  </section>
</template>

<script>
export default {
  // functions go inside methods.
  methods: {
    // function to get element with ID "viewType" and toggle class, used in the @click event above
    changeView() {
      document.getElementById("viewType").classList.toggle("gridView");
    },
  },

  name: "user-tweets",
  data() {
    return {
      tweets: [
        {
          tweet: `Getting older. I used to be able to run a 4-minute mile, bench press 380 pounds, and tell the truth.`,
          username: `@ConanOBrien`,
          created_at: `10-25-2020`,
          id: 1,
        },

        {
          tweet: `Women get to smell like real things (vanilla, lavender) but men have to smell like concepts. What the fuck is "cool sport rush"`,
          username: `@ronnui_`,
          created_at: `08-15-2020`,
          id: 2,
        },

        {
          tweet: `Me: i have a headache WebMD: and it’ll be your last`,
          username: `@YRN_Jay15`,
          created_at: `12-16-2020`,
          id: 3,
        },

        {
          tweet: `Feel bad for the person who has to type all those words so fast every time I turn on subtitles`,
          username: `@Sonny5ideUp`,
          created_at: `05-14-2019`,
          id: 4,
        },

        {
          tweet: `prounounces molecules like hercules`,
          username: `@notviking`,
          created_at: `04-02-2019`,
          id: 5,
        },

        {
          tweet: `To the guy who stole my antidepressants, I hope you're happy now.`,
          username: `@EddyElfenbein`,
          created_at: `07-29-2018`,
          id: 6,
        },

        {
          tweet: `Why don't crabs give to charity? Because they're shellfish. #dadjokes`,
          username: `@DaddyPoppinsBlg`,
          created_at: `04-20-2017`,
          id: 7,
        },

        {
          tweet: `I was addicted to the hokey pokey... But, I turned myself around.`,
          username: `@RedShiningStar`,
          created_at: `04-21-2017`,
          id: 8,
        },

        {
          tweet: `Do they allow loud laughing in Hawaii, or just a low ha?`,
          username: `@trawwithtweets`,
          created_at: `11-15-2020`,
          id: 9,
        },

        {
          tweet: `Millenials. Walking around like they rent the place.`,
          username: `@SpenceDen`,
          created_at: `01-03-2018`,
          id: 10,
        },
      ],
    };
  },
};
</script>

<style scoped>
section {
  display: grid;
  place-items: center;
  margin: 10px;
}
button {
  padding: 10px 20px;
  background: #8f90a6;
  border: 0;
}

button:hover {
  background: #9798a7;
  cursor: pointer;
}

article {
  display: grid;
  place-items: center;
}

.listView {
  display: grid;
  place-items: center;
  background-color: #28293d;
  color: #8f90a6;
  padding: 10px;
  margin: 10px 0;
  border-radius: 5px;
  width: 80%;
}

.gridView {
  display: grid;
  place-items: center;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  margin-top: 10px;
}

.gridItem {
  display: grid;
  background-color: #28293d;
  color: #8f90a6;
  border-radius: 5px;
  padding: 10px;
  margin: 10px 0;
  height: 100%;
  width: 100%;
}

.gridItem > .infoGrid {
  place-self: end center;
}

.byOn {
  font-weight: bold;
  color: #8f90a6;
}

.infoGrid {
  display: grid;
  grid-auto-flow: column;
  width: 100%;
  margin-bottom: 0;
  padding-bottom: 0;
}

.createdBy {
  place-self: center start;
}

.createdOn {
  place-self: center end;
}
</style>
