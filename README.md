<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Currículum</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
       

        header {
            background-image: url('/IMG/fondo.jpeg'); /* Cambia 'ruta_de_la_imagen.jpg' por la ruta real de tu imagen */
            background-size: cover; /* Ajusta la imagen para cubrir todo el encabezado */
            background-position: center; /* Centra la imagen en el encabezado */
            color: #130b0b;
            text-align: center;
            padding: 1rem;
}


        .tabs {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }
        .tab {
            padding: 10px 20px;
            cursor: pointer;
            background-color: #8d8c8c;
            border: 1px solid #ccc;
            margin: 0 10px;
        }
        .tab.active {
            background-color: #d1d0d0;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 2rem;
            background-color: #fafafa; /* Color de fondo */
            border-radius: 10px; /* Bordes redondeados */
            box-shadow: 0 2px 5px rgb(240, 236, 236); /* Sombra suave */
        }
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            grid-gap: 10px;
            margin-top: 20px;
        }
        .gallery img {
            max-width: 100%;
            height: auto;
            cursor: pointer;
        }
        #modal {
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
        #modal img {
            max-width: 80%;
            max-height: 80%;
        }
    </style>
</head>
<body>
    <header>
        <h1>Mi Currículum</h1>
    </header>
    <div class="tabs">
        <div class="tab active" onclick="showTab('datosPersonales')">Datos Personales</div>
        <div class="tab" onclick="showTab('experienciaLaboral')">Experiencia Laboral</div>
        <div class="tab" onclick="showTab('educacion')">Educación</div>
        <div class="tab" onclick="showTab('habilidades')">Habilidades</div>
        <div class="tab" onclick="showTab('fotogaleria')">Fotogalería</div>
    </div>
    <div class="container" id="datosPersonales">
        <h2>Datos Personales</h2>
        <p>Nombre: Martin Chama Salazar</p>
        <p>Correo electrónico: Martinchama211160001@gmail.com</p>
        <p>Teléfono de Casa: 5590517495</p>
        <p>Teléfono Celular: 5619958972</p>

    </div>
    <div class="container" id="experienciaLaboral" style="display: none;">
        <h2>Experiencia Laboral</h2>
        <p>[Año] - [Año]: [Empresa] - [Cargo]</p>
        <p>[Descripción de las responsabilidades y logros]</p>
    </div>
    <div class="container" id="educacion" style="display: none;">
        <h2>Educación</h2>
        <p>[Año] - [Año]: [Título obtenido] - [Institución]</p>
    </div>
    <div class="container" id="habilidades" style="display: none;">
        <h2>Habilidades</h2>
        <ul>
            <li>[Habilidad 1]</li>
            <li>[Habilidad 2]</li>
            <li>[Habilidad 3]</li>
        </ul>
    </div>
    <div class="container" id="fotogaleria" style="display: none;">
        <h2>Fotogalería</h2>
        <div class="gallery">
            <img src="/IMG/WhatsApp Image 2023-07-09 at 10.32.18 PM(1).jpeg" alt="Imagen 1" onclick="openModal('IMG/WhatsApp Image 2023-07-09 at 10.32.18 PM(1).jpeg')">
            <img src="/IMG/WhatsApp Image 2023-07-09 at 10.32.18 PM(2).jpeg" alt="Imagen 2" onclick="openModal('IMG/WhatsApp Image 2023-07-09 at 10.32.18 PM(2).jpeg')">
            <img src="/IMG/WhatsApp Image 2023-07-09 at 10.32.18 PM(3).jpeg" alt="Imagen 3" onclick="openModal('IMG/WhatsApp Image 2023-07-09 at 10.32.18 PM(3).jpeg')">
            <img src="/IMG/WhatsApp Image 2023-07-09 at 10.32.18 PM(4).jpeg" alt="Imagen 3" onclick="openModal('IMG/WhatsApp Image 2023-07-09 at 10.32.18 PM(4).jpeg')">
            <img src="/IMG/WhatsApp Image 2023-07-09 at 10.32.18 PM(5).jpeg" alt="Imagen 3" onclick="openModal('IMG/WhatsApp Image 2023-07-09 at 10.32.18 PM(5).jpeg')">

        </div>
    </div>
    <div id="modal">
        <img id="modalImage" src="" alt="Imagen en modal" onclick="closeModal()">
    </div>
    
    <script>
        function showTab(tabId) {
            const tabs = document.querySelectorAll('.container');
            tabs.forEach(tab => {
                if (tab.id === tabId) {
                    tab.style.display = 'block';
                } else {
                    tab.style.display = 'none';
                }
            });

            const activeTabs = document.querySelectorAll('.tab');
            activeTabs.forEach(activeTab => {
                if (activeTab.getAttribute('onclick').includes(tabId)) {
                    activeTab.classList.add('active');
                } else {
                    activeTab.classList.remove('active');
                }
            });
        }

        function openModal(imageSrc) {
            const modal = document.getElementById("modal");
            const modalImage = document.getElementById("modalImage");
            modalImage.src = imageSrc;
            modal.style.display = "flex";
        }

        function closeModal() {
            const modal = document.getElementById("modal");
            modal.style.display = "none";
        }

        // Mostrar la primera pestaña al cargar la página
        showTab('datosPersonales');
    </script>
</body>
</html>

