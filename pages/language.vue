<template lang="pug">
  main
    section.whatcanteach
      .whatcanteachContainer
        h2.whatcanteachTitle 
          p 具体的には
          p こんなことを教えられます。
          .corner
          .corner
        ul.languagesWrapper
          li.language(
            v-for="(description, languageName, languageIndex) in languages" :key="`language${languageIndex}`"
          )
            p.languageName {{ languageName }}
            p.description(v-html="description")
</template>

<script>
import { gsap } from 'gsap'
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
import { TimelineMax } from 'gsap'
export default {
  data() {
    return {
      languages: {
        'JavaScript': 'メニューの開閉や、スクロール時のアニメーションの管理、日付の表示などHTMLやCSSでは難しかったり、出来ない処理を行うことができるのがJavascriptです。近年では3DCGの生成や音楽の処理などもできるようになり、かなり進化しています。ほとんどのサイトで使用されています。（jQueryを教えることも可能です）',
        'Vue.js / Nuxt.js': 'JavaScriptを効率良く書く為のフレームワークの１つです。フロントエンド開発においてはReact.jsというもう１つの人気フレームワークと並んで良く使われるものになっています。Reactは任天堂がNintendo Switchの実装に使ったことでも有名です。',
        'Sass': 'Sass・Scss / Less / Stylus これらの言語はCSSを効率良く書くことができる言語です。最近の開発現場ではCSSをそのまま書くよりもSassが使われることの方が多いです。変数やmixinや条件分岐など、CSSよりもプログラミング言語としての記述ができるので、CSSで書くコード量の半分くらいになることもあります。Sass / Scss / Less / Stylus はそれぞれお教えすることができます。',
        'HTML / CSS': '初心者はまずこの言語から！ホームページ・ウェブサイトを作る上で「必須」の言語です。HTMLは文章を表示したり、その文章に「見出し」などの意味づけをします。もちろんこのページにもHTMLが使われています。CSSはHTMLで表示したものに対して、色や位置やアニメーションを指定することによってデザインをしたり、動きをつけたりする言語です興味のある方にはCSSを使ったダイナミックなアニメーションを教えることも出来ます。',
        'SEO / Webマーケティング': 'サイトの売り上げや集客に直結してくるのが、SEO（Search Engine Optimization）です。具体的にはGoogleなどの検索システムの順位を上位表示させることを言います。日本では主にGoogleがWebサイトの検索システムとして浸透していますが、Googleの検索の順番・ランキングはあるルールに則って決められています。SEOを向上させるには、様々な知識やツールの使い方を覚える必要があります。例えば「Google Analytics（アナリティクス）」「Google キーワードプランナー」「Google Search Console（サーチコンソール）」「PageSpeed Insights（ページスピードインサイト）」などです。この講義ではこういったツールの使い方はもちろん、実際の活用例までを具体的に教えることができます。',
        'サイトの立ち上げ、運用': 'Webサイトはパソコン上で作成しただけでは、世界中に公開できません。ドメインと呼ばれるものを取得し、サーバーを契約する必要があります。この講義では、初心者の方でも「ドメインの取得」「サーバーの契約」「サーバーとの接続とファイルのアップロード」「SSL化・常時SSL化」などを１から教えることができます。',
        'Git': '複数人で１つのプロジェクトを管理するサイトやアプリケーションのファイル管理に使うのがこのGit（ギット）というツールです。ファイルの変更履歴などが確認できるほか、以前の変更部分まで遡ってファイルの状態を戻すこともできるので、１人で開発をする際にもかなり便利なツールです。IT企業では基本的にこのGitか似たようなツールのSVNが必ずと言って良いほど使われています。Gitをさらに活用するためのGithub（ギットハブ）というサービスの使い方などを教えることもできます。',
        'Gulp / Webpack': '近年の開発では複雑なツールや変換をしないと使えない言語（Sassなど）が多く誕生したことにより、管理が煩雑になってきました。そこで登場したのが、このGulpやWebpackです。最新の開発現場ではこのどちらかが使われることが多くなってきました。',
        'Command line tool': 'GitやGulp、Webpackなどを扱う上で必須となるのが、このCommand line tool（コマンドラインツール）です。Windowsでは「コマンドプロンプト」、Macでは「ターミナル」として最初から扱う為のツールがインストールされています。様々な高度なツールを使う上で必ず覚えなければならないものなので、フロントエンドエンジニアとしてやっていくには扱えるようにしなくてはならないものです',
        'Wordpress': 'Wordpressは、基本的にはプログラミングなどの専門的な知識がなくとも簡単にWebサイトを作れてしまう高機能ツールです。その上カスタマイズ性が非常に高く、HTML / CSS / JavaScript / PHPなどの知識があると、独自の機能やUIを追加することができます！なんと、世界の約30%がWordpressで出来ています。特にブログサイトで使われることが多いですが、一般的なウェブサイトでも使われることが多いです。',
        'その他にも': '・HTMLやCSSなどを短い記述で書き出せるEmmet（エメット）・複雑なアニメーションを扱うことができるTweenmax（トゥイーンマックス。このサイトでもたくさん使われています）などの講義も可能です。ご希望があれば、お問い合わせください。',
      }
    }
  },

  methods: {
    // noteStyle() {
    //   return this.noteClass
    // },

    // playingPiano() {
    //   this.showNote = true;
    //   this.$refs.whiteKey.forEach(el => {
    //     console.log(el)
    //     // gsap.set(el, {
    //     //   y: 0,
    //     //   x: 0
    //     // })

    //     gsap.to(el, .5, {
    //       background: '#ccc',
    //     })

        // gsap.to(el, 2.5, {
        //   y: 'random(-50, -100)',
        //   x: 'random(-100, 100)',
        //   // autoAlpha: 1,
        //   scale: 3,
        //   ease: "power1.inOut",
    //     // })
    //   });
    // },
  },

  mounted() {
  }
}
</script>
