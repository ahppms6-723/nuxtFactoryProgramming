<template lang="pug">
  main
    .firstView
      ul.circleWrapper
        li.circle(
          v-for="(circle, circleIndex) in circles" :key="`circle${circleIndex}`"
          ref="circle"
          :class="circle"
        )
          .insideRound
      .firstViewContainer
        h1.title
          .titleBack: p 初心者から中・上級者まで
          .titleBack: p プログラミングのことを
          .titleBack: p マンツーマンで丁寧に教えます
        a.applyButton 申し込み詳細を見る
      .triangle

    section.problems
      .problemsTitleArea
        h2.problemTitle(ref="problemTitle")
          p こんなことに
          p 困っていませんか？
        .backGray(ref="problemTitle")
        .backBlue(ref="backBlue")
      ul.problemList
        li.problem(
          v-for="(problem, problemIndex) in problemTexts" :key="`problem${problemIndex}`"
          ref="problem"
        )
          p(v-html="problem")
      
    section.solveProblems
      div(class="solveProblemsContainer scaleAnimation" ref="scaleAnimation")
        h2.solveProblemsTitle その問題、解決できます！
        .solveProblemsTextsWrapper
          p この講座はHTMLやCSSを使ったホームページ作成や、WordPressなどを始めてみたい・ブログや自分のサイトを作ってみたいといった<span>「最初の一歩」</span>から、もっと集客を増やすためのSEO・進化するGoogle検索エンジンに対応するための対策といった<span>「次のステップ」</span>まで個別にお伺いします！
    
    section.features
      div.Contents
        div.sectionTitleArea
          sectionTitle(secTitle="この講義の3つの特徴")
        div(class="whiteTriangle")
        ul(class="featuresList")
          li(v-for="(feature, featureTitle, featureIndex) in features" :key="`feature${featureIndex}`"
            class="scrollAnimation"
          )
            div(class="featuresTitleArea")
              h3.featuresListTitle {{ featureTitle }}
              div(class="borderBottom")
            p.feature(v-html="feature")
            div(class="OneOnOne icon")

    section.evaluation
      div.Contents
        div.sectionTitleArea
          sectionTitle(secTitle="受講者の声")
        ul.evaluationList
          li(v-for="(evaluation, evaluationAge, evaluationIndex) in evaluations" :key="`evaluation${evaluationIndex}`"
            class="scrollAnimation"
          )
            div.areaHuman
              div.figure.woman
              div.sex(v-html="evaluationAge")
            div.commentArea
              p(v-html="evaluation")
        button 申し込み詳細を見る

    section.profile(ref="profile")
      div.Contents
        div.sectionTitleArea
          sectionTitle(secTitle="講師プロフィール")
        div.allProfile
          div.profiletextSide(ref="profiletextSide")
            p プログラムとの出会いは14歳（中学二年生）の時。
            p 当時流行っていた、オンラインゲームのファンサイトを作りたくて、勉強を始めたのがきっかけです。
            p プログラミングの文字列によってデザインやアニメーションを組めるプログラミングは私にとって最高の自己表現でした。
            p 今もそれは変わりません。
            p.marginTop ただ、私自身最初は何もわからず、手探りでHTMLを書いていました。当時相談できる人も側におらず、今思うと本当に簡単なミスのせいで、<span style="font-weight: bold;">一箇所の余白を調整するのに１週間悩み続けた</span> ことを覚えています。
            p.marginTop これからプログラミングを学びたい方には、<span style="font-weight: bold;">できればそんな苦労はしてほしくない。</span>
            p でも逆に、あの頃悩んだ経験があるから、一歩一歩成長する喜びもよくわかると思います。
            p.marginTop WEBを作っていく楽しさや苦しさも踏まえて、<span style="font-weight: bold;">自身の経験が誰かの成長のお役に立てれば嬉しい</span>です。
          div.profileImgSide
            div.takedaImg(ref="takedaImg")
            div.profileDetail(ref="profileDetail")
              p 武田一真（たけだかずま）
              p 宮城出身のフリーランスエンジニア。
              p 15年以上のプログラミング経験。
              p 本業のエンジニアの他に、スクール経営・個別講義などを行っています。
              p 趣味は5歳からやっているエレクトーン・ピアノの演奏や作曲・編曲。たまにバンドもやったりしています。
              p.marginTop エンジニアの為のサイト制作支援ツール（主にジェネレーター）を制作・運営しています。
              p こちらも見てみてください。
              a.linkFrontEndTool(href="#") Front-end Tools
              ul.areaSns
                li: a(href="#" class="fab fa-twitter twitter i")
                li: a(href="#" class="fab fa-youtube youtube i")
          div.backYellow(ref="backYellow")

    section.belongings
      div.Contents
        div.sectionTitleArea
          sectionTitle(secTitle="講義場所・持ち物")
        div(class="belongingsTextArea scrollAnimation")
          p 緊急事態宣言中は基本的にオンラインとなります。
          p また、地方・海外の方など都内にアクセスが難しい方やコロナウイルスなどが心配な方はオンラインでの講義も可能となっております。
          p ※使用するサービスはSkype（スカイプ）やZoom（ズーム）など
          p オフライン希望の場合は講義場所は基本的に「新宿駅」（東京都内）近くとなります。
          p 申し込み後、待ち合わせ場所と講義場所をご連絡させていただきます。
          p 講師は小田急線沿い（神奈川県川崎市）に住んでいますので、近くにお住まいの方は場所を調整できます。
          p 持ち物は、ノートパソコン（Windows/Mac可）と、必要であれば筆記用具をお持ちください。

    section.questions
      div.Contents
        div.sectionTitleArea
          sectionTitle(secTitle="よくある質問")
        ul.questionList
          li(v-for="(questionLi, answer, questionIndex) in questions" :key="`questionLi${questionIndex}`"
            class="scrollAnimation questionLi"
            ref="questionLi"
            @click="openAnswer"
          )
            div.question(v-html="questionLi")
            div.answer(v-html="answer")
        button 申し込み詳細を見る
</template>

<script>
import { gsap } from 'gsap'
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
import { TimelineMax } from 'gsap'
export default {
  data() {
    return {
      whiteKeyBoard: 8,
      circles: 10,
      problems: 8,
      problemTexts: [
        '会社のホームページやブログを<br>簡単に作ってみたい',
        'Wordpressって何？',
        'ドメイン、SSLとは…？',
        'HTML・CSSの書き方が分からない！',
        'レスポンシブ・スマホ対応ってどうするの？',
        'SEOを向上させるには？',
        'フリーランスや自営業で生きていくには？',
        'サイトが遅い…泣'
      ],
      features: {
        '1. 初心者でも安心！マンツーマン講義！': '個別に教えるので、他の複数人同時におこなう講義と違い、<span style="font-weight: bold;">個別のレベルに応じた適切なことを教えることが出来ます！</span><br>さらに、質問しづらいといったこともないので、聞きたいことが聞けなかった！のようなことがありません。',
        '2. 現役エンジニアがしっかり教えます。': '現役のエンジニアが教えていない他の講義では、平気で数年前のことをそのまま教えていたりします。そうすると、今では使われていないことを覚えなければならない為、無駄が多くなりがちです。<br>しかしこの講義では、<span style="font-weight: bold;">現役のエンジニアが今の時代に沿った最新の技術を教える</span>ので、効率的に技術を学ぶことが出来ます。',
        '3. フリーランスとしての経験もお伝え出来ます。': '働き方が多様化した現代では、会社員を辞めてフリーランサーとして自由に仕事がしたいという方のご相談も増えています。<br>希望する方には、個人事業主としてのメリット・デメリットや、どういう経験や技術を身に付けたらフリーランスとして働けるのかを、<span style="font-weight: bold;">実体験を元にお話することが出来ます。</span><br>相談がメインの方もいらっしゃいます。'
      },
      evaluations: {
        '40代 女性': 'マンツーマンで、わたしには丁度良いテンポでした。<br>というか、瞬時にレベルに合わせてくださって、質問しやすい雰囲気でした！<br>教え上手だし、聞きづらい雰囲気がないんです。<br>学ぶことが楽しくなりました。<br>新しい技術などについても詳しくて頼もしいです。<br>もっと早く受けたかったです！',
        '30代 女性': '現役の方から教わるのは、こんなにも違うのかと思いました。また、最新の情報を幅広く知ってらっしゃるので安心感がありました。実際にHPのお仕事を夢を持って進んでいられるようで、スキルアップすることの価値を感じられ、ちゃんと学んでいこうというモチベーションにもつながりました。とてもわかりやすく、楽しい講座でした。ありがとうございました。',
        '20代 男性': '初心者でしたが、わかりやすく説明してもらい、さらに勉強していきたいと思いました！HTMLやCSSで様々なことができるということを教えてもらいそのための基本的な操作を実践を踏まえてしっかりと教えてもらいました。講座中気になったことや深く知りたいことなどを質問すると、しっかりと答えてもらえたので講座終わりはスッキリとした気持ちでした！講座時間があっという間で勉強したい気持ちが強く残りました。また受講したいと思います。',
        '50代 女性': '聞きたいことが山のようにあったので、とても２時間じゃ無理だろうな…と思って挑んでいましたが、先生は、サクサク解決しれて気持ちがいいテンポで進めてくださいました。色んなモヤモヤが解消されたこともあって、やるべきことが明確になり、本当に受けてよかったです。マンツーマンなところ。先生の知識の豊富さが加わり、無駄がない時間を過ごすことが出来たので、私はいい講座だと思いました。また、何個か解決できない悩みが溜まったら、お願いすると思います。',
      },
      questions: {
        'コロナウイルス（COVID-19）が心配です。対面での講義ではなく、オンライン（Skype・Zoomなど）の対応も可能でしょうか？': '可能です。是非一度お問い合わせください！',
        'プログラミングのことだけではなく、フリーランスとして働いて行くには？などご相談だけ講義内でさせていただくことも可能でしょうか？':'はい！もちろん問題ありません。講師の経験を元に、精一杯アドバイスさせていただきます。',
        '個室での講義も可能ですか？':'基本的にはカフェで講義を行なっていますが、可能です。',
        'ただし、レンタルスペースを探す手間やコストがかかるので、基本的にはお客様の方で用意していただく形になります。':'Web制作などを外注しようと思っていますが、どのように外部に発注したらいいかわかりません。こういった内容の相談でも可能でしょうか？',
        'はい、もちろん可能です。もし不安な方は、あらかじめお問い合わせください。':'現在請け負っている案件・仕事の相談をしてもよろしいでしょうか？また、その場合情報は秘密にしておいていただけますか？',
        'そういった相談でも問題ありません。もちろん講義内で知り得た情報を口外することはありませんし、もし不安なようであればNDAなどを交わすことも可能です。（ただし、契約書などはご用意ください）':'Wordpressの独自テーマ作成 / HTML, CSSで作ったページのWordpress化を教えて欲しいのですが可能ですか？</div>',
        'Wordpressの独自テーマ作成 / HTML, CSSで作ったページのWordpress化を教えて欲しいのですが可能ですか？':'可能です。ただし、実装したい内容によっては時間がかかる場合もありますので、事前にご連絡いただくとスムーズかと思います。',
        '会社でいきなりWeb担当にさせられてしまいました…。会社HPの修正や、ネットショップについても教えてもらえますか？':'是非ご相談ください。<br>講師が教えられることであれば、時間内でどんなことでもお教え出来ます。<br>もし不安でしたら、お気軽にお問い合わせください',
        'Wordpressのカスタム投稿・カスタムメニュー・カスタムフィールド・プラグインやテーマのカスタマイズなど、少し踏み込んだことも教えてもらえますか？':'もちろん教えることができます。それぞれの実例をお見せしながら、活用の仕方を一緒に学んでいきましょう！',
        '都内にアクセスするのが難しい地域（地方や海外）に住んでいますが、その場合はどうしたら良いでしょうか？':'オンライン（Skype・Zoomなど）での対応が可能です。是非一度お問い合わせください！',
        '全くの初心者ですが、受講は可能ですか？':'もちろん可能です。<br>むしろ受講者の8割ほどの方が初心者なので、ご安心ください。',
        '講義時間や場所の調整は可能でしょうか？':'はい、可能です。<br>ただ、前後の講義の兼ね合いなどがありますので、まずは一度お問い合わせください。',
      },
    }
  },

  methods: {
    openAnswer(e) {
      if (e.target.parentElement.classList.contains('active')) {
        e.target.parentElement.classList.remove('active');
      } else {
        this.$refs.questionLi.forEach(el => {
          el.classList.remove('active');
        });
        e.target.parentElement.classList.add('active');
      }
    }
  },

  mounted() {
    gsap.registerPlugin(ScrollTrigger);
    gsap.registerPlugin(TimelineMax);

    gsap.fromTo(this.$refs.scaleAnimation,
    { //アニメーションしたい要素を指定
      autoAlpha: 0,
      scale: .9
    },
    {
      autoAlpha: 1,
      scale: 1,
      ease: "power1.inOut",
      duration: 1,
      scrollTrigger: {
        trigger: this.$refs.scaleAnimation,//アニメーションが始まるトリガーとなる要素
        start: 'top 75%', //アニメーションが始まる位置を指定
      }
    });

    const scrollAnimations = document.querySelectorAll('.scrollAnimation');

    scrollAnimations.forEach(element => {
      gsap.fromTo(element,
      { //アニメーションしたい要素を指定
        autoAlpha: 0,
        y: 50,
      },
      {
        autoAlpha: 1,
        y: 0,
        ease: "power1.inOut",
        duration: 1,
        scrollTrigger: {
          trigger: element,//アニメーションが始まるトリガーとなる要素
          start: 'top 100%', //アニメーションが始まる位置を指定
        }
      });
    });

    gsap.set(".circle", {
      y: 20,
      opacity: 0
    })
    gsap.set(".triangle", {
      opacity: 0
    })
    gsap.set(".title", {
      opacity: 0
    })
    gsap.set(".applyButton", {
      opacity: 0
    })

    let firstViewTl = new TimelineMax
    firstViewTl.to('.triangle', 1, {
      opacity: 1,
    },)
    .to('.circle', .3, {
      y: 0,
      opacity: 1,
      stagger: {
        each: .1,
        from: "random",
      }
    })
    .to('.title', .1, {
      opacity: 1,
    })
    .to('.applyButton', .1, {
      opacity: 1,
      delay: -.1,
      onComplete: function() {
        const circles = document.querySelectorAll('.circleWrapper > .circle');
        const values = {
          minSeconds: 3,
          maxSeconds: 8,
          distance: window.innerWidth > 768 ? 40 : 20,
        }

        for (let i = 0; i < circles.length; i++) {
          let circlesTl = new TimelineMax();

          circlesTl.to(circles[i], {
            x: 'random(' + values.distance + ',' + values.distance * -1 + ')',
            y: 'random(' + values.distance + ',' + values.distance * -1 + ')',
            ease: "power2.inOut",
            duration: 'random(' + values.minSeconds + ',' + values.maxSeconds + ')'
          })
            .to(circles[i], {
            x: 'random(' + values.distance + ',' + values.distance * -1 + ')',
            y: 'random(' + values.distance + ',' + values.distance * -1 + ')',
            ease: "power2.inOut",
            duration: 'random(' + values.minSeconds + ',' + values.maxSeconds + ')'
          })
          .to(circles[i], {
            x: 'random(' + values.distance + ',' + values.distance * -1 + ')',
            y: 'random(' + values.distance + ',' + values.distance * -1 + ')',
            ease: "power2.inOut",
            duration: 'random(' + values.minSeconds + ',' + values.maxSeconds + ')'
          })
          .to(circles[i], {
            x: 'random(' + values.distance + ',' + values.distance * -1 + ')',
            y: 'random(' + values.distance + ',' + values.distance * -1 + ')',
            ease: "power2.inOut",
            duration: 'random(' + values.minSeconds + ',' + values.maxSeconds + ')'
          })
          .repeat(-1)
          .yoyo(true)
        }
      }
    })

    let problemsScrollTl = new TimelineMax({
      scrollTrigger: {
        trigger: this.$refs.problem,
        start: "bottom 75%",
      }
    });

    problemsScrollTl.fromTo(this.$refs.problemTitle, .5,
    {
      opacity: 0,
      scale: .9,
      x: "-50%",
      y: "-50%",
    },
    {
      opacity: 1,
      scale: 1,
      ease: "power3.out"
    })
    .fromTo(this.$refs.problem,
    {
      opacity: 0,
      scale: .9,
    },
    {
      opacity: 1,
      scale: 1,
      ease: "power3.out",
      stagger: {
        amount: 1
      }
    })
    .fromTo(this.$refs.backBlue, .3,
    {
      opacity: 0,
      scale: .9,
      x: "-50%",
      y: "-50%",
    },
    {
      opacity: 1,
      scale: 1,
      ease: "power3.out"
    })

    let profileScrollTl = new TimelineMax({
      scrollTrigger: {
        trigger: this.$refs.profile, // トリガーとなる要素は".wrapper"
        start: "40% 75%",
      }
    });

    profileScrollTl.fromTo(this.$refs.backYellow, .4,
    {
      opacity: 0,
      y: 30
    },
    {
      opacity: 1,
      y: 0,
      ease: "power3.inout"
    })
    .fromTo(this.$refs.profiletextSide, .3,
    {
      opacity: 0,
      y: -20,
      x: -20
    },
    {
      opacity: 1,
      ease: "power3.inout",
      y: 0,
      x: 0,
      delay: '-.1'
    })
    .fromTo(this.$refs.takedaImg, .3,
    {
      opacity: 0,
      y: 20,
      x: 20
    },
    {
      opacity: 1,
      ease: "power3.inout",
      y: 0,
      x: 0,
      delay: '-.1'
    })
    .fromTo(this.$refs.profileDetail, .3,
    {
      opacity: 0,
      y: 20
    },
    {
      opacity: 1,
      ease: "power3.inout",
      y: 0,
      delay: '-.1'
    })

    const sectionTitle = document.querySelectorAll('.sectionTitle');

    for (let i = 0; i < sectionTitle.length; i++) {
      const targetElement = sectionTitle[i],
            texts = targetElement.textContent,
            textsArray = [];
      targetElement.textContent = "";

      for (let j = 0; j < texts.split("").length; j++) {
        const t = texts.split("")[j];
        textsArray.push('<span class="sectionText">' + t + '</span>')
        // textsArray.push('span.sectionText' + t)
      }
      for (let k = 0; k < textsArray.length; k++) {
        targetElement.innerHTML += textsArray[k];
      }
    };

    const sectionTitleArea = document.querySelectorAll('.sectionTitleArea'),
          backcircleFill = document.querySelectorAll('.backcircleFill'),
          backcircleStripes = document.querySelectorAll('.backcircleStripes'),
          underLine = document.querySelectorAll('.underLine'),
          secTitle = document.querySelectorAll('.sectionTitle');

          console.log(secTitle)

    for (let i = 0; i < secTitle.length; i++) {
      let sectionTitleScrollTl = new TimelineMax({
        scrollTrigger: {
          trigger: secTitle[i],
          start: "top 75%",
        }
      });
      sectionTitleScrollTl.fromTo(backcircleFill[i], .5,
      {
        opacity: 0,
        x: -30
      },
      {
        opacity: 1,
        x: 0,
        ease: "power3.inout"
      })
      .fromTo(backcircleStripes[i], .5,
      {
        opacity: 0,
        x: -30
      },
      {
        opacity: 1,
        x: 0,
        ease: "power3.inout",
        delay: '-.3'
      })
      .fromTo(underLine[i], .5,
      {
        width: 0
      },
      {
        width: '100%',
      })
      .fromTo(sectionTitle[i].querySelectorAll(`.sectionText`),
      {
        y: '120%'
      },
      {
        ease: "power3.inout",
        stagger: {
          y: 0,
          amount: .5
        }
      })
    };
  }
}
</script>
