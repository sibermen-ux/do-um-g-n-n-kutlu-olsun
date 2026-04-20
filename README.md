<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sana Bir Sürprizim Var ❤️</title>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap');

        body, html {
            margin: 0; padding: 0; width: 100%; height: 100%;
            font-family: 'Poppins', sans-serif;
            overflow: hidden; color: #4a4a4a;
            background-color: #fff5f7;
        }

        /* EMOJİ YAĞMURU STİLLERİ */
        .emoji-yagmur {
            position: fixed;
            top: -50px;
            font-size: 24px;
            user-select: none;
            pointer-events: none; /* Metnin tıklanmasını engellemez */
            z-index: 0; /* İçeriklerin arkasında kalması için */
            animation: yagmur-dusis linear forwards;
        }

        @keyframes yagmur-dusis {
            to { transform: translateY(110vh); }
        }

        /* KATMAN AYARLARI */
        .katman {
            width: 100%; height: 100vh; display: flex; flex-direction: column;
            align-items: center; justify-content: center; text-align: center;
            position: absolute; top: 0; left: 0; transition: transform 1s cubic-bezier(0.85, 0, 0.15, 1);
            padding: 20px; box-sizing: border-box;
        }

        #katman1 { background: linear-gradient(135deg, #fff5f7 0%, #ffe3ec 100%); z-index: 3; }

        .romantik-cerceve {
            border: 2px solid rgba(255, 77, 109, 0.2);
            padding: 40px; border-radius: 30px;
            background: rgba(255, 255, 255, 0.4);
            backdrop-filter: blur(10px);
            min-height: 200px; display: flex; align-items: center; justify-content: center;
        }

        .kocaman-yazi { font-family: 'Dancing Script', cursive; font-size: 3rem; color: #ff4d6d; }

        /* 2. KATMAN: MEKTUP */
        #katman2 { 
            z-index: 2; background: #ffffff; transform: translateY(100%);
            overflow-y: auto; display: block; padding-top: 50px; padding-bottom: 100px;
        }

        .mektup-kutu {
            max-width: 700px; margin: 0 auto; padding: 40px; border-radius: 30px;
            background: rgba(255, 250, 250, 0.9); /* Biraz şeffaf ki emojiler hafif görünsün */
            border: 1px solid #fce4ec; box-shadow: 0 10px 30px rgba(0,0,0,0.03);
            text-align: left; position: relative; z-index: 10;
        }

        .mektup-metni { font-size: 1.05rem; line-height: 1.8; color: #555; white-space: pre-line; }

        /* 3. KATMAN: ŞİİRLER */
        #katman3 { z-index: 1; background: #fffcfd; transform: translateY(100%); overflow-y: auto; }

        .siir-grid {
            display: grid; grid-template-columns: repeat(5, 1fr); gap: 12px;
            max-width: 500px; margin: 20px auto; position: relative; z-index: 10;
        }

        .kutucuk {
            width: 60px; height: 60px; background: #ffe3ec; color: #ff4d6d;
            display: flex; align-items: center; justify-content: center;
            border-radius: 15px; cursor: pointer; font-weight: bold; transition: 0.4s;
        }
        .kutucuk:hover { background: #ff4d6d; color: white; transform: scale(1.1); }

        .devam-btn {
            position: fixed; bottom: 30px; right: 30px; padding: 15px 35px;
            background: #ff4d6d; color: white; border: none; border-radius: 50px;
            font-size: 1rem; font-weight: bold; cursor: pointer; display: none; z-index: 100;
        }

        .modal {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.8); z-index: 300; align-items: center; justify-content: center;
            backdrop-filter: blur(8px);
        }
        .modal-icerik { background: white; padding: 40px; border-radius: 30px; max-width: 85%; text-align: center; }

        @media (max-width: 600px) { .siir-grid { grid-template-columns: repeat(4, 1fr); } }
    </style>
</head>
<body>

    <section id="katman1" class="katman">
        <div class="romantik-cerceve">
            <div id="mesaj-ekrani" class="kocaman-yazi">Hoş Geldin Sevgilim...</div>
            <div id="sayac" style="font-size: 6rem; font-family: 'Dancing Script'; color: #ff4d6d; display: none;"></div>
        </div>
        <button id="btn1" class="devam-btn" onclick="gec(2)">Sana Bir Mesajım Var ✨</button>
    </section>

    <section id="katman2" class="katman">
        <div class="mektup-kutu">
            <h2 style="font-family: 'Dancing Script', cursive; font-size: 2.5rem; color: #ff4d6d; text-align: center;">Canım Sevgilime... 💌</h2>
            <div class="mektup-metni">
                Merhaba şwmspwsm biraz heycan var kusura bakma aslında bu yazıyı çok önceden yazmıştım ama tamda hediyeni vereceğim zaman tartıştık olsun hayat işte her zaman mutlu olmuyoz hiç istemezdim doğum gününden önce tartışmak malesef oldu ama ne olursa olsun seni çok seviyorum bazen kırıyorum üzüyorum ne bilim bişiler oluyo ama ne kadar tartışsakda kavga etsekte sana olan aşkım sevgim güvenim hiç bir zaman bitmedi bitmicekte benim için o kadar kıymetlsinki kelimelere dökemem o kadar değişik, benim hakkımda düşüncelerini biliyorum insanlara olan sinirimi senden çıkarıyorum sinirlenince azarlıyorum ve daha fazlası aslında böyle yapmıyorum ama öyle anlaşılıyor seni suçlamıyorum hata bende , korkuyorum böyle bi an senin gözünden kalbinden bi anlık bile olsa çizik olmasını herşey için çok pişmanım, seni çok seviyorum be kızım 1 ay önceden başladım bu hediyeyi yapmaya bana gerçek aşkı sevgiyi güveni saf duyguyu yaşattın ne desem boş çok teşekkür ederimm bazen ne kadar salaklığım olsada beni üzmemek için yalnız kaldın yuttun hakkın ödenmez ama bu gün benim için milad oldu biliyormusun sanki bir yaşıma daha girmiş gibiyim sana söz veriyorum oturucam kendimi ölçücem herşeyi düşünücem sana karşı o eskş hatalarımı geri tekrarlamıcam buda sana İlhan sözü olsun seni çokmu çok seven adamın sözü senden ricam bana biras daha açık olman garip bir kişiliğim var biliyorum anlaması güç hala haraketlerim tavırlarım çocukca anlıyorum ama senden isteğim biras daha bana karşı açık olman, biliyormusun hayatımda ilk defa aşkı sevilmeyi yaşadım gerçek saf karşılıksız sevgiyi umarım bende sana yaşatabilmişimdir,İlk defa odamda bu kadar çok ağlıyorum bilmiyom normlade söylemem ama içimden geldi şqmspwms valla varya seni çok seviyorum be güzelim herşey için çok özür dilerim.

                Saygılarımla seni deliler gibi seven İlhan...
            </div>
        </div>
        <button id="btn2" class="devam-btn" style="display: block;" onclick="gec(3)">Devam Et ❤️</button>
    </section>

    <section id="katman3" class="katman">
        <h2 style="font-family: 'Dancing Script', cursive; font-size: 2.5rem; color: #ff4d6d;">30 Gün, 30 Şiir ✨</h2>
        <div class="siir-grid" id="grid"></div>
    </section>

    <div id="modal" class="modal" onclick="kapat()">
        <div class="modal-icerik"><p id="siirMetni" style="font-size: 1.1rem; white-space: pre-line;"></p></div>
    </div>

    <script>
        const hitaplar = ["İYİ Kİ DOĞDUN PRENSESİM", "HAYATIMIN ANLAMI", "AŞK BAHÇEM", "YAVRUM", "CEYLAN GÖZLÜM"];
        const emojiler = ['💓','🍥','💖','🥰','🤩','🫶'];
        let yagmurDurumu = false;

        window.onload = () => {
            const ekran = document.getElementById('mesaj-ekrani');
            let i = 0;
            const hitapInterval = setInterval(() => {
                if (i < hitaplar.length) {
                    ekran.style.opacity = 0;
                    setTimeout(() => { ekran.innerText = hitaplar[i]; ekran.style.opacity = 1; i++; }, 500);
                } else {
                    clearInterval(hitapInterval);
                    setTimeout(baslatGeriSayim, 1500);
                }
            }, 2000);
        };

        function emojiOlustur() {
            if (!yagmurDurumu) return;
            const e = document.createElement('div');
            e.className = 'emoji-yagmur';
            e.innerText = emojiler[Math.floor(Math.random() * emojiler.length)];
            e.style.left = Math.random() * 100 + 'vw';
            e.style.animationDuration = Math.random() * 3 + 2 + 's';
            e.style.opacity = Math.random();
            document.body.appendChild(e);
            setTimeout(() => { e.remove(); }, 5000);
        }

        function baslatGeriSayim() {
            document.getElementById('mesaj-ekrani').style.display = 'none';
            const sayacDiv = document.getElementById('sayac');
            sayacDiv.style.display = 'block';
            let s = 3;
            let interval = setInterval(() => {
                sayacDiv.innerText = s;
                if (s === 0) {
                    clearInterval(interval);
                    sayacDiv.innerHTML = "İYİ Kİ DOĞDUN!<br><span style='font-size: 1.5rem'>Seni Seviyorum ❤️</span>";
                    konfeti();
                    document.getElementById('btn1').style.display = 'block';
                }
                s--;
            }, 1000);
        }

        function konfeti() {
            confetti({ particleCount: 100, spread: 70, origin: { y: 0.6 } });
        }

        function gec(n) {
            yagmurDurumu = true; // 2. katmana geçerken yağmuru başlat
            setInterval(emojiOlustur, 300); // Her 300ms'de bir emoji düşsün

            if (n === 2) {
                document.getElementById('katman1').style.transform = 'translateY(-100%)';
                document.getElementById('katman2').style.transform = 'translateY(0)';
            } else if (n === 3) {
                document.getElementById('katman2').style.transform = 'translateY(-100%)';
                document.getElementById('katman3').style.transform = 'translateY(0)';
                gridOlustur();
            }
        }

        const siirler = [
            "Gözlerin uzağımda, hayalin yanı başımda,\nBir ince sızı gizli, her lokma aşımda.\nYollar engel olsa da, sevdan kalbimde,\nAdın yankılanır hep, şu gençlik yaşımda.",
            "Haritada bir nokta, senin olduğun şehir,\nAramızda uzanır, koca bir kara nehir.\nSesini duymadığım her geçen dakika,\nİçtiğim her yudum su, sanki bana bir zehir.",
            "Telefonun ekranı, tek pencerem sana,\nBakıp bakıp dururum, şu bitmez zamana.\nBir gün elbet bitecek, bu hasret kokan yol,\nDaha sıkı sarılmak, nasip olur bana.",
            "Güneş seninle doğar, bende ise batıyor,\nKalbimiz uzaklarda, bir ritimle atıyor.\nRüzgar esse kuzeyden, kokunu getirir mi?\nRuhum senin olduğun, o şehirde yatıyor.",
            "Mektuplar yazılmıyor, mesajlar çok hızlı,\nAma her satırında, bir özlem var gizli.\nMesafeler ne ki yar, gönül bağımız varken,\nBizim aşkımız böyle, tertemiz ve nazlı.",
            "Uçak kanatlarında, selam yolladım sana,\nBiraz sabret sevdiğim, darılma hiç zamana.\nKavuşmak hayaliyle, uyurum her gece ben,\nCanım feda olsun o, seni tutan limana.",
            "Aynı gökyüzü altındayız, bu yeter şimdilik,\nAramızdaki bağlar, en sağlamından çelik.\nGözyaşım düşer bazen, ekranın üzerine,\nSensiz geçen her günüm, sanki bir eksiklik.",
            "Kilometreler saydım, bitmek bilmedi yollar,\nSeni sarmak istiyor, bu bomboş kalan kollar.\nTakvime her gün bir çizik, atarken düşünürüm,\nBize ne zaman gülecek, bu sevdalı yıllar?",
            "Sesin bir ilaç gibi, kulaklarımda çınlar,\nHâlimizi ne bilsin, o sevmeyen insanlar.\nÖzlemek ibadettir, senin gibi güzele,\nAncak çekenler bilir, biter mi bu hüzünler?",
            "Bir kahve içerim ben, senin için burada,\nRuhum seninle gezer, o uzak kıyıda.\nFiziken uzağız yar, kalben ise bir bütün,\nAşkımız gerçek bizim, kalmasınlar darada.",
            "Uykuya dalmadan evvel, resmine bakıyorum,\nYüreğime her gece, bir mum da ben yakıyorum.\nYollar bizi ayırsa, gönlüm seni bırakmaz,\nHasretin sel olsa da, ben sana akıyorum.",
            "Bulutlar haber uçurur, belki benim yerime,\nSevdan işlemiş artık, en derinden derime.\nHiç kimse dokunamaz, senin bıraktığın yere,\nSadakat yeminimiz, derman olsun ferime.",
            "Gün saymak yorucuymuş, aylar geçmek bilmiyor,\nSenin yerini kimse, gelip de doldurmuyor.\nAramızda dağlar var, aşılması güç ama,\nSeven insan sevdiğin, asla yarıda bırakmıyor.",
            "Gülüşün bir video, izleyip durduğum her an,\nSensiz geçen bu ömür, ziyan oluyor ziyan.\nSabır meyvesi tatlı, derdi eskiler bize,\nKavuşacağımız o gün, olacak bana bayram.",
            "Camın buğusuna ben, adını yazıyorum,\nHasretin kuyusunu, her gün daha kazıyorum.\nKızma bana sevdiğim, özledim çok diyorsam,\nSensizlik ikliminde, yaprak gibi sızıyorum.",
            "Uzaklık dediğin şey, bir rakamdan ibaret,\nYeter ki kalbimizde, bitmesin bu hararet.\nBen burada beklerim, bir ömür boyu seni,\nYeter ki gözlerinde, göreyim bir işaret.",
            "Yastığımda kokun yok, ama fikrimde varsın,\nSen benim bu hayatta, en vefalı yarımsın.\nAraya yollar girdi, araya dağlar girdi,\nSen benim bitmeyecek, sevda rüzgarımsın.",
            "Yağmur yağar buralara, belki oraya da yağar,\nSeven kalbe her sabah, yeni bir umut doğar.\nAyrılığın sancısı, ağır gelse de bazen,\nBir tatlı sözün senin, tüm dertlerimi boğar.",
            "Penceremden bakarım, geçtiğin yollar diye,\nAşkın kalsın kalbimde, en kıymetli hediye.\nHasretle harmanlandık, piştik bu sevda ile,\nŞükrediyorum Tanrı’ya, seni verdi diye.",
            "Bir gün aynı sofrada, ekmek bölüşeceğiz,\nBütün bu zorluklara, beraber güleceğiz.\nUzaklık imtihandır, sabreden kazanırmış,\nBiz bu aşkın sonunda, murada ereceğiz.",
            "Aramızdaki o yol, çiçeklensin gelince,\nKalbim küt küt atıyor, adın kalbe değince.\nUzaklık engel değil, ruhların vuslatına,\nDünya durur sanki biz, birbirimizi sevince.",
            "Geceleri yıldızlara, anlatırım derdimi,\nKimselere veremem, bu yaralı kalbimi.\nGözlerin aklımdadır, her saniye her saat,\nSeninle tamamladım, eksik olan kendimi.",
            "Gömleğinin bir teki, bende kaldı hatıra,\nSığdıramam aşkımı, ne sayfaya ne satıra.\nÖzlemine alıştım, can yoldaşım oldu o,\nHasretini yükledim, şu giden her katara.",
            "Şehirler arası otobüs, seni bana getirsin,\nŞu bitmek bilmez acı, artık burada bitsin.\nElini tuttuğum an, unuturum her şeyi,\nBütün ayrılıklar da, artık öteye gitsin.",
            "Gözden ırak olan yar, gönülden ırak olmaz,\nSevenlerin bahçesi, hiç solmaz ve sararmaz.\nMesafe dediğin ne? Birkaç saatlik bir yol,\nGerçek bir aşkın sonu, asla hüsranla dolmaz.",
            "Bana \"günaydın\" yazman, günümü aydınlatır,\nSanki sesin yanımda, o an beni parlatır.\nBir mesajla ısınır, bu üşüyen ellerim,\nUzaklık olsa bile, aşk kendini anlatır.",
            "Hasretin rüzgarı sert, ama gemim sağlamdır,\nSenin sevgin kalbimde, en kıymetli bağlamdır.\nKavuşmanın hayali, ayakta tutar beni,\nŞu upuzun yollar da, aşılacak yollardır.",
            "Seni sevmek uzakken, bir ibadet gibidir,\nBu gönül okyanusu, en çok senin dibidir.\nAyrılık olsa bile, kopmaz bizim bağımız,\nHer bir güzel hatıra, bu aşkın sahibidir.",
            "Gözlerimi kapatsam, yanındayım aslında,\nRuhum seninle gezer, o sahilin kıyısında.\nBize uzaklık değil, yakınlık yakışıyor,\nAdın yazılı kalsın, şu aşkın sayfasında.",
            "Bitti dörtlükler ama, bitmez sana bu sevdam,\nSeninle her zorluğa, ben her zaman hazırım.\nMesafe olsa bile, gönül gözüyle bakarım,\nSenin olduğun yere, ben kalbimi kazırım."
        ];

        function gridOlustur() {
            const grid = document.getElementById('grid');
            if (grid.children.length > 0) return;
            for (let i = 1; i <= 30; i++) {
                const k = document.createElement('div');
                k.className = 'kutucuk';
                k.innerText = i;
                k.onclick = () => ac(i - 1);
                grid.appendChild(k);
            }
        }
        function ac(i) {
            document.getElementById('siirMetni').innerText = siirler[i];
            document.getElementById('modal').style.display = 'flex';
        }
        function kapat() { document.getElementById('modal').style.display = 'none'; }
    </script>
</body>
</html>
