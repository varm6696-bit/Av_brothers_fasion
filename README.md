
<!DOCTYPE html>
<html>
<head>
    <title>AV Brothers Fashion & Clothing</title>
    <meta name="viewport" content="width=device-width, initial-scale=100">

    <style>
        body {font-family: Arial; margin:0; padding:0; text-align:center;}

        header {background:black; color:white; padding:20px;}

        .section {padding:40px;}

        .products {
            display:flex;
            justify-content:center;
            gap:20px;
            flex-wrap:wrap;
        }

        .card {
            border:1px solid #ddd;
            padding:15px;
            width:220px;
            border-radius:10px;
        }

        .card img {
            width:100%;
            border-radius:10px;
        }

        button {
            background:#e91e63;
            color:white;
            padding:10px 20px;
            border:none;
            border-radius:5px;
        }

        footer {
            background:#f1f1f1;
            padding:20px;
        }
    </style>
</head>

<body>

<header>
    <h1>AV Brothers Fashion & Clothing</h1>
    <p>Fena Gaon, Kamatghar, Bhiwandi</p>
<input type="text" placeholder="Search product..." onkeyup="searchProduct(this.value)">
<input type="text" id="search" placeholder="Search product..." onkeyup="filterProduct()">

<select onchange="filterProduct()" id="category">
  <option value="all">All</option>
  <option value="top">Top</option>
  <option value="kurti">Kurti</option>
</select>
</header>

<div class="section">

<h2>Our Products</h2>

<div class="products">

<!-- Product 1 -->
<div class="card" data-category="top">
<div class="card">
<img src="top4.jpg">
<h3>Stylish Collar Girls Top</h3>
<p>Price: ₹199</p>
<a href="payment.html"><button>Explore</button></a>
</div>

<!-- Product 2 -->
<div class="card" data-category="top">
<div class="card">
<img src="top3.jpg">
<h3>Ribbed V-Neck Crop Top (White)</h3>
<p>Price: ₹299</p>
<a href="payment.html"><button>Explore</button></a>
</div>

<!-- Product 3 -->
<div class="card" data-category="top">
<div class="card">
<img src="top2.jpg">
<h3>Trending Crop Top (White)</h3>
<p>Price: ₹199</p>
<a href="payment.html"><button>Explore</button></a>
</div>

<!-- Product 4 -->
<div class="card" data-category="top">
<div class="card">
<img src="top5.jpg">
<h3>Stylish Party Wear Top</h3>
<p>Price: ₹199</p>
<a href="payment.html"><button>Explore</button></a>
</div>

</div>

</div>

<div class="section">
    <h2>Contact</h2>
    <p>Phone: +91 7248906682</p>
    <p>Location: Fena Gaon, Kamatghar, Bhiwandi</p>
</div>

<footer>
    © 2026 AV Brothers Fashion & Clothing
</footer>

<script>
function searchProduct(value){
  let cards = document.querySelectorAll(".card");
  value = value.toLowerCase();

  cards.forEach(card => {
    let text = card.innerText.toLowerCase();

    if(text.includes(value)){
      card.style.display = "block";
    } else {
      card.style.display = "none";
    }
  });
}
</script>
<script>
function filterProduct(){
  let search = document.getElementById("search").value.toLowerCase();
  let category = document.getElementById("category").value;
  let cards = document.querySelectorAll(".card");

  cards.forEach(card => {
    let text = card.innerText.toLowerCase();
    let cardCategory = card.getAttribute("data-category");

    let matchSearch = text.includes(search);
    let matchCategory = (category === "all" || category === cardCategory);

    if(matchSearch && matchCategory){
      card.style.display = "block";
    } else {
      card.style.display = "none";
    }
  });
}
</script>
</body>
</html>
