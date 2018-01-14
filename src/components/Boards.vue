<template>
  <div class="f22-boards">
    <nav-bar></nav-bar>
    <title-section></title-section>
    <div class="card-stack-container">
      <template v-for="stack in board_stacks">
        <board-stack :item="stack"></board-stack>
      </template>
      <div class="add-new-board">
        <img class="add-icon-white" src="../assets/add_icon_white.svg">
        Add a board
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar'
import TitleSection from '@/components/TitleSection'
import BoardStack from '@/components/BoardStack'

export default {
  name: 'Boards',
  components: {
    'nav-bar': Navbar,
    'title-section': TitleSection,
    'board-stack': BoardStack
  },
  created() {
    // Event.$on('add-new-card-to-board', event=>{
    //   for (var i = 0; i<this.board_stacks.length; i++) {
    //     if (this.board_stacks[i].id == event) {
    //       this.board_stacks[i].cards.push({
    //         id: this.board_stacks[i].cards.length+1,
    //         title: "New Card"
    //       });
    //     }
    //   }
    // });
  },
  data () {
    return {
      board_stacks: [
        {
          id: 1,
          name: "Backlog",
          card_count: 8,
          stack_color: "#00aaff",
          cards: [
            {
              id: 1,
              title: "Monetisation (Share revenue with developers)",
              card_color: "#00aaff",
              comments: {
                count: 2
              },
              checks: {
                count: [1,4]
              },
              users: [1,4]
            },
            {
              id: 2,
              title: "Post new Dribble shot and share it on social media",
              thumbnail: 1,
              comments: {
                count: 3
              },
              checks: {
                count: [2,4]
              },
              users: [2,3]
            },
            {
              id: 3,
              title: "New Infographic Designs for Investors"
            },
            {
              id: 4,
              title: "Design a new dashboard for Apple Watch",
              card_color: "#1bb934",
              comments: {
                count: 5
              },
              checks: {
                count: [0,4]
              },
              users: [2]
            },
            {
              id: 5,
              title: "Release new version of landing page designed by Joel",
              card_color: "#ffd400",
              time: "12:00"
            },
            {
              id: 6,
              title: "New Revenue streams, speak with Vladimir about details",
              comments: {
                count: 9
              },
              users: [4,5]
            }
          ]
        },
        {
          id: 2,
          name: "Next Priority",
          card_count: 4,
          stack_color: "#ff7800",
          cards: [
            {
              id: 7,
              title: "Unsplash.com Research, find the best examples for article",
              thumbnail: 2,
              comments: {
                count: 3
              },
              users: [6]
            },
            {
              id: 8,
              title: "New Team Pictures",
              card_color: "#ffd400"
            },
            {
              id: 9,
              title: "Discuss new ideas about new Marketing techniques",
              comments: {
                count: 14
              },
              users: [1]
            },
            {
              id: 10,
              title:"Visual Overview of the Dashboard Prepare UI Kit",
              comments: {
                count: 3
              },
              checks: {
                count: [1,4]
              },
              users: [3,4]
            }
          ]
        },
        {
          id: 3,
          name: "In Progress",
          card_count: 3,
          stack_color: "#1bb934",
          cards: [
            {
              id: 11,
              title: "New Pitch Deck for CEO, based on feedback of X Ventures"
            },
            {
              id: 12,
              title: "Infographic about Water resources in India (+ Pictures)",
              thumbnail: 3,
              comments: {
                count: 3
              },
              checks: {
                count: [2,4]
              }
            },
            {
              id: 13,
              title: "Prepare Q2 Overview of Mixpanel Statistics (Keynote required)",
              card_color: "#00aaff",
              comments: {
                count: 2
              },
              checks: {
                count: [1,4]
              }
            }
          ]
        },
        {
          id: 4,
          name: "QA",
          card_count: 3,
          stack_color: "#6b6b6b",
          cards: [
            {
              id: 14,
              title: "Final version of Travel Website Promo pictures",
              thumbnail: 4,
              comments: {
                count: 8
              },
              checks: {
                count: [3,4]
              },
              users: [1]
            },
            {
              id: 15,
              title: "Release first teaser of Night & Travel UI Kit",
              thumbnail: 5,
              comments: {
                count: 3
              },
              checks: {
                count: [0,4]
              },
              users: [2]
            },
            {
              id: 16,
              title: "Final Prototype before meeting with CEO Jason Stan",
              card_color: "#1bb934",
              time: "15:00"
            }
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>
  .f22-boards {
    padding-top: 70px;
  }
  .card-stack-container {
    display: flex;
    margin: 0 5px;
    padding: 25px 0;
    overflow-x: auto;
  }

  .add-new-board {
    display: flex;
    align-items: center;
    padding-left: 20px;
    margin-top: 35px;
    width: 250px;
    height: 45px;
    background-color: #ccd3da;
    border-radius: 3px;
    color: #fff;
    font-size: 12px;
    font-weight: 600;
    flex: none;

  }

  .add-new-board > img {
    width: 10px;
    height: 10px;
    margin-right: 10px;
  }
</style>