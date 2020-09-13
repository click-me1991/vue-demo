<template>
  <div class="page">
    <SubjectDistribution></SubjectDistribution>
    <AwardStatistics></AwardStatistics>
    <SchoolDistribution></SchoolDistribution>
    <StandardChinese></StandardChinese>
  </div>
</template>

<script>
import SubjectDistribution from "../components/subjectDistribution";
import AwardStatistics from "../components/awardStatistics";
import SchoolDistribution from "../components/schoolDistribution";
import StandardChinese from "../components/standardChinese";
export default {
  name: "About",
  components: {
    SubjectDistribution,
    AwardStatistics,
    SchoolDistribution,
    StandardChinese
  }
};
</script>

<style></style>
