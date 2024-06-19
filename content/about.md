+++
title = "關於我們"
+++

---

<style>

.partnercomcontainer {
    height: 24rem;
}

.partnercomelement {
    width: auto;
    height: 33.333333%;
}

@media (min-aspect-ratio: 7/10) {
    .visioncontainer {
        display: flex;
        flex-direction: row;
    }

    .visionelement {
        width: 33.333333%;
        border-left-width: 0.25rem;
        border-left-color: transparent;
        border-right-width: 0.25rem;
        border-right-color: transparent;
    }
}    

@media (min-width: 930px) {
    .partnercomcontainer {
        display: flex;
        flex-direction: row;
        height: 8rem;
    }

    .partnercomelement {
        width: 33.333333%;
        height: auto;
    }
}

</style>


### 公司簡介

<!--div style="width: 440px;"-->

![](/img/introduction.svg)

台灣智能漁電科技股份有限公司，  
立足台灣，深耕地方。  
結合各方專家與顧問團隊，  
主要經營項目包含：
- 智：企業智慧化轉型整合服務
- 能：再生能源規劃、憑證與碳權顧問服務
- 漁：農漁養殖技術與顧問服務
- 電：綠電交易等主要核心業務。

<!--/div-->

### 公司願景

<div class="visioncontainer">
<div class="visionelement">
<center>
<div class="w-1/2">

![](/img/vision1.svg)

</div>

### 漁電雙贏

</center>

**投資者取得建置太陽能土地，穩定售電20年；維持原養殖戶權益，維持原養殖戶持續養殖；降地養殖戶場域租金支出、改善養殖設施與場域維護費用。**

</div>
<div class="visionelement">
<center>
<div class="w-1/2">

![](/img/vision2.svg)

</div>

### 產業商機與轉型

</center>

**帶動農業產業供應鏈商機，促進養殖產業轉型；提升產業價值。**

</div>
<div class="visionelement">
<center>
<div class="w-1/2">

![](/img/vision3.svg)

</div>

### 土地發展永續

</center>

**一地多用、農漁為本綠能加值綠能之外，同時兼顧漁業經濟產值。**

</div>
</div>

台灣智能漁電科技包括聯盟合作成員，以碳中和最佳化方案與ESG永續觀點，為各企業提供最專業的技術服務與顧問服務。

### 經營理念

![](/img/philosophy.svg)

我們致力於永續創新與綠色轉型，透過智慧整合提高效率，同時減少碳足跡。作為責任領導者，我們透明溝通，與客戶和合作夥伴共同探索可持續發展解決方案，分享知識，提升社會對綠色轉型的認識。我們定期評估業務對環境的影響，選擇理念相符的合作夥伴，並積極社會貢獻，以實際行動推動產業鏈的綠色發展，朝淨零目標邁進。

### 合作夥伴

<div id="partnerdiv">
</div>

<script>
    const partners = [{
        img: "hsinjing.png",
        link: "http://www.hsinjing-holding.com.tw/",
    }, {
        img: "tainewenergy.png",
        link: "https://www.tai-newenergy.com/",
    }, {
        img: "btc.png",
        link: "https://www.btc.com.tw/",
    }, {
        img: "nexcom.gif",
        link: "https://www.nexcom.com.tw/",
    }, {
        img: "guangteng.png",
        link: "https://www.twincn.com/item.aspx?no=83456687",
    }, {
        img: "bullwill.jpeg",
        link: "https://www.bullwill.com.tw/",
    }, {
        img: "wpd.svg",
        link: "https://www.wpd.tw/",
    }, {
        img: "ntut.png",
        link: "https://incu.ntut.edu.tw/",
    }, {
        img: "ncku.jpeg",
        link: "https://www.facebook.com/YourZeroCarbon/",
    }];
    
    const partnerdiv = document.getElementById("partnerdiv");
    var partnerrows = [];
    var partnercols = [];

    for (let i = 0; i < partners.length; i++) {
        let colpartner = document.createElement("div");
        let ppartner = document.createElement("p");
        ppartner.style.marginTop = '20px';
        ppartner.style.marginBottom = '20px';
        let apartner = document.createElement("a");
        apartner.href = partners[i].link;
        let imgpartner = document.createElement("img");
        imgpartner.style.marginTop = '0px';
        imgpartner.style.marginBottom = '0px';
        imgpartner.src = `/img/partnercom/${partners[i].img}`;

        colpartner.appendChild(ppartner).appendChild(apartner).appendChild(imgpartner);

        partnercols.push(colpartner);
    }
    
    function setpartner() {
        let colnum = Math.max(Math.floor(partnerdiv.offsetWidth / 370), 1);
        let rownum = Math.floor((partners.length - 1) / colnum) + 1;

        for (let i = 0; i < partnerrows.length; i++) {
            partnerrows[i].className = "";
        }

        for (let i = 0; i < rownum; i++) {
            if (partnerrows.length <= i) {
                partnerrows.push(partnerdiv.appendChild(document.createElement("div")));
            }
            for (let k = 0; k < colnum; k++) {
                let index = i * colnum + k;
                if (index < partners.length) {
                    let img = partnercols[index].getElementsByTagName("img")[0];
                    partnerrows[i].appendChild(partnercols[index]);
                    partnercols[index].className = "";
                    img.className = "";
                    if (colnum > 1 || img.naturalWidth / img.naturalHeight * 88 < partnerdiv.offsetWidth) {
                        partnerrows[i].classList.add("flex");
                        partnerrows[i].classList.add("flex-row");
                        partnerrows[i].classList.add("h-32");
                        partnercols[index].classList.add("flex");
                        partnercols[index].classList.add("flex-row");
                        partnercols[index].classList.add(`w-1/${colnum}`);
                        img.classList.add("h-full");
                        img.classList.add("max-w-full");
                    } else {
                        img.classList.add("w-full");
                    }
                }
            }
        }
    }
    window.addEventListener("load", setpartner);
    window.addEventListener("resize", setpartner);
    // w-1/1 w-1/2 w-1/3 w-1/4
</script>


