<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Galeria zdjęć</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f4f4f4;
        }
        .gallery {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        .thumbnail {
            width: 150px;
            cursor: pointer;
            border: 2px solid #ccc;
            transition: border-color 0.3s;
        }
        .thumbnail:hover {
            border-color: #333;
        }
        .lightbox {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            justify-content: center;
            align-items: center;
        }
        .lightbox img {
            max-width: 90%;
            max-height: 90%;
        }
        .close {
            position: absolute;
            top: 20px;
            right: 30px;
            color: #fff;
            font-size: 30px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<h1>Galeria zdjęć</h1>
<div class="gallery">
    <img src="image1_thumb.jpg" alt="Zdjęcie 1" class="thumbnail" data-full="image1.jpg">
    <img src="image2_thumb.jpg" alt="Zdjęcie 2" class="thumbnail" data-full="image2.jpg">
    <img src="image3_thumb.jpg" alt="Zdjęcie 3" class="thumbnail" data-full="image3.jpg">
    <img src="image4_thumb.jpg" alt="Zdjęcie 4" class="thumbnail" data-full="image4.jpg">
</div>

<div class="lightbox" id="lightbox">
    <span class="close" id="close">&times;</span>
    <img id="lightbox-img" src="" alt="Pełne zdjęcie">
</div>

<script>
    const thumbnails = document.querySelectorAll('.thumbnail');
    const lightbox = document.getElementById('lightbox');
    const lightboxImg = document.getElementById('lightbox-img');
    const closeBtn = document.getElementById('close');

    thumbnails.forEach(thumbnail => {
        thumbnail.addEventListener('click', () => {
            const fullImage = thumbnail.getAttribute('data-full');
            lightboxImg.src = fullImage;
            lightbox.style.display = 'flex';
        });
    });

    closeBtn.addEventListener('click', () => {
        lightbox.style.display = 'none';
    });

    lightbox.addEventListener('click', () => {
        lightbox.style.display = 'none';
    });
</script>

</body>
</html>
