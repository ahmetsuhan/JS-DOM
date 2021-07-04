# JS-DOM <a name="top"></a>
JS-DOM-NOTES

## Events --> <a href="#jsdom-events">Click</a>

## Methods

1-) document.doctype : Belge döküman türü referansını elde etmek için kullanılır. Eğer ki belgenin doctypeını öğrenmek istiyorsak bu methodu kullanmamız yeterli olacaktır.

      let name = document.doctype.name;
        console.log(name); --> HTML
     
2-) document.documentElement : HTML tagının referansını element nesnesi halinde elde etmek için kullanılır.

      let name = document.documentElement;
        console.log(name);

        let name2 = document.documentElement.nodeName;
        console.log(name2); --> HTML

3-) implementation : Belge ile ilgili DOM implementatşon arayüzünden türetilmiş bir DOM implementation nesnesi referansını bool veri türünde elde etmek için kullanılır.

      let process = document.implementation;
      document.getElementById("res").innerHTML = process.hasFeature("HTML", "1.0");

4-) document.body :  body : Belge içerisindeki body tagının referansını elde etmek için kullanılır.

       let body = document.body;
       console.log(body);

5-)head :  head : Belge içerisindeki head tagının referansını elde etmek için kullanılır.
      
        let head = document.head;
        console.log(head);
      
6-)characterSet : Belgenin karakter kodlamasının referansını elde etmek için kullanılır.
      
      let res = document.characterSet;
      console.log(res);
      
7-)document.inputEncoding : Belgenin karakter kodlamasının referansını elde etmek için kullanılır.

      let res = document.inputEncoding;
      console.log(res); --> UTF-8
      
8-) document.title : Belge içerisindeki title tagının referansını almak için kullanılır.

       let title = document.title;
       console.log(title);
       
9-)  document.compatMode :Belgenin tarayıcı tarafından hangi modda çalıştırıldığının referansını elde etmek için kullanılır.

       --> BackCompat : tuhaf veya rastlantı modu. birşeylerde problem var demektir 
       --> CSS1compat : standar/normal mod. bunu alırsak problem yok demektir
      
       let res = document.compatMode;
       console.log(res);

10-) document.documentMode : Belgeyi oluşturmak için tarayıcı tarafından kullanılan modun referansını elde etmek için kullanılır. sadece (Internet Explorer) için geliştirilmiş           bir methodtur.

        let res = document.documentMode;
        console.log(res);

11-) document.defaultView : Belgenin window referansını elde etmek için kullanılır.

         let res = document.defaultView;
        console.log(res);

12-)document.documentURI : Belge sayfasının URI(uniform resource indentifier) adresi referansının elde etmek için kullanılır.
      (Dosyanın çalıştığı yolu almak istiyorsak bunu kullan.)
      
      let res = document.documentURI;
      console.log(res); --> index.html:24 http://127.0.0.1:5500/index.html gibi.

13-) document.location : document.location : Belge url(uniform resource locator) adresi referansını elde etmek için ve ayarlamak için kullanılır.
      
         let res = document.location;
        console.log(res);

        //// 
        let resHref = res.href;
        console.log(resHref);

        /*ayarlam işlemi */
        //let islem = document.location.href = "https://www.google.com.tr"; bunu açarsan google gider :D

        /*mail gönderimi için */
        //let islem2 = document.location.href = "mailto:ahmetsuhanoka0@gmail.com";

        //Döküman içerisinde hareketlilik sağlamak kullanılabilir.(kaydırma istenilen yere gitme fln.)
            
14-)document.baseURI :  Belgenin mutlak url(uniform resource locator) adresi referansını elde etmek için kullanılır.
      
        let res = document.baseURI;
        console.log(res);

15-)document.URL : Belgenin tam url(uniform resource locator) adresi referansını elde etmek için kullanılır.

       let res = document.URL;
        console.log(res);

16-) document.domain : Belgenin domain adı referansını elde etmek için kullanılır.

         let res = document.domain;
        console.log(res);

17-) document.lastModified : Belgenin en son güncelleme tarihini ve saatinin referansını elde etmek için kullanılır.
      
18-)  document.readyState : Belge içeriğinin tarayıcı tarafından yüklenme durumu değeri referansını elde etmek için kullanılır.

         return value :
         -complete
         -loading
         
19-) document.designMode : Belgenin çalışma anında düzenlenebilir olup olmadığı referansını elde etmek için kullanılır.

       on --> dönerse belge düzenlenebilir demek.
       off --> dönerse düzenlenemez demektir.
       inherit --> dönerse düzenlenemez. 

20-)document.hasFocus() : Belge odağının olup olmadığı referansını elde etmek için kullanılır. BOOL veri tipi döner. Örneğin başka bir yer tıkladığımda false döner.
      sayfa odağı içerisinde tru döner. !!!

       let res = document.hasFocus();
        console.log(res);

21-) document.activeElement : Belge içerisindeki seçili veya odaklanılmış elemanın referansını elde etmek için kullanılır.

      const body = document.querySelector("body");

        const findActiveElement = () => {
            let res = document.activeElement;
            console.log(res);

        }
        const writeActiveElementName = () => {
            let res = document.activeElement.tagName;
            console.log(res);
        }
        body.addEventListener("click", findActiveElement);
        body.addEventListener("click", writeActiveElementName);

22-) document.anchors : Bu method kaldırılmaya çalışıyor ve tavsiye edilmiyor. kullanma!
     detaylı bilgi için <a  href="https://developer.mozilla.org/en-US/docs/Web/API/Document/anchors">TIKLA</a>
     
23-)document.links : document.links : Belge içerisindeki tüm linklerin referanslarını elde etmek için kullanılır. Referanslar birden fazla ise herbir link referansı döngü ile         elde edilebilir.

      let allLinks = document.links; // let allLinks = document.getElemenByTagName("a");

24-) document.scripts : Belge içerisindeki script tagına sahip olan tüm elemnaların referanslarını elde etmek için kullanılır.

      let scripts = document.scripts; 

25-) document.embeds :Belge içerisindeki embed veya object tagına sahip tüm elemanların referansını elde etmke için kullanılır.Embed HTML tarafında çok
     kullanılmamalı(img/iframe/video/audio) tagları kullanılmalı.
     
     let embeds= document.embeds;

26-) document.forms :Belge içerisindeki form tagına sahip tüm elemanların referanslarını elde etmek için kullanılır. Eğer birden fazla ise döngü ile herbirine tek tek
     ulaşılabilir.
     
      let forms = document.forms;
      
27-) document.images : Belge içerisindeki img tagına sahip tüm elemanların referanslarını elde etmek için kullanılır. Eğer birden fazla ise döngü ile herbirine tek tek 
     ulaşılabilir. 
      
      var imagesCollection = document.images;

28-)navigator.plugins : Tarayıcıdaki tüm eklentilerin referansını elde etmek için kullanılır. Eklenti referansları birden fazla ise her bir eklenti döngü ile elde edilebilir.
      
      let pluginsColletion = navigator.plugins;

29-) document.createAttribute() : Belge içerisinde istenilen elemena yeni bir nitelik Node u oluşturuyor ve bu oluşturduğu Nodu Node Object olarak geri dönüyor. 

   document.setAttributeNode : createAttribute() metodu ile oluşturulan özellik nodunu node nesnesine uygular.
   
    //butone tıklandığında seçilen h1 tagının color:red olacak :)
      const header1 = document.getElementById("header1");
        const button = document.getElementById("button1");
        button.addEventListener("click", function() {
            header1.setAttributeNode(att);
        });
        let att = document.createAttribute("style");
        att.value = "color:red;";

30-) document.createElement() : Belge içerisinde yeni bir HTML Node oluşturur ve oluşturduğu bu node'u bir NOde object oalrak geri döndürür.

   createTextNode() : document.createElement() methodu ile oluşturulan HTML elemanına metin nodu oluşturur ve oluşturduğu bu Node'u Node Object olarak geri döndürür.
   
   appendChild() : Bir nodu belirtilecek olan herhangi bir elemanın içerisine en sonda olmak üzere eklemek için kullanılır. 
   
        let body = document.querySelector("body");
        let div = document.createElement("div");
        let textNode = document.createTextNode("Ahmet Suhan OKA");
        div.appendChild(textNode);
        body.appendChild(div);

31-) document.createComment(): Belge içerisine yeni bir açıklama Node'u oluşturur ve oluşturduğu bu Node'u bir Node object olarak geriye döndürür.

      const areaDiv = document.querySelector("#area");
        let comment = document.createComment("Comment ekledim :)");
        areaDiv.appendChild(comment);
        
32-) addeventListener("eventAdi",function) : Belgeye Event Listener eklemek için kullanılır yani olay ekleriz. İşaretşlenen veya dinlenen olay belgede gerçekleştirilecek olur 
      ise belirtilecek olan fonksiyon veya fonksiyonlar çalışır.
      
      resultArea.addEventListener("mouseover", ornek1);
       resultArea.addEventListener("click", function(){});


33-) removeEventListener("eventAdi",function) : Belgeye addEventListener ile eklenmiş olan event'tı silmek için kullanılır.

      kaldırılacakEleman.removeEventListener("eventAdi",kaldırılacakFonksiyonAdi);
      
34-) dir : Belge içerisindeki metinlerin yazılış yönü referansını elde etmek için kullanılır. Ayrıca Belge içerisindeki metinlerin yazılış yönünün atamasını ayarlamak için de
     kullanılır.
     
        1-)ltr --> left to right
        2-)rtl --> right to left
     
        let area3 = document.getElementById("area3")
        console.log(area3.dir); --> rtl
        area3.dir = "ltr";
        console.log(area3.dir); --> ltr

35-) open() : Belge içerisinden yeni bir HTML çıktı akışı açmak için kullanılır.

   close() : Open metodu ile açılan HTML çıktı akışını kapatmak/sonlandırmak için kullanılır.
   
       Parametreler: 
        1-) Dosyanın Mime türü
        2-) Geçmiş aktarımı
        
         function ornek1() {

            let islen = window.open(); // yeni sayfada açmak için
            islem.document.open("text/html", "replace"); //geçmiş hatırlanır
            islem.document.write("burası yeni");
            islem.document.close();
        }
        
36-) document.styleSheets :Belge üzerinde etkisi olan tüm stil sayfalarının nesne referansını elde etmek için kullanılır. Eğer stil sayfası referansları birden fazla ise her
     style sayfası referansı döngü ile elde edilebilir.
     
      let styleSheets = document.styleSheets;

37-) document.adoptNode() : Belge içerisine başka bir belgeden node eklemek için kullanılır. Ekelenecek olan Node un varsa tüm alt node'larıda işleme dahil edilerek ilgili tüm
      nodlar diğer belgeden kaldırılır. 

38-) document.importNode() : Belge içerisine başka bir belgeden node eklemek için kullanılır. Eklenecek olan node un varsa tüm alt node ları da eklenir.

39-) document.normalize() : Belge içerisindeki boş text node larını kaldırarak bitişik düğüme katılmasını sağlar.

40-) document.cookie : 

       Cookie Yapısı :
        1-)Çerez ADI : 
        2-):erez değeri: 
        3-)Ceçer yaşam süresi
        4-)Path
        cookie adı = Cookie değeri; Cooki yaşam süresi ; Path

41-) Atribute üzeinde --> lenght() : Belge içerisindeki HTML elemanına eklenmiş olan attribute lerin sayısını elde etmek için kullanılır.
      
      let asdDivAttributeLength = asdDiv.attributes.length;

42-) attributes[index].name : Belge içerisindeki HTML elemanına eklenmiş olan attribute adı referansını elde etmek için kullanılır. HTML elemanı içerisindek, çzellik sayısı birden fazla ise her
      bir özellik adı referansı döngü ile elde edilebilir.
      
            const asdDiv = document.getElementById("asd");
            let asdDivAttrName = asdDiv.attributes[0].name;
            console.log(asdDivAttrName);
            console.log(asdDiv.getAttributeNames());
            

43-) attributes[index].value : Belge içerisindeki HTML elemanına eklenmiş olan attribute değerinin referansını elde etmek için kullanılır. HTML elemenanı içerisindeki attribute 
      sayısı birden fazl ise her bir attribute değeri döngü ile elde edilebilir.
      
          let asdDiv = document.getElementById("asd");
            for(let i = 0 ; i< asdDiv.attributes.length; i++){
                console.log(asdDiv.attributes[i].value);
            }  

44-)  attributes[index].specified : Belge içerisindeki HTML elemanına Her hangi bir attribute nin klenip eklenmediğini referansını bool veri türünde elde etmek için  kullanılır.

            let asdDiv = document.getElementById("asd");
            console.log(asdDiv.attributes[0].specified);
            console.log(asdDiv.attributes.item(1).specified);
            let res = asdDiv.getAttributeNode("id").specified;
            console.log(res);
            let res2 = asdDiv.getAttributeNode("class").specified;
            console.log(res2);

45-)  attributes.getNamedItem() : Belge içerisindeki HTML elemanına eklenmiş olan attribute Node u referansını elde etmek için kullanılır.

      <div id="asd" class="container" style="color:red;" ></div>
      let asdDiv = document.getElementById("asd");
      console.log(asdDiv.attributes.getNamedItem("class"));
      console.log(asdDiv.attributes.getNamedItem("id"));


46-)  attributes.setNamedItem("setEdilecekAttr","setValue") : Belge içerisindeki HTML elemanına eklenmiş olan attribute Node u referansını elde etmek için kullanılır.

      let asdDiv = document.getElementById("asd");
      let asdDivClassAttrName = asdDiv.attributes.getNamedItem("class");
      console.log(asdDivClassAttrName); --> ilkte container dı aşağıdaki işlemi yapınca Ahmet oldu
      asdDiv.setAttribute("class","Ahmet");
      console.log(asdDiv.attributes.getNamedItem("class")); --> Ahmet oldu
      
      /*dassssssssssssssssssssssssssssss*/

      let newAttribute =document.createAttribute("style");
      newAttribute.value = "color:blue";
      let asdDiv2 = document.getElementById("asd2");
      asdDiv2.attributes.setNamedItem(newAttribute);
      console.log(asdDiv2);

      

47-)    attributes.removeNamedItem("silinecekAttr") : Belge içerisindeki HTML elemanına eklenmiş olan attribute Node unu kaldırmayı sağlıyor. 

            let div1 = document.querySelector("#asd");
            let div2 = document.querySelector("#asd2");
            let a =(div1.attributes.getNamedItem("style"));
            console.log(a);
            div1.attributes.removeNamedItem("style");
            console.log(div1.hasAttribute("style"));
            

48-) attributes.item() : Belge içerisindeki HTML elemanına eklenmiş olan attribute Node unun referansını elde etmek için veya ayarlamak için kullanılır. Eğer attribute sayısı
      birden fazla ise döngü ile ulaşılabilir. 
      
      let div1 = document.getElementById("asd");
      let div2 = document.getElementById("asd2");

      console.log(div1.attributes.item("div"));
      console.log(div1.attributes.item(1));
      for( let i = 0 ; i<div2.attributes.length;i++){
      console.log(div2.attributes.item(i));
      }
 
 
 49-) style : Belge içerisindeki HTML elemanına veya elemanlarına CSS (Cascading Style Sheets) özellikleri ve değerleri eklemen veya referansını elde etmek içi kullanılır.
 
      let div1 = document.getElementById("asd");
      console.log(div1.style);
      console.log(div1.style[0]);
      console.log(div1.style.item(2));
      for(let i = 0 ; i< div1.style.length; i++){
          console.log(div1.style[i]);
          console.log(div1.style.item(i));
            }
 
 50-) accesskey : Belge içerisindeki herhangi bir HTML elemanına atanmış olan accessKey değerini elde etmek veya ayarlamak için kullanılır.<a href="https://developer.mozilla.org/en-us/docs/Web/HTML/Global_attributes/accesskey">Click more info</a>
      
      let a1 = document.getElementById("a1");
      let a2 = document.getElementById("a2");
      let a1AccessKey= a1.accessKey;
      let a2AccessKey= a1.accessKey;
      let spanBir = document.getElementById("bir");
      let spanIki = document.getElementById("iki");
      spanBir.innerHTML =  "    "+a1AccessKey;
      spanIki.innerHTML = "    "+a2AccessKey;

      /* AccessKey atama */

      a1.accessKey ="5";
      console.log(a1.accessKey);

 
 51-) focus : Belge içerisindeki herhangi bir HTML elemanına odaklanmak için kullanılır.
 
      var a = document.getElementById("link1");
         a.focus(); 
      
 
 52-)  blur() : belge içerisinde odaklanılmış herhangi bir HTML elemanının odağından çıkmak için kullanılır.
 
      document.getElementById("baglanti2").blur();
 
 53-)  classList = belge içerisindeki herhangi bir HTML elemanına atanmış olan class listesi isimlerini elde etmek veya ayarlamak için kullanılır.
      
       item : class adını döndürür
        length : class sayısını döner
        add : class adı ekler
        remove : class adı kaldırır
        toggle : class adı ekler/kaldırır
        contains : class adı arar
      
            <div id="sonucAlani" class="bir">Js Öğreniyorum</div>
                <script>
            let sonucAlaniClassLists= document.getElementById("sonucAlani").classList;
            console.log(sonucAlaniClassLists);

            document.getElementById("sonucAlani").classList="bir iki uc dort";
            let sonucAlaniDiv = document.getElementById("sonucAlani");
            for(let i = 0 ; i<sonucAlaniDiv.classList.length;i++){
                console.log(sonucAlaniDiv.classList.item(i));
            }

            function classListEkle(){
                sonucAlaniDiv.classList.add("bes");
            }
            function classListSil(className){
                sonucAlaniDiv.classList.remove(className);
            }
            console.log(sonucAlaniDiv.classList);

            console.log(sonucAlaniDiv.classList.contains("bir"));
            function classListToggle(...args){
               for (let index = 0; index < args.length; index++) {
                   const element = args[index];
                sonucAlaniDiv.classList.toggle(element);

               }
               console.log(sonucAlaniDiv.classList);
            }


   54-) className = belge içerisindeki herhangi bir HTML elemanına atanmış olan class  isimlerini elde etmek veya ayarlamak için kullanılır.
   
            
            let sonucAlaniDiv= document.getElementById("sonucAlani");

            console.log(sonucAlaniDiv.className);

   55-) nodeType : belge içerisindeki herhangi bir Node un türünü elde etmek için kullanılır. <a href="https://developer.mozilla.org/en-us/docs/Web/API/Node/nodeType">More info <a>
      
        ELEMENT_NODE --> 1  --> An Element node like <p> or <div>.
        ATTRIBUTE_NODE   -->2  --> 	An Attribute of an Element.
        TEXT_NODE -->3 --> The actual Text inside an Element or Attr.
        CDATA_SECTION_NODE (CDATA kesit düğümü) --> 4 --> A CDATASection, such as <!CDATA[[ … ]]>.
        ENTITY_REFERANCE_NODE (Varlık referansı düğümü) --> 5 --> An XML Entity Reference node, such as &foo;. Removed in DOM4.
        ENTITY_NODE (Varlık düğümü) -->6 --> 	An XML <!ENTITY …> node. Removed in DOM4.
        PROCESSION_INSTRUCTION_NODE (işlem yönergesi düğümü) -->7 --> A ProcessingInstruction of an XML document, such as <?xml-stylesheet … ?>.
        COMMENT_NODE --> 8 --> A Comment node, such as <!-- … -->.
        DOCUMENT_NODE --> 9  --> A Document node.
        DOCUMENT_TYPE_NODE --> 10 --> A DocumentType node, such as <!DOCTYPE html>.
        DOCUMENT_FRAGMENT_NODE--> 11 --> A DocumentFragment node.
        NOTATION_NODE --> 12  --> 	An XML <!NOTATION …> node. Removed in DOM4.
      
       var dugumbul	=	document.getElementById("OrnekBir").nodeType;
            
   
   56-) nodeName : Belge içerisindeki herhangi bir node'un (düğümün) adını elde etmek için kullanılır.
   
            document.getElementById("deneme").nodeName;
   
   57-) nodeValue: Belge içerisindeki herhangi bir node un değerini elde etmek için kullanılır. <a href="https://developer.mozilla.org/en-us/docs/Web/API/Node/nodeValue">More Info</a>
   
      document.getElementById("selector").childNodes[0].nodeValue;
          
   
   58-) childElementCount : Belge içerisindeki herhangi bir HTML elemanının içerdiği alt elemnalarının sayısını elde etmek için kullanılır.
   
      document.getElementById("selector").childElemmentCount;
   
   59-) hasChildNodes : Belge içerisindeki herhangi bir HTML elemanının alt node larının olup olmadığını kontrol ederek bool veri türünde sonucu geri döner.
   
       document.getElementById("id1").hasChildNodes(); --> return value would be true or false
   
   60-) children 	: Belge içerisindeki herhangi bir HTML elemanının içerdiği alt elemanları elde etmek için kullanılır.
            
            let div = document.getElementById("id1");
            let divChildren = div.children;
            console.log(divChildren); 
            for(let i = 0 ; i<divChildren.length; i++){
                console.log(divChildren[i]);
            }
      
   61-) childNodes : Belge içerisindeki herhangi bir HTML elemanının içerdiği alt node'ları (düğümleri) elde etmek için kullanılır.
   
       document.getElementById("selector").childNodes;
   
   62-) firstChildElement : Belge içerisindeki herhangi bir HTML elementinin içerdiği ilk elemanı elde etmek için kullanılır.
   
      let div1 = document.getElementById("id1");
      let div1FirstElemenChild = div1.firstElementChild;
      console.log(div1FirstElemenChild);
   
   63-) firstChild :  Belge içerisindeki herhangi bir HTML elementinin içerdiği ilk alt nodu'u elde etmek için kullanılır.
   
      let div1 = document.getElementById("id1");
      let div1FirstChild = div1.firstChild;
      console.log(div1FirstChild);
   
   64-) lastElementChild : Belge içerisindeki herhangi bir HTML elementinin içerdiği son elemanı elde etmek için kullanılır.
   
      let div1 = document.getElementById("id1");
      let div1LastElementChild = div1.lastElementChild;
      console.log(div1LastElementChild);
   
   65-) lastChild : Belge içerisindeki herhangi bir HTML elemanının içerisindeki son alt node'u (düğümü) elde etmek için kullanılır.
   
      let div1 = document.getElementById("id1");
      let div1LastChild = div1.lastChild;
      console.log(div1LastChild);
   
   66-) nextElementSibling : Belge içerisindeki herhangi bir HTML elemanının içerisindeki aynı seviyede yani kardeş olan elemanlardan, belirtilecek olan elemandan sonra gelen
        ilk elemanı elde etmek için kullanılır.
        
            let div1NextElementSibling = div1.nextElementSibling;
            
   
   67-) nextSibling : Belge içerisindeki herhangi bir HTML elemanının içerisindeki aynı seviyede yani kardeş olan node'lardan (düğümlerden), belirtilecek olan node'dan 
   (düğümden) sonra gelen ilk node'u (düğümü) elde etmek için kullanılır.
   
      let div1NexSibling = div1.nextSibling;
   
   68-) previousElementSibling : Belge içerisindeki herhangi bir HTML elemanının içerisindeki aynı seviyede yani kardeş olan elemanlardan, belirtilecek olan elemandan önce gelen
        ilk elemanı elde etmek için kullanılır.
        
            let div1PreviousElementSibling = div1.previousElementSibling;

   69-) previousSibling : Belge içerisindeki herhangi bir HTML elemanının içerisindeki aynı seviyede yani kardeş olan node'lardan (düğümlerden), belirtilecek olan node'dan 
        (düğümden) önce gelen ilk node'u (düğümü) elde etmek için kullanılır.
        
        let div1PreviousSibling = div1.previousSibling;

   
   70-) offsetParent : Belge içerisindeki herhangi bir HTML elemanının içerisinde mutlak olarak konumlandırıldığı ilk elemanın referans nesnesini elde etmek için kullanılır.
   
            let div1OffsetParent = div1.offsetParent;

   
   71-) contains() : Belge içerisindeki herhangi bir node'un başka bir node'un alt node'u olup olmadığının bilgisini bool veri türünde geri döner.
   
            let div1 = document.getElementById("div1");
            let p1 = document.getElementById("p1");
            console.log(div1.contains(p1)); 
   
   72-) textContent :  Belge içerisindeki herhangi bir node'un textNode larının değerini elde etmek için veya ayarlamak
        için kullanılır.
   
      const foo = () => {
            var deger = document.getElementById("div1").textContent;
            document.getElementById("res").innerHTML = deger;
        }
        const foo2= () => {
            var deger = document.querySelector("button").textContent;
            document.getElementById("res").textContent=deger;
        }
   
   73-) compareDocumentPosition() : Belge içerisinde bulunan node'ların birbirlerine göre konum değerlerini elde etmek için kullanılır.
   
        Return Values: 
        2 : Belirtilen ilk node belirtilen ikinci düğümden sonra
        4 : Belirtilen ilk node belirtilen ikinci düğümden önce
        
         let Js = document.getElementById("Js"); 
          let Css = document.getElementById("Css");
          let val = Js.compareDocumentPosition(Css);
          console.log(val); //4
   
   74-) Element.parenElement : Belge içerisindeki herhangi bir html elemanının bir üst elemanını elde etmek için kullanılır.
   
         let divJs = document.getElementById("Js");
         let divReact = document.getElementById("React");
         let divHooks = document.getElementById("Hooks");

         let divJsParent = divJs.parentElement;
         let divReactParent = divReact.parentElement;
         let divHooksParent = divHooks.parentElement;

         let divReactParentParent = divReact.parentElement.parentElement;
         let divHooksParentParentText = divHooks.parentElement.parentElement.textContent;
         console.log(divHooksParentParentText);
   
   75-) parentNode : Belge içerisindeki herhangi bir node'un bir üst node'unu elde etmek için kullanılır.
   
      let divJs = document.getElementById("Js");
      let divJsParentNode = divJs.parentNode;
   
   76-) appendChild() : Bir node'u belge içerisinde belirtilecek olan herhangi bir elemanın içerisine ensonda olmak üzere eklemek için kullanılır.
   
      const ekle=()=>{
      let pYazi = document.createElement("p");
       pYazi.textContent="Ahmet SUhan Oka ";
      let resDiv = document.getElementById("res");
       resDiv.appendChild(pYazi);
      }

   
   77-) removeChild() : Belge içerisindeki herhangi bir HTML elemanının içerdiği node'u kaldırmak/silmek için kullanılır.
   
       const ekle=()=>{
          let pYazi = document.createElement("p");
        pYazi.textContent="Ahmet SUhan Oka ";
          resDiv.appendChild(pYazi);
      }

      const sil=() =>{
      let resDiv = document.getElementById("res");
      a = resDiv.childNodes;
           resDiv.removeChild(a[0]);
      console.log(a);

      }

      const sil2=() =>{
      let resDiv = document.getElementById("res");
      a = resDiv.childNodes;
           resDiv.removeChild(a[a.length-1]);
      console.log(a);

      }
   
   78-) replaceChild(new,old) : Belge içerisindeki herhangi bir HTML elemanının içerdiği node'u değiştirmek için kullanılır.
   
      const degistir=() =>{
      let resDiv = document.getElementById("res");
      let a = resDiv.children;

      let newElement = document.createElement("p");
      let newTextNode = document.createTextNode("ben yeniyim");
      newElement.appendChild(newTextNode);
      resDiv.replaceChild(newElement,resDiv.children.item(0));
      }
   
   79-) cloneNode() : Belge içerisindeki herhangi bir HTML elemanının içerdiği node'u  kopyalamak için kullanılır.
            
            let a = document.getElentById("selector").cloneNode(true); 
            
             let resDiv = document.querySelector("#res");
              const copy=()=>{
              let copyItem = resDiv.children.item(1).cloneNode(true);
              resDiv.firstChild.textContent=copyItem.textContent;
              }
   
   80-) insertBefore(new,place) : Bir node'u belge içerisndeki belirtilecek olan herhangi bir node'un  önüne eklemek için kullanılır.
   
            new: yeni node
            place: yeni node u bu parametrenin önüne ekliyoruz
            
       const insertBefore2 = ()=>{
        let newElement = document.createElement("p");
        let textNode = document.createTextNode("Eklendim :D");
        newElement.appendChild(textNode);

        let resDivP1 = document.querySelector("#res #p1");
        document.getElementById("res").insertBefore(newElement,resDivP1);
    }
   
   81-) hasAttribute() : Belge içerisindeki herhangi bir HTML elemanının belirtilen özelliğe sahip olup olmadığını kontrol ederek, bool veri türünde sonucu geriye döndürür.
   
        let div = document.querySelector("#res");
          let a = div.hasAttribute("class");
          let b = div.hasAttribute("style");
          let c= div.hasAttributes();
          console.log(a);
          console.log(b);
          console.log(c);
   
   82-) hasAttribute() : Belge içerisindeki herhangi bir HTML elemanının herhangi bir özelliğe sahip olup olmadığını kontrol ederek, bool veri türünde sonucu geriye döndürür.
            
            let a = document.getelementById(".res");
            let b= a.hasAttributes();
            console.log(b);
            
   83-) getAttribute() : Belge içerisindeki herhangi bir HTML elemanının belirtilen özelliğinin değerini elde etmek için kullanılır. Eğer elementte belirtilen attribute yoksa
            null değer geri döner.
   
            let div = document.getElementById("selector");
            let divClassAttr = div.getAttribute("class");
            console.log(dicClassAttr);
   
   84-) getAttributeNames() : Belge içerisindeki herhangi bir HTML elementinin sahip olduğu attribute isimlerini elde etmek için kullanılır.
   
            let div = document.getElementById("selector");
            let a = div.getAttributeNames();
            console.log(a); --> ["style","id","class"]

   
   85-) getAttributeNode() : Belge içerisindeki herhangi bir HTML elemanının belirtilen özellik node'unun değerini elde etmek veya ayarlamak için kullanılır.
            document.getElementById("selector").getAttributeNode("attrName").value; ile attribute nin değerini alıp değiştirebilirsin.
            
                let resDiv = document.getElementById("res");
               let a = resDiv.getAttributeNode("style");
               console.log(a);
               let c = resDiv.getAttributeNode("style").value;
            console.log(c);
            resDiv.getAttributeNode("style").value="color:red;";
            console.log(resDiv.getAttributeNode("style"));
   
   86-) setAttribute("attrName","attrValue") : Belge içerisindeki herhangi bir HTML elemanına belirtilen özelliği ve değerini eklemek için kullanılır.
      
            const ekle=() =>{
           let div = document.createElement("div");
           let p = document.createElement("p");
           p.innerText="Ahmet Suhan Oka";

           div.appendChild(p);
           div.setAttribute("style",["color:Red;","border:1px solid red;"]);

           document.body.appendChild(div);
           console.log(div);
            }
   
   87-) setAttributeNode() :  Belge içerisindeki herhangi bir HTML elemanına createAttribute() metodu ile oluşturulan özellik node'unu ve değerini, node object'ine uygulamak
            için kullanılır.
   
             <div id="div">asd</div>

            let styleAttr = document.createAttribute("style");
            let div = document.getElementById("div");
            styleAttr.value="color:white;";
            let classAttr=document.createAttribute("class");
            classAttr.value="AhmetSuhan";
            div.setAttributeNode(styleAttr);
            div.setAttributeNode(classAttr);
            console.log(div);
   
   88-) removeAttribute() : Belge içerisindeki herhangi bir HTML elemanının belirtilen özelliğini kaldırmak/silmek için kullanılır.
   
      <div id="div" class="AhmetSuhan" >asd</div>
     
      let div = document.getElementById("div");
      console.log(div.getAttribute("class")); --> AhmetSuhan
      div.removeAttribute("class");
      console.log(div.getAttribute("class")); --> null
   
   89-) removeAttributeNode() : Belge içerisindeki herhangi bir HTML elemanına getAttributeNode() metodu ile belirtilmiş özellik node'unu, node object'inden kaldırmak / silmek
        için kullanılır.
        
        <div id="div" class="AhmetSuhan" >asd</div>
     
      let div = document.getElementById("div");
      console.log(div.getAttributeNames());
      let divClassAttr = div.getAttributeNode("class");
      console.log(divClassAttr);
      div.removeAttributeNode(divClassAttr);
      console.log(div.getAttributeNames());
   
   90-) clientLeft : Belge içerisindeki herhangi bir HTML elemanının sol kenarlık genişliği değerini elde etmek için kullanılır.Sol border uzunluğunu verir.
   
      document.getElementById("selector").clientLeft;
   
   91-) clientTop : Belge içerisindeki herhangi bir HTML elemanının üst kenarlık yüksekliği değerini elde etmek için kullanılır. Üst border uzunluğunu verir.
   
       document.getElementById("selector").clientTop;
   
   92-) clientWidth : Belge içerisindeki herhangi bir HTML elemanının içerik genişliği değerini elde etmek için kullanılır. 
   
      document.getElementById("selector").clientWidth;
   
      Hesaplama
      Genişlik  :	padding-left + genişlik + padding-right
      Yükseklik :	padding-top + yükseklik + padding-bottom
   
   93-) clientHeight : Belge içerisindeki herhangi bir HTML elemanının içerik yüksekliği değerini elde etmek için kullanılır
   
       document.getElementById("selector").clientHeight;
   
       Hesaplama
       Genişlik  : padding-left + genişlik + padding-right
       Yükseklik : padding-top + yükseklik + padding-bottom
   
   94-) offsetLeft :  Belge içerisindeki herhangi bir HTML elemanının sol üst köşesi ile browser (tarayıcı) penceresinin sol üst köşesi arasındaki yatay uzaklık farkı değerini
        elde etmek için kullanılır.
        
        document.getElementById("selector").offsetLeft;
   
   95-)offsetTop 	: Belge içerisindeki herhangi bir HTML elemanının sol üst köşesi ile browser (tarayıcı) penceresinin sol üst köşesi arasındaki dikey uzaklık farkı değerini
      elde etmek için kullanılır.
      
        document.getElementById("selector").offsetTop;
   
   96-) offsetWidth : Belge içerisindeki herhangi bir HTML elemanının genişlik değerini elde etmek için kullanılır.
   
      document.getElementById("alan").offsetWidth;
      
      Hesaplama :
      Genişlik			:	border-left + padding-left + genişlik + padding-right + border-right;
      Yükseklik			:	border-top + padding-top + yükseklik + padding-bottom + border-bottom;
      
   
   97-) offsetHeight : Belge içerisindeki herhangi bir HTML elemanının yükseklik değerini elde etmek için kullanılır.
   
      document.getElementById("alan").offsetHeight;
      
      Hesaplama :
      Genişlik			:	border-left + padding-left + genişlik + padding-right + border-right;
      Yükseklik			:	border-top + padding-top + yükseklik + padding-bottom + border-bottom;
      
   
   98-) scrollLeft : Belge içerisindeki herhangi bir HTMl elemanının yatay kaydırılma genişliği pixel değerini elde etmek için kullanılır. 
   
            Hesaplama : 
            Yatay (Genişlik) 	:	margin-left + border-left + padding-left + genişlik + padding-right + border-right + margin-right
            Dikey (Yükseklik) 	:	margin-top + border-top + padding-top + yükseklik + padding-bottom + border-bottom + margin-bottom
            
            const area = document.getElementById("area");
            const ex=()=>{
                  console.log(area.scrollLeft);
            }
            const EventListenerHandler=()=>{
                  area.addEventListener("scroll",ex);
            }
            EventListenerHandler();
   
   99-) scrollTop : Belge içerisindeki herhangi bir HTMl elemanının dikey kaydırılma genişliği pixel değerini elde etmek için kullanılır.
   
            Hesaplama : 
            Yatay (Genişlik) 	:	margin-left + border-left + padding-left + genişlik + padding-right + border-right + margin-right
            Dikey (Yükseklik) 	:	margin-top + border-top + padding-top + yükseklik + padding-bottom + border-bottom + margin-bottom
            
            const area = document.getElementById("area");
            const ex=()=>{
                  console.log(area.scrollTop);
            }
            const EventListenerHandler=()=>{
                  area.addEventListener("scroll",ex);
            }
            EventListenerHandler();
   
   100-) scrollWidth : Belge içerisindeki herhangi bir HTMl elemanının toplam yatay kaydırılma genişliği pixel değerini elde etmek için kullanılır.
      
      Hesaplama : 
      Yatay (Genişlik) 	: margin-left + border-left + padding-left + genişlik + padding-right + border-right + margin-right
      Dikey (Yükseklik) : margin-top + border-top + padding-top + yükseklik + padding-bottom + border-bottom + margin-bottom
      
      let a = document.getElementById("selector").scrollWidth;
   
   101-) scrollHeight : Belge içerisindeki herhangi bir HTMl elemanının toplam dikey kaydırılma genişliği pixel değerini elde etmek için kullanılır.
   
      Hesaplama : 
      Yatay (Genişlik)  : margin-left + border-left + padding-left + genişlik + padding-right + border-right + margin-right
      Dikey (Yükseklik)  : margin-top + border-top + padding-top + yükseklik + padding-bottom + border-bottom + margin-bottom
      
      let a = document.getElementById("selector").scrollHeight;

	
   102- document.referrer : previouspage link <a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/referrer" target="_blank">More</a>
	
	The Document.referrer property returns the URI of the page that linked to this page.
	
   103- Element.insertAdjacentHTML(position,text) <a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML" target="_blank">More</a>
	
	positions: 
		beforebegin
		afterbegin 
		beforeend
		afterend
   
## JS DOM Events <--> <a name="jsdom-events"></a><a href="#top">Back to top</a>
   
   1-) onClick() || "click" : Belge içerisindeki herhangi bir elemana mouse ile sol tıklandığında belirtilecek olan fonksiyon çalışır.
   
         let a = document.getElementById("selector");
          a.addEventListener("click",function(){
            //do somethin here
            });
   
   2-) ondblClick() || "dblClik" : Belge içerisindeki herhangi bir elemana mouse (fare) ile çift sol tıklandığında belirtilecek olan fonksiyon çalışır.
   
       Element.addEventListener("dblclick",foo);
   
   3-)onmousedown() || "mousedown" :Belge içerisindeki herhangi bir elemana mouse ile sol veya sağ tıklandığında belirtilecek olan fonksiyon çalışır.
      
      div1.addEventListener("mousedown",foo);
   
   4-) oncontextmenu() || "contextmenu" : Belge içerisindeki herhangi bir elemana mouse ile sağ tıklandığında belirtilecek olan fonksiyon çalışır.
      <a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncontextmenu">More Info</a>
   
       Element.addEventListener("contextmenu",foo);
   
   5-) onmouseover() || "mouseover" : Belge içerisindeki herhangi bir elemanın mouse ile üzerine gelindiğinde belirtilecek olan fonksiyon çalışır.
   
      let divs = document.querySelectorAll("div");
      console.log(divs);
      divs.forEach(e=>{
	e.addEventListener("mouseover",function(e){
		this.style.backgroundColor="#f90";
	});

	e.addEventListener("mouseout",function(e){
		this.style.backgroundColor="red";
	      });
      });
   
   6-) onmouseout || "mouseout" : Belge içerisindeki herhangi bir elemanın mouse ile üzerinden gidildiğinde belirtilecek olan fonksiyon çalışır. <a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseout_event">More Info</a>
   
   	Element.addEventListener("mouseout",foo);
   
   7-) onmouseenter() || mouseenter : Belge içerisindeki herhangi bir elemanın mouse ile kapsama alanına giriş yapıldığında belirtilecek olan fonksiyon çalışır.
   
   	Element.addEventListener("mouseenter",foo);
   
   8-) onmouseleave() || "mouseleave" : Belge içerisindeki herhangi bir elemanın mouse ile kapsama alanından çıkış yapıldığında belirtilecek olan fonksiyon çalışır.
   
   	Element.addEventListener("mouseleave",foo);
   
   9-) onmousemove() || "mousemove": Belge içerisindeki herhangi bir elemanın mouse ile kapsama alanında gezildiğinde belirtilecek olan fonksiyon çalışır.
   
   	Element.addEventListener("mousemove",foo);
   
   10-) onmouseup() || "mouseup" : Belge içerisindeki herhangi bir elemana mouse ile sol basılı duran tıklama bırakıldığında belirtilecek olan fonksiyon çalışır.
   	
	Element.addEventListener("mouseup",foo);
   
   11-) onwheel() || "wheel" : Belge içerisindeki herhangi bir eleman üzerindeyken mouse'un tekerleği yukarı veya aşağı yuvarlandığında belirtilecek olan fonksiyon çalışır.
   
   	Element.addEventListener("wheel",foo);
   
   12-) button : Belge içerisinde mouse ile tıklama event'ı gerçekleştiğinde mouse'un  hangi tuşuna basıldığı değerini geriye döndürür. 
          /*
        0	:	Sol Tuş
        1	:	Orta Tuş & Tekerlek
        2	:	Sağ Tuş
        
        Internet Explorer (8 ve 8 öncesi sürümleri)
        1	:	Sol Tuş
        2	:	Sağ Tuş
        4	:	Orta Tuş & Tekerlek
        */
   	
	MouseEvent.button;
	
	const btn = document.getElementById("btn");

	let div = document.getElementById("res");
	btn.addEventListener("mousedown",function(e){
	    div.innerHTML=e.button;
	});

   
   13-)MouseEvent.buttons : Belge içerisindeki mouse ile tıklama event'ı gerçekleştiğinde mouse'un hangi tuşuna veya tuşlarına basıldığı değerini geriye döndürür.
      
   	Return Values : 
	1	:	Sol Tuş
	2	:	Sağ Tuş
	3	:	Sol Tuş ve Aynı Anda Sağ Tuş
	4	:	Orta Tuş & Tekerlek
	5	:	Sol Tuş ve Aynı Anda Orta Tuş & Tekerlek
	6	:	Sağ Tuş ve Aynı Anda Orta Tuş & Tekerlek
	8	:	4. Tuş
	16	:	5. Tuş
	
	MouseEvent.buttons;
   
   14-)   Event.detail :Belge içerisindeki mouse  ile tıklama event'ı  gerçekleştirildiğinde mouse'a  kaç defa arka arkaya tıklandığı sayısı değerini geriye döndürür. Tıklamayı bıraktığınızda detail değeri sıfırlanır.
   
   	const btn = document.getElementById("btn");

	let div = document.getElementById("res");
	btn.addEventListener("mousedown",function(e){
	   let detail = e.detail;
	   console.log(detail);
	});
   
   	
   
   15-) MouseEvent.screenX : Belge içerisindeki herhangi bir mouse  event'ı gerçekleştiğinde bilgisayar ekranına göre mouse'un yatay konum koordinatının değerini geriye
   	döndürür.
   	
	let screenLog = document.querySelector('#screen-log');
	document.addEventListener('mousemove', logKey);

	function logKey(e) {
	  screenLog.innerText = `
	    Screen X/Y: ${e.screenX}, ${e.screenY}
	    Client X/Y: ${e.clientX}, ${e.clientY}`;
	}

   16-) MouseEvent.screenY : Belge içerisindeki herhangi bir mouse event'ı gerçekleştiğinde bilgisayar ekranına göre mouse'un dikey konum koordinatının değerini geriye döndürür.
   
   	let screenLog = document.querySelector('#screen-log');
	document.addEventListener('mousemove', logKey);

	function logKey(e) {
	  screenLog.innerText = `
	    Screen X/Y: ${e.screenX}, ${e.screenY}
	    Client X/Y: ${e.clientX}, ${e.clientY}`;
	}
   
   17-) MouseEvent.clientX : Belge içerisindeki herhangi bir mouse event'ı gerçekleştiğinde browser penceresine göre mouse'un yatay konum koordinatının değerini geriye döndürür.
   
  	function logKey(e) {
	  screenLog.innerText = `
	    Screen X/Y: ${e.screenX}, ${e.screenY}
	    Client X/Y: ${e.clientX}, ${e.clientY}`;
	}
	
  18-) MouseEvent.clienY : Belge içerisindeki herhangi bir mouse event'ı gerçekleştiğinde browser penceresine göre mouse'un dikey konum koordinatının değerini geriye döndürür
   
	 function logKey(e) {
	  screenLog.innerText = `
	  Screen X/Y: ${e.screenX}, ${e.screenY}
	  Client X/Y: ${e.clientX}, ${e.clientY}`;
         }
	 
   19-) pageX : Belge içerisindeki herhangi bir mouse event'ı gerçekleştiğinde browser penceresine / sayfaya göre mouse'un yatay konum koordinatının değerini geriye
   döndürür.
   
	   let screenLog = document.querySelector('#screen-log');
	document.addEventListener('mousemove', logKey);

	function logKey(e) {
	  screenLog.innerText = `Page X/Y: ${e.pageX}, ${e.pageY}`;
	}
   
   20-) pageY : Belge içerisindeki herhangi bir mouse event'ı gerçekleştiğinde browser penceresine / sayfaya göre mouse'un dikey konum koordinatının değerini geriye döndürür.
   
   	let screenLog = document.querySelector('#screen-log');
	document.addEventListener('mousemove', logKey);

	function logKey(e) {
	  screenLog.innerText = `Page X/Y: ${e.pageX}, ${e.pageY}`;
	}

   
   21-) onkeydown || "keydown" : Belge içerisindeki herhangi bir eleman üzerinde klavyeden herhangi bir tuşa basıldığında belirtilecek olan fonksiyon çalışır.
   
   	Element.addEventListener("keydown",callBackFunc);
   
   22-) onkeypress || "keypress" : Belge içerisinde herhangi bir eleman üzerinde klavyeden bir tuşa basıldığında çalışır.
   
   	Element.addEventListener("keypress",callBackFunc);
   
   23-) onkeyup || "keyup": Belge içerisinde herhangi bir eleman üzerinde klavyeden bir tuşa basılıp bırakıldığında çalışır.
   	
	Element.addEventListener("keyup",callBackFunc);
   
   24-) KeyboardEvent.key : Belge içerisindeki onkeypress, onkeydown, onkeyup gibi klavye eventleri gerçekleştiğinde klavyeden basılan tuşun değeri geriye döndürür. 
   	<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key">Click More Info</a>
   
   		let div=document.getElementById("resArea");
		const getVal =(event) =>{
		   let clickedButton = event.key;
		   div.innerHTML+=clickedButton;
		}
		
		
   25-) KeyboardEvent.location : Belge içerisindeki onkeydown ve onkeyup eventleri gerçekleştiğinde ilgili tuşun klavyedeki konum bilgisi değerini geriye döndürür.
   
   	KeyboardEvent.location;
	
	return values : 
	
	0: Standart tuşlar
        <br>
        1: Sol tuşlar
        <br>
        2: Sağ tuşlar
        <br>
        3: Numpad tuşlar
   
   26-) Event.altKey : Belge içerisindeki herhangi bir event tetiklenirken alt tuşuna basılıp basılmadığını kontrol ederek boolean veri türünde sonucu geriye döndürür.
   
   	Event --> mouse,keyboar,touch
	
	Event.altKey;
   
   27-)  Event.ctrlKey : Belge içerisindeki herhangi bir event tetiklenirken ctrl tuşuna basılıp basılmadığını kontrol ederek boolean veri türünde sonucu geriye döndürür.
   
   28-) Event.shiftKey : Belge içerisindeki herhangi bir event tetiklenirken shift tuşuna basılıp basılmadığını kontrol ederek boolean veri türünde sonucu geriye döndürür.
   
   29-) Event.metaKey : Belge içerisindeki herhangi bir event tetiklenirken pencere tuşuna veya emir tuşuna basılıp basılmadığını kontrol ederek boolean veri türünde sonucu
        geriye döndürür.
	
		
   30-) onload || 'load' : Sayfanın veya herhangi bir HTML elemanının yüklnemesi tamamlandığında belirtilecek olan fonksiyon çalışır
   	
	window.addEventListener("load",(event)=>{
	    console.log("Page is fully loaded");
	});
	
	window.onload = (event) => {
	  console.log('page is fully loaded');
	};
   
   31-) onunload || unload : Sayfanın veya herhangi bir HTML elemanının kapatıldığında yada kaldırıldığında belirtilecek olan fonksiyon çalışır
   
   	window.addEventListener("unload", function(event) { ... });
	window.onunload = function(event) { ... };
   
   32-) onbeforeunload || beforeonload : Sayfanın kullanıcı tarafından yenileme ve kapatma isteklerinde işlem gerçekleştirilmeden belirtilecek olan fonksiyon çalışır
   
   	window.addEventListener('beforeunload', function (e) {
	  // Cancel the event
	  e.preventDefault(); // If you prevent default behavior in Mozilla Firefox prompt will always be shown
	  // Chrome requires returnValue to be set
	  e.returnValue = '';
	});
	
	window.addEventListener('beforeunload', function (e) {
	  // the absence of a returnValue property on the event will guarantee the browser unload happens
	  delete e['returnValue'];
	});
   
   33-) onhashchange || "hashchange" : Sayfa URL'inin bağlantı bölümünde değişiklik olursa belirtilecek fonksiyon çalışır. <a href"https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onhashchange">Click</a> to more info
   
   	window.addEventListener("hashchange", funcRef, false);
   
   34-) hashchangeEvent.oldURL : Sayfa URL'inin bağlantı bölümünde değişiklik olursa eski URL adresini geri döndürür. <a href="https://developer.mozilla.org/en-US/docs/Web/API/HashChangeEvent/oldURL">Click</a> more info
   
   	window.addEventListener('hashchange', function(event) {
	  console.log('Hash changed from ' + event.oldURL);
	});
   
   35-) hashchangeEvent.newURL : Sayfa URL'inin bağlantı bölümünde değişiklik olursa yeni URL değerini geri döndürür. <a href='https://developer.mozilla.org/en-US/docs/Web/API/HashChangeEvent/newURL'>Click</a> more info
   
   	window.addEventListener('hashchange', function(event) {
	  console.log('Hash changed from ' + event.newURL);
	});
   
   36-) onpageshow || 'pageshow' :  Sayfa kullanıcı tarafından görüntülenebiliyorsa belirtilecek olan fonksyion çalışır 
   	
	window.addEventLister("pageshow",func);
	
   37-) onpagehide || 'pagehide' : Sayfa kullanıcı tarafından görüntülenemiyorsa belirtilecek olan fonksyion çalışır 
   	
	window.addEventLister("pagehide",func);
	
   38-)  ononline || 'online' : Browser çevrimdışı modda çalışırken, çevrim içi modda çalışmaya başlarsa belirtilecek olan fonksiyon çalışır. 
   
   	// addEventListener version
	window.addEventListener('online', (event) => {
	    console.log("You are now connected to the network.");
	});

	// ononline version
	window.ononline = (event) => {
	  console.log("You are now connected to the network.");
	};
   
   39-)  onoffline || 'offline': Browser çevrimiçi modda çalışırken, çevrimdışı modda çalışmaya başlarsa belirtilecek olan fonksiyon çalışır.
   
   	// addEventListener version
	window.addEventListener('offline', (event) => {
	    console.log("The network connection has been lost.");
	});

	// onoffline version
	window.onoffline = (event) => {
	  console.log("The network connection has been lost.");
	};
   
   40-) onresize || 'resize' : Kullanıcı tarafından Browserin sayfa boyutu değiştirilmek istendiğinde belirtilecek olan fonksiyon çalışır.
   
   	window.addEventListener("resize",foo);
   
   41-) onscroll || 'scroll' : Sayfanın veya herhangi bir html elemanının kaydırma çubuğu yukarı veya aşağı hareket ettirildiğinde beliritlecek olan fonksiyon çalışır.
   
   	document.getElementById("selector").addEventListener("scroll",foo);
   
   42-) ontoggle : Belge içerisindeki HTML details elemanının içeriği açıldığında veya kapandığında belirtelecek olan fonksiyon çalışır.
   
   	<details  ontoggle="ornek()">
	    <summary>Açılır/Kapanır alan</summary>
	    <div>Javascript</div>
	    <div>Javascript</div>
	    <div>Javascript</div>
	    <div>Javascript</div>
	    <div>Javascript</div>
	    <div>Javascript</div>
	</details>
   
   43-) oncanplay : Medya elemanı yürütülmeye hazır olduğunda belirtilecek olan fonksiyon çalışır.
   	
	
   44-)

   
   
   
  
   
   

	
 
	
	
      
      
    

        
        
   




 
   

      
   

     
   
      
