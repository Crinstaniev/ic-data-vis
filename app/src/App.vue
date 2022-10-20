<template>
    <div id="app">
        <ul id="menu">
            <li data-menuanchor="intro"><a href="#intro">Intro</a></li>
            <li data-menuanchor="terminus"><a href="#terminus">Terminus</a></li>
            <li data-menuanchor="chord" class="active"><a href="#chord">Chord Chart</a></li>
            <li data-menuanchor="wordcloud"><a href="#wordcloud">Word Cloud</a></li>
            <li data-menuanchor="network"><a href="#network">Network</a></li>
            <li data-menuanchor="area"><a href="#area">Area Chart</a></li>
        </ul>
        <full-page :options="options" id="fullpage" ref="fullpage">
            <div class="section" id="intro-page">
                <h1>IC On-Chain Governance NNS Visualization</h1>
                <h3>Welcome to the world of blockchain</h3>
                <h3><code>By Xinyu Tian and Zesen Zhuang</code></h3>
            </div>
            <div class="section">
                <iframe src="./pages/terminus.html" frameborder="0"></iframe>
                <h3>Visualization 1: Terminus</h3>
            </div>
            <div class="section">
                <iframe src="./pages/chord.html" frameborder="0"></iframe>
                <h3>Visualization 2: Chord Chart</h3>
            </div>
            <div class="section">
                <iframe src="./pages/wordcloud.html" frameborder="0">
                </iframe>
                <h3>Visualization 3: Word Cloud</h3>
            </div>
            <div class="section">
                <iframe src="./pages/network.html" frameborder="0"></iframe>
                <h3>Visualization 4: Network</h3>
            </div>
            <div class="section">
                <iframe id="areac" src="./pages/topic_area_chart.html" frameborder="0" align="middle"></iframe>
                <h3>Visualization 5: Area Chart</h3>
            </div>
        </full-page>
    </div>
</template>

<script>

// Optional. When using fullpage extensions
// import './fullpage.scrollHorizontally.min'
export default {
    name: 'app',
    components: {

    },
    data() {
        return {
            options: {
                licenseKey: 'YOUR_KEY_HERE',
                afterLoad: this.afterLoad,
                scrollOverflow: true,
                scrollBar: false,
                menu: '#menu',
                navigation: true,
                anchors: ['intro', 'terminus', 'chord', 'wordcloud', 'network', 'area'],
                sectionsColor: ['black', 'black', 'black', 'black', 'black', 'black']
            }
        }
    },
    methods: {

        afterLoad() {
            console.log('After load')
        },

    }
}
</script>

<style>
h1 {
    font-size: 50px;
    color: white;
    margin: 20px;
}

#intro-page {
    display: flex;
    justify-content: center;
    align-items: center;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: inline-block;
    margin: 0 10px;
}

a {
    color: #42b983;
}

h3 {
    font-size: large;
    margin: 20px;
}

iframe {
    width: 100%;
    height: 75vh;
}

#areac {
    margin-left: 15%;
}

/* 
full-page {
    display: flex;
    justify-content: center;
    align-items: center;
} */

#app {
    width: 100%;
    height: 100%;
}
</style>