# HTML-CSS-profeccional-3
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <title>3D Ag'dariluvchi Karta</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="scene">
        <div class="card">
            <div class="card-face card-front">
                <h2>Old tomon</h2>
                <p>Kursor bilan ustiga bosing/olib boring</p>
            </div>
            <div class="card-face card-back">
                <h2>Orqa tomon</h2>
                <p>Bu yerda maxfiy ma'lumotlar bo'lishi mumkin</p>
            </div>
        </div>
    </div>

</body>
</html>

/* Asosiy sahifa sozlamalari */
body {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background-color: #f0f2f5;
    margin: 0;
    font-family: sans-serif;
}

/* 3D chuqurlik hissi (perspective) */
.scene {
    width: 300px;
    height: 400px;
    perspective: 1000px;
}

/* Karta konteyneri */
.card {
    width: 100%;
    height: 100%;
    position: relative;
    transform-style: preserve-3d;
    transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1);
    cursor: pointer;
}

/* Hover paytida ag'darilish */
.card:hover {
    transform: rotateY(180deg);
}

/* Old va orqa tomonlar umumiy sozlamalari */
.card-face {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden; /* Eski tomonni yashirish */
    border-radius: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: white;
    box-shadow: 0 10px 20px rgba(0,0,0,0.2);
}

.card-front {
    background: linear-gradient(135deg, #4f46e5, #818cf8);
}

.card-back {
    background: linear-gradient(135deg, #ec4899, #f472b6);
    transform: rotateY(180deg); /* Orqa tomonni oldindan ag'darib qo'yish */
}
