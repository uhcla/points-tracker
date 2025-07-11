<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Points Tracker Multilang</title>
<style>
  body { font-family: Arial, sans-serif; margin: 20px; }
  select { margin-bottom: 10px; }
  table { border-collapse: collapse; width: 100%; margin-bottom: 20px;}
  th, td { border: 1px solid #aaa; padding: 6px; text-align: center;}
  th { background-color: #f0f0f0; }
  caption { font-weight: bold; margin-bottom: 5px; }
</style>
</head>
<body>

<label for="lang-select" id="lang-label">Select Language:</label>
<select id="lang-select">
  <option value="en">English</option>
  <option value="fr">Français</option>
  <option value="zh">中文 (Chinese)</option>
  <option value="ar">العربية (Arabic)</option>
  <option value="es">Español (Spanish)</option>
  <option value="hi">हिन्दी (Hindi)</option>
  <option value="ru">Русский (Russian)</option>
  <option value="pt">Português (Portuguese)</option>
  <option value="bn">বাংলা (Bengali)</option>
  <option value="ja">日本語 (Japanese)</option>
  <option value="de">Deutsch (German)</option>
  <option value="ko">한국어 (Korean)</option>
  <option value="it">Italiano (Italian)</option>
  <option value="vi">Tiếng Việt (Vietnamese)</option>
  <option value="pl">Polski (Polish)</option>
  <option value="nl">Nederlands (Dutch)</option>
  <option value="tr">Türkçe (Turkish)</option>
  <option value="fa">فارسی (Persian)</option>
  <option value="ro">Română (Romanian)</option>
  <option value="hu">Magyar (Hungarian)</option>
  <option value="el">Ελληνικά (Greek)</option>
  <option value="sv">Svenska (Swedish)</option>
  <option value="cs">Čeština (Czech)</option>
  <option value="da">Dansk (Danish)</option>
  <option value="fi">Suomi (Finnish)</option>
  <option value="he">עברית (Hebrew)</option>
  <option value="th">ไทย (Thai)</option>
  <option value="id">Bahasa Indonesia (Indonesian)</option>
  <option value="ms">Bahasa Melayu (Malay)</option>
  <option value="uk">Українська (Ukrainian)</option>
  <option value="sr">Српски (Serbian)</option>
  <option value="hr">Hrvatski (Croatian)</option>
  <option value="lt">Lietuvių (Lithuanian)</option>
  <option value="lv">Latviešu (Latvian)</option>
  <option value="sk">Slovenčina (Slovak)</option>
  <option value="bg">Български (Bulgarian)</option>
  <option value="sl">Slovenščina (Slovenian)</option>
  <option value="et">Eesti (Estonian)</option>
  <option value="mt">Malti (Maltese)</option>
  <option value="ga">Gaeilge (Irish)</option>
  <option value="is">Íslenska (Icelandic)</option>
  <option value="mk">Македонски (Macedonian)</option>
  <option value="sq">Shqip (Albanian)</option>
  <option value="hy">Հայերեն (Armenian)</option>
  <option value="ka">ქართული (Georgian)</option>
  <option value="af">Afrikaans (Afrikaans)</option>
  <option value="cy">Cymraeg (Welsh)</option>
</select>

<div id="content"></div>

<script>
// Data for points and translations
const data = {
  en: {
    days: ["Day 1 – City Construction","Day 2 – Basic Skills Up","Day 3 – Pet Training","Day 4 – Hero Development","Day 5 – Power Boost"],
    elements: [
      "Raise Governor Gear Charm max score by 1",
      "Use 1 Truegold to upgrade a building",
      "Use 1m of Speedups for Construction",
      "Use 1m of Speedups for Research",
      "Use 1m of Speedups for Troop Training or Promotion",
      "Finish 1 Intel Mission(s)",
      "Play Hero Roulette 1 Time(s)",
      "Use 1 Rare Hero Shard to ascend Heroes",
      "Use 1 Epic Hero Shard to ascend Heroes",
      "Use 1 Mythic Hero Shard to ascend Heroes",
      "Gather 1000 Bread in the Wilderness",
      "Gather 1000 Wood in the Wilderness",
      "Gather 200 Stone in the Wilderness",
      "Gather 50 Iron in the Wilderness",
      "Raise Pet Advancement Score by 1",
      "Use 1 Advanced Taming Mark(s) to refine Pets",
      "Use 1 Common Taming Mark(s) to refine Pets",
      "Use 1 Hero Gear Forgehammer(s)",
      "Use 1 Widget for Hero Exclusive Gear",
      "Use 1 Mithril",
      "Train 1 Level 1 Troop(s)",
      "Train 1 Level 2 Troop(s)",
      "Train 1 Level 3 Troop(s)",
      "Train 1 Level 4 Troop(s)",
      "Train 1 Level 5 Troop(s)",
      "Train 1 Level 6 Troop(s)",
      "Train 1 Level 7 Troop(s)",
      "Train 1 Level 8 Troop(s)",
      "Train 1 Level 9 Troop(s)",
      "Train 1 Level 10 Troop(s)",
      "Raise Governor Gear max score by 1"
    ],
    scores: [
      [70, null, null, null, null],
      [2000, 2000, null, null, 2000],
      [30, 30, 30, null, 30],
      [30, 30, null, null, 30],
      [30, 30, 30, null, 30],
      [6000, null, 6000, null, 6000],
      [null, 8000, 8000, null, null],
      [null, 350, 350, null, null],
      [null, 1220, 1220, null, null],
      [null, 3040, 3040, null, null],
      [null, 2, null, 2, 2],
      [null, 2, null, 2, 2],
      [null, 2, null, 2, 2],
      [null, 2, null, 2, 2],
      [null, null, 50, null, 50],
      [null, null, 15000, null, 15000],
      [null, null, 1150, null, 1150],
      [null, null, null, 4000, 4000],
      [null, null, null, 8000, 8000],
      [null, null, null, 40000, 40000],
      [null, null, null, 3, null],
      [null, null, null, 4, null],
      [null, null, null, 5, null],
      [null, null, null, 8, null],
      [null, null, null, 12, null],
      [null, null, null, 18, null],
      [null, null, null, 25, null],
      [null, null, null, 35, null],
      [null, null, null, 45, null],
      [null, null, null, 60, null],
      [null, null, null, null, 36]
    ],
    equipLegendTitle: "Governor Gear Rarity Level Up Scores",
    equipLegend: [
      ["Uncommon",1125],
      ["Uncommon (1-Star)",1875],
      ["Rare",3000],
      ["Rare (1-Star)",4500],
      ["Rare (2-Star)",5100],
      ["Rare (3-Star)",5400],
      ["Epic",3230],
      ["Epic (1-Star)",3230],
      ["Epic (2-Star)",3225],
      ["Epic (3-Star)",3225],
      ["Epic T1",3440],
      ["Epic T1 (1-Star)",3440],
      ["Epic T1 (2-Star)",4085],
      ["Epic T1 (3-Star)",4085],
      ["Mythic",6250],
      ["Mythic (1-Star)",6250],
      ["Mythic (2-Star)",
