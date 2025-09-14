
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>El Bien y el Mal: Ayer y Hoy</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Merriweather:ital,wght@0,300;000&display=swap');
        body {
            font-family: 'Merriweather', serif;
            color: #2c3e50;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow: hidden;
            background-color: #f7f1e3;
        }
        .background-image {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: -2;
            filter: grayscale(40%) opacity(0.8);
        }
        .container {
            max-width: 1000px;
            padding: 2rem;
            background-color: rgba(255, 255, 255, 0.6);
            backdrop-filter: blur(5px);
            border-radius: 1rem;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            position: relative;
            z-index: 1;
        }
        .toggle-switch-container {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-top: 1.5rem;
            font-size: 1.25rem;
            font-weight: 500;
        }
        .switch {
            position: relative;
            display: inline-block;
            width: 60px;
            height: 34px;
            margin: 0 1rem;
        }
        .switch input {
            opacity: 0;
            width: 0;
            height: 0;
        }
        .slider {
            position: absolute;
            cursor: pointer;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #ccc;
            transition: .4s;
            border-radius: 34px;
        }
        .slider:before {
            position: absolute;
            content: "";
            height: 26px;
            width: 26px;
            left: 4px;
            bottom: 4px;
            background-color: white;
            transition: .4s;
            border-radius: 50%;
        }
        input:checked + .slider {
            background-color: #4CAF50;
        }
        input:checked + .slider:before {
            transform: translateX(26px);
        }
        .card {
            background-color: #f8f8f8;
            border-radius: 0.75rem;
            padding: 1rem;
            margin-bottom: 1rem;
            transition: all 0.3s ease-in-out;
            border: 2px solid transparent;
        }
        .good {
            border-color: #4CAF50;
            box-shadow: 0 0 10px rgba(76, 175, 80, 0.4);
        }
        .bad {
            border-color: #f44336;
            box-shadow: 0 0 10px rgba(244, 67, 54, 0.4);
        }
        .animated-figure {
            position: absolute;
            bottom: -50px;
            animation: moveFigure linear infinite;
            height: 100px;
        }
        @keyframes moveFigure {
            from {
                left: 0;
                transform: translateX(0);
            }
            to {
                left: 100%;
                transform: translateX(-100%);
            }
        }
    </style>
</head>
<body class="bg-gray-100 flex items-center justify-center min-h-screen">
    <img src="https://tse3.mm.bing.net/th/id/OIP.McTz1mvQi3W_usWOb3xrRQHaDt?rs=1&pid=ImgDetMain&o=7&rm=3" alt="Un caballero y un castillo de estilo medieval" class="background-image">
    <div class="container mx-auto p-8 rounded-lg shadow-lg max-w-4xl">
        <h1 class="text-4xl md:text-5xl font-bold text-center mb-2">El Bien y el Mal: Ayer y Hoy</h1>
        <p class="text-center text-lg md:text-xl text-gray-600 mb-8 max-w-2xl mx-auto">
            La moralidad cambia con el tiempo. Lo que era virtuoso en la Edad Media puede ser visto de forma muy diferente hoy. Explora estas diferencias.
        </p>

        <div class="toggle-switch-container">
            <span id="label-medieval" class="text-red-500 font-bold">Perspectiva Medieval</span>
            <label class="switch">
                <input type="checkbox" id="moral-toggle">
                <span class="slider"></span>
            </label>
            <span id="label-modern" class="text-gray-500">Perspectiva Moderna</span>
        </div>

        <div id="content-container" class="mt-8 grid grid-cols-1 md:grid-cols-2 gap-6">
            <div id="good-medieval" class="flex flex-col">
                <h2 class="text-2xl font-semibold text-center mb-4">Considerado BUENO en la Edad Media</h2>
                <div id="medieval-good-list">
                    <div class="card" data-moral-type="good">
                        <p class="text-lg">Las Cruzadas</p>
                    </div>
                    <div class="card" data-moral-type="good">
                        <p class="text-lg">Aceptación de la Jerarquía Social</p>
                    </div>
                    <div class="card" data-moral-type="good">
                        <p class="text-lg">La Usura (cobrar intereses)</p>
                    </div>
                </div>
            </div>

            <div id="bad-medieval" class="flex flex-col">
                <h2 class="text-2xl font-semibold text-center mb-4">Considerado MALO en la Edad Media</h2>
                <div id="medieval-bad-list">
                    <div class="card" data-moral-type="bad">
                        <p class="text-lg">El Individualismo y la elección personal</p>
                    </div>
                    <div class="card" data-moral-type="bad">
                        <p class="text-lg">La risa descontrolada o la diversión exagerada</p>
                    </div>
                    <div class="card" data-moral-type="bad">
                        <p class="text-lg">El Pensamiento Crítico contra la autoridad</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Animated figures for decoration -->
    <div class="animated-figure" style="animation-duration: 25s; left: 10%; animation-delay: 0s;">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" style="fill: #2c3e50;"><path d="M224 256A128 128 0 1 0 224 0a128 128 0 1 0 0 256zm-45.7 391.7c7.9 12.4 21.6 20.3 36.3 20.3h100.8c26.2 0 47.6-21.4 47.6-47.6V400H320c-17.7 0-32-14.3-32-32V288C288 270.3 273.7 256 256 256H192c-17.7 0-32 14.3-32 32v128h-32v47.6c0 26.2 21.4 47.6 47.6 47.6z"/></svg>
    </div>
    <div class="animated-figure" style="animation-duration: 30s; left: 60%; animation-delay: 10s;">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" style="fill: #2c3e50;"><path d="M224 256A128 128 0 1 0 224 0a128 128 0 1 0 0 256zm-45.7 391.7c7.9 12.4 21.6 20.3 36.3 20.3h100.8c26.2 0 47.6-21.4 47.6-47.6V400H320c-17.7 0-32-14.3-32-32V288C288 270.3 273.7 256 256 256H192c-17.7 0-32 14.3-32 32v128h-32v47.6c0 26.2 21.4 47.6 47.6 47.6z"/></svg>
    </div>

    <script>
        const data = {
            medieval: {
                good: [
                    'Las Cruzadas',
                    'Aceptación de la Jerarquía Social',
                    'La Usura (cobrar intereses)'
                ],
                bad: [
                    'El Individualismo y la elección personal',
                    'La risa descontrolada o la diversión exagerada',
                    'El Pensamiento Crítico contra la autoridad'
                ]
            },
            modern: {
                good: [
                    'El Pensamiento Crítico',
                    'El Individualismo y la libertad de elección',
                    'La risa y la diversión'
                ],
                bad: [
                    'Las Cruzadas (violencia en nombre de la fe)',
                    'La aceptación de la jerarquía social (falta de libertad)',
                    'La usura (préstamos con intereses)'
                ]
            }
        };

        const toggle = document.getElementById('moral-toggle');
        const medievalGoodList = document.getElementById('medieval-good-list');
        const medievalBadList = document.getElementById('medieval-bad-list');
        const h2Good = document.querySelector('#good-medieval h2');
        const h2Bad = document.querySelector('#bad-medieval h2');
        const labelMedieval = document.getElementById('label-medieval');
        const labelModern = document.getElementById('label-modern');

        function updateContent(isModern) {
            const perspective = isModern ? data.modern : data.medieval;

            h2Good.textContent = isModern ? 'Considerado BUENO hoy en día' : 'Considerado BUENO en la Edad Media';
            h2Bad.textContent = isModern ? 'Considerado MALO hoy en día' : 'Considerado MALO en la Edad Media';

            const goodItems = perspective.good;
            const badItems = perspective.bad;

            // Update the content and classes for the "good" column
            const goodCardsHTML = goodItems.map(item => `
                <div class="card ${isModern ? 'good' : 'bad'}" data-moral-type="good">
                    <p class="text-lg">${item}</p>
                </div>
            `).join('');

            // Update the content and classes for the "bad" column
            const badCardsHTML = badItems.map(item => `
                <div class="card ${isModern ? 'bad' : 'good'}" data-moral-type="bad">
                    <p class="text-lg">${item}</p>
                </div>
            `).join('');

            medievalGoodList.innerHTML = goodCardsHTML;
            medievalBadList.innerHTML = badCardsHTML;

            labelMedieval.classList.toggle('text-gray-500', isModern);
            labelMedieval.classList.toggle('text-red-500', !isModern);
            labelModern.classList.toggle('text-gray-500', !isModern);
            labelModern.classList.toggle('text-red-500', isModern);
        }

        toggle.addEventListener('change', (event) => {
            updateContent(event.target.checked);
        });

        // Set the initial state on page load
        updateContent(false);
    </script>
</body>
</html>


