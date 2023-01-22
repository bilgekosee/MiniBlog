<template>
  <div id="app">
    <header>
      <h1>MY<span>BLOG</span></h1>
    </header>

    <div class="faqs">
      <FAQ
        v-for="(faq, i) in faqs"
        :faq="faq"
        :index="i"
        :key="i"
        :open="faq.open"
        @toggleOpen="toggleOpen"
      />
    </div>
  </div>
</template>

<script>
import FAQ from "./FAQ";
export default {
  name: "app",
  components: {
    FAQ,
  },
  data() {
    return {
      faqs: [
        {
          question: "2022 Crunchyroll Anime Ödüllerinde 1. Hangisi Oldu?",

          answer:
            "2022 Crunchyroll Anime Ödülleri açıklandı. Ünlü anime yayın servisi, büyük bir jüri topluluğuyla, çeşitli kategorilerde en iyileri belirledi. Yılın Animesi Attack on Titan oldu.Son sezonuyla anime listelerini değiştiren Attack on Titan 4. sezon, 1. kısmı ile Yılın Animesi seçildi. Ayrıca En İyi Karşı Karakter, En İyi Açılış ve En İyi Japonca Seslendirme ödüllerini aldı.Ödül kazanan yapımların tam listesi ise şöyle: Yılın Animesi: Attack on Titan Final Sezonu 1. Kısım,En İyi Erkek Karakter: Bojji – Ranking of Kings, En İyi Kadın Karakter: Nobara Kugisaki – Jujutsu Kaisen, En İyi Ana Karakter: Odokawa – ODDTAXI,  En İyi Karşı Karakter: Eren Jaeger – Attack on Titan Final Sezonu 1. Kısım, En İyi Dövüş Sahnesi: Yuji Itadori & Aoi Todo vs Hanami – Jujutsu Kaisen, En İyi Yönetmen: Baku Kinoshita – ODDTAXI",

          open: false,
        },
        {
          question: "Yazılıma nereden başlamalıyım?",
          answer:
            "Yazılım alt dalları bulunan bir disiplindir yani yazılım da yapmakistediğiniz şey o alt dallardan biri yada birkaçıdır. Örnek vermekgerekirse mobil bir uygulama geliştirmek istiyoruz ve React Native platformumuzu seçtik ancak bu platformda geliştirme yapmak için bize lazım olan üç farklı dil bulunmakta; JS, Html,Css Genel olarak yeni başlayacaklara; Html, css gibi etiket dilleri dikte edilir belki ilk adım için uygun gözükebilir ancak dikkat edin kendinizi web geliştirici olarak bulabilirsiniz önemli olan sizin ne yapmak istediğiniz! Kol saatleri, akıllı televizyonlar, bilgisayarlar, yapay zeka, IoT nesnelerin interneti… gibi bir çok farklı alana ayrılan bu alandan kendinize bir yol haritası çizmeniz gerekmekte.",

          open: false,
        },
        {
          question: "Japon efsanesi mitleri ve özellikleri nelerdir?",
          answer:
            "Daikokuten: Japon mitolojisinde yer alan yedi adet şans tanrısından biridir. Zenginliğin tanrısı ve çiftçilerin koruyucusudur. Genellikle iri yarı bir biçimde esmer bir tanrı olarak betimlenir. Sağ elinde dilekleri gerçekleştirdiği kabul edilen asası varken sırtında da içi oldukça kıymetli eşyalar ile doldurulmuş çantası bulunur. Daikokuten, pirinç çuvalı üzerinde oturur biçimde betimlenmektedir.Fujin: Japon mitolojisinde yer alan rüzgâr tanrısıdır ve en görkemli Şinto tanrılarından da bir tanesidir. Fujin'in omuzlarında büyük bir çanta vardır ve bu çanta rüzgâr taşır. Kırmızı tenli bir leopard cildine sahip olan Fujin korkunç bir sihirbaza benzer ve iblis olarak betimlenir. Japon sanatı içerisinde bu tanrı genellikle yıldırım, fırtına ve gök gürlemesiyle birlikte resmedilir.Fukurokuju: Yedi şans tanrısından bir tanesidir. Ömrün uzunluğunu ve bilgeliği temsil eden bir tanrıdır. Bu tanrının vakti zamanında bir Taocu olarak dünyada yaşadığına da inanılır. Kendi betimlenirken genelde kafası uzun ve saçsız olan bir ihtiyar olarak resmedilmektedir. Genelde yanında kaplumbağa, geyik veya turna bulunur. Bunlar onun uzun ömrünü nitelemektedir.Hiru – Ko: Japon mitolojisindeki önemli tanrılardan bir tanesidir. Balıkçıların, iyi şansın ve tüccarların tanrısı olarak bilinir. Hem sağlıktan hem de küçük çocukların iyiliğinden sorumludur ve Hiru – Ko'da yedi şans tanrısından bir tanesidir. Burada onu en özel kılan şeylerden biri Japon kökenli olan tek tanrı olmasıdır. Sakat doğmuştur.Hoori: Japonya imparatorlarının atalarından bir tanesidir.Inugami: köpek atnrısı ya da köpek ruhu. Batı Japonya bölgesinde popülerdir. Bir köpeğin ruhu ile ilgilidir manevi bir tanrıdır.",

          open: false,
        },
      ],
    };
  },
  methods: {
    toggleOpen: function (index) {
      this.faqs = this.faqs.map((faq, i) => {
        if (index === i) {
          faq.open = !faq.open;
        } else {
          faq.open = false;
        }
        return faq;
      });
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background: #80b481;
  font-family: sans-serif;
}
header {
  background-color: #b49daa;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 15px;
}
header h1 {
  color: #b40e2f;
  font-size: 28px;
  font-weight: 500;
  text-transform: uppercase;
}
header h1 span {
  color: #36151e;
  font-weight: 900;
}
.faq {
  display: block;
  width: 100%;
  max-width: 768px;
  margin: 15px auto;
  padding: 15px;
  border-radius: 8px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
  background-color: #e6dbd0;
}
.faq .question {
  position: relative;
  color: #3c3c3c;
  font-size: 20px;
  transition: all 0.4s linear;
}
.faq .question::after {
  content: "";
  position: absolute;
  top: 50%;
  right: 0px;
  transform: translateY(-50%) rotate(0deg);
  width: 30px;
  height: 30px;
  background-image: url("./arrow-down-mint.svg");
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;

  transition: all 0.2s linear;
}
.faq.open .question {
  margin-bottom: 15px;
}
.faq.open .question::after {
  transform: translateY(-50%) rotate(90deg);
}
.faq .answer {
  color: #181717;
  font-size: 18px;
  opacity: 0;
  max-height: 0px;
  overflow-y: hidden;
  transition: all 0.4s ease-out;
}
.faq.open .answer {
  opacity: 1;
  max-height: 1000px;
}
</style>