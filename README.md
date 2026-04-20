<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>İyi Ki Doğdun Sevgilim!</title>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        body, html {
            margin: 0; padding: 0; width: 100%; height: 100%;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #fff5f7; overflow: hidden; color: #4a4a4a;
        }
        .katman {
            width: 100%; height: 100vh; display: flex; flex-direction: column;
            align-items: center; justify-content: center; text-align: center;
            position: absolute; top: 0; left: 0; transition: transform 0.8s ease-in-out;
            padding: 20px; box-sizing: border-box;
        }
        #katman1 { z-index: 3; background: #fff5f7; }
        #katman2 { z-index: 2; background: #ffffff; transform: translateY(100%); }
        #katman3 { z-index: 1; background: #fdf2f4; transform: translateY(100%); overflow-y: auto; }

        .kocaman-yazi { font-size: 3.5rem; font-weight: bold; color: #ff4d6d; margin-bottom: 20px; }
        .geri-sayim { font-size: 5rem; font-weight: 900; color: #ff758f; }

        .mektup-kutu {
            max-width: 600px; background: #fff; padding: 30px; border-radius: 30px;
            box-shadow: 0 15px 35px rgba(255, 77, 109, 0.1); line-height: 1.8;
            border: 2px dashed #ffb7c5;
        }

        .siir-grid {
            display: grid; grid-template-columns: repeat(5, 1fr); gap: 10px;
            max-width: 450px; margin: 20px auto;
        }
        @media (max-width: 500px) {
            .siir-grid { grid-template-columns: repeat(4, 1fr); }
            .kocaman-yazi { font-size: 2.2rem; }
        }

        .kutucuk {
            width: 55px; height: 55px; background: #ffb7c5; color: white;
            display: flex; align-items: center; justify-content: center;
            border-radius: 12px; cursor: pointer; font-weight: bold; transition: 0.3s;
        }
        .kutucuk:hover { background: #ff4d6d; transform: scale(1.1); }

        .devam-btn {
            position: fixed; bottom: 30px; right: 30px; padding: 12px 25px;
            background: #ff4d6d; color: white; border: none; border-radius: 50px;
            font-size: 1rem; font-weight: bold; cursor: pointer; display: none; z-index: 5;
        }

        .modal {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.7); z-index: 100; align-items: center; justify-content: center;
            backdrop-filter: blur(5px);
        }
        .modal-icerik {
            background: white; padding: 30px; border-radius: 20px; max-width: 85%;
            text-align: center; max-height: 80vh; overflow-y: auto;
        }
    </style>
</head>
<body>

    <section id="katman1" class="katman">
        <div id="baslik" class="kocaman-yazi">HOŞ GELDİN SEVGİLİM! ❤️</div>
        <div id="sayac" class="geri-sayim"></div>
        <button id="btn1" class="devam-btn" onclick="gec(2)">DEVAM ➡️</button>
    </section>

    <section id="katman2" class="katman">
        <div class="mektup-kutu">
            <h2 style="color: #ff4d6d;">Sana Sözlerim... 💌</h2>
            <p id="benim-paragrafim" style="font-size: 1.1rem; color: #555;">
                deneme yazısı deneme yazısı
            </p>
        </div>
        <button id="btn2" class="devam-btn" style="display: block;" onclick="gec(3)">ŞİİRLERE GEÇ ➡️</button>
    </section>

    <section id="katman3" class="katman">
        <h2 style="color: #ff4d6d;">30 Gün, 30 Şiir ✨</h2>
        <div class="siir-grid" id="grid"></div>
    </section>

    <div id="modal" class="modal" onclick="kapat()">
        <div class="modal-icerik">
            <p id="siirMetni" style="font-size: 1.1rem; white-space: pre-line; color: #555;"></p>
            <p style="color: #ff4d6d; margin-top: 15px;">❤️</p>
        </div>
    </div>

    <script>
        window.onload = () => {
            setTimeout(() => {
                document.getElementById('baslik').style.display = 'none';
                baslatSayac();
            }, 2000);
        };

        function baslatSayac() {
            let s = 3;
            const ekran = document.getElementById('sayac');
            let interval = setInterval(() => {
                ekran.innerText = s;
                if (s === 0) {
                    clearInterval(interval);
                    ekran.innerHTML = "İYİ Kİ DOĞDUN! <br> 🎉🐱🌹";
                    ekran.style.fontSize = "2.5rem";
                    konfeti();
                    document.getElementById('btn1').style.display = 'block';
                }
                s--;
            }, 1000);
        }

        function konfeti() {
            var end = Date.now() + (3 * 1000);
            (function frame() {
                confetti({ particleCount: 3, angle: 60, spread: 55, origin: { x: 0 } });
                confetti({ particleCount: 3, angle: 120, spread: 55, origin: { x: 1 } });
                if (Date.now() < end) { requestAnimationFrame(frame); }
            }());
        }

        function gec(n) {
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
            const m = document.getElementById('siirMetni');
            m.innerText = siirler[i];
            document.getElementById('modal').style.display = 'flex';
        }

        function kapat() { document.getElementById('modal').style.display = 'none'; }
    </script>
</body>
</html>
