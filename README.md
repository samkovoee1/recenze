
<!DOCTYPE html>
<html lang="cs">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Recenze her</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 700px;
      margin: auto;
      padding: 20px;
      background: #f9f9f9;
      color: #333;
    }
    h1 {
      text-align: center;
      color: #2a7ae2;
    }
    nav {
      margin-bottom: 20px;
      text-align: center;
    }
    nav button {
      background-color: #2a7ae2;
      color: white;
      border: none;
      padding: 10px 15px;
      margin: 5px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 4px;
      transition: background-color 0.3s;
    }
    nav button:hover {
      background-color: #1853b6;
    }
    nav button.active {
      background-color: #144a96;
    }
    article {
      background: white;
      padding: 20px;
      border-radius: 6px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }
    h2 {
      color: #2a7ae2;
    }
    p {
      line-height: 1.5;
    }
    strong {
      color: #555;
    }
  </style>
</head>
<body>
  <h1>Recenze her</h1>
  <nav>
    <button data-review="0" class="active">Stellar Quest</button>
    <button data-review="1">Shadowbound</button>
    <button data-review="2">Pixel Racers</button>
    <button data-review="3">Mystic Forest</button>
    <button data-review="4">Cyber Siege</button>
    <button data-review="5">Dragonfall Legends</button>
  </nav>

  <article id="review-content">
    <!-- Recenze se sem načte skrz JS -->
  </article>

  <script>
    const reviews = [
      {
        title: "Stellar Quest",
        genre: "Sci-fi akční RPG",
        description: "Stellar Quest je napínavá vesmírná dobrodružná hra, která vás zavede do vzdálených galaxií plných neznámých hrozeb a přátel. Příběh je poutavý, grafika detailní a herní mechaniky zábavné.",
        rating: "8.5/10"
      },
      {
        title: "Shadowbound",
        genre: "Taktická stealth akce",
        description: "Shadowbound vás postaví do role mistra infiltrace v temném světě plném nebezpečí. Hra klade důraz na strategii, ticho a precizní plánování. Skvělé pro fanoušky stealth žánru.",
        rating: "9/10"
      },
      {
        title: "Pixel Racers",
        genre: "Arkádové závody",
        description: "Pixel Racers je retro závodní hra s pixelartovou grafikou a svižnou hratelností. Ideální pro krátké, zábavné závody s kamarády. Jednoduché ovládání a spousta tratí.",
        rating: "7.8/10"
      },
      {
        title: "Mystic Forest",
        genre: "Fantasy adventura",
        description: "Mystic Forest je krásná adventura plná magie, hádanek a tajemných míst. Atmosféra je kouzelná, příběh dojemný a gameplay vyvážený. Doporučuji všem milovníkům fantasy.",
        rating: "8.9/10"
      },
      {
        title: "Cyber Siege",
        genre: "Sci-fi strategie v reálném čase",
        description: "Cyber Siege kombinuje rychlé taktické souboje s futuristickým prostředím. Hra nabízí širokou škálu jednotek a technologií. Výzva i pro zkušené stratégové.",
        rating: "8.2/10"
      },
      {
        title: "Dragonfall Legends",
        genre: "Akční RPG",
        description: "Dragonfall Legends nabízí epické bitvy, rozmanité schopnosti a rozsáhlý otevřený svět plný draků a nebezpečných nepřátel. Hra je vhodná pro všechny, kdo milují akční dobrodružství.",
        rating: "9.3/10"
      }
    ];

    const buttons = document.querySelectorAll("nav button");
    const content = document.getElementById("review-content");

    function showReview(index) {
      const review = reviews[index];
      content.innerHTML = `
        <h2>${review.title}</h2>
        <p><strong>Žánr:</strong> ${review.genre}</p>
        <p>${review.description}</p>
        <p><strong>Hodnocení:</strong> ${review.rating}</p>
      `;

      buttons.forEach(btn => btn.classList.remove("active"));
      buttons[index].classList.add("active");
    }

    // Při načtení ukážeme první recenzi
    showReview(0);

    // Přepínání recenzí po kliknutí na tlačítka
    buttons.forEach((btn, i) => {
      btn.addEventListener("click", () => {
        showReview(i);
      });
    });
  </script>
</body>
</html>
