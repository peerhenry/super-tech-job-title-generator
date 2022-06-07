<script setup lang="ts">
import { ref } from "vue";

function getRandomElement<T>(list: Array<T>): T {
  return list[Math.floor(Math.random() * list.length)];
}

const finalTitleOptions = [
  "Engineer",
  "Architect",
  "Consultant",
  "Expert",
  "Director",
  "Leader",
  "Officer",
  "Analyst",
  "Product Owner",
  "Epic Owner",
  "Head",
  "Agile Coach",
  "Account Manager",
];
const adjectiveOptions = [
  "Support Desk",
  "Digital Business",
  "Domain",
  "Consulting",
  "Devops",
  "Security",
];
const twoPartAdjectiveFirstOptions = [
  "Change",
  "Business",
  "Digital",
  "Domain",
  "Customer",
  "Integration",
  "Corporate",
  "Strategic",
  "Continuous",
  "IT",
  "Security",
  "Consulting",
  "Cloud",
  "Automation",
  "Security",
  "Management",
  "Service Delivery",
];
const twoPartAdjectiveSecondOptions = [
  "Management",
  "Engagement",
  "Success",
  "Solution",
  "Service Delivery",
  "Product Lifecycle",
  "Security",
];
const rankOptions = ["Junior", "Senior", "Experienced", "Expert"];
const prefixOptions = ["Vice", "Assisting", "Chief", "Lead"];

const title = ref("Click generate!");

function generateTwoPartAdjective() {
  const part1 = getRandomElement(twoPartAdjectiveFirstOptions);
  let part2 = part1;
  while (part1 === part2) {
    part2 = getRandomElement(twoPartAdjectiveSecondOptions);
  }
  return `${part1} ${part2}`;
}

function generate() {
  const isManager = Math.random() > 0.8;
  const getsPrefix = Math.random() > 0.5;
  const getsRank = Math.random() > 0.5;
  const makeTwoPartAdjective = Math.random() > 0.5;

  const finalTitle = isManager
    ? "Manager"
    : getRandomElement(finalTitleOptions);

  const adjective = makeTwoPartAdjective
    ? generateTwoPartAdjective()
    : getRandomElement(adjectiveOptions);

  const base =
    finalTitle === "Head"
      ? `Head of ${adjective}`
      : `${adjective} ${finalTitle}`;

  const secondBase = getsPrefix
    ? `${getRandomElement(prefixOptions)} ${base}`
    : base;

  title.value = getsRank
    ? `${getRandomElement(rankOptions)} ${secondBase}`
    : secondBase;
}
</script>

<template lang="pug">
.flex.items-center.justify-center.h-full
  .lg_-mt-16
    button.px-4.py-2.border.border-black.bg-blue.mb-16.font-bold.bg-slate-200.hover_bg-slate-100.text-black(@click="generate") Generate!
    p.text-4xl.font-bold.drop-shadow-2xl.merriweather {{ title }}
</template>

<style>
.merriweather {
  font-family: "Merriweather", serif;
}
</style>
