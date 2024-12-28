<template>
  <div class="people-list">
    <PersonCard v-for="person in people" :key="person.id" :person="person" />
  </div>
</template>

<script>
// import { ref, onMounted } from 'vue';
// import axios from 'axios';
import PersonCard from '@/components/PersonCard.vue';
// import { people } from './data.js';

export default {
  components: {
    PersonCard
  },
  // setup() {
  //   const people = ref([]);

  //   // Fetch data when component mounts
  //   onMounted(async () => {
  //     try {
  //       const response = await axios.get('http://your-api-url/people');
  //       people.value = response.data;
  //     } catch (error) {
  //       console.error('Error fetching data:', error);
  //     }
  //   });

  //   return { people };
  // }
  setup() {
    // Stand-in variable with mock data
    const people = [
      { id: 1, name: "David Thomson & Family", photo: "/user-xmark.svg", netWorth: "$69.6 billion", mediaInfluence: "Owners of Thomson Reuters", controversies: "Family disputes over succession" },
      { id: 2, name: "Changpeng Zhao", photo: "/user-xmark.svg", netWorth: "$64.15 billion", mediaInfluence: "Crypto industry leader with Binance", controversies: "Regulatory scrutiny globally" },
      { id: 3, name: "Joseph Tsai", photo: "/user-xmark.svg", netWorth: "$10.12 billion", mediaInfluence: "Owner of Brooklyn Nets", controversies: "Data privacy concerns with Alibaba" },
      { id: 4, name: "David Cheriton", photo: "/user-xmark.svg", netWorth: "$17.07 billion", mediaInfluence: "Early investor in Google", controversies: "Minimal" },
      { id: 5, name: "Tobi Lütke", photo: "/user-xmark.svg", netWorth: "$9.54 billion", mediaInfluence: "Shopify’s impact on e-commerce", controversies: "Hosting controversial merchants" },
      { id: 6, name: "Jim Pattison", photo: "/user-xmark.svg", netWorth: "$8.67 billion", mediaInfluence: "Owns multiple media outlets", controversies: "Criticized for labor practices" },
      { id: 7, name: "Arthur Irving", photo: "/user-xmark.svg", netWorth: "$6.6 billion", mediaInfluence: "Family-owned newspapers in Atlantic Canada", controversies: "Environmental concerns" },
      { id: 8, name: "Galen Weston & Family", photo: "/user-xmark.svg", netWorth: "$9 billion", mediaInfluence: "Retail advertising dominance", controversies: "Bread price-fixing scandal" },
      { id: 9, name: "Garrett Camp", photo: "/user-xmark.svg", netWorth: "$6.5 billion", mediaInfluence: "Co-founder of Uber", controversies: "Uber’s labor practices" },
      { id: 10, name: "Anthony von Mandl", photo: "/user-xmark.svg", netWorth: "$6.56 billion", mediaInfluence: "Lifestyle brands like White Claw", controversies: "Minimal" },
      { id: 11, name: "Bruce Flatt", photo: "/user-xmark.svg", netWorth: "$4 billion", mediaInfluence: "Real estate dominance through Brookfield", controversies: "Investment practices scrutiny" },
      { id: 12, name: "Lawrence Stroll", photo: "/user-xmark.svg", netWorth: "$3.9 billion", mediaInfluence: "Formula 1 team owner", controversies: "Criticized for management decisions" },
      { id: 13, name: "Alain Bouchard", photo: "/user-xmark.svg", netWorth: "$7.31 billion", mediaInfluence: "Couche-Tard’s branding", controversies: "Labor disputes" },
      { id: 14, name: "Chip Wilson", photo: "/user-xmark.svg", netWorth: "$5.9 billion", mediaInfluence: "Lululemon marketing", controversies: "Remarks on product sizing" },
      { id: 15, name: "Emanuele Saputo", photo: "/user-xmark.svg", netWorth: "$5.24 billion", mediaInfluence: "Limited", controversies: "Allegations of past mob connections" },
      { id: 16, name: "James Irving", photo: "/user-xmark.svg", netWorth: "$6.4 billion", mediaInfluence: "Newspapers in New Brunswick", controversies: "Environmental issues" },
      { id: 17, name: "Richardson Family", photo: "/user-xmark.svg", netWorth: "$4.45 billion", mediaInfluence: "Agricultural influence", controversies: "Minimal" },
      { id: 18, name: "Jeffrey Skoll", photo: "/user-xmark.svg", netWorth: "$4.92 billion", mediaInfluence: "Participant Media", controversies: "Limited" },
      { id: 19, name: "Carlo Fidani", photo: "/user-xmark.svg", netWorth: "$4.08 billion", mediaInfluence: "Limited", controversies: "Minimal" },
      { id: 20, name: "Victor Li", photo: "/user-xmark.svg", netWorth: "$10 billion", mediaInfluence: "Indirect through business interests", controversies: "Family disputes" },
      { id: 21, name: "Pierre Karl Péladeau", photo: "/user-xmark.svg", netWorth: "$3.4 billion", mediaInfluence: "CEO of Quebecor, major media conglomerate", controversies: "Political conflicts in Quebec" },
      { id: 22, name: "Fred Mannix & Family", photo: "/user-xmark.svg", netWorth: "$3.2 billion", mediaInfluence: "Indirect through real estate holdings", controversies: "Environmental criticisms" },
      { id: 23, name: "Peter Gilgan", photo: "/user-xmark.svg", netWorth: "$3.9 billion", mediaInfluence: "Indirect through charitable contributions", controversies: "Minimal" },
      { id: 24, name: "Ronald Southern & Family", photo: "/user-xmark.svg", netWorth: "$2.9 billion", mediaInfluence: "Calgary Stampede sponsorships", controversies: "Minimal" },
      { id: 25, name: "Stephen Smith", photo: "/user-xmark.svg", netWorth: "$2.8 billion", mediaInfluence: "Mortgage industry influence", controversies: "Limited" },
      { id: 26, name: "Michael Lee-Chin", photo: "/user-xmark.svg", netWorth: "$2.7 billion", mediaInfluence: "Indirect through philanthropy", controversies: "Investment risks" },
      { id: 27, name: "Daryl Katz", photo: "/user-xmark.svg", netWorth: "$2.9 billion", mediaInfluence: "Edmonton Oilers ownership", controversies: "Urban development disputes" },
      { id: 28, name: "Isadore Sharp", photo: "/user-xmark.svg", netWorth: "$2.5 billion", mediaInfluence: "Four Seasons branding", controversies: "Limited" },
      { id: 29, name: "Barry Zekelman", photo: "/user-xmark.svg", netWorth: "$2.4 billion", mediaInfluence: "Industrial lobbying", controversies: "Tariff debates" },
      { id: 30, name: "Jim Balsillie", photo: "/user-xmark.svg", netWorth: "$2.2 billion", mediaInfluence: "BlackBerry legacy", controversies: "Intellectual property disputes" },
      { id: 31, name: "Mitchell Goldhar", photo: "/user-xmark.svg", netWorth: "$2 billion", mediaInfluence: "Shopping center influence", controversies: "Development disputes" },
      { id: 32, name: "Prem Watsa", photo: "/user-xmark.svg", netWorth: "$1.9 billion", mediaInfluence: "Fairfax Financial", controversies: "Limited" },
      { id: 33, name: "Frank Giustra", photo: "/user-xmark.svg", netWorth: "$1.8 billion", mediaInfluence: "Film and gold mining industries", controversies: "Political donations" },
      { id: 34, name: "John Risley", photo: "/user-xmark.svg", netWorth: "$1.7 billion", mediaInfluence: "Fisheries industry", controversies: "Environmental issues" },
      { id: 35, name: "Murray Edwards", photo: "/user-xmark.svg", netWorth: "$1.6 billion", mediaInfluence: "Oil sands lobbying", controversies: "Environmental concerns" },
      { id: 36, name: "W. Brett Wilson", photo: "/user-xmark.svg", netWorth: "$1.5 billion", mediaInfluence: "TV and philanthropy", controversies: "Controversial comments" },
      { id: 37, name: "Aldo Bensadoun", photo: "/user-xmark.svg", netWorth: "$1.4 billion", mediaInfluence: "Fashion retail", controversies: "Labor practices" },
      { id: 38, name: "Sandra and Joe Rotman", photo: "/user-xmark.svg", netWorth: "$1.3 billion", mediaInfluence: "Philanthropy", controversies: "Minimal" },
      { id: 39, name: "David Azrieli", photo: "/user-xmark.svg", netWorth: "$1.2 billion", mediaInfluence: "Architecture", controversies: "Minimal" },
      { id: 40, name: "Kevin O’Leary", photo: "/user-xmark.svg", netWorth: "$1.1 billion", mediaInfluence: "Shark Tank and personal brand", controversies: "Investment schemes" },
      { id: 41, name: "Daniel Lamarre", photo: "/user-xmark.svg", netWorth: "$1 billion", mediaInfluence: "Cirque du Soleil", controversies: "Labor disputes" },
      { id: 42, name: "Paul Desmarais Jr.", photo: "/user-xmark.svg", netWorth: "$1 billion", mediaInfluence: "Power Corporation", controversies: "Political connections" },
      { id: 43, name: "Marcel Adams", photo: "/user-xmark.svg", netWorth: "$900 million", mediaInfluence: "Real estate", controversies: "Minimal" },
      { id: 44, name: "Tim Hortons Founders' Families", photo: "/user-xmark.svg", netWorth: "$850 million", mediaInfluence: "National advertising", controversies: "Franchise disputes" },
      { id: 45, name: "Patrick Dovigi", photo: "/user-xmark.svg", netWorth: "$800 million", mediaInfluence: "Waste management innovation", controversies: "Minimal" },
      { id: 46, name: "Graham Weston", photo: "/user-xmark.svg", netWorth: "$750 million", mediaInfluence: "Tech startups", controversies: "Limited" },
      { id: 47, name: "Donald Sobey", photo: "/user-xmark.svg", netWorth: "$700 million", mediaInfluence: "Empire Company Limited", controversies: "Labor disputes" },
      { id: 48, name: "Iain Scott", photo: "/user-xmark.svg", netWorth: "$600 million", mediaInfluence: "Limited", controversies: "Minimal" },
      { id: 49, name: "Brent Belzberg", photo: "/user-xmark.svg", netWorth: "$500 million", mediaInfluence: "Private equity", controversies: "Limited" },
      { id: 50, name: "Heather Reisman", photo: "/user-xmark.svg", netWorth: "$450 million", mediaInfluence: "Indigo Books", controversies: "Criticism for industry consolidation" },
    ];


    return { people };
  }
}
</script>

<style scoped>
.people-list {
  padding: 20px;
}
</style>
