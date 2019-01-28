# LF-verkefni1  
Verkefni 1

**1.Útskýrðu vel Game Loop í leikjagerð Unity.**  

Game Loops líkjast gömlum ævintýraleikjum þ.e. forritið bíður eftir einhvernskonar inputi frá notenda. Áður fyrr var það oftast text input og leikurinn var með mismunandi svör við mismunandi inputi, en núna bíður leikurinn eftir að ýtt sé á takka eða músin hreyfð. Munurinn er þó að þótt ekkert input sé gefið er forritið ekki að bíða eftir því, hlutir halda áfram að hreyfast á skjánum og leikurinn heldur sínum gangi. Game Loop-an heldur áfram að „tikka“. Í hvert skipti sem Game Loop-an keyrir hreyfist leikurinn áfram, hve oft loop-an keyrist á sekúndu kallast „frames per second“ eða FPS. Því meira FPS því meira „smooth“ virðist leikurinn vera.
Game Loop í stuttu máli:
Hún keyrir stöðugt alltaf þegar leikurinn er í gangi, í hverri keyrslu vinnur hún input frá notenda án þess að stoppa leikinn, uppfærir stöðu leiksins eftir þörf og renderar leikinn á skjáinn. Hún er meðvituð um tímann til að stjórna hraða leiksins.
Update loopan er mikilvægur hluti af Game Loop. Hún uppfærir stöðu leiksins eða hlutar innan leiksins eftir inputi eða öðrum áhrifahlutum. Unity býður upp á þrjár gerðir update-a.
Update: Loopan kallar á uppfærslu í hverjum ramma, alveg sama hve lengi það tekur að processa rammann. Update getur því komið með óreglulegu millibili.
FixedUpdate: Með fixed update getur maður stillt tíma milli uppfærslu. Ef framerate er lágt getur update komið mörgum sinnum milli ramma. Uppfærslan kemur með reglulegu millibili því hún er óháð römmum.
LateUpdate: Keyrir einusinni per ramma, eftir að Update loopan er búin að keyra. Það þýðir að allir útreikningar hafa átt sér stað áður en LateUpdate keyrir.  

**2. Hvað er leikjavél? Berðu saman tvær vélar t.d. Unity og Unreal.**  

Í stuttu máli er leikjavél hugbúnaður/umhverfi sem veitir notenda nauðsynleg tól til að geta búið til leiki hratt og skilvirklega. Umtöluð tól eru til dæmis leiðir til að importa list og hluti, í tvívídd og þrívídd frá öðrum hugbúnaði, setja þessa hluti saman inn í senur og umhverfi, bæta við lýsingu, hljóði, raunverulegri hreyfingu o.fl. Notandi getur að sjálfsögðu editað, debuggað og sérhæft leikinn fyrir þann platform sem hentar.

Unity og Unreal eru báðar mjög vinsælar, en eftir því sem ég sé á netinu þarf maður að velja á milli eftir því í hvaða átt maður er að fara með leikinn, t.d. á leikurinn að vera í tvívídd eða þrívídd? Eftir því sem ég sé á netinu hentar Unity betur í gerð 2D leikja og farsímaleikja þar sem umhverfið býður upp á öll tól sem þarf til að búa til og deploya leikinn. Ef planið er að gera leik í 3D þar sem grafík er höfð í hávegi er Unreal vænni kostur. Ég hef spilað marga leiki sem keyra á Unreal engine, þess má geta Playerunknown‘s Battlegrounds sem keyrir á Unreal Engine 4.
Fyrir byrjendur virðist Unity koma betur út þar sem það býður upp á betra og meira upplýsandi interface til að fylgja og læra af. Unity býður líka upp á betra efni til að læra af. Unreal hinsvegar státar sig ekki af auðveldri notkun.  


**3. Útskýrðu hvernig árekstur gæti verið útfærður í leik með sýnidæmi.**  

Árekstur gerist þegar tveir hlutir innan leiksins rekast saman, eða þegar fjarlægðin á milli þeirra fer niður fyrir ákveðna fjarlægð. Ef margir hlutir eru til staðar sem geta rekist saman margfaldast fjöldi „árekstraprófa“ í kóðanum og til að minnka fjöldan er árekstrarferlinu oftast skipt upp í tvo hluta: Broad phase og Narrow phase.
Broad phase finnur hluti sem gætu bráðum farið að rekast saman og hunsar alveg þá hluti sem eru pottþétt ekki að fara að rekast saman. Til þess að þetta virki eru sett ytri mörk á hlutina og ef þessi ytri mörk skerast á fer Broad phase í gang.
Narrow phase skoðar svo þessa hluti sem Broad phase sagði því að gætu verið að rekast saman. Í þessu skrefi eru hlutirnir skoðaðir nánar til að sjá hvort árekstrar séu í raun að gerast. Fyrir hvern árekstur eru árekstrarpunktar skráðir og eru notaðir síðar.  
Myndir sem útskýra broad og narrow phase fylgja með fyrir ofan.  

**4. Hvað er asset? Nefndu algengar tegundir.**  

Asset getur í raun verið nánast hvaða hlutur sem er, ef unity styður notkun hans, sem þú notar í leiknum þínum. T.d. Þrívíddarmódel, mynd, eða hljóðskrá.  

**5. Hvað er e.game object og hvernig tengist það e.components í e.inspector?**  

Allir hlutir sem maður notar í leiknum teljast sem game objects. Components eru í raun eiginleikar sem game objects hafa. Í components listanum getur maður breytt t.d. stærð og stöðu. Scriptur teljast líka sem components. Allir objectar hafa inspector tab þar sem maður t.d. copyað objectinn.  

**6. Hvað er líkt og ólíkt með game object og prefab?**  

Eins og ég skil þetta þá er meginmunurinn á object og prefab hvernig þeir eru geymdir. Object er til í Library möppunni á meðan prefab er geymt eins og skrá í tölvunni og er hægt að nota mörgum sinnum.  

**7. Hvert er samband þríhyrnings og mesh í 3D umhverfi?**  

**8. Hvað er tags og layers?**  

Tags eru values sem þú getur sett á objecta til að þekkja þá í sundur. Einskonar nöfn. Layers eru kannski smá eins og klasar í html og css. Ef eiga að hafa sömu eiginleika er hægt að setja þá undir sama layer.  

**9. Útskýrðu stuttlega eftirfarandi svæði í Unity:**  

a) Scene View:  
Í scene view vinnur maður með objecta og það sem þeim fylgir til að búa til senur í leiknum.  

b) Game View:  
Í game view getur maður spilað senuna sem maður setti upp í scene view.  

c) Project  
Í project glugganum hefur maður yfirsýn yfir asset files.  

d) Hierarchy  
Yfirsýn yfir game objects raðað eftir arfleið.  

e) Inspector  
Yfirsýn yfir eiginleika game objects sem valinn er.









