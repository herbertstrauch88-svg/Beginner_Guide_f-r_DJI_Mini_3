# Erste-Schritte-mit-deiner-neuen-Drohne
Ein kurzer Beginner Guide für die ersten Schritte mit deiner DJI Mini 3 Drohne 

#
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DJI Mini 3 - Tutorial</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            background: #fff;
            color: #1d1d1f;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            position: relative;
            background: linear-gradient(180deg, #fff 0%, #f5f5f7 100%);
        }

        .hero h1 {
            font-size: 6rem;
            font-weight: 700;
            letter-spacing: -0.05em;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #000 0%, #333 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: fadeIn 1.5s ease;
        }

        .hero p {
            font-size: 1.5rem;
            font-weight: 300;
            color: #6e6e73;
            animation: fadeIn 2s ease;
        }

        .section {
            min-height: 100vh;
            padding: 100px 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-top: 1px solid #d2d2d7;
        }

        .section:nth-child(even) {
            background: #f5f5f7;
        }

        .container {
            max-width: 1400px;
            width: 100%;
            margin: 0 auto;
        }

        .split-layout {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 80px;
            align-items: center;
        }

        .content-side h2 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 30px;
            letter-spacing: -0.03em;
            color: #1d1d1f;
        }

        .content-side h3 {
            font-size: 1.8rem;
            font-weight: 600;
            margin: 40px 0 20px 0;
            color: #1d1d1f;
        }

        .content-side p {
            font-size: 1.2rem;
            color: #6e6e73;
            line-height: 1.8;
            margin-bottom: 20px;
        }

        .content-side ul {
            list-style: none;
            margin: 20px 0;
        }

        .content-side li {
            font-size: 1.1rem;
            color: #6e6e73;
            padding: 12px 0;
            padding-left: 30px;
            position: relative;
        }

        .content-side li:before {
            content: "→";
            position: absolute;
            left: 0;
            color: #000;
            font-weight: 600;
        }

        /* Video-Kasten */
        .video-side {
            position: sticky;
            top: 100px;
            height: 600px;
            background: #f5f5f7;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
            border: 1px solid #d2d2d7;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .video-side:hover {
            transform: scale(1.02);
            box-shadow: 0 30px 80px rgba(0,0,0,0.2);
        }

        /* Container um Video - zentriert und responsive */
        .video-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100%;
            width: 100%;
            padding: 18px;
            text-align: center;
        }

        .video-label {
            font-size: 1rem;
            color: #6e6e73;
            margin-bottom: 12px;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }

        /* Video füllt den Kasten und behält das Seitenverhältnis */
        .video-container video {
            width: 100%;
            height: calc(100% - 48px); /* Platz für Label / padding */
            object-fit: cover; /* füllt den Bereich, schneidet bei Bedarf, ohne zu verzerren */
            border-radius: 12px;
            display: block;
        }

        .video-placeholder {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #f5f5f7 0%, #e8e8ed 100%);
            position: relative;
        }

        .video-placeholder::before {
            content: "";
            width: 80px;
            height: 80px;
            border: 3px solid #000;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
            position: relative;
        }

        .video-placeholder::after {
            content: "▶";
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-40%, -50%);
            font-size: 3rem;
            color: #000;
        }

        .button-demo {
            background: #f5f5f7;
            border-radius: 15px;
            padding: 30px;
            margin: 30px 0;
            border: 1px solid #d2d2d7;
        }

        .button-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-top: 20px;
        }

        .button-item {
            background: #fff;
            padding: 20px;
            border-radius: 12px;
            border: 1px solid #d2d2d7;
            transition: all 0.3s ease;
        }

        .button-item:hover {
            background: #f5f5f7;
            border-color: #000;
            transform: translateY(-2px);
        }

        .button-name {
            font-size: 1.2rem;
            font-weight: 600;
            color: #1d1d1f;
            margin-bottom: 10px;
        }

        .button-desc {
            font-size: 0.95rem;
            color: #6e6e73;
        }

        .warning-box {
            background: rgba(0, 0, 0, 0.03);
            border-left: 4px solid #000;
            padding: 30px;
            margin: 40px 0;
            border-radius: 10px;
        }

        .warning-box h4 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: #1d1d1f;
        }

        .step-number {
            font-size: 1rem;
            color: #6e6e73;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            margin-bottom: 10px;
            display: block;
        }

        .checklist {
            background: #f5f5f7;
            border-radius: 15px;
            padding: 30px;
            margin: 30px 0;
            border: 1px solid #d2d2d7;
        }

        .checklist-item {
            padding: 15px;
            border-bottom: 1px solid #d2d2d7;
            display: flex;
            align-items: center;
            transition: all 0.3s ease;
        }

        .checklist-item:last-child {
            border-bottom: none;
        }

        .checklist-item:hover {
            background: #e8e8ed;
        }

        .checklist-item input[type="checkbox"] {
            width: 22px;
            height: 22px;
            margin-right: 15px;
            cursor: pointer;
            accent-color: #000;
        }

        .checklist-item label {
            font-size: 1.05rem;
            color: #1d1d1f;
            cursor: pointer;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .scroll-indicator {
            position: absolute;
            bottom: 50px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 0.9rem;
            color: #6e6e73;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translate(-50%, 0); }
            50% { transform: translate(-50%, 10px); }
        }

        /* Accordion / Bilder im Accordion */
        .checklist-item {
            border-bottom: 1px solid #ddd;
            margin-bottom: 5px;
        }

        .item-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 10px 0;
            width: 100%;
        }

        .item-header input[type="checkbox"] {
            margin-right: 10px;
            transform: scale(1.2);
        }

        .accordion-toggle {
            background: none;
            border: none;
            cursor: pointer;
            display: flex;
            align-items: center;
            padding: 0;
        }

        .accordion-content {
            display: none;
            padding: 10px 0 15px 25px;
            width: 100%;
        }

        .accordion-content img {
            width: 100%;
            max-width: 500px;
            height: 300px;
            object-fit: cover;
            border-radius: 10px;
            border: 1px solid #ccc;
            display: block;
            margin: 10px auto;
        }

        .arrow {
            transition: transform 0.3s ease;
            transform-origin: center;
        }

        .checklist-item.active .arrow {
            transform: rotate(90deg);
        }

        /* Responsive Anpassungen */
        @media (max-width: 1024px) {
            .split-layout {
                grid-template-columns: 1fr;
                gap: 40px;
            }
            
            .video-side {
                position: relative;
                top: 0;
                height: 420px;
            }
            
            .hero h1 {
                font-size: 3.5rem;
            }
            
            .content-side h2 {
                font-size: 2.5rem;
            }
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero p {
                font-size: 1.2rem;
            }
            
            .content-side h2 {
                font-size: 2rem;
            }
            
            .button-grid {
                grid-template-columns: 1fr;
            }

            .video-side {
                height: 300px;
            }

            .video-container video {
                height: calc(100% - 40px);
            }
        }
    </style>
</head>
<body>
    <div class="hero">
        <h1>DJI Mini 3</h1>
        <p>Beginner Guide: Erste Schritte mit deiner DJI Mini 3.</p>
        <div class="scroll-indicator">↓ Scroll</div>
    </div>

   <section class="section">
    <div class="container">
        <div class="split-layout">
            <div class="content-side">
                <span class="step-number">Schritt 01</span>
                <h2>Auspacken</h2>
                <p>Nimm dir Zeit, jedes Teil sorgfältig zu überprüfen. Es ist wichtig, dass du alle Teile vor deinem ersten Flug besitzt.</p>
                
                <div class="checklist">

                    <!-- DJI Mini 3 Drohne -->
                    <div class="checklist-item">
                        <div class="item-header">
                            <div style="display:flex; align-items:center; gap:12px;">
                                <input type="checkbox" id="item1">
                                <label for="item1">DJI Mini 3 Drohne</label>
                            </div>
                            <button class="accordion-toggle">
                                <svg class="arrow" viewBox="0 0 24 24" width="18" height="18">
                                    <path d="M8 5l8 7-8 7" stroke="#555" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
                                </svg>
                            </button>
                        </div>
                        <div class="accordion-content">
                            <img src="https://se-cdn.djiits.com/tpc/uploads/carousel/image/920f3e349b9544a7620eab7bc34ecb2e@ultra.jpg" alt="DJI Mini 3 Drohne">
                        </div>
                    </div>

                    <!-- Fernsteuerung -->
                    <div class="checklist-item">
                        <div class="item-header">
                            <div style="display:flex; align-items:center; gap:12px;">
                                <input type="checkbox" id="item2">
                                <label for="item2">Fernsteuerung (RC-N1 oder RC)</label>
                            </div>
                            <button class="accordion-toggle">
                                <svg class="arrow" viewBox="0 0 24 24" width="18" height="18">
                                    <path d="M8 5l8 7-8 7" stroke="#555" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
                                </svg>
                            </button>
                        </div>
                        <div class="accordion-content">
                            <img src="https://www-cdn.djiits.com/dps/5919beda1853e73f3db4c2d3ea0f695c.jpg" alt="Fernsteuerung">
                        </div>
                    </div>

                    <!-- Intelligent Flight Battery -->
                    <div class="checklist-item">
                        <div class="item-header">
                            <div style="display:flex; align-items:center; gap:12px;">
                                <input type="checkbox" id="item3">
                                <label for="item3">Intelligent Flight Battery</label>
                            </div>
                            <button class="accordion-toggle">
                                <svg class="arrow" viewBox="0 0 24 24" width="18" height="18">
                                    <path d="M8 5l8 7-8 7" stroke="#555" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
                                </svg>
                            </button>
                        </div>
                        <div class="accordion-content">
                            <img src="https://se-cdn.djiits.com/tpc/uploads/photo/image/3e380d691e909c51214811e948060255@large.jpg" alt="Intelligent Flight Batterie">
                        </div>
                    </div>

                    <!-- Batterie Ladestation -->
                    <div class="checklist-item">
                        <div class="item-header">
                            <div style="display:flex; align-items:center; gap:12px;">
                                <input type="checkbox" id="item4">
                                <label for="item4">Batterie-Ladestation</label>
                            </div>
                            <button class="accordion-toggle">
                                <svg class="arrow" viewBox="0 0 24 24" width="18" height="18">
                                    <path d="M8 5l8 7-8 7" stroke="#555" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
                                </svg>
                            </button>
                        </div>
                        <div class="accordion-content">
                            <img src="https://www-cdn.djiits.com/dps/a740cce33196b6e86d0ce874615abedc.jpg" alt="Ladestation der Intelligent Flight Batterie">
                        </div>
                    </div>

                    <!-- Propeller -->
                    <div class="checklist-item">
                        <div class="item-header">
                            <div style="display:flex; align-items:center; gap:12px;">
                                <input type="checkbox" id="item5">
                                <label for="item5">Propeller (4 + Ersatz)</label>
                            </div>
                            <button class="accordion-toggle">
                                <svg class="arrow" viewBox="0 0 24 24" width="18" height="18">
                                    <path d="M8 5l8 7-8 7" stroke="#555" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
                                </svg>
                            </button>
                        </div>
                        <div class="accordion-content">
                            <img src="https://se-cdn.djiits.com/tpc/uploads/photo/image/8d0b042823571659a8482d3840312e3b@large.jpg" alt="Propeller">
                        </div>
                    </div>

                    <!-- USB-C Ladekabel -->
                    <div class="checklist-item">
                        <div class="item-header">
                            <div style="display:flex; align-items:center; gap:12px;">
                                <input type="checkbox" id="item6">
                                <label for="item6">USB-C Ladekabel</label>
                            </div>
                            <button class="accordion-toggle">
                                <svg class="arrow" viewBox="0 0 24 24" width="18" height="18">
                                    <path d="M8 5l8 7-8 7" stroke="#555" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
                                </svg>
                            </button>
                        </div>
                        <div class="accordion-content">
                            <img src="https://store.storeimages.cdn-apple.com/1/as-images.apple.com/is/MU2G3?wid=1144&hei=1144&fmt=jpeg&qlt=90&.v=MkZNbUNINEozYTU1b25iT2hXdjB4d2tuVHYzMERCZURia3c5SzJFOTlPalpQUlZGaitSQjJVekdLRWQ5QlBiN0RPZUhRVTBDL0lJdmdIOXVmUElrVnc" alt="USB-C Ladekabel">
                        </div>
                    </div>

                </div>

                <div class="warning-box">
                    <h4>Wichtig</h4>
                    <p>Überprüfe alle Komponenten auf Transportschäden. Bei Beschädigungen kontaktiere umgehend den Support, um deine Garantie für eine Ersetzung der Teile nutzen zu können.</p>
                </div>
            </div>

            <!-- Hier ist das aktualisierte Video-Kästchen -->
            <div class="video-side">
                <div class="video-container">
                    <span class="video-label"><b>Video zum Auspacken der verschiedenen Einzelteile</b></span>
                    <video controls>
                        <source src="Video_Auspacken_von_Drohne.mp4" type="video/mp4">
                        Dein Browser unterstützt das Video-Tag nicht.
                    </video>
                </div>
            </div>

        </div>
    </div>
</section>

<script>
    // Accordion Funktionalität (einmalig)
    document.querySelectorAll('.accordion-toggle').forEach(button => {
        button.addEventListener('click', () => {
            const item = button.closest('.checklist-item');
            item.classList.toggle('active');
            const content = item.querySelector('.accordion-content');
            if(item.classList.contains('active')) {
                content.style.display = 'block';
            } else {
                content.style.display = 'none';
            }
        });
    });
</script>


// Akku der Drohne Laden



    <section class="section">
        <div class="container">
            <div class="split-layout">
                <div class="video-side">
                    <div class="video-placeholder">
                        <span class="video-label">Video: Akku Installation</span>
                    </div>
                </div>
                <div class="content-side">
                    <span class="step-number">Schritt 02</span>
                    <h2>Akku laden</h2>
                    <p>Ein vollständig geladener Akku ist die Grundlage für deinen ersten Flug.</p>
                    
                    <h3>Ladevorgang</h3>
                    <ul>
                        <li>Setze den Akku in die Drohne ein</li>
                        <li>Verbinde das USB-C Kabel mit der Drohne</li>
                        <li>Ladezeit: circa 90 Minuten</li>
                        <li>LED-Anzeige informiert über den Status</li>
                        <li>Verbinde das USB-C Kabel mit deiner Fernsteuerung nachdem die Drohne vollständig geladen ist.</li>

                    </ul>

                    <div class="warning-box">
                        <h4>Pro Tipp</h4>
                        <p>Lade die Fernsteuerung parallel zu deiner Drohne, falls du noch ein zweites USB-C Ladekabel besitzt. So bist du für Schritt 3 bereit, wenn beide Akkus geladen sind und ersparst dir eine Menge Zeit.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>










</body>
</html>





