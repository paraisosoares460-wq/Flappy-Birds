
!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Flappy Bird</title>
<style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        background: linear-gradient(180deg, #1a1a2e 0%, #16213e 100%);
        font-family: 'Segoe UI', Arial, sans-serif;
        color: #fff;
    }
    h1 { margin-bottom: 10px; font-size: 24px; letter-spacing: 2px; }
    canvas {
        border: 3px solid #fff;
        border-radius: 10px;
        box-shadow: 0 0 30px rgba(0,0,0,0.6);
        display: block;
    }
    p { margin-top: 10px; font-size: 14px; opacity: 0.8; }
</style>
<base target="_blank">
</head>
<body>
<h1>🐦 FLAPPY BIRD</h1>
<canvas id="game" width="400" height="600"></canvas>
<p>Pressione ESPAÇO, clique ou toque para voar!</p>

<script>
const canvas = document.getElementById('game');
const ctx = canvas.getContext('2d');

// ====== CONFIGURAÇÕES ======
const GRAVIDADE = 0.45;
const FORCA_PULO = -8;
const VELOCIDADE_CANO = 2.5;
const LARGURA_CANO = 60;
const ABERTURA = 150;
const INTERVALO_CANOS = 300;

// ====== ESTADO DO JOGO ======
let bird = { x: 80, y: 300, r: 15, vy: 0, angulo: 0 };
let canos = [];
