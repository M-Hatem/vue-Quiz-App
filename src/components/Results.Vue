<template>
    <div class="result">
        <div class="title">{{ results[calcResult].title }}</div>
        <div class="desc">{{ results[calcResult].desc }}</div>
    </div>
</template>

<script>
export default {
    name: "Results",
    props: ["results", "totalCorrect"],
    computed: {
        calcResult() {
            let index = 0;
            this.results.forEach((e, i) => {
                if (e.min <= this.totalCorrect && e.max >= this.totalCorrect)
                    index = i;
            });
            return index;
        },
    },
};
</script>
