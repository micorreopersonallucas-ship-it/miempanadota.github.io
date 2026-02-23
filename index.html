<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Empanadas Express - Pedidos</title>
    <style>
        :root { --primary: #5D4037; --bg: #F5F5DC; --dark: #212121; --card: #FFFFFF; }
        body { margin: 0; font-family: 'Trebuchet MS', sans-serif; background: var(--bg); color: var(--dark); padding-bottom: 200px; }
        
        .header { background: var(--primary); padding: 25px; text-align: center; color: var(--bg); box-shadow: 0 2px 10px rgba(0,0,0,0.2); }
        .header h1 { margin: 0; font-size: 1.8rem; text-transform: uppercase; letter-spacing: 1px; }
        .header p { margin: 5px 0 0; font-weight: bold; color: #D7CCC8; }

        .container { padding: 15px; max-width: 500px; margin: auto; }

        /* SECCIÓN CLIENTE - UNA SOLA VEZ */
        .cliente-form { 
            background: #efebe9; 
            padding: 20px; 
            border-radius: 15px; 
            margin-bottom: 20px; 
            border: 1px dashed var(--primary); 
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }
        .cliente-form label { display: block; font-weight: bold; margin-bottom: 5px; font-size: 0.9rem; }
        .cliente-form input { 
            width: 100%; 
            padding: 12px; 
            margin-bottom: 15px; 
            border: 1px solid #ccc; 
            border-radius: 8px; 
            box-sizing: border-box; 
            font-size: 1rem;
        }

        /* TARJETAS DE SABORES */
        .sabor-card { 
            background: var(--card); 
            border-radius: 15px; 
            padding: 15px; 
            margin-bottom: 12px; 
            display: flex; 
            justify-content: space-between; 
            align-items: center; 
            border: 1px solid #eee; 
            box-shadow: 0 2px 4px rgba(0,0,0,0.02);
        }
        .sabor-info h3 { margin: 0; font-size: 1.1rem; color: var(--dark); }
        .sabor-info p { margin: 3px 0 0; font-size: 0.8rem; color: #8a7a6a; }

        .controls { display: flex; align-items: center; gap: 12px; background: #f1f1f1; padding: 5px 10px; border-radius: 25px; }
        .btn-qty { width: 35px; height: 35px; border-radius: 50%; border: none; background: var(--primary); color: white; font-weight: bold; font-size: 1.2rem; cursor: pointer; }
        .qty-val { font-weight: bold; min-width: 20px; text-align: center; font-size: 1.2rem; }

        /* FOOTER FIJO */
        .footer { 
            position: fixed; bottom: 0; left: 0; right: 0; 
            background: white; padding: 20px; 
            border-radius: 25px 25px 0 0; 
            box-shadow: 0 -5px 20px rgba(0,0,0,0.1); 
            max-width: 500px; margin: auto; 
        }
        .total-row { display: flex; justify-content: space-between; margin-bottom: 15px; font-weight: bold; font-size: 1.5rem; }
        .btn-confirm { 
            width: 100%; 
            background: #10b981; 
            color: white; 
            border: none; 
            padding: 18px; 
            border-radius: 15px; 
            font-size: 1.2rem; 
            font-weight: bold; 
            cursor: pointer; 
            box-shadow: 0 4px 10px rgba(16, 185, 129, 0.3);
        }
    </style>
</head>
<body>

    <div class="header">
        <h1>EMPANADAS EXPRESS</h1>
        <p>¡Hace tu pedido!</p>
    </div>

    <div class="container">
        <div class="cliente-form">
            <label>👤 Nombre del Cliente:</label>
            <input type="text" id="c-nombre" placeholder="Nombre completo">
            
            <label>📞 Teléfono:</label>
            <input type="tel" id="c-tel" placeholder="Ej: 351xxxxxxx">
            
            <label>📍 Dirección de Entrega:</label>
            <input type="text" id="c-dir" placeholder="Calle, número y barrio">
        </div>

        <div id="lista-sabores"></div>
    </div>

    <div class="footer">
        <div class="total-row">
            <span>Total</span>
            <span id="total-txt" style="color: var(--primary);">$0</span>
        </div>
        <button class="btn-confirm" onclick="enviarWhatsApp()">Confirmar y Enviar</button>
    </div>

    <script>
        const PRECIO = 1400;
        const MI_WHATSAPP = "5493517485182"; 
        
        const sabores = [
            { id: 'mat', nom: 'Matambre', desc: 'Carne de matambre tiernizada a cuchillo' },
            { id: 'ara', nom: 'Árabes', desc: 'Carne con limón y especias' },
            { id: 'dul', nom: 'Dulces', desc: 'Carne de la casa salteada y azucarada' },
            { id: 'sal', nom: 'Saladas', desc: 'Carne suave tradicional' },
            { id: 'pol', nom: 'Pollo', desc: 'Pollo seleccionado con verdeo' },
            { id: 'jyq', nom: 'Jamón y Queso', desc: 'Dados de jamón y muzzarella' },
            { id: 'cyq', nom: 'Cebolla y Queso', desc: 'Muzzarella y cebolla blanca' },
            { id: 'hum', nom: 'Humita', desc: 'Choclo, queso y salsa blanca' }
        ];

        let carrito = {};

        function cargarMenu() {
            document.getElementById('lista-sabores').innerHTML = sabores.map(s => `
                <div class="sabor-card">
                    <div class="sabor-info">
                        <h3>${s.nom}</h3>
                        <p>${s.desc}</p>
                    </div>
                    <div class="controls">
                        <button class="btn-qty" style="background:#ccc; color:#333;" onclick="cambiar('${s.id}', -1)">-</button>
                        <span class="qty-val" id="q-${s.id}">0</span>
                        <button class="btn-qty" onclick="cambiar('${s.id}', 1)">+</button>
                    </div>
                </div>`).join('');
        }

        function cambiar(id, val) {
            carrito[id] = Math.max(0, (carrito[id] || 0) + val);
            document.getElementById(`q-${id}`).innerText = carrito[id];
            
            let unidades = Object.values(carrito).reduce((a, b) => a + b, 0);
            document.getElementById('total-txt').innerText = `$${(unidades * PRECIO).toLocaleString('es-AR')}`;
        }

        function enviarWhatsApp() {
            const nom = document.getElementById('c-nombre').value;
            const tel = document.getElementById('c-tel').value;
            const dir = document.getElementById('c-dir').value;
            let unidades = Object.values(carrito).reduce((a, b) => a + b, 0);

            if (!nom || !dir || unidades === 0) {
                return alert("Por favor, completa el nombre, la dirección y elige al menos una empanada.");
            }

            let texto = `*PEDIDO - EMPANADAS EXPRESS*%0A%0A`;
            texto += `*CLIENTE:* ${nom}%0A`;
            texto += `*TEL:* ${tel}%0A`;
            texto += `*DIR:* ${dir}%0A%0A`;
            texto += `--- *DETALLE* ---%0A`;

            Object.entries(carrito).forEach(([id, q]) => {
                if (q > 0) {
                    texto += `• ${q} x ${sabores.find(s => s.id === id).nom}%0A`;
                }
            });

            texto += `%0A*TOTAL: $${(unidades * PRECIO).toLocaleString('es-AR')}*`;
            
            window.open(`https://wa.me/${MI_WHATSAPP}?text=${texto}`, '_blank');
        }

        window.onload = cargarMenu;
    </script>
</body>
</html>
