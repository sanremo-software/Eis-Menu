
<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Eiscafé San Remo – Tischbestellung</title>

<style>
    :root {
        --primary: #d40000;
        --primary-dark: #a00000;
        --bg: #f4f4f4;
        --card-bg: #ffffff;
    }
    * { box-sizing: border-box; }
    body {
        font-family: Arial, sans-serif;
        background: var(--bg);
        margin: 0;
        padding: 0;
        color: #222;
    }
    .header {
        background: linear-gradient(135deg, var(--primary), var(--primary-dark));
        color: #fff;
        padding: 18px;
        text-align: center;
    }
    .header-title {
        font-size: 24px;
        font-weight: bold;
    }
    .header-sub {
        font-size: 14px;
        margin-top: 4px;
        opacity: 0.95;
    }
    .container {
        padding: 15px;
        max-width: 960px;
        margin: 0 auto 25px auto;
    }
    .section-title {
        font-size: 18px;
        margin-top: 18px;
        margin-bottom: 8px;
        border-left: 4px solid var(--primary);
        padding-left: 8px;
    }
    .card {
        background: var(--card-bg);
        padding: 14px;
        border-radius: 12px;
        margin-bottom: 12px;
        box-shadow: 0 0 10px rgba(0,0,0,0.07);
    }
    label {
        font-size: 14px;
        display: block;
        margin-top: 5px;
        margin-bottom: 3px;
    }
    select, input {
        width: 100%;
        padding: 9px 10px;
        font-size: 14px;
        border-radius: 8px;
        border: 1px solid #ccc;
        background: #fff;
    }
    select:focus, input:focus {
        outline: none;
        border-color: var(--primary);
    }
    .btn {
        background: var(--primary);
        color: #fff;
        padding: 10px;
        display: inline-block;
        text-align: center;
        border-radius: 8px;
        text-decoration: none;
        margin-top: 12px;
        font-size: 16px;
        border: none;
        cursor: pointer;
        width: 100%;
    }
    .btn:hover {
        background: var(--primary-dark);
    }
    .btn:disabled {
        background: #999;
        cursor: not-allowed;
    }
    #warenkorb {
        background: #fff;
        padding: 14px;
        border-radius: 12px;
        margin-top: 20px;
        box-shadow: 0 0 10px rgba(0,0,0,0.07);
        border: 1px solid #f0f0f0;
    }
    #liste-items div {
        padding: 6px 0;
        border-bottom: 1px solid #eee;
        font-size: 14px;
    }
    .line-item {
        display: flex;
        justify-content: space-between;
        gap: 10px;
        align-items: center;
    }
    .item-info {
        flex: 1;
    }
    .btn-remove {
        background: #999;
        border: none;
        color: #fff;
        padding: 4px 8px;
        border-radius: 6px;
        font-size: 11px;
        cursor: pointer;
    }
    .total {
        font-weight: bold;
        font-size: 16px;
        margin-top: 10px;
        text-align: right;
    }
    .small {
        font-size: 12px;
        color: #666;
        margin-top: 3px;
    }
    optgroup {
        font-style: normal;
        font-weight: bold;
        color: #444;
        background: #f7f7f7;
    }
</style>
</head>

<body>

<div class="header">
    <div class="header-title">🍨 Eiscafé San Remo</div>
    <div class="header-sub">Digitale Tischbestellung – ein QR-Code für alle Tische</div>
</div>

<div class="container">

    <!-- TISCHWAHL -->
    <div class="card">
        <h2 class="section-title">Tisch wählen</h2>
        <label for="tisch">Tischnummer auswählen:</label>
        <select id="tisch">
            <option value="">Tisch auswählen…</option>
        </select>
        <div class="small">Verfügbar: Tisch 1 bis 33</div>
    </div>

    <!-- PRODUKTWAHL -->
    <div class="card">
        <h2 class="section-title">Produkt wählen</h2>

        <label for="produkt">Produkt:</label>
        <select id="produkt">
            <option value="">Bitte wählen…</option>

            <optgroup label="Portionen (Sorten optional)">
                <option value="23">23. Kinder Portion (2 Kugeln) – 3,50 €</option>
                <option value="24">24. Kleine Portion (3 Kugeln) – 5,00 €</option>
                <option value="25">25. Normale Portion (4 Kugeln) – 6,50 €</option>
                <option value="26">26. Große Portion (6 Kugeln) – 9,50 €</option>
            </optgroup>

            <optgroup label="Eisbecher">
                <option value="30">30. Amarena Becher – 8,50 €</option>
                <option value="31">31. Erdbeer Becher – 8,50 €</option>
                <option value="32">32. Banana Cup – 9,00 €</option>
                <option value="33">33. Liebes Traum – 13,50 €</option>
                <option value="34">34. Kiwi Becher – 8,50 €</option>
                <option value="35">35. Frucht Becher – 8,50 €</option>
                <option value="36">36. Großer Frucht Becher – 11,90 €</option>
                <option value="37">37. Großer Amarena Becher – 12,50 €</option>
                <option value="38">38. Großer Erdbeer Becher – 12,50 €</option>
                <option value="39">39. Erdbeer-Banane Becher – 10,90 €</option>
                <option value="40">40. Exotischer Becher – 12,00 €</option>
                <option value="41">41. Wald Becher – 10,50 €</option>
                <option value="42">42. Bella Italia – 11,00 €</option>
                <option value="43">43. Mango Becher – 9,00 €</option>
                <option value="44">44. Banana Split – 10,00 €</option>
                <option value="45">45. Sommer Becher – 13,00 €</option>
                <option value="46">46. Coppa Melone – 9,50 €</option>
                <option value="47">47. Heidelbeer Becher – 9,50 €</option>
                <option value="48">48. Himbeer Becher – 9,50 €</option>

                <option value="81">81. Heiße Kirschen – 8,50 €</option>
                <option value="82">82. Heiße Himbeeren – 9,00 €</option>
                <option value="83">83. Zimt Becher – 8,50 €</option>
                <option value="84">84. Cup Dänemark – 8,50 €</option>
                <option value="85">85. Wiener Mokka – 8,50 €</option>

                <option value="90">90. Amaretto Becher – 8,50 €</option>
                <option value="91">91. Schwarzwald Becher – 9,00 €</option>
                <option value="92">92. Malaga Becher – 9,00 €</option>
                <option value="93">93. Mon Chéri Becher – 9,50 €</option>
                <option value="94">94. Raffaello Becher – 9,50 €</option>
                <option value="96">96. Eierlikör Becher – 8,50 €</option>
                <option value="98">98. Nuss Becher – 9,50 €</option>
                <option value="99">99. Rocher Becher – 9,50 €</option>
                <option value="100">100. Giotto Becher – 9,00 €</option>
                <option value="101">101. Berg Becher – 10,50 €</option>
                <option value="102">102. Walnuss Becher – 9,50 €</option>
                <option value="103">103. Coppa Delizia – 10,90 €</option>

                <option value="110">110. After Eight Becher – 8,90 €</option>
                <option value="111">111. Stracciatella Becher – 7,90 €</option>
                <option value="112">112. Tartufo Nero – 9,50 €</option>
                <option value="113">113. Tartufo Bianco – 9,50 €</option>
                <option value="114">114. Hausbecher – 20,00 €</option>
                <option value="116">116. Krokant Becher – 8,50 €</option>
                <option value="117">117. Schoko Becher – 8,50 €</option>
                <option value="118">118. Schoko Becher groß – 12,00 €</option>
                <option value="122">122. Pistazien Becher – 11,50 €</option>
            </optgroup>

            <optgroup label="Spaghetti Eis & Pizza Eis">
                <option value="50">50. Spaghetti Eis – 6,50 €</option>
                <option value="51">51. Spaghetti Eis groß – 9,50 €</option>
                <option value="52">52. Spaghetti Vanille – 7,40 €</option>
                <option value="53">53. Spaghetti Erdbeere – 8,90 €</option>
                <option value="54">54. Spaghetti Kiwi – 8,50 €</option>
                <option value="55">55. Spaghetti Vanille-Schoko – 7,50 €</option>
                <option value="56">56. Spaghetti Carbonara – 9,50 €</option>
                <option value="57">57. Spaghetti Nussknacker – 9,50 €</option>
                <option value="58">58. Spaghetti Amarena – 8,90 €</option>
                <option value="59">59. Spaghetti Waldfrüchte – 8,90 €</option>
                <option value="60">60. Spaghetti Melone – 8,90 €</option>
                <option value="61">61. Spaghetti Tutti Frutti – 8,90 €</option>
                <option value="62">62. Lasagne Eis – 8,90 €</option>

                <option value="63">63. Pizza Margherita – 9,00 €</option>
                <option value="64">64. Pizza Grandiosa – 12,00 €</option>
            </optgroup>

            <optgroup label="Joghurt Becher">
                <option value="70">70. Mixgetränk Spezial – 6,50 €</option>
                <option value="71">71. Joghurrette Becher – 9,50 €</option>
                <option value="72">72. Joghurt Cocktail – 9,50 €</option>
                <option value="73">73. Joghurt Kiwi – 9,00 €</option>
                <option value="74">74. Joghurt Erdbeere – 9,00 €</option>
                <option value="75">75. Joghurt Ananas – 9,00 €</option>
                <option value="76">76. Müsli Joghurt Becher – 9,00 €</option>
                <option value="77">77. Joghurt Heidelbeere – 9,00 €</option>
                <option value="78">78. Joghurt Banane – 9,00 €</option>
                <option value="79">79. Joghurt Amarena – 9,00 €</option>
                <option value="80">80. Joghurt Himbeere – 9,00 €</option>
            </optgroup>

            <optgroup label="Donuts Eis">
                <option value="160">Erdbeer Donut – 6,90 €</option>
                <option value="161">Schoko Donut – 6,90 €</option>
                <option value="162">Caramel Donut – 6,90 €</option>
                <option value="163">Pistazien Donut – 7,20 €</option>
                <option value="164">Kinder Donut – 6,50 €</option>
            </optgroup>

            <optgroup label="Eisgetränke & Cocktails">
                <option value="130">130. Flipper – 5,00 €</option>
                <option value="131">131. Bellini – 6,00 €</option>
                <option value="132">132. Mimosa – 6,00 €</option>
                <option value="133">133. Formula 1 – 6,00 €</option>
                <option value="134">134. Formula 2 – 6,00 €</option>

                <option value="140">140. Eiskaffee – 5,50 €</option>
                <option value="141">141. Eisschokolade – 5,50 €</option>
                <option value="142">142. Eis-Cappuccino – 5,50 €</option>

                <option value="150">150. Milch-Mix 0,3 l – 4,00 €</option>
                <option value="151">151. Milchshake 0,3 l – 4,60 €</option>
                <option value="152">152. Riesen Milch-Mix 0,5 l – 5,00 €</option>
                <option value="153">153. Riesen Milchshake 0,5 l – 5,50 €</option>
                <option value="154">154. Vulcano – 3,70 €</option>
                <option value="155">155. Orangensaft (frisch) – 4,50 €</option>
                <option value="156">156. Kalte Zitrone – 3,50 €</option>
            </optgroup>

            <optgroup label="Kaffee & Heißgetränke (Auswahl)">
                <option value="200">Espresso – 2,00 €</option>
                <option value="201">Espresso Macchiato – 2,30 €</option>
                <option value="202">Espresso Corretto – 3,40 €</option>
                <option value="203">Doppelter Espresso – 3,60 €</option>
                <option value="204">Doppelter Espresso Macchiato – 3,80 €</option>
                <option value="210">Kaffee – 2,20 €</option>
                <option value="220">Milchkaffee – 3,00 €</option>
                <option value="221">Milchkaffee mit Baileys – 4,00 €</option>
                <option value="230">Latte Macchiato – 3,60 €</option>
                <option value="231">Latte Macchiato mit Sirup – 3,20 €</option>
                <option value="240">Cappuccino – 2,60 €</option>
                <option value="241">Cappuccino groß – 3,00 €</option>
                <option value="244">Cappuccino mit Amaretto – 4,00 €</option>
                <option value="245">Cappuccino mit Eierlikör – 4,00 €</option>
                <option value="246">Cappuccino mit Baileys – 4,00 €</option>
            </optgroup>

            <optgroup label="Kalte Getränke">
                <option value="300">Coca-Cola 0,2 l – 2,70 €</option>
                <option value="301">Coca-Cola Light 0,2 l – 2,70 €</option>
                <option value="302">Coca-Cola Zero 0,2 l – 2,70 €</option>
                <option value="303">Fanta 0,2 l – 2,70 €</option>
                <option value="304">Mezzo Mix 0,2 l – 2,70 €</option>
                <option value="305">Sprite 0,2 l – 2,70 €</option>
                <option value="306">Bitter Lemon 0,2 l – 2,70 €</option>
                <option value="307">Apfelschorle – 1,90 €</option>
                <option value="308">Eistee – 1,90 €</option>
                <option value="309">Wild Berry – 2,20 €</option>
                <option value="310">Tonic Water – 2,20 €</option>
                <option value="311">S.Pellegrino 0,25 l – 2,40 €</option>
                <option value="312">S.Pellegrino 0,75 l – 5,90 €</option>
            </optgroup>

            <optgroup label="Bier, Wein & Aperitif">
                <option value="350">Krombacher Pils 0,33 l – 2,80 €</option>
                <option value="351">Krombacher Radler 0,33 l – 2,80 €</option>
                <option value="352">Erdinger Weißbier 0,5 l – 4,50 €</option>
                <option value="353">Erdinger Alkoholfrei 0,33 l – 2,80 €</option>
                <option value="354">Erdinger Alkoholfrei 0,5 l – 4,50 €</option>

                <option value="400">Rotwein trocken 0,2 l – 4,90 €</option>
                <option value="401">Weißwein trocken 0,2 l – 4,90 €</option>
                <option value="402">Glas Sekt – 3,90 €</option>
                <option value="403">Campari Sekt – 3,90 €</option>

                <option value="410">Aperitif Rosato – 5,90 €</option>
                <option value="430">Grappa – 4,70 €</option>
                <option value="431">Asbach – 3,20 €</option>
                <option value="432">Ramazzotti – 3,20 €</option>
                <option value="433">Aperol – 6,10 €</option>
                <option value="434">Hugo – 6,10 €</option>
            </optgroup>

            <optgroup label="Snacks & Herzhaftes">
                <option value="500">Flammkuchen Elsässer Art – 8,90 €</option>
                <option value="501">Flammkuchen Wildlachs & Shrimps – 8,90 €</option>
                <option value="502">Flammkuchen Griechische Art – 8,90 €</option>

                <option value="510">Toast mit Käse – 3,70 €</option>
                <option value="511">Toast mit Käse & Schinken – 4,30 €</option>
                <option value="512">Toast mit Salami & Käse – 4,30 €</option>
                <option value="513">Toast Hawaii – 5,60 €</option>

                <option value="520">Baguette XXL (Salami/Schinken/Caprese) – 6,90 €</option>
            </optgroup>

            <optgroup label="Desserts & Waffeln">
                <option value="600">Apfelstrudel – 3,70 €</option>
                <option value="601">Apfelstrudel mit Vanillesoße – 4,00 €</option>
                <option value="602">Apfelstrudel mit Sahne – 4,70 €</option>
                <option value="603">Apfelstrudel mit Eis – 6,10 €</option>
                <option value="610">Hausgemachtes Tiramisu – 4,20 €</option>

                <option value="620">Waffel mit Puderzucker – 4,00 €</option>
                <option value="621">Waffel mit Sahne – 5,00 €</option>
                <option value="622">Waffel mit Eis – 5,30 €</option>
                <option value="623">Waffel mit Eis & Sahne – 6,30 €</option>
                <option value="624">Waffel mit Nutella – 5,00 €</option>

                <option value="631">630a. Waffel Zimt & Banane – 6,80 €</option>
                <option value="632">630b. Waffel Obstsalat – 7,90 €</option>
                <option value="633">630c. Waffel Erdbeeren – 7,50 €</option>
                <option value="634">630d. Waffel Waldbeeren – 7,20 €</option>
                <option value="635">630e. Waffel Schoko-Banane – 7,90 €</option>
                <option value="636">630f. Waffel Heiße Kirschen – 7,00 €</option>
                <option value="637">630g. Waffel Schoko – 6,80 €</option>
                <option value="638">630h. Waffel Tutti Frutti – 7,50 €</option>
            </optgroup>

        </select>

        <!-- Sortenwahl nur für Portionen (optional) -->
        <div id="geschmack-box" style="margin-top:12px; display:none;">
            <label>Sorten (optional, bis zu 3 wählen):</label>
            <select id="geschmack1"></select>
            <select id="geschmack2" style="margin-top:6px;"></select>
            <select id="geschmack3" style="margin-top:6px;"></select>
            <div class="small">
                Wenn keine Sorten gewählt werden, kommt die Portion in unserer Standardmischung.
            </div>
        </div>

        <!-- Sahne-Option (nur bei Eis-Artikeln angezeigt) -->
        <div id="sahne-box" style="margin-top:8px; display:none;">
            <label for="sahne">Sahne:</label>
            <select id="sahne">
                <option value="">Bitte auswählen (optional)</option>
                <option value="mit Sahne">mit Sahne</option>
                <option value="ohne Sahne">ohne Sahne</option>
            </select>
            <div class="small">
                Wenn nichts gewählt wird, bereiten wir es wie auf der Karte zu.
            </div>
        </div>

        <label for="bemerkung" style="margin-top:8px;">Bemerkung (optional):</label>
        <input id="bemerkung" type="text" placeholder="z.B. ohne Sahne, wenig Soße …">

        <button class="btn" onclick="addToCart()">Zum Warenkorb hinzufügen</button>
    </div>

    <!-- WARENKORB -->
    <div id="warenkorb">
        <h2 class="section-title">🧺 Warenkorb</h2>
        <div id="liste-items"></div>
        <div class="total" id="gesamt">Gesamt: 0,00 €</div>

        <button id="btn-whatsapp" class="btn" onclick="sendWhatsApp()" disabled>
            Bestellung per WhatsApp senden 📲
        </button>

        <button class="btn" style="margin-top:8px; background:#555;" onclick="resetTable()">
            Tisch löschen / Neue Gäste
        </button>

        <div class="small" style="margin-top:6px;">
            Nach dem Senden bleibt der Tisch gespeichert. Neue Gäste bitte mit „Tisch löschen / Neue Gäste“ starten.
        </div>
    </div>

</div>

<script>
// WhatsApp-Nummer der Küche (ohne +, mit Ländervorwahl)
const WHATSAPP_NUMMER = "4917672809926";

// Produkte mit Preisen und Typ
// type: "cup3" = Portionen (Sorten optional) | "normal" = feste Kombination
const PRODUKTE = {
    23: { name: "23. Kinder Portion (2 Kugeln)", preis: 3.50, type: "cup3" },
    24: { name: "24. Kleine Portion (3 Kugeln)", preis: 5.00, type: "cup3" },
    25: { name: "25. Normale Portion (4 Kugeln)", preis: 6.50, type: "cup3" },
    26: { name: "26. Große Portion (6 Kugeln)", preis: 9.50, type: "cup3" },

    30: { name: "30. Amarena Becher", preis: 8.50, type: "normal" },
    31: { name: "31. Erdbeer Becher", preis: 8.50, type: "normal" },
    32: { name: "32. Banana Cup", preis: 9.00, type: "normal" },
    33: { name: "33. Liebes Traum", preis: 13.50, type: "normal" },
    34: { name: "34. Kiwi Becher", preis: 8.50, type: "normal" },
    35: { name: "35. Frucht Becher", preis: 8.50, type: "normal" },
    36: { name: "36. Großer Frucht Becher", preis: 11.90, type: "normal" },
    37: { name: "37. Großer Amarena Becher", preis: 12.50, type: "normal" },
    38: { name: "38. Großer Erdbeer Becher", preis: 12.50, type: "normal" },
    39: { name: "39. Erdbeer-Banane Becher", preis: 10.90, type: "normal" },
    40: { name: "40. Exotischer Becher", preis: 12.00, type: "normal" },
    41: { name: "41. Wald Becher", preis: 10.50, type: "normal" },
    42: { name: "42. Bella Italia", preis: 11.00, type: "normal" },
    43: { name: "43. Mango Becher", preis: 9.00, type: "normal" },
    44: { name: "44. Banana Split", preis: 10.00, type: "normal" },
    45: { name: "45. Sommer Becher", preis: 13.00, type: "normal" },
    46: { name: "46. Coppa Melone", preis: 9.50, type: "normal" },
    47: { name: "47. Heidelbeer Becher", preis: 9.50, type: "normal" },
    48: { name: "48. Himbeer Becher", preis: 9.50, type: "normal" },

    50: { name: "50. Spaghetti Eis", preis: 6.50, type: "normal" },
    51: { name: "51. Spaghetti Eis groß", preis: 9.50, type: "normal" },
    52: { name: "52. Spaghetti Vanille", preis: 7.40, type: "normal" },
    53: { name: "53. Spaghetti Erdbeere", preis: 8.90, type: "normal" },
    54: { name: "54. Spaghetti Kiwi", preis: 8.50, type: "normal" },
    55: { name: "55. Spaghetti Vanille-Schoko", preis: 7.50, type: "normal" },
    56: { name: "56. Spaghetti Carbonara", preis: 9.50, type: "normal" },
    57: { name: "57. Spaghetti Nussknacker", preis: 9.50, type: "normal" },
    58: { name: "58. Spaghetti Amarena", preis: 8.90, type: "normal" },
    59: { name: "59. Spaghetti Waldfrüchte", preis: 8.90, type: "normal" },
    60: { name: "60. Spaghetti Melone", preis: 8.90, type: "normal" },
    61: { name: "61. Spaghetti Tutti Frutti", preis: 8.90, type: "normal" },
    62: { name: "62. Lasagne Eis", preis: 8.90, type: "normal" },

    63: { name: "63. Pizza Margherita", preis: 9.00, type: "normal" },
    64: { name: "64. Pizza Grandiosa", preis: 12.00, type: "normal" },

    70: { name: "70. Mixgetränk Spezial", preis: 6.50, type: "normal" },
    71: { name: "71. Joghurrette Becher", preis: 9.50, type: "normal" },
    72: { name: "72. Joghurt Cocktail", preis: 9.50, type: "normal" },
    73: { name: "73. Joghurt Kiwi", preis: 9.00, type: "normal" },
    74: { name: "74. Joghurt Erdbeere", preis: 9.00, type: "normal" },
    75: { name: "75. Joghurt Ananas", preis: 9.00, type: "normal" },
    76: { name: "76. Müsli Joghurt Becher", preis: 9.00, type: "normal" },
    77: { name: "77. Joghurt Heidelbeere", preis: 9.00, type: "normal" },
    78: { name: "78. Joghurt Banane", preis: 9.00, type: "normal" },
    79: { name: "79. Joghurt Amarena", preis: 9.00, type: "normal" },
    80: { name: "80. Joghurt Himbeere", preis: 9.00, type: "normal" },

    81: { name: "81. Heiße Kirschen", preis: 8.50, type: "normal" },
    82: { name: "82. Heiße Himbeeren", preis: 9.00, type: "normal" },
    83: { name: "83. Zimt Becher", preis: 8.50, type: "normal" },
    84: { name: "84. Cup Dänemark", preis: 8.50, type: "normal" },
    85: { name: "85. Wiener Mokka", preis: 8.50, type: "normal" },

    90: { name: "90. Amaretto Becher", preis: 8.50, type: "normal" },
    91: { name: "91. Schwarzwald Becher", preis: 9.00, type: "normal" },
    92: { name: "92. Malaga Becher", preis: 9.00, type: "normal" },
    93: { name: "93. Mon Chéri Becher", preis: 9.50, type: "normal" },
    94: { name: "94. Raffaello Becher", preis: 9.50, type: "normal" },
    96: { name: "96. Eierlikör Becher", preis: 8.50, type: "normal" },
    98: { name: "98. Nuss Becher", preis: 9.50, type: "normal" },
    99: { name: "99. Rocher Becher", preis: 9.50, type: "normal" },
    100:{ name: "100. Giotto Becher", preis: 9.00, type: "normal" },
    101:{ name: "101. Berg Becher", preis: 10.50, type: "normal" },
    102:{ name: "102. Walnuss Becher", preis: 9.50, type: "normal" },
    103:{ name: "103. Coppa Delizia", preis: 10.90, type: "normal" },

    110:{ name: "110. After Eight Becher", preis: 8.90, type: "normal" },
    111:{ name: "111. Stracciatella Becher", preis: 7.90, type: "normal" },
    112:{ name: "112. Tartufo Nero", preis: 9.50, type: "normal" },
    113:{ name: "113. Tartufo Bianco", preis: 9.50, type: "normal" },
    114:{ name: "114. Hausbecher", preis: 20.00, type: "normal" },
    116:{ name: "116. Krokant Becher", preis: 8.50, type: "normal" },
    117:{ name: "117. Schoko Becher", preis: 8.50, type: "normal" },
    118:{ name: "118. Schoko Becher groß", preis: 12.00, type: "normal" },
    122:{ name: "122. Pistazien Becher", preis: 11.50, type: "normal" },

    130:{ name: "130. Flipper", preis: 5.00, type: "normal" },
    131:{ name: "131. Bellini", preis: 6.00, type: "normal" },
    132:{ name: "132. Mimosa", preis: 6.00, type: "normal" },
    133:{ name: "133. Formula 1", preis: 6.00, type: "normal" },
    134:{ name: "134. Formula 2", preis: 6.00, type: "normal" },

    140:{ name: "140. Eiskaffee", preis: 5.50, type: "normal" },
    141:{ name: "141. Eisschokolade", preis: 5.50, type: "normal" },
    142:{ name: "142. Eis-Cappuccino", preis: 5.50, type: "normal" },

    150:{ name: "150. Milch-Mix 0,3 l", preis: 4.00, type: "normal" },
    151:{ name: "151. Milchshake 0,3 l", preis: 4.60, type: "normal" },
    152:{ name: "152. Riesen Milch-Mix 0,5 l", preis: 5.00, type: "normal" },
    153:{ name: "153. Riesen Milchshake 0,5 l", preis: 5.50, type: "normal" },
    154:{ name: "154. Vulcano", preis: 3.70, type: "normal" },
    155:{ name: "155. Orangensaft (frisch)", preis: 4.50, type: "normal" },
    156:{ name: "156. Kalte Zitrone", preis: 3.50, type: "normal" },

    160:{ name: "Erdbeer Donut", preis: 6.90, type: "normal" },
    161:{ name: "Schoko Donut", preis: 6.90, type: "normal" },
    162:{ name: "Caramel Donut", preis: 6.90, type: "normal" },
    163:{ name: "Pistazien Donut", preis: 7.20, type: "normal" },
    164:{ name: "Kinder Donut", preis: 6.50, type: "normal" },

    200:{ name: "Espresso", preis: 2.00, type: "normal" },
    201:{ name: "Espresso Macchiato", preis: 2.30, type: "normal" },
    202:{ name: "Espresso Corretto", preis: 3.40, type: "normal" },
    203:{ name: "Doppelter Espresso", preis: 3.60, type: "normal" },
    204:{ name: "Doppelter Espresso Macchiato", preis: 3.80, type: "normal" },
    210:{ name: "Kaffee", preis: 2.20, type: "normal" },
    220:{ name: "Milchkaffee", preis: 3.00, type: "normal" },
    221:{ name: "Milchkaffee mit Baileys", preis: 4.00, type: "normal" },
    230:{ name: "Latte Macchiato", preis: 3.60, type: "normal" },
    231:{ name: "Latte Macchiato mit Sirup", preis: 3.20, type: "normal" },
    240:{ name: "Cappuccino", preis: 2.60, type: "normal" },
    241:{ name: "Cappuccino groß", preis: 3.00, type: "normal" },
    244:{ name: "Cappuccino mit Amaretto", preis: 4.00, type: "normal" },
    245:{ name: "Cappuccino mit Eierlikör", preis: 4.00, type: "normal" },
    246:{ name: "Cappuccino mit Baileys", preis: 4.00, type: "normal" },

    300:{ name: "Coca-Cola 0,2 l", preis: 2.70, type: "normal" },
    301:{ name: "Coca-Cola Light 0,2 l", preis: 2.70, type: "normal" },
    302:{ name: "Coca-Cola Zero 0,2 l", preis: 2.70, type: "normal" },
    303:{ name: "Fanta 0,2 l", preis: 2.70, type: "normal" },
    304:{ name: "Mezzo Mix 0,2 l", preis: 2.70, type: "normal" },
    305:{ name: "Sprite 0,2 l", preis: 2.70, type: "normal" },
    306:{ name: "Bitter Lemon 0,2 l", preis: 2.70, type: "normal" },
    307:{ name: "Apfelschorle", preis: 1.90, type: "normal" },
    308:{ name: "Eistee", preis: 1.90, type: "normal" },
    309:{ name: "Wild Berry", preis: 2.20, type: "normal" },
    310:{ name: "Tonic Water", preis: 2.20, type: "normal" },
    311:{ name: "S.Pellegrino 0,25 l", preis: 2.40, type: "normal" },
    312:{ name: "S.Pellegrino 0,75 l", preis: 5.90, type: "normal" },

    350:{ name: "Krombacher Pils 0,33 l", preis: 2.80, type: "normal" },
    351:{ name: "Krombacher Radler 0,33 l", preis: 2.80, type: "normal" },
    352:{ name: "Erdinger Weißbier 0,5 l", preis: 4.50, type: "normal" },
    353:{ name: "Erdinger Alkoholfrei 0,33 l", preis: 2.80, type: "normal" },
    354:{ name: "Erdinger Alkoholfrei 0,5 l", preis: 4.50, type: "normal" },

    400:{ name: "Rotwein trocken 0,2 l", preis: 4.90, type: "normal" },
    401:{ name: "Weißwein trocken 0,2 l", preis: 4.90, type: "normal" },
    402:{ name: "Glas Sekt", preis: 3.90, type: "normal" },
    403:{ name: "Campari Sekt", preis: 3.90, type: "normal" },
    410:{ name: "Aperitif Rosato", preis: 5.90, type: "normal" },
    430:{ name: "Grappa", preis: 4.70, type: "normal" },
    431:{ name: "Asbach", preis: 3.20, type: "normal" },
    432:{ name: "Ramazzotti", preis: 3.20, type: "normal" },
    433:{ name: "Aperol", preis: 6.10, type: "normal" },
    434:{ name: "Hugo", preis: 6.10, type: "normal" },

    500:{ name: "Flammkuchen Elsässer Art", preis: 8.90, type: "normal" },
    501:{ name: "Flammkuchen Wildlachs & Shrimps", preis: 8.90, type: "normal" },
    502:{ name: "Flammkuchen Griechische Art", preis: 8.90, type: "normal" },
    510:{ name: "Toast mit Käse", preis: 3.70, type: "normal" },
    511:{ name: "Toast mit Käse & Schinken", preis: 4.30, type: "normal" },
    512:{ name: "Toast mit Salami & Käse", preis: 4.30, type: "normal" },
    513:{ name: "Toast Hawaii", preis: 5.60, type: "normal" },
    520:{ name: "Baguette XXL", preis: 6.90, type: "normal" },

    600:{ name: "Apfelstrudel", preis: 3.70, type: "normal" },
    601:{ name: "Apfelstrudel mit Vanillesoße", preis: 4.00, type: "normal" },
    602:{ name: "Apfelstrudel mit Sahne", preis: 4.70, type: "normal" },
    603:{ name: "Apfelstrudel mit Eis", preis: 6.10, type: "normal" },
    610:{ name: "Hausgemachtes Tiramisu", preis: 4.20, type: "normal" },
    620:{ name: "Waffel mit Puderzucker", preis: 4.00, type: "normal" },
    621:{ name: "Waffel mit Sahne", preis: 5.00, type: "normal" },
    622:{ name: "Waffel mit Eis", preis: 5.30, type: "normal" },
    623:{ name: "Waffel mit Eis & Sahne", preis: 6.30, type: "normal" },
    624:{ name: "Waffel mit Nutella", preis: 5.00, type: "normal" },

    631:{ name: "630a. Waffel Zimt & Banane", preis: 6.80, type: "normal" },
    632:{ name: "630b. Waffel Obstsalat", preis: 7.90, type: "normal" },
    633:{ name: "630c. Waffel Erdbeeren", preis: 7.50, type: "normal" },
    634:{ name: "630d. Waffel Waldbeeren", preis: 7.20, type: "normal" },
    635:{ name: "630e. Waffel Schoko-Banane", preis: 7.90, type: "normal" },
    636:{ name: "630f. Waffel Heiße Kirschen", preis: 7.00, type: "normal" },
    637:{ name: "630g. Waffel Schoko", preis: 6.80, type: "normal" },
    638:{ name: "630h. Waffel Tutti Frutti", preis: 7.50, type: "normal" }
};

// Sortenliste (für Portionen – optional)
const SORTEN = [
    "Vanille",
    "Amarena",
    "Joghurt",
    "Nuss",
    "Schokolade",
    "Stracciatella",
    "After Eight",
    "Schlumpfeis",
    "Malaga",
    "Walnuss",
    "Cookies",
    "Zitrone",
    "Erdbeere",
    "Mango",
    "Banane",
    "Himbeere",
    "Limette",
    "Dunkle Schokolade",
    "Paw Patrol",
    "Snickers",
    "Pistazien"
];

// Artikel, bei denen Sahne wählbar ist (Eis, Eisbecher, Spaghetti, Joghurt, Donuts, Eis-Desserts, Eisgetränke)
const SAHNE_PRODUKTE = new Set([
    // Portionen
    23, 24, 25, 26,
    // Eisbecher
    30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48,
    81, 82, 83, 84, 85,
    90, 91, 92, 93, 94, 96, 98, 99, 100, 101, 102, 103,
    110, 111, 112, 113, 114, 116, 117, 118, 122,
    // Spaghetti Eis & Pizza Eis
    50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62,
    63, 64,
    // Joghurt Becher
    70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80,
    // Donuts Eis
    160, 161, 162, 163, 164,
    // Eisgetränke & Cocktails (mit Eis/Sahne)
    130, 131, 132, 133, 134,
    140, 141, 142,
    150, 151, 152, 153, 154, 155, 156,
    // Desserts & Waffeln (mit Eis oder Sahne)
    600, 601, 602, 603,
    610,
    620, 621, 622, 623, 624,
    631, 632, 633, 634, 635, 636, 637, 638
]);

let warenkorb = [];

// Tische füllen
const tischSelect = document.getElementById("tisch");
for (let i = 1; i <= 33; i++) {
    const opt = document.createElement("option");
    opt.value = i;
    opt.textContent = "Tisch " + i;
    tischSelect.appendChild(opt);
}

// Sorten-Selects füllen
function fillSortenSelect(id) {
    const sel = document.getElementById(id);
    sel.innerHTML = "<option value=''>Sorte wählen…</option>";
    SORTEN.forEach(s => {
        const opt = document.createElement("option");
        opt.value = s;
        opt.textContent = s;
        sel.appendChild(opt);
    });
}
["geschmack1", "geschmack2", "geschmack3"].forEach(fillSortenSelect);

// Produktwechsel: Sorten-Box und Sahne-Box anzeigen/verstecken
document.getElementById("produkt").addEventListener("change", function() {
    const wert = this.value;
    const geschmackBox = document.getElementById("geschmack-box");
    const sahneBox = document.getElementById("sahne-box");

    if (!wert || !PRODUKTE[wert]) {
        geschmackBox.style.display = "none";
        sahneBox.style.display = "none";
        document.getElementById("sahne").value = "";
        return;
    }

    const idNum = parseInt(wert, 10);

    // Sorten nur bei Portionen (cup3)
    if (PRODUKTE[wert].type === "cup3") {
        geschmackBox.style.display = "block";
    } else {
        geschmackBox.style.display = "none";
        ["geschmack1", "geschmack2", "geschmack3"].forEach(id => {
            const sel = document.getElementById(id);
            if (sel) sel.value = "";
        });
    }

    // Sahne nur bei Artikeln mit Eis/Sahne
    if (SAHNE_PRODUKTE.has(idNum)) {
        sahneBox.style.display = "block";
    } else {
        sahneBox.style.display = "none";
        document.getElementById("sahne").value = "";
    }
});

function addToCart() {
    const tisch = document.getElementById("tisch").value;
    if (!tisch) {
        alert("Bitte zuerst den Tisch auswählen.");
        return;
    }

    const produktId = document.getElementById("produkt").value;
    if (!produktId || !PRODUKTE[produktId]) {
        alert("Bitte ein Produkt auswählen.");
        return;
    }

    const produkt = PRODUKTE[produktId];
    let sorten = [];
    const bemerkung = document.getElementById("bemerkung").value.trim();

    // Sorten nur bei Portionen
    if (produkt.type === "cup3") {
        const s1 = document.getElementById("geschmack1").value;
        const s2 = document.getElementById("geschmack2").value;
        const s3 = document.getElementById("geschmack3").value;

        if (s1) sorten.push(s1);
        if (s2) sorten.push(s2);
        if (s3) sorten.push(s3);
    }

    // Sahne nur bei Produkten mit Eis/Sahne
    let sahne = "";
    const idNum = parseInt(produktId, 10);
    if (SAHNE_PRODUKTE.has(idNum)) {
        sahne = document.getElementById("sahne").value;
    }

    warenkorb.push({
        id: produktId,
        name: produkt.name,
        preis: produkt.preis,
        type: produkt.type,
        sorten: sorten,
        bemerkung: bemerkung,
        sahne: sahne
    });

    // Eingaben leeren
    document.getElementById("bemerkung").value = "";
    if (produkt.type === "cup3") {
        ["geschmack1", "geschmack2", "geschmack3"].forEach(id => {
            document.getElementById(id).value = "";
        });
    }
    document.getElementById("produkt").value = "";
    document.getElementById("sahne").value = "";

    updateCart();
}

function updateCart() {
    const liste = document.getElementById("liste-items");
    const totalDiv = document.getElementById("gesamt");
    const btnWpp = document.getElementById("btn-whatsapp");

    liste.innerHTML = "";
    let total = 0;

    warenkorb.forEach((item, index) => {
        total += item.preis;

        const line = document.createElement("div");
        line.className = "line-item";

        const info = document.createElement("div");
        info.className = "item-info";

        let text = item.name + " – " + item.preis.toFixed(2).replace(".", ",") + " €";
        if (item.type === "cup3" && item.sorten.length > 0) {
            text += "<br><span class='small'>Sorten: " + item.sorten.join(", ") + "</span>";
        }
        if (item.bemerkung) {
            text += "<br><span class='small'>Bemerkung: " + item.bemerkung + "</span>";
        }
        if (item.sahne) {
            text += "<br><span class='small'>Sahne: " + item.sahne + "</span>";
        }
        info.innerHTML = text;

        const btnRemove = document.createElement("button");
        btnRemove.className = "btn-remove";
        btnRemove.textContent = "X";
        btnRemove.onclick = () => removeItem(index);

        line.appendChild(info);
        line.appendChild(btnRemove);

        liste.appendChild(line);
    });

    totalDiv.textContent = "Gesamt: " + total.toFixed(2).replace(".", ",") + " €";
    btnWpp.disabled = warenkorb.length === 0;
}

function removeItem(index) {
    warenkorb.splice(index, 1);
    updateCart();
}

function sendWhatsApp() {
    const tisch = document.getElementById("tisch").value;
    if (!tisch) {
        alert("Bitte zuerst den Tisch auswählen.");
        return;
    }
    if (warenkorb.length === 0) {
        alert("Der Warenkorb ist leer.");
        return;
    }

    let total = 0;
    let text = `Tisch ${tisch} - Bestellung:%0A`;

    warenkorb.forEach(item => {
        total += item.preis;
        let line = `• ${item.name} (${item.preis.toFixed(2)} €)`;
        if (item.type === "cup3" && item.sorten.length > 0) {
            line += ` – Sorten: ${item.sorten.join(", ")}`;
        }
        if (item.bemerkung) {
            line += ` – Bemerkung: ${item.bemerkung}`;
        }
        if (item.sahne) {
            line += ` – Sahne: ${item.sahne}`;
        }
        text += line + "%0A";
    });

    text += `%0AGesamtbetrag: ${total.toFixed(2)} €`;

    const url = `https://wa.me/${WHATSAPP_NUMMER}?text=${text}`;
    window.open(url, "_blank");

    // Nach dem Senden: Warenkorb leeren, Tisch bleibt erhalten
    warenkorb = [];
    updateCart();
}

function resetTable() {
    if (!confirm("Möchten Sie den Tisch wirklich zurücksetzen? Alle Bestellungen werden gelöscht.")) {
        return;
    }

    // Warenkorb leeren
    warenkorb = [];
    updateCart();

    // Tisch zurücksetzen
    const tischSel = document.getElementById("tisch");
    if (tischSel) {
        tischSel.value = "";
    }

    // Produkt und Auswahl zurücksetzen
    const produktSel = document.getElementById("produkt");
    if (produktSel) {
        produktSel.value = "";
    }

    ["geschmack1", "geschmack2", "geschmack3"].forEach(id => {
        const sel = document.getElementById(id);
        if (sel) sel.value = "";
    });

    const sahneSel = document.getElementById("sahne");
    if (sahneSel) {
        sahneSel.value = "";
    }

    document.getElementById("bemerkung").value = "";
}
</script>

</body>
</html>
